---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 16b41711e98276fee37d56f77f57e7372daa4cf3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597623"
---
# Stop-Transcript

## SINOPSE
Interrompe uma transcrição.

## SYNTAX

```
Stop-Transcript [<CommonParameters>]
```

## DESCRIPTION

O `Stop-Transcript` cmdlet interrompe uma transcrição que foi iniciada pelo `Start-Transcript` cmdlet.
Como alternativa, você pode encerrar uma sessão para interromper uma transcrição.

## EXEMPLOS

### Exemplo 1: parar todas as transcrições

```powershell
Stop-Transcript
```

Esse comando interrompe todas as transcrições.

## PARAMETERS

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System.String

Esse cmdlet retorna uma cadeia de caracteres que contém uma mensagem de status e o caminho para o arquivo de saída.

## OBSERVAÇÕES

* Se uma transcrição não tiver sido iniciada, o comando falha.

*

## LINKS RELACIONADOS

[Start-Transcript](Start-Transcript.md)

