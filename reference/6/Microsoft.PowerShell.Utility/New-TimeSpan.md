---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 1cfc2cdf4aaf15d54485fb04741f2bbca65fd3be
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194389"
---
# New-TimeSpan

## SINOPSE
Cria um objeto TimeSpan.

## SYNTAX

### Data (padrão)

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### Tempo

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## DESCRIPTION

O `New-TimeSpan` cmdlet cria um objeto **TimeSpan** que representa um intervalo de tempo.
Você pode usar um objeto **TimeSpan** para adicionar ou subtrair time de objetos **DateTime** .

Sem parâmetros, um `New-TimeSpan` comando retorna um objeto **TimeSpan** que representa um intervalo de tempo igual a zero.

## EXEMPLOS

### Exemplo 1: criar um objeto TimeSpan para uma duração especificada

Esse comando cria um objeto **TimeSpan** com uma duração de 1 hora e 25 minutos e o armazena em uma variável chamada `$TimeSpan` . Ele exibe uma representação do objeto **TimeSpan** .

```powershell
$TimeSpan = New-TimeSpan -Hours 1 -Minutes 25
$TimeSpan
```

```Output
Days              : 0
Hours             : 1
Minutes           : 25
Seconds           : 0
Milliseconds      : 0
Ticks             : 51000000000
TotalDays         : 0.0590277777777778
TotalHours        : 1.41666666666667
TotalMinutes      : 85
TotalSeconds      : 5100
TotalMilliseconds : 5100000
```

### Exemplo 2: criar um objeto TimeSpan para um intervalo de tempo

Este exemplo cria um novo objeto **TimeSpan** que representa o intervalo entre a hora em que o comando é executado e 1º de janeiro de 2010.

Esse comando não requer o parâmetro **Start** , pois o valor padrão do parâmetro **Start** é a data e a hora atuais.

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### Exemplo 3: obter a data de 90 dias a partir da data atual

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

Estes comandos retornam a data que é de 90 dias depois da data atual.

### Exemplo 4: descobrir o TimeSpan desde que um arquivo foi atualizado

Esse comando informa quanto tempo foi desde que o arquivo de ajuda [about_Remote](../Microsoft.PowerShell.Core/About/about_Remote.md) foi atualizado pela última vez.
Você pode usar esse formato de comando em qualquer arquivo ou qualquer outro objeto que tenha uma propriedade **LastWriteTime** .

Esse comando funciona porque o parâmetro **inicial** de `New-TimeSpan` tem um alias de **LastWriteTime** . Quando você canaliza um objeto que tem uma propriedade **LastWriteTime** para `New-TimeSpan` , o PowerShell usa o valor da propriedade **LastWriteTime** como o valor do parâmetro **Start** .

```powershell
Get-ChildItem $PSHOME\en-us\about_remote.help.txt | New-TimeSpan
```

```Output
Days              : 321
Hours             : 21
Minutes           : 59
Seconds           : 22
Milliseconds      : 312
Ticks             : 278135623127728
TotalDays         : 321.916230471907
TotalHours        : 7725.98953132578
TotalMinutes      : 463559.371879547
TotalSeconds      : 27813562.3127728
TotalMilliseconds : 27813562312.7728
```

## PARAMETERS

### -Days

Especifica os dias no período de tempo.
O valor padrão é 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fim

Especifica o fim de um período de tempo.
O valor padrão é a data e hora atuais.

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: False
Position: 1
Default value: Current date and time
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Horas

Especifica as horas no período de tempo.
O valor padrão é zero.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Minutos

Especifica os minutos no período de tempo.
O valor padrão é 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Segundos

Especifica o comprimento do período de tempo em segundos.
O valor padrão é 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Iniciar

Especifica o início de um período de tempo.
Insira uma cadeia de caracteres que represente a data e a hora, como "3/15/09" ou um objeto **DateTime** , como um de um `Get-Date` comando. O valor padrão é a data e hora atuais.

Você pode usar **Start** ou seu alias, **LastWriteTime** .
O alias **LastWriteTime** permite que você redirecione objetos que têm uma propriedade **LastWriteTime** , como arquivos no sistema de arquivos `[System.Io.FileIO]` , para o parâmetro **Start** de `New-TimeSpan` .

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases: LastWriteTime

Required: False
Position: 0
Default value: Current date and time
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.DateTime

É possível canalizar um objeto **DateTime** que representa essa hora de início para `New-TimeSpan` .

## SAÍDAS

### System.TimeSpan

`New-TimeSpan` Retorna um objeto que representa o período de tempo.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Obter Data](Get-Date.md)

[Set-Date](Set-Date.md)
