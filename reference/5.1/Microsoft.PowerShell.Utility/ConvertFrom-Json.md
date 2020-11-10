---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: e1bab9250269dadf0d899f9e172e8a4a8387271d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388120"
---
# ConvertFrom-Json

## SINOPSE
Converte uma cadeia de caracteres formatada em JSON em um objeto personalizado.

## SYNTAX

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

O `ConvertFrom-Json` cmdlet converte uma cadeia de caracteres formatada JavaScript Object Notation (JSON) em um objeto **PSCustomObject** personalizado que tem uma propriedade para cada campo na cadeia de caracteres JSON. JSON utilizado comumente por sites da web para fornecer uma representação textual de objetos. O padrão JSON não proíbe o uso que seja proibido com um **PSCustomObject**. Por exemplo, se a cadeia de caracteres JSON contiver chaves duplicadas, somente a última chave será usada por esse cmdlet. Consulte outros exemplos abaixo.

Para gerar uma cadeia de caracteres JSON de qualquer objeto, use o `ConvertTo-Json` cmdlet.

Esse cmdlet foi introduzido no PowerShell 3,0.

> [!NOTE]
> Este cmdlet não dá suporte a JSON com comentários.

## EXEMPLOS

### Exemplo 1: converter um objeto DateTime em um objeto JSON

Esse comando usa os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto **DateTime** do `Get-Date` cmdlet em um objeto JSON, em seguida, em um **PSCustomObject**.

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

O exemplo usa o `Select-Object` cmdlet para obter todas as propriedades do objeto **DateTime** . Ele usa o `ConvertTo-Json` cmdlet para converter o objeto **DateTime** em uma cadeia de caracteres formatada como um objeto JSON e o `ConvertFrom-Json` cmdlet para converter a cadeia de caracteres formatada em JSON em um objeto **PSCustomObject** .

### Exemplo 2: obter cadeias de caracteres JSON de um serviço Web e convertê-las em objetos do PowerShell

Esse comando usa o `Invoke-WebRequest` cmdlet para obter cadeias de caracteres JSON de um serviço Web e, em seguida, usa o `ConvertFrom-Json` cmdlet para converter o conteúdo JSON em objetos que podem ser gerenciados no PowerShell.

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

Você também pode usar o `Invoke-RestMethod` cmdlet, que converte automaticamente o conteúdo JSON em objetos.

### Exemplo 3: converter uma cadeia de caracteres JSON em um objeto personalizado

Este exemplo mostra como usar o `ConvertFrom-Json` cmdlet para converter um arquivo JSON em um objeto personalizado do PowerShell.

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

O comando usa Get-Content cmdlet para obter as cadeias de caracteres em um arquivo JSON. Em seguida, ele usa o operador de pipeline para enviar a cadeia de caracteres delimitada ao `ConvertFrom-Json` cmdlet, que converte-o em um objeto personalizado.

## PARAMETERS

### -InputObject

Especifica as cadeias de caracteres JSON a converter em objetos JSON. Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia. Você também pode canalizar uma cadeia de caracteres para `ConvertFrom-Json` .

O parâmetro **InputObject** é obrigatório, mas seu valor pode ser uma cadeia de caracteres vazia. Quando o objeto de entrada é uma cadeia de caracteres vazia, o não `ConvertFrom-Json` gera nenhuma saída. O valor **InputObject** não pode ser `$null` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres JSON para `ConvertFrom-Json` .

## SAÍDAS

### PSCustomObject

## OBSERVAÇÕES

O `ConvertFrom-Json` cmdlet é implementado usando a [classe JavaScriptSerializer](/dotnet/api/system.web.script.serialization.javascriptserializer).

## LINKS RELACIONADOS

[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
