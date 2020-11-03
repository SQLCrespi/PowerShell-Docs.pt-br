---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: cc94d85e48849d47531ac0a83527f3c68c21377e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194667"
---
# Enable-PSTrace

## SINOPSE
Habilita os logs do provedor de eventos Microsoft-Windows-PowerShell.

## SYNTAX

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet habilita os logs de eventos operacionais e analíticos do provedor de eventos Microsoft-Windows-PowerShell.

Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.

## EXEMPLOS

### Exemplo 1: habilitar o log de eventos analíticos para o PowerShell

O exemplo a seguir habilita somente o log de eventos analíticos do provedor Microsoft-Windows-PowerShell.

```powershell
Enable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -AnalyticOnly

Quando esse parâmetro é usado, o cmdlet habilita o log de eventos analíticos do provedor Microsoft-Windows-PowerShell. O log de eventos operacional não é alterado.

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

### -Force

Usado para forçar a alteração sem avisar.

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
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

[Disable-PSTrace](Disable-PSTrace.md)

