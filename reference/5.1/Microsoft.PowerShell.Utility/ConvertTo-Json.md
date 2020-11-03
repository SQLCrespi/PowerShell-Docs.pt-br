---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: b91d3b7cbf86c7ea827539903b2e8373cdfdac72
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193840"
---
# ConvertTo-Json

## SINOPSE
Converte um objeto em uma cadeia de caracteres formatada em JSON.

## SYNTAX

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## DESCRIPTION

O `ConvertTo-Json` cmdlet converte qualquer objeto .net em uma cadeia de caracteres no formato JavaScript Object Notation (JSON). As propriedades são convertidas em nomes de campo, os valores de campo são convertidos em valores de propriedade e os métodos são removidos.

Você pode usar o `ConvertFrom-Json` cmdlet para converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell.

Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1

```powershell
PS C:\> (Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
    "MinSupportedDateTime":  "\/Date(-62135596800000)\/",
    "MaxSupportedDateTime":  "\/Date(253402300799999)\/",
    "AlgorithmType":  1,
    "CalendarType":  1,
    "Eras":  [
                 1
             ],
    "TwoDigitYearMax":  2029,
    "IsReadOnly":  false
}
```

Esse comando usa o `ConvertTo-Json` cmdlet para converter um objeto GregorianCalendar em uma cadeia de caracteres formatada em JSON.

### Exemplo 2

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

Esse comando mostra o efeito de usar o parâmetro **compress** de `ConvertTo-Json` . A compactação afeta apenas a aparência da cadeia de caracteres, não sua validade.

### Exemplo 3:

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
    "DisplayHint":  2,
    "DateTime":  "Friday, January 13, 2012 8:06:16 PM",
    "Date":  "\/Date(1326441600000)\/",
    "Day":  13,
    "DayOfWeek":  5,
    "DayOfYear":  13,
    "Hour":  20,
    "Kind":  2,
    "Millisecond":  221,
    "Minute":  6,
    "Month":  1,
    "Second":  16,
    "Ticks":  634620819762218083,
    "TimeOfDay":  {
                      "Ticks":  723762218083,
                      "Days":  0,
                      "Hours":  20,
                      "Milliseconds":  221,
                      "Minutes":  6,
                      "Seconds":  16,
                      "TotalDays":  0.83768775241087956,
                      "TotalHours":  20.104506057861109,
                      "TotalMilliseconds":  72376221.8083,
                      "TotalMinutes":  1206.2703634716668,
                      "TotalSeconds":  72376.22180829999
                  },
    "Year":  2012
}
```

Este exemplo usa o `ConvertTo-Json` cmdlet para converter um objeto **System. DateTime** do `Get-Date` cmdlet em uma cadeia de caracteres formatada em JSON. O comando usa o `Select-Object` cmdlet para obter todos ( `*` ) das propriedades do objeto **DateTime** . A saída mostra a cadeia de caracteres JSON `ConvertTo-Json` retornada.

### Exemplo 4

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

Este exemplo mostra como usar os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto em uma cadeia de caracteres JSON e um objeto JSON.

## PARAMETERS

### -Compactar

Omite o espaço em branco e a formatação recuada na cadeia de saída.

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

### -Profundidade

Especifica quantos níveis de objetos contidos estão incluídos na representação JSON. O valor padrão é 2.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos para converter em formato JSON. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos. Também é possível canalizar um objeto para `ConvertTo-Json` .

O parâmetro **InputObject** é necessário, mas seu valor pode ser nulo ( `$null` ) ou uma cadeia de caracteres vazia.
Quando o objeto de entrada é, o não `$null` `ConvertTo-Json` gera nenhuma saída. Quando o objeto de entrada é uma cadeia de caracteres vazia, `ConvertTo-Json` retorna uma cadeia de caracteres vazia.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.Object

Você pode canalizar qualquer objeto para `ConvertTo-Json` .

## SAÍDAS

### System.String

## OBSERVAÇÕES

O `ConvertTo-Json` cmdlet é implementado usando a [classe JavaScriptSerializer](/dotnet/api/system.web.script.serialization.javascriptserializer).

## LINKS RELACIONADOS

[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertFrom-Json](ConvertFrom-Json.md)

[Get-Content](../Microsoft.PowerShell.Management/Get-Content.md)

[Get-UICulture](Get-UICulture.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
