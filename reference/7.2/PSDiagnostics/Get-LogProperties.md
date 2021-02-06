---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: f532dd3ff46f14348437de531e80e94b192b13e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596374"
---
# Get-LogProperties

## SINOPSE
Recupera as propriedades de um log de eventos do Windows.

## SYNTAX

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet obtém as definições de configuração de um log de eventos do Windows. Esse cmdlet é usado pelos `Enable-PSTrace` `Disable-PSTrace` cmdlets e.

## EXEMPLOS

### Exemplo 1: obter as definições de configuração do log de eventos do Windows PowerShell

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## PARAMETERS

### -Name

O nome do provedor de eventos.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

## SAÍDAS

### Microsoft. PowerShell. Diagnostics. LogDetails

O módulo **PSDiagnostics** adiciona a classe **LogDetails** ao `Microsoft.PowerShell.Diagnostics` namespace.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)

[Disable-PSTrace](Disable-PSTrace.md)

