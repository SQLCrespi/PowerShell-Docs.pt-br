---
ms.date: 07/10/2019
keywords: jea,powershell,segurança
title: Usando JEA
description: Este artigo descreve as várias maneiras pelas quais você pode se conectar a um ponto de extremidade JEA e usá-lo.
ms.openlocfilehash: b3d81cc0aa76549c81136e5a1a5af28df9c6fa7a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501534"
---
# <a name="using-jea"></a>Usando JEA

Este artigo descreve as várias maneiras pelas quais você pode se conectar a um ponto de extremidade JEA e usá-lo.

## <a name="using-jea-interactively"></a>Usando o JEA interativamente

Se você estiver testando sua configuração JEA ou tiver tarefas simples para os usuários, use o JEA da mesma forma que faria com uma sessão de comunicação remota regular do PowerShell. Para tarefas complexas de comunicação remota, é recomendável usar a [comunicação remota implícita](#using-jea-with-implicit-remoting). A comunicação remota implícita permite que os usuários operem com os objetos de dados localmente.

Para usar o JEA de maneira interativamente, você precisará:

- Do nome do computador ao qual está se conectando (pode ser o computador local)
- Do nome do ponto de extremidade JEA registrado nesse computador
- Das credenciais que têm acesso ao ponto de extremidade JEA nesse computador

Considerando essas informações, você poderá iniciar uma sessão JEA usando [New-PSSession](/powershell/module/microsoft.powershell.core/New-PSSession) ou [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).

```powershell
$nonAdminCred = Get-Credential
Enter-PSSession -ComputerName localhost -ConfigurationName JEAMaintenance -Credential $nonAdminCred
```

Se a conta de usuário atual tiver acesso ao ponto de extremidade JEA, você poderá omitir o parâmetro **Credential**.

Quando o prompt do PowerShell mudar para `[localhost]: PS>`, você saberá que está interagindo com a sessão JEA remota. Você pode executar o `Get-Command` para verificar quais comandos estão disponíveis. Consulte o administrador para saber se há alguma restrição nos parâmetros disponíveis ou nos valores de parâmetros permitidos.

Lembre-se de que as sessões JEA operam no modo NoLanguage. Algumas das maneiras habituais de usar o PowerShell podem não estar disponíveis. Por exemplo, você não pode usar variáveis para armazenar dados ou inspecionar as propriedades em objetos retornados de cmdlets. O exemplo a seguir mostra duas abordagens para fazer com que os mesmos comandos funcionem no modo NoLanguage.

```powershell
# Using variables is prohibited in NoLanguage mode. The following will not work:
# $vm = Get-VM -Name 'SQL01'
# Start-VM -VM $vm

# You can use pipes to pass data through to commands that accept input from the pipeline
Get-VM -Name 'SQL01' | Start-VM

# You can also wrap subcommands in parentheses and enter them inline as arguments
Start-VM -VM (Get-VM -Name 'SQL01')

# You can also use parameter sets that don't require extra data to be passed in
Start-VM -VMName 'SQL01'
```

Para invocações de comando mais complexas que dificultam essa abordagem, considere o uso da [comunicação remota implícita](#using-jea-with-implicit-remoting) ou a [criação de funções personalizadas](role-capabilities.md#creating-custom-functions) que encapsulam a funcionalidade necessária.

## <a name="using-jea-with-implicit-remoting"></a>Usando o JEA com comunicação remota implícita

O PowerShell tem um modelo de comunicação remota implícita que permite importar cmdlets de proxy de um computador remoto e interagir com eles como se fossem comandos locais. A comunicação remota implícita é explicada nesta **postagem no blog** [Hey, Scripting Guy!](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/)
A comunicação remota implícita é útil ao trabalhar com o JEA porque permite que você trabalhe com os cmdlets do JEA em um modo de linguagem completa. Você pode usar a preenchimento com Tab, variáveis, manipular objetos e, até mesmo, usar scripts locais para automatizar tarefas em um ponto de extremidade JEA. Sempre que você invocar um comando de proxy, os dados serão enviados ao ponto de extremidade JEA no computador remoto e executados nele.

A comunicação remota implícita funciona ao importar cmdlets de uma sessão existente do PowerShell. Opcionalmente, você pode optar por colocar prefixos nos substantivos de cada cmdlet de proxy com uma cadeia de caracteres de sua escolha. O prefixo permite distinguir os comandos que são destinados ao sistema remoto. Um módulo de script temporário contendo todos os comandos de proxy será criado e importado durante a sessão local do PowerShell.

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Import the entire PSSession and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA'

# Invoke "Get-Command" on the remote JEA endpoint using the proxy cmdlet
Get-JEACommand
```

> [!IMPORTANT]
> Alguns sistemas poderão não ser capazes de importar uma sessão inteira do JEA devido a restrições em cmdlets padrão do JEA. Para contornar isso, importe apenas os comandos necessários da sessão JEA fornecendo explicitamente os nomes deles para o parâmetro `-CommandName`. Uma atualização futura solucionará o problema com a importação de sessões inteiras do JEA nos sistemas afetados.

Se você não puder importar uma sessão JEA devido às restrições do JEA nos parâmetros padrão, siga as etapas abaixo para filtrar os comandos padrão do conjunto importado. Você poderá continuar usando comandos como `Select-Object`, mas apenas usará a versão local instalada no computador em vez daquela importada da sessão JEA remota.

```powershell
# Create a new PSSession to your JEA endpoint
$jeasession = New-PSSession -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance'

# Get a list of all the commands on the JEA endpoint
$commands = Invoke-Command -Session $jeasession -ScriptBlock { Get-Command }

# Filter out the default cmdlets
$jeaDefaultCmdlets = 'Clear-Host', 'Exit-PSSession', 'Get-Command', 'Get-FormatData', 'Get-Help', 'Measure-Object', 'Out-Default', 'Select-Object'
$filteredCommands = $commands.Name | Where-Object { $jeaDefaultCmdlets -notcontains $_ }

# Import only commands explicitly added in role capabilities and prefix each imported cmdlet with "JEA"
Import-PSSession -Session $jeasession -Prefix 'JEA' -CommandName $filteredCommands
```

Também é possível manter os cmdlets do proxy da comunicação remota implícita, usando o [Export-PSSession](/powershell/module/microsoft.powershell.utility/Export-PSSession).
Para obter mais informações sobre a comunicação remota implícita, confira a documentação de [Import-PSSession](/powershell/module/microsoft.powershell.utility/import-pssession) e [Import-Module](/powershell/module/microsoft.powershell.core/import-module).

## <a name="using-jea-programmatically"></a>Usando o JEA de forma programática

O JEA também pode ser usado em sistemas de automação e em aplicativos de usuário, como sites e aplicativos de assistência técnica na empresa. A abordagem é a mesma usada para a criação de aplicativos que se comunicam com pontos de extremidade irrestritos do PowerShell. Garanta que o programa seja projetado para trabalhar com a limitação imposta pelo JEA.

Para tarefas simples e únicas, use [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) para executar comandos em uma sessão JEA.

```powershell
Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Process; Get-Service }
```

Para verificar quais comandos estão disponíveis para uso quando você se conectar a uma sessão JEA, execute o `Get-Command` e percorra os resultados para verificar os parâmetros permitidos.

```powershell
$allowedCommands = Invoke-Command -ComputerName 'SERVER01' -ConfigurationName 'JEAMaintenance' -ScriptBlock { Get-Command }
$allowedCommands | Where-Object { $_.CommandType -in 'Function', 'Cmdlet' } | Format-Table Name, Parameters
```

Se você estiver criando um aplicativo C#, crie um runspace do PowerShell que se conecta a uma sessão JEA especificando o nome da configuração em um objeto [WSManConnectionInfo](/dotnet/api/system.management.automation.runspaces.wsmanconnectioninfo).

```csharp
// using System.Management.Automation;
var computerName = "SERVER01";
var configName   = "JEAMaintenance";
// See https://docs.microsoft.com/dotnet/api/system.management.automation.pscredential
var creds        = // create a PSCredential object here

WSManConnectionInfo connectionInfo = new WSManConnectionInfo(
    false,                 // Use SSL
    computerName,          // Computer name
    5985,                  // WSMan Port
    "/wsman",              // WSMan Path
                           // Connection URI with config name
    string.Format(CultureInfo.InvariantCulture, "http://schemas.microsoft.com/powershell/{0}", configName),
    creds);                // Credentials

// Now, use the connection info to create a runspace where you can run the commands
using (Runspace runspace = RunspaceFactory.CreateRunspace(connectionInfo))
{
    // Open the runspace
    runspace.Open();

    using (PowerShell ps = PowerShell.Create())
    {
        // Set the PowerShell object to use the JEA runspace
        ps.Runspace = runspace;

        // Now you can add and invoke commands
        ps.AddCommand("Get-Command");
        foreach (var result in ps.Invoke())
        {
            Console.WriteLine(result);
        }
    }

    // Close the runspace
    runspace.Close();
}
```

## <a name="using-jea-with-powershell-direct"></a>Usando o JEA com o PowerShell Direct

O Hyper-V no Windows 10 e no Windows Server 2016 oferece o [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct), um recurso que permite aos administradores do Hyper-V gerenciar máquinas virtuais com o PowerShell, independentemente da configuração da rede ou das configurações de gerenciamento remoto na máquina virtual.

Use o PowerShell Direct com o JEA para fornecer acesso limitado de administrador do Hyper-V à VM.
Isso poderá ser útil se você perder a conectividade de rede com a VM e precisar de um administrador de datacenter para corrigir as configurações da rede.

Nenhuma configuração adicional é necessária para usar o JEA com o PowerShell Direct. No entanto, o sistema operacional convidado em execução na máquina virtual precisa ser o Windows 10, o Windows Server 2016 ou superior. O administrador do Hyper-V pode se conectar ao ponto de extremidade JEA usando os parâmetros `-VMName` ou `-VMId` em cmdlets PSRemoting:

```powershell
# Entering a JEA session using PowerShell Direct when the VM name is unique
Enter-PSSession -VMName 'SQL01' -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'

# Entering a JEA session using PowerShell Direct using VM ids
$vm = Get-VM -VMName 'MyVM' | Select-Object -First 1
Enter-PSSession -VMId $vm.VMId -ConfigurationName 'NICMaintenance' -Credential 'localhost\JEAformyHoster'
```

É recomendável que você crie uma conta de usuário dedicada com os direitos mínimos necessários para gerenciar o sistema para uso por um administrador do Hyper-V. Lembre-se de que, até mesmo, um usuário sem privilégios pode entrar em um computador Windows por padrão, incluindo o uso do PowerShell irrestrito. Isso permite que ele navegue pelo sistema de arquivos e saiba mais sobre o ambiente do sistema operacional. Para bloquear um administrador do Hyper-V e limitá-lo somente ao acesso de uma VM usando o PowerShell Direct com o JEA, você precisará negar direitos de logon local à conta do JEA do administrador do Hyper-V.
