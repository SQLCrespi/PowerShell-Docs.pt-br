---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: df7f9000cf66cebce83e3146cd5c95a7d1a78bf8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597012"
---
# New-Guid

## SINOPSE
Cria um GUID.

## SYNTAX

```
New-Guid [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **New-GUID** cria um GUID (identificador global exclusivo) aleatório.
Se precisar de uma ID exclusiva em um script, você poderá criar um GUID, conforme necessário.

## EXEMPLOS

### Exemplo 1: criar um GUID

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

Este comando cria um GUID aleatório.
Como alternativa, você pode armazenar a saída desse cmdlet em uma variável para usar em outro lugar em um script.

## PARAMETERS

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### System.Guid

Esse cmdlet retorna um GUID.

## OBSERVAÇÕES

## LINKS RELACIONADOS

