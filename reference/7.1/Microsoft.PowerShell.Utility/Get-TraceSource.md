---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: aae535c105480553a01b02079c2d989970b65b39
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193572"
---
# Get-TraceSource

## SINOPSE
Obtém os componentes do PowerShell que são instrumentados para rastreamento.

## SYNTAX

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-tracename** Obtém as fontes de rastreamento para os componentes do PowerShell que estão em uso no momento.
Você pode usar os dados para determinar quais componentes do PowerShell você pode rastrear.
Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.
Os desenvolvedores utilizam os dados de rastreamento para monitorar o fluxo de dados, a execução do programa e erros.

Os cmdlets de rastreamento foram projetados para desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.

## EXEMPLOS

### Exemplo 1: obter fontes de rastreamento por nome

```
PS C:\> Get-TraceSource -Name "*provider*"
```

Esse comando obtém todas as fontes de rastreamento que têm nomes que incluem o provedor.

### Exemplo 2: obter todas as fontes de rastreamento

```
PS C:\> Get-TraceSource
```

Esse comando obtém todos os componentes do PowerShell que podem ser rastreados.

## PARAMETERS

### -Name

Especifica as origens de rastreamento a serem obtidas.
Caracteres curinga são permitidos.
O *nome* do parâmetro é opcional.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém o nome de uma origem de rastreamento para **Get-tracename** .

## SAÍDAS

### System. Management. Automation. PSTraceSource

**Get-tracename** retorna objetos que representam as origens de rastreamento.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Set-TraceSource](Set-TraceSource.md)

[Trace-Command](Trace-Command.md)

