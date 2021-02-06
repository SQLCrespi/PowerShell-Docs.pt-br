---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 22034eeac6988478a5f2ff87b2582cc5e1acc1c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597815"
---
# Get-TimeZone

## SINOPSE
Obtém o fuso horário atual ou uma lista de fusos horários disponíveis.

## SYNTAX

### Nome (padrão)

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### ID

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### ListAvailable

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-TimeZone** Obtém o fuso horário atual ou uma lista de fusos horários disponíveis.

## EXEMPLOS

### Exemplo 1: obter o fuso horário atual

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

Esse comando obtém o fuso horário atual.

### Exemplo 2: obter fusos horários que correspondem a uma cadeia de caracteres especificada

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

Esse comando obtém todos os fusos horários que correspondem ao curinga especificado.

### Exemplo 3: obter todos os fusos horários disponíveis

```
PS C:\> Get-TimeZone -ListAvailable
```

Esse comando obtém todos os fusos horários disponíveis.

## PARAMETERS

### -Id

Especifica, como uma matriz de cadeia de caracteres, a ID ou IDs dos fusos horários que esse cmdlet obtém.

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ListAvailable

Indica que este cmdlet obtém todos os fusos horários disponíveis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica, como uma matriz de cadeia de caracteres, o nome ou os nomes dos fusos horários que esse cmdlet obtém.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String[]

## SAÍDAS

### System. TimeZoneInfo []

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

## LINKS RELACIONADOS

[Set-TimeZone](Set-TimeZone.md)
