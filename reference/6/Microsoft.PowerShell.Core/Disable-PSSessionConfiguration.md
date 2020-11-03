---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSSessionConfiguration
ms.openlocfilehash: 4e551c42c0ae6e447906c5541fb100ef0ef82681
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194081"
---
# Disable-PSSessionConfiguration

## SINOPSE
Desabilita as configurações de sessão no computador local.

## SYNTAX

```
Disable-PSSessionConfiguration [[-Name] <String[]>] [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Disable-PSSessionConfiguration` cmdlet desabilita as configurações de sessão no computador local, o que impede que todos os usuários usem as configurações de sessão para criar sessões gerenciadas pelo usuário ( **PSSessions** ) no computador local. Esse é um cmdlet avançado projetado para ser utilizado por administradores de sistema a fim de gerenciar configurações de sessão personalizadas para seus usuários.

A partir do PowerShell 3,0, o `Disable-PSSessionConfiguration` cmdlet define a configuração **habilitada** da configuração de sessão ( `WSMan:\localhost\Plugins\<SessionConfiguration>\Enabled` ) como false.

No PowerShell 2,0, o `Disable-PSSessionConfiguration` cmdlet adiciona uma entrada de **Deny_All** ao descritor de segurança de uma ou mais configurações de sessão registradas.

Sem parâmetros, `Disable-PSSessionConfiguration` desabilita a configuração do **Microsoft. PowerShell** , a configuração padrão usada para sessões. A menos que o usuário especifique uma configuração diferente, tanto os usuários locais e remotos são efetivamente impedidos de criar quaisquer sessões que se conectem ao computador.

Para desabilitar todas as configurações de sessão no computador, use `Disable-PSRemoting` .

## EXEMPLOS

### Exemplo 1: desabilitar a configuração padrão

Este exemplo desabilita a configuração de sessão do Microsoft. PowerShell.

```powershell
Disable-PSSessionConfiguration
```

### Exemplo 2: desabilitar todas as configurações de sessão registradas

Este exemplo desabilita todas as configurações de sessão registradas no computador.

```powershell
Disable-PSSessionConfiguration -Name *
```

### Exemplo 3: desabilitar as configurações de sessão por nome

Este exemplo desabilita todas as configurações de sessão que têm nomes que começam com a Microsoft. O parâmetro **Force** suprime todos os prompts do usuário do cmdlet.

```powershell
Disable-PSSessionConfiguration -Name Microsoft* -Force
```

### Exemplo 4: desabilitar as configurações de sessão usando o pipeline

Este exemplo desabilita as configurações de sessão **MaintenanceShell** e **AdminShell** . O operador de pipeline (|) envia os resultados de um `Get-PSSessionConfiguration` para `Disable-PSSessionConfiguration` .

```powershell
Get-PSSessionConfiguration -Name MaintenanceShell, AdminShell | Disable-PSSessionConfiguration
```

### Exemplo 5: efeitos da desabilitação de uma configuração de sessão

Este exemplo mostra as permissões antes e depois `Disable-PSSessionConfiguration` da execução e o efeito de desabilitar uma configuração de sessão.

```
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> Disable-PSSessionConfiguration -Name MaintenanceShell -Force
PS> Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Name                   Permission
----                   ----------
MaintenanceShell       Everyone AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell   BUILTIN\Administrators AccessAllowed
microsoft.powershell32 BUILTIN\Administrators AccessAllowed

PS> New-PSSession -ComputerName localhost -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message : Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

> [!NOTE]
> Desabilitar a configuração não impede que você altere a configuração usando o `Set-PSSessionConfiguration` cmdlet. Ele só impede o uso da configuração.

## PARAMETERS

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

### -Name

Especifica uma matriz de nomes de configurações de sessão a serem desabilitadas. Insira um ou mais nomes de configuração. Caracteres curinga são permitidos. Você também pode canalizar uma cadeia de caracteres que contém um nome de configuração ou um objeto de configuração de sessão para `Disable-PSSessionConfiguration` .

Se você omitir esse parâmetro, `Disable-PSSessionConfiguration` o desabilitará a configuração de sessão do Microsoft. PowerShell.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -NoServiceRestart

Usado para impedir a reinicialização do serviço WSMan. Não é necessário reiniciar o serviço para desabilitar a configuração.

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

### Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration, System. String

É possível canalizar um objeto de configuração de sessão ou uma cadeia de caracteres que contém o nome de uma configuração de sessão para esse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhum objeto.

## OBSERVAÇÕES

Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
