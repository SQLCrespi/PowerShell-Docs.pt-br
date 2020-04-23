---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Auditoria e relatórios no JEA (Just Enough Administration)
ms.openlocfilehash: 2afefe83acecc1fc3643d49766120ffecc25378f
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "70017787"
---
# <a name="auditing-and-reporting-on-jea"></a>Auditoria e relatórios no JEA (Just Enough Administration)

Depois de implantar o JEA, você precisará auditar regularmente a configuração JEA. A auditoria ajudará você a avaliar se as pessoas corretas têm acesso ao ponto de extremidade JEA e suas funções atribuídas ainda são apropriadas.

## <a name="find-registered-jea-sessions-on-a-machine"></a>Encontre sessões JEA registradas em um computador

Para verificar quais sessões JEA estão registradas em um computador, use o cmdlet [Get-PSSessionConfiguration](/powershell/module/microsoft.powershell.core/get-pssessionconfiguration).

```powershell
# Filter for sessions that are configured as 'RestrictedRemoteServer' to find JEA-like session configurations
Get-PSSessionConfiguration | Where-Object { $_.SessionType -eq 'RestrictedRemoteServer' }
```

```Output
Name          : JEAMaintenance
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : CONTOSO\JEA_DNS_ADMINS AccessAllowed, CONTOSO\JEA_DNS_OPERATORS AccessAllowed,
                CONTOSO\JEA_DNS_AUDITORS AccessAllowed
```

Os direitos efetivos do ponto de extremidade estão listados na propriedade **Permissão**. Esses usuários têm o direito de se conectar ao ponto de extremidade JEA. No entanto, as funções e os comandos aos quais eles têm acesso são determinados pela propriedade **RoleDefinitions** no [arquivo de configuração de sessão](session-configurations.md) que foi usado para registrar o ponto de extremidade. Expanda a propriedade **RoleDefinitions** para avaliar os mapeamentos de função em um ponto de extremidade JEA registrado.

```powershell
# Get the desired session configuration
$jea = Get-PSSessionConfiguration -Name 'JEAMaintenance'

# Enumerate users/groups and which roles they have access to
$jea.RoleDefinitions.GetEnumerator() | Select-Object Name, @{
  Name = 'Role Capabilities'
  Expression = { $_.Value.RoleCapabilities }
}
```

## <a name="find-available-role-capabilities-on-the-machine"></a>Encontre recursos de função disponíveis no computador

O JEA obtém as capacidades de função dos arquivos `.psrc` armazenados na pasta **RoleCapabilities** em um módulo do PowerShell. A função a seguir encontra todas as capacidades de função disponíveis em um computador.

```powershell
function Find-LocalRoleCapability {
    $results = @()

    # Find modules with a "RoleCapabilities" subfolder and add any PSRC files to the result set
    Get-Module -ListAvailable | ForEach-Object {
        $psrcpath = Join-Path -Path $_.ModuleBase -ChildPath 'RoleCapabilities'
        if (Test-Path $psrcpath) {
            $results += Get-ChildItem -Path $psrcpath -Filter *.psrc
        }
    }

    # Format the results nicely to make it easier to read
    $results | Select-Object @{ Name = 'Name'; Expression = { $_.Name.TrimEnd('.psrc') }}, @{
        Name = 'Path'; Expression = { $_.FullName }
    } | Sort-Object Name
}
```

> [!NOTE]
> A ordem dos resultados dessa função não é, necessariamente, a ordem na qual os recursos de função serão selecionados se vários recursos de função compartilham o mesmo nome.

## <a name="check-effective-rights-for-a-specific-user"></a>Verifique os direitos efetivos de um usuário específico

O cmdlet [Get-PSSessionCapability](/powershell/module/microsoft.powershell.core/Get-PSSessionCapability) enumera todos os comandos disponíveis em um ponto de extremidade JEA com base nas associações a um grupo de um usuário.
A saída de `Get-PSSessionCapability` é idêntica à saída do usuário especificado executando o `Get-Command -CommandType All` em uma sessão JEA.

```powershell
Get-PSSessionCapability -ConfigurationName 'JEAMaintenance' -Username 'CONTOSO\Alice'
```

Se os usuários não forem membros permanentes de grupos que concederão a eles direitos adicionais do JEA, esse cmdlet poderá não refletir essas permissões extras. Isso ocorre ao usar sistemas de gerenciamento de acesso privilegiado just-in-time para permitir que os usuários pertençam temporariamente a um grupo de segurança. Avalie cuidadosamente o mapeamento de usuários para funções e capacidades para garantir que os usuários obtenham apenas o nível de acesso necessário para realizar seus trabalhos com êxito.

## <a name="powershell-event-logs"></a>Logs de eventos do PowerShell

Se você habilitar o log de módulo ou de bloco de script no sistema, poderá ver eventos nos logs de eventos do Windows para cada comando executado por um usuário em uma sessão JEA. Para encontrar esses eventos, abra o log de eventos **Microsoft-Windows-PowerShell/Operational** e procure eventos com a ID do evento **4104**.

Cada entrada de log de eventos inclui informações sobre a sessão na qual o comando foi executado. Para as sessões JEA, o evento inclui informações sobre o **ConnectedUser** e o **RunAsUser**. O **ConnectedUser** é o usuário real que criou a sessão JEA. O **RunAsUser** é a conta do JEA usada para executar o comando.

Os logs de eventos do aplicativo mostram as alterações feitas pelo **RunAsUser**. Portanto, habilitar o log de módulo e de script é necessário para rastrear uma invocação de comando específica novamente para o **ConnectedUser**.

## <a name="application-event-logs"></a>Logs de eventos do aplicativo

Os comandos executados em uma sessão JEA que interagem com aplicativos ou serviços externos podem registrar eventos em seus próprios logs de eventos. Ao contrário das transcrições e dos logs do PowerShell, outros mecanismos de log não capturam o usuário conectado da sessão JEA. Em vez disso, esses aplicativos apenas registram em log o usuário virtual Executar como.
Para determinar quem executou o comando, você precisará consultar uma [transcrição da sessão](#session-transcripts) ou correlacionar os logs de eventos do PowerShell com a hora e o usuário mostrados no log de eventos do aplicativo.

O log do WinRM também pode ajudar você a correlacionar os usuários Executar como com o usuário que está se conectando em um log de eventos do aplicativo. A ID do evento **193** no log **Microsoft-Windows-Windows Remote Management/Operational** registra o SID (identificador de segurança) e o nome da conta do usuário que está se conectando e do usuário Executar como, sempre que uma sessão JEA é criada.

## <a name="session-transcripts"></a>Transcrições de sessão

Se você configurar o JEA para criar uma transcrição para cada sessão de usuário, uma cópia do texto de todas as ações do usuário será armazenada na pasta especificada.

O comando a seguir (como administrador) localiza todos os diretórios de transcrição.

```powershell
Get-PSSessionConfiguration |
  Where-Object { $_.TranscriptDirectory -ne $null } |
    Format-Table Name, TranscriptDirectory
```

Cada transcrição começa com informações sobre a hora em que a sessão foi iniciada, qual usuário se conectou à sessão e qual identidade JEA foi atribuída a eles.

```
**********************
Windows PowerShell transcript start
Start time: 20160710144736
Username: CONTOSO\Alice
RunAs User: WinRM Virtual Users\WinRM VA_1_CONTOSO_Alice
Machine: SERVER01 (Microsoft Windows NT 10.0.14393.0)
[...]
```

O corpo da transcrição contém informações sobre cada comando invocado pelo usuário. A sintaxe exata do comando usado não está disponível em sessões JEA devido à maneira como os comandos são transformados para a comunicação remota do PowerShell. No entanto, você ainda poderá determinar o comando efetivo que foi executado. Abaixo está um exemplo de snippet de transcrição de um usuário executando `Get-Service Dns` em uma sessão JEA:

```
PS>CommandInvocation(Get-Service): "Get-Service"
>> ParameterBinding(Get-Service): name="Name"; value="Dns"
>> CommandInvocation(Out-Default): "Out-Default"
>> ParameterBinding(Out-Default): name="InputObject"; value="Dns"

Running  Dns                DNS Server
```

Uma linha **CommandInvocation** é gravada para cada comando executado por um usuário. **ParameterBindings** registra cada parâmetro e valor fornecido com o comando. No exemplo anterior, você pode ver que o parâmetro **Name** foi fornecido com o valor **Dns** para o cmdlet `Get-Service`.

A saída de cada comando também dispara uma **CommandInvocation**, geralmente para `Out-Default`. O **InputObject** de `Out-Default` é o objeto do PowerShell retornado pelo comando. Os detalhes desse objeto estão impressos algumas linhas abaixo, imitando de perto o que o usuário veria.

## <a name="see-also"></a>Confira também

[*Postagem no blog sobre segurança* PowerShell ♥ the Blue Team](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)
