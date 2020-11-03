---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: 5e43e9e23e52885325eaf1eb4d460a60dc110567
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194884"
---
# Unregister-PSSessionConfiguration

## SINOPSE
Exclui configurações de sessão registradas do computador.

## SYNTAX

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Unregister-PSSessionConfiguration` cmdlet exclui as configurações de sessão registradas do computador. Esse cmdlet foi projetado para administradores de sistema gerenciar configurações de sessão personalizadas para usuários.

Para que a alteração entre em vigor, `Unregister-PSSessionConfiguration` o reinicia o serviço **WinRM** . Para evitar a reinicialização, especifique o parâmetro **NoServiceRestart** .

Se você excluir acidentalmente as configurações de sessão padrão **Microsoft. PowerShell** ou **Microsoft. powershell32** , use o `Enable-PSRemoting` cmdlet para restaurá-las. Para obter mais informações, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

## EXEMPLOS

### Exemplo 1: excluir uma configuração de sessão

Este exemplo exclui a configuração de sessão **MaintenanceShell** do computador.

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### Exemplo 2: excluir uma configuração de sessão e reiniciar o serviço WinRM

Neste exemplo, excluímos a configuração **MaintenanceShell** e reiniciamos o serviço WinRM. O parâmetro **Force** suprime todas as mensagens de usuário para reiniciar o serviço **WinRM** sem avisar.

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### Exemplo 3: excluir todas as configurações de sessão

Este exemplo mostra duas maneiras de excluir todas as configurações de sessão no computador. Ambos os comandos têm o mesmo efeito e podem ser usados de forma intercambiável.

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### Exemplo 4: cancelar o registro sem uma reinicialização

Este exemplo mostra o efeito de usar o parâmetro **NoServiceRestart** para impedir que uma reinicialização de serviço interrompa as sessões no computador.

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

O `Unregister-PSSessionConfiguration` exclui a configuração de sessão **MaintenanceShell** .
No entanto, como o comando usa o parâmetro **NoServiceRestart** , o serviço **WinRM** não é reiniciado e a alteração ainda não está completamente efetiva.

Em seguida, o `Get-PSSessionConfiguration` tenta obter a sessão **MaintenanceShell** . Como a sessão foi removida da tabela de recursos WS-Management, `Get-PSSessionConfiguration` não é possível retorná-la.

O `New-PSSession` cmdlet cria uma sessão usando a configuração **MaintenanceShell** . O comando é bem-sucedido. Em seguida, reiniciamos o serviço **WinRM** .

Por fim, o `New-PSSession` cmdlet tenta criar uma sessão que usa a configuração **MaintenanceShell** . Desta vez, a sessão falhará porque a configuração **MaintenanceShell** foi excluída quando o serviço WinRM for reiniciado.

## PARAMETERS

### -Force

Indica que o cmdlet não solicita confirmação e reinicia o serviço **WinRM** sem avisar. Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.

Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart** .

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

### -Name

Especifica os nomes das configurações de sessão a excluir. Insira um nome de configuração de sessão ou um padrão de nome de configuração. Caracteres curinga são permitidos. Este parâmetro é necessário.

Você também pode canalizar as configurações de sessão para o `Unregister-PSSessionConfiguration` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoServiceRestart

Indica que esse cmdlet não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.

Por padrão, quando você executa um `Unregister-PSSessionConfiguration` comando, é solicitado que você reinicie o serviço **WinRM** para que a alteração seja efetiva. Até que o serviço **WinRM** seja reiniciado, os usuários ainda poderão usar a configuração de sessão não registrada, embora `Get-PSSessionConfiguration` não o encontre.

Para reiniciar o serviço **WinRM** sem avisar, especifique o parâmetro **Force** . Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.

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

### Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration

É possível canalizar um objeto de configuração de sessão `Get-PSSessionConfiguration` a partir desse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhum objeto.

## OBSERVAÇÕES

Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
