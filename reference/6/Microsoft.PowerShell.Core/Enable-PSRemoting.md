---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 6dd0b6a997551aba0df2da666eb21dddeb2e1fcf
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344075"
---
# Enable-PSRemoting

## SINOPSE
Configura o computador para receber comandos remotos.

## SYNTAX

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Enable-PSRemoting` cmdlet configura o computador para receber comandos remotos do PowerShell que são enviados usando a tecnologia de WS-Management. No momento, há suporte para a comunicação remota do PowerShell baseada em WS-Management apenas na plataforma Windows.

A comunicação remota do PowerShell é habilitada por padrão nas plataformas do Windows Server. Você pode usar o `Enable-PSRemoting` para habilitar a comunicação remota do PowerShell em outras versões com suporte do Windows e para reabilitar a comunicação remota se ela for desabilitada.

Você precisa executar esse comando apenas uma vez em cada computador que receberá comandos. Você não precisa executá-lo em computadores que só enviam comandos. Como a configuração inicia os ouvintes para aceitar conexões remotas, é prudente executá-lo somente onde for necessário.

Habilitar a comunicação remota do PowerShell em versões de cliente do Windows quando o computador está em uma rede pública normalmente não é permitido, mas você pode ignorar essa restrição usando o parâmetro **SkipNetworkProfileCheck** . Para obter mais informações, consulte a descrição do parâmetro **SkipNetworkProfileCheck**.

Várias instalações do PowerShell podem existir lado a lado em um único computador. `Enable-PSRemoting`A execução irá configurar um ponto de extremidade de comunicação remota para a versão de instalação específica em que você está executando o cmdlet. Portanto, se você executar `Enable-PSRemoting` o powershell 6,2 em execução, um ponto de extremidade de comunicação remota será configurado para executar o powershell 6,2. Se você executar `Enable-PSRemoting` o PowerShell 7-Preview em execução, um ponto de extremidade de comunicação remota será configurado para executar o PowerShell 7-Preview.

`Enable-PSRemoting` cria duas configurações de ponto de extremidade de comunicação remota conforme necessário. Se as configurações do ponto de extremidade já existirem, elas serão simplesmente habilitadas. As configurações criadas são idênticas, mas têm nomes diferentes. Uma terá um nome simples correspondente à versão do PowerShell que hospeda a sessão. O outro nome de configuração contém informações mais detalhadas sobre a versão do PowerShell que hospeda a sessão. Por exemplo, ao executar `Enable-PSRemoting` no PowerShell 6,2, você obterá dois pontos de extremidade configurados chamados **PowerShell. 6** , **PowerShell. 6.2.2**.
Isso permite que você crie uma conexão com a versão mais recente do host do PowerShell 6 usando o nome simples **PowerShell. 6**. Ou você pode se conectar a uma versão específica do host do PowerShell usando o nome mais longo **PowerShell. 6.2.2**.

Para usar os pontos de extremidade de comunicação remota habilitados recentemente, você deve especificá-los pelo nome com o parâmetro **ConfigurationName** ao criar uma conexão remota usando os `Invoke-Command` `New-PSSession` `Enter-PSSession` cmdlets,,. Para obter mais informações, consulte o exemplo 4.

O `Enable-PSRemoting` cmdlet executa as seguintes operações:

- Executa o cmdlet [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) , que executa as seguintes tarefas:
  - Inicia o serviço WinRM.
  - Define o tipo de inicialização no serviço WinRM como automático.
  - Cria um ouvinte para aceitar solicitações em qualquer endereço IP.
  - Habilita uma exceção de firewall para WS-Management comunicações.
  - Cria as configurações de ponto de extremidade de sessão de nome longo e simples, se necessário.
  - Habilita todas as configurações de sessão.
  - Altera o descritor de segurança de todas as configurações de sessão para permitir o acesso remoto.
- Reinicia o serviço WinRM para tornar as alterações anteriores efetivas.

Para executar esse cmdlet na plataforma Windows, inicie o PowerShell usando a opção Executar como administrador. Este cmdlet não está disponível nas versões Linux ou MacOS do PowerShell.

> [!CAUTION]
> Esse cmdlet não afeta as configurações de ponto de extremidade remoto criadas pelo Windows PowerShell.
> Ele só afeta os pontos de extremidade criados com o PowerShell versão 6 e superior. Para habilitar e desabilitar pontos de extremidade de comunicação remota do PowerShell que são hospedados pelo Windows PowerShell, execute o `Enable-PSRemoting` cmdlet de dentro de uma sessão do Windows PowerShell.

## EXEMPLOS

### Exemplo 1: configurar um computador para receber comandos remotos

Este comando configura o computador para receber comandos remotos.

```powershell
Enable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### Exemplo 2: configurar um computador para receber comandos remotos sem um prompt de confirmação

Este comando configura o computador para receber comandos remotos.
O parâmetro **Force** suprime os prompts do usuário.

```powershell
Enable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.
```

### Exemplo 3: permitir acesso remoto em clientes

Este exemplo mostra como permitir o acesso remoto de redes públicas em versões de cliente do sistema operacional Windows. O nome da regra de firewall pode ser diferente para diferentes versões do Windows.
Use `Get-NetFirewallRule` para ver uma lista de regras. Antes de habilitar a regra de firewall, exiba as configurações de segurança na regra para verificar se a configuração é apropriada para o seu ambiente.

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

Por padrão, o `Enable-PSRemoting` cria regras de rede que permitem o acesso remoto de redes privadas e de domínio. O comando usa o parâmetro **SkipNetworkProfileCheck** para permitir acesso remoto por meio de redes públicas contidas na mesma sub-rede local. O comando especifica o parâmetro **Force** para suprimir as mensagens de confirmação.

O parâmetro **SkipNetworkProfileCheck** não afeta as versões de servidor do sistema operacional Windows, que permitem o acesso remoto de redes públicas na mesma sub-rede local por padrão.

O `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** adiciona uma regra de firewall que permite o acesso remoto de redes públicas de qualquer local remoto. Isso inclui locais em sub-redes diferentes.

### Exemplo 4: criar uma sessão remota para a configuração de ponto de extremidade habilitada recentemente

Este exemplo mostra como habilitar a comunicação remota do PowerShell em um computador, localizar os nomes de ponto de extremidade configurados e criar uma sessão remota para um dos pontos de extremidades.

O primeiro comando habilita a comunicação remota do PowerShell no computador.

O segundo comando lista as configurações do ponto de extremidade.

O terceiro comando cria uma sessão remota do PowerShell para o mesmo computador, especificando o ponto de extremidade do **PowerShell. 6** por nome. A sessão remota será hospedada com a versão mais recente do PowerShell 6 (6.2.2).

O último comando acessa a `$PSVersionTable` variável na sessão remota para exibir a versão do PowerShell que está hospedando a sessão.

```powershell
Enable-PSRemoting -Force

Get-PSSessionConfiguration

$session = New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6

Invoke-Command -Session $session -ScriptBlock { $PSVersionTable }
```

```Output
WARNING: PowerShell remoting has been enabled only for PowerShell Core configurations and does not
affect Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect
all PowerShell remoting configurations.

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                BUILTIN\Remote Management Users AccessAllowed

Name                           Value
----                           -----
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0…}
PSEdition                      Core
PSRemotingProtocolVersion      2.3
Platform                       Win32NT
SerializationVersion           1.1.0.1
GitCommitId                    6.2.2
WSManStackVersion              3.0
PSVersion                      6.2.2
OS                             Microsoft Windows 10.0.18363
```

> [!NOTE]
> O nome da regra de firewall pode ser diferente dependendo da versão do Windows. Use o `Get-NetFirewallRule` cmdlet para listar os nomes das regras em seu sistema.

## PARAMETERS

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipNetworkProfileCheck

Indica que esse cmdlet habilita a comunicação remota em versões de cliente do sistema operacional Windows quando o computador está em uma rede pública. Este parâmetro habilita uma regra de firewall para redes públicas que permite o acesso remoto somente por meio de computadores na mesma sub-rede local.

Esse parâmetro não afeta as versões de servidor do sistema operacional Windows, que, por padrão, têm uma regra de firewall de sub-rede local para redes públicas. Se a regra de firewall de sub-rede local estiver desabilitada em uma versão de servidor, habilite-a `Enable-PSRemoting` novamente, independentemente do valor desse parâmetro.

Para remover a restrição de sub-rede local e habilitar o acesso remoto de todos os locais em redes públicas, use o `Set-NetFirewallRule` cmdlet no módulo **NetSecurity** .

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System.String

Esse cmdlet retorna cadeias de caracteres que descrevem seus resultados.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

Em versões de servidor do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto e cria uma regra de firewall para redes públicas que permite o acesso remoto somente de computadores na mesma sub-rede local.

Nas versões cliente do sistema operacional Windows, o `Enable-PSRemoting` cria regras de firewall para redes privadas e de domínio que permitem acesso remoto irrestrito. Para criar uma regra de firewall para redes públicas que permite acesso remoto por meio da mesma sub-rede local, use o parâmetro **SkipNetworkProfileCheck**.

Em versões de cliente ou servidor do sistema operacional Windows, para criar uma regra de firewall para redes públicas que remove a restrição de sub-rede local e permite o acesso remoto, use o `Set-NetFirewallRule` cmdlet no módulo NetSecurity para executar o seguinte comando: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`

`Enable-PSRemoting` habilita todas as configurações de sessão definindo o valor da propriedade **habilitada** de todas as configurações de sessão como `$True` .

`Enable-PSRemoting` Remove as configurações de **Deny_All** e **Network_Deny_All** . Isso fornece acesso remoto a configurações de sessão que foram reservadas para uso local.

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Disable-PSRemoting](Disable-PSRemoting.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Remote](About/about_Remote.md)

[about_Session_Configurations](About/about_Session_Configurations.md)
