---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: f7ec371e0d9826dc095fbf71c4785cae2856875b
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192604"
---
# Disable-WSManTrace

## SINOPSE
Pare a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.

## SYNTAX

```
Disable-WSManTrace [<CommonParameters>]
```

## DESCRIPTION
Esse cmdlet interrompe a sessão de registro em log do WSMan iniciada por Enable-WSManTrace.

Esse cmdlet usa o `Stop-Trace` cmdlet.

Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.

## EXEMPLOS

### Exemplo 1: parar um rastreamento WSMan

```powershell
Disable-WSManTrace
```

## PARAMETERS

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

## SAÍDAS

### Nenhum

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Rastreamento de eventos](/windows/desktop/ETW/event-tracing-portal)

[Stop-Trace](stop-trace.md)

[Enable-WSManTrace](Enable-WSManTrace.md)
