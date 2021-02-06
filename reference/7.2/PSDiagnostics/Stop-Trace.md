---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 5727ae52326830fa16012722d0b801b7d43e50dd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595757"
---
# Stop-Trace

## SINOPSE
Interromper uma sessão de log de rastreamento de eventos.

## SYNTAX

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## DESCRIPTION

Esse cmdlet interrompe uma sessão de log de rastreamento de eventos do Windows.

Esse cmdlet é usado pelos seguintes cmdlets:

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.

## EXEMPLOS

### Exemplo 1: parar uma sessão de log de rastreamento do WSMan

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## PARAMETERS

### -ETS
Envie comandos para sessões de rastreamento de eventos diretamente sem salvar ou agendar.

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

### -SESSIONNAME
O nome da sessão de rastreamento de eventos a ser interrompida.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

## LINKS RELACIONADOS

[Rastreamento de eventos](/windows/desktop/ETW/event-tracing-portal)

[Start-Trace](start-trace.md)

[Disable-PSWSManCombinedTrace](Disable-PSWSManCombinedTrace.md)

[Disable-WSManTrace](Disable-WSManTrace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)

[Enable-WSManTrace](Enable-WSManTrace.md)

