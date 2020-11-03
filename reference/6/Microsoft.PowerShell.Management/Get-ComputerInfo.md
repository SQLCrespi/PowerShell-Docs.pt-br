---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: 55e7831112d6385b6d449123973ca4b877faa7fd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194402"
---
# Get-ComputerInfo

## SINOPSE
Obtém um objeto consolidado das propriedades sistema e sistema operacional.

## SYNTAX

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-ComputerInfo` cmdlet obtém um objeto consolidado das propriedades sistema e sistema operacional.
Esse cmdlet foi introduzido no Windows PowerShell 5,1.

## EXEMPLOS

### Exemplo 1: obter todas as propriedades do computador

```powershell
Get-ComputerInfo
```

Esse comando obtém todas as propriedades do sistema e do sistema operacional do computador.

### Exemplo 2: obter todas as propriedades do sistema operacional do computador

```powershell
Get-ComputerInfo -Property "os*"
```

Esse comando obtém todas as propriedades do sistema operacional do computador.

## PARAMETERS

### -Propriedade

Especifica, como uma matriz de cadeia de caracteres, as propriedades do computador em que esse cmdlet é exibido.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String[]

## SAÍDAS

### Microsoft. PowerShell. Management. ComputerInfo

## OBSERVAÇÕES

## LINKS RELACIONADOS
