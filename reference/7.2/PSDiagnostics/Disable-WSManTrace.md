---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 647a7676eddf2175bf29e02b3482cc9c7c4d8ebe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596786"
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

