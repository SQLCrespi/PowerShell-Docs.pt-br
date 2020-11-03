---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 50ad2d48faee88c196942b13141d3ad57c51fdeb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192834"
---
# Disable-PSTrace

## SINOPSE
Desabilita os logs do provedor de eventos Microsoft-Windows-PowerShell.

## SYNTAX

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet desabilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.

Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.

## EXEMPLOS

### Exemplo 1: desabilitar o log de eventos analíticos para o PowerShell

O exemplo a seguir desabilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.

```powershell
Disable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -AnalyticOnly

Quando esse parâmetro é usado, o cmdlet desabilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell. O log de eventos operacional não é alterado.

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

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

## SAÍDAS

### Nenhum

## OBSERVAÇÕES

Esse cmdlet usa os `Get-LogProperties` `Set-LogProperties` cmdlets e.

Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.

## LINKS RELACIONADOS

[Get-LogProperties](Get-LogProperties.md)

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)
