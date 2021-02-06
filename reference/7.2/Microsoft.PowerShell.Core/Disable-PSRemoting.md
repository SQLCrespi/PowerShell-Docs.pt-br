---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 4410c8f41fffcaae9c9f447af246f335033d53a1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598423"
---
# Disable-PSRemoting

## SINOPSE
Impede que os pontos de extremidade do PowerShell recebam conexões remotas.

## SYNTAX

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Disable-PSRemoting` cmdlet bloqueia o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell versão 6 e superiores no computador local. Ele não afeta as configurações de ponto de extremidade do Windows PowerShell. Para desabilitar as configurações de ponto de extremidade de sessão do Windows PowerShell, execute `Disable-PSRemoting` o comando de dentro de uma sessão do Windows PowerShell.

Para reabilitar o acesso remoto a todas as configurações do PowerShell versão 6 e superiores de ponto de extremidade de sessão, use o `Enable-PSRemoting` cmdlet. Para reabilitar o acesso remoto a todas as configurações de ponto de extremidade de sessão do Windows PowerShell, execute `Enable-PSRemoting` de dentro de uma sessão do Windows PowerShell.

> [!NOTE]
> Se você quiser desabilitar todo o acesso remoto do PowerShell para um computador local do Windows, deverá executar esse comando de um dentro do PowerShell versão 6 ou superior e de dentro de uma sessão do Windows PowerShell. Por padrão, o Windows PowerShell é instalado em todas as máquinas Windows.

Para desabilitar e reabilitar o acesso remoto a configurações de ponto de extremidade de sessão específicas, use os `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` cmdlets e. Para definir configurações de acesso específicas de pontos de extremidade individuais, use o `Set-PSSessionConfiguration` cmdlet junto com o parâmetro **AccessMode** . Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

> [!NOTE]
> Mesmo após a execução `Disable-PSRemoting` , você ainda poderá fazer conexões de loopback no computador local. Uma conexão de auto-retorno é uma sessão remota do PowerShell que se origina do e se conecta ao mesmo computador local. As sessões remotas de fontes externas permanecem bloqueadas. Para conexões de loopback, você deve usar credenciais implícitas ao longo do parâmetro **EnableNetworkAccess** . Para obter mais informações sobre conexões de loopback, consulte [New-PSSession](New-PSSession.md).

Esse cmdlet só está disponível na plataforma Windows. Ele não está disponível nas versões Linux ou macOS do PowerShell. Para executar esse cmdlet, inicie o PowerShell com a opção **Executar como administrador** .

## EXEMPLOS

### Exemplo 1: impedir o acesso remoto a todas as configurações de sessão do PowerShell

Este exemplo impede o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador.

```powershell
Disable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### Exemplo 2: impedir o acesso remoto a todas as configurações de sessão do PowerShell sem prompt de confirmação

Este exemplo impede o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador sem avisar.

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### Exemplo 3: efeitos da execução deste cmdlet

Este exemplo mostra o efeito de usar o `Disable-PSRemoting` cmdlet. Para executar essa sequência de comandos, inicie o PowerShell com a opção **Executar como administrador** .

Depois de desabilitar as configurações de sessões, o `New-PSSession` cmdlet tenta criar uma sessão remota para o computador local (também conhecido como "Loopback"). Como o acesso remoto está desabilitado no computador local, o comando falha.

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### Exemplo 4: efeitos da execução deste cmdlet e Enable-PSRemoting

Este exemplo mostra o efeito nas configurações de sessão do usando os `Disable-PSRemoting` `Enable-PSRemoting` cmdlets e.

`Disable-PSRemoting` é usado para desabilitar o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell. O parâmetro **Force** suprime todos os prompts de usuário. Os `Get-PSSessionConfiguration` `Format-Table` cmdlets e exibem as configurações de sessão no computador.

A saída mostra que todos os usuários remotos com um token de rede têm acesso negado às configurações do ponto de extremidade. O grupo de administradores no computador local tem permissão para acessar as configurações do ponto de extremidade, desde que eles estejam se conectando localmente (também conhecido como loopback) e usando credenciais implícitas.

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
```

O `Enable-PSRemoting` cmdlet habilita novamente o acesso remoto a todas as configurações de ponto de extremidade de sessão do PowerShell no computador. O parâmetro **Force** suprime todos os prompts do usuário e reinicia o serviço WinRM sem avisar. A nova saída mostra que os descritores de segurança **AccessDenied** foram removidos de todas as configurações de sessão.

### Exemplo 5: conexões de loopback com configurações de ponto de extremidade de sessão desabilitadas

Este exemplo demonstra como as configurações de ponto de extremidade estão desabilitadas e mostra como fazer uma conexão de loopback bem-sucedida para um ponto de extremidade desabilitado. `Disable-PSRemoting` desabilita todas as configurações de ponto de extremidade de sessão do PowerShell.

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -Credential (Get-Credential)
```

```Output
PowerShell credential request
Enter your credentials.
User: UserName
Password for user UserName: ************

New-PSSession: [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

O primeiro uso de `New-PSSession` tentativas para criar uma sessão remota para o computador local. O parâmetro **ConfigurationName** é usado para especificar um ponto de extremidade desabilitado do PowerShell. As credenciais são passadas explicitamente para o comando por meio do parâmetro **Credential** . Esse tipo de conexão passa pela pilha de rede e não é um loopback. Consequentemente, a tentativa de conexão com o ponto de extremidade desabilitado falha com um erro de **acesso negado** .

O segundo uso do `New-PSSession` também tenta criar uma sessão remota para o computador local.
Nesse caso, ele é executado com sucesso porque é uma conexão de loopback que ignora a pilha de rede.

Uma conexão de loopback é criada quando as seguintes condições são atendidas:

- O nome do computador ao qual se conectar é ' localhost '.
- Nenhuma credencial é passada. O usuário conectado no momento (credenciais implícitas) é usado para a conexão.
- O parâmetro de opção **EnableNetworkAccess** é usado.

Para obter mais informações sobre conexões de loopback, consulte o documento [New-PSSession](New-PSSession.md) .

### Exemplo 6: desabilitando todas as configurações de ponto de extremidade de comunicação remota do PowerShell

Este exemplo demonstra como a execução do `Disable-PSRemoting` comando não afeta as configurações de ponto de extremidade do Windows PowerShell. `Get-PSSessionConfiguration` executar no Windows PowerShell mostra todas as configurações de ponto de extremidade. Vemos que as configurações de ponto de extremidade do Windows PowerShell não estão desabilitadas.

```powershell
Disable-PSRemoting -Force
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

```powershell
powershell.exe -command 'Disable-PSRemoting -Force'
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting or
Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the
Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management
                Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

Para desabilitar essas configurações de ponto de extremidade, o `Disable-PSRemoting` comando deve ser executado de dentro de uma sessão do Windows PowerShell. Agora, `Get-PSSessionConfiguration` Executar de dentro do Windows PowerShell mostra que todas as configurações de ponto de extremidade estão desabilitadas.

### Exemplo 7: impedir o acesso remoto a configurações de sessão que têm descritores de segurança personalizados

Este exemplo demonstra que o `Disable-PSRemoting` cmdlet desabilita o acesso remoto a todas as configurações de sessão que incluem configurações de sessão com descritores de segurança personalizados.

`Register-PSSessionConfiguration` cria a configuração da sessão de **teste** . O parâmetro **FilePath** especifica um arquivo de configuração de sessão que personaliza a sessão. O parâmetro **ShowSecurityDescriptorUI dos** exibe uma caixa de diálogo que define permissões para a configuração de sessão. Na caixa de diálogo permissões, criamos permissões personalizadas de acesso completo para o usuário indicado.

Os `Get-PSSessionConfiguration` `Format-Table` cmdlets e exibem as configurações de sessão e suas propriedades. A saída mostra que a configuração da sessão de **teste** permite acesso interativo e permissões especiais para o usuário indicado.

`Disable-PSRemoting` desabilita o acesso remoto a todas as configurações de sessão.

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, User01 AccessAllowed

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName Test
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

Agora `Get-PSSessionConfiguration` , os `Format-Table` cmdlets e mostram que um descritor de segurança **AccessDenied** para todos os usuários de rede é adicionado a todas as configurações de sessão, incluindo a configuração da sessão de **teste** . Embora os outros descritores de segurança não sejam alterados, a descrição de segurança "network_deny_all" tem precedência. Isso é ilustrado pela tentativa de usar `New-PSSession` o para se conectar à configuração da sessão de **teste** .

### Exemplo 8: reabilitar o acesso remoto para as configurações de sessão selecionadas

Este exemplo mostra como reabilitar o acesso remoto apenas para as configurações de sessão selecionadas. Depois de desabilitar todas as configurações de sessão, reabilitamos uma sessão específica.

O `Set-PSSessionConfiguration` cmdlet é usado para alterar a configuração de sessão do **PowerShell. 6** . O parâmetro **AccessMode** com um valor de reabilitar **remotamente** o acesso remoto à configuração.

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name PowerShell.6 -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\ ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
```

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

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

Não é possível canalizar nenhum objeto para este cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

- Desabilitar as configurações de sessão não desfaz todas as alterações feitas pelos `Enable-PSRemoting` `Enable-PSSessionConfiguration` cmdlets ou. Você talvez precise desfazer, manualmente, as alterações listadas a seguir.

  1. Interrompa e desabilite o serviço WinRM.
  2. Exclua o ouvinte que aceita solicitações em qualquer endereço IP.
  3. Desabilite as exceções de firewall para comunicações do WS-Management.
  4. Restaure o valor de LocalAccountTokenFilterPolicy para 0, o que restringe o acesso remoto apenas a membros do grupo Administradores do computador.

- Uma configuração de ponto de extremidade de sessão é um grupo de configurações que definem o ambiente de uma sessão.
  Cada sessão que se conecta ao computador deve usar uma das configurações de ponto de extremidade de sessão registradas no computador. Ao negar acesso remoto a todas as configurações de ponto de extremidade de sessão, você efetivamente impede que usuários remotos estabeleçam sessões que se conectam ao computador.

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSRemoting](Enable-PSRemoting.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
