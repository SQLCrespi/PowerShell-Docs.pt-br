---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: 26c899b5560df566ec97eb4f81a6f7a4416932ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194522"
---
# <span data-ttu-id="59753-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="59753-103">ConvertTo-Json</span></span>

## <span data-ttu-id="59753-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="59753-104">SYNOPSIS</span></span>
<span data-ttu-id="59753-105">Converte um objeto em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="59753-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="59753-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59753-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## <span data-ttu-id="59753-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="59753-107">DESCRIPTION</span></span>

<span data-ttu-id="59753-108">O `ConvertTo-Json` cmdlet converte qualquer objeto .net em uma cadeia de caracteres no formato JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="59753-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="59753-109">As propriedades são convertidas em nomes de campo, os valores de campo são convertidos em valores de propriedade e os métodos são removidos.</span><span class="sxs-lookup"><span data-stu-id="59753-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="59753-110">Você pode usar o `ConvertFrom-Json` cmdlet para converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59753-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="59753-111">Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.</span><span class="sxs-lookup"><span data-stu-id="59753-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="59753-112">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59753-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="59753-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="59753-113">EXAMPLES</span></span>

### <span data-ttu-id="59753-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="59753-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
  "MinSupportedDateTime": "0001-01-01T00:00:00",
  "MaxSupportedDateTime": "9999-12-31T23:59:59.9999999",
  "AlgorithmType": 1,
  "CalendarType": 1,
  "Eras": [
    1
  ],
  "TwoDigitYearMax": 2029,
  "IsReadOnly": true
}
```

<span data-ttu-id="59753-115">Esse comando usa o `ConvertTo-Json` cmdlet para converter um objeto GregorianCalendar em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="59753-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="59753-116">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="59753-116">Example 2</span></span>

```powershell
Get-Date | ConvertTo-Json; Get-Date | ConvertTo-Json -AsArray
```

```Output
{
  "value": "2018-10-12T23:07:18.8450248-05:00",
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 11:07:18 PM"
}
[
  {
    "value": "2018-10-12T23:07:18.8480668-05:00",
    "DisplayHint": 2,
    "DateTime": "October 12, 2018 11:07:18 PM"
  }
]
```

<span data-ttu-id="59753-117">Este exemplo mostra a saída do `ConvertTo-Json` cmdlet com e sem o parâmetro de opção **asarray** .</span><span class="sxs-lookup"><span data-stu-id="59753-117">This example shows the output from `ConvertTo-Json` cmdlet with and without the **AsArray** switch parameter.</span></span> <span data-ttu-id="59753-118">Você pode ver que a segunda parte da saída é encapsulada em colchetes de matriz.</span><span class="sxs-lookup"><span data-stu-id="59753-118">You can see the second portion of the output is wrapped in array brackets.</span></span>

### <span data-ttu-id="59753-119">Exemplo 3:</span><span class="sxs-lookup"><span data-stu-id="59753-119">Example 3</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="59753-120">Esse comando mostra o efeito de usar o parâmetro **compress** de `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="59753-120">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="59753-121">A compactação afeta apenas a aparência da cadeia de caracteres, não sua validade.</span><span class="sxs-lookup"><span data-stu-id="59753-121">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="59753-122">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="59753-122">Example 4</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 10:55:32 PM",
  "Date": "2018-10-12T00:00:00-05:00",
  "Day": 12,
  "DayOfWeek": 5,
  "DayOfYear": 285,
  "Hour": 22,
  "Kind": 2,
  "Millisecond": 639,
  "Minute": 55,
  "Month": 10,
  "Second": 32,
  "Ticks": 636749817326397744,
  "TimeOfDay": {
    "Ticks": 825326397744,
    "Days": 0,
    "Hours": 22,
    "Milliseconds": 639,
    "Minutes": 55,
    "Seconds": 32,
    "TotalDays": 0.95523888627777775,
    "TotalHours": 22.925733270666665,
    "TotalMilliseconds": 82532639.774400011,
    "TotalMinutes": 1375.54399624,
    "TotalSeconds": 82532.6397744
  },
  "Year": 2018
}
```

<span data-ttu-id="59753-123">Este exemplo usa o `ConvertTo-Json` cmdlet para converter um objeto **System. DateTime** do `Get-Date` cmdlet em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="59753-123">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="59753-124">O comando usa o `Select-Object` cmdlet para obter todos ( `*` ) das propriedades do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="59753-124">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="59753-125">A saída mostra a cadeia de caracteres JSON `ConvertTo-Json` retornada.</span><span class="sxs-lookup"><span data-stu-id="59753-125">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="59753-126">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="59753-126">Example 5</span></span>

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

<span data-ttu-id="59753-127">Este exemplo mostra como usar os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto em uma cadeia de caracteres JSON e um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="59753-127">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="59753-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="59753-128">PARAMETERS</span></span>

### <span data-ttu-id="59753-129">-Asarray</span><span class="sxs-lookup"><span data-stu-id="59753-129">-AsArray</span></span>

<span data-ttu-id="59753-130">Gera o objeto em colchetes de matriz, mesmo que a entrada seja um único objeto.</span><span class="sxs-lookup"><span data-stu-id="59753-130">Outputs the object in array brackets, even if the input is a single object.</span></span>

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

### <span data-ttu-id="59753-131">-Compactar</span><span class="sxs-lookup"><span data-stu-id="59753-131">-Compress</span></span>

<span data-ttu-id="59753-132">Omite o espaço em branco e a formatação recuada na cadeia de saída.</span><span class="sxs-lookup"><span data-stu-id="59753-132">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="59753-133">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="59753-133">-Depth</span></span>

<span data-ttu-id="59753-134">Especifica quantos níveis de objetos contidos estão incluídos na representação JSON.</span><span class="sxs-lookup"><span data-stu-id="59753-134">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="59753-135">O valor padrão é 2.</span><span class="sxs-lookup"><span data-stu-id="59753-135">The default value is 2.</span></span>

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

### <span data-ttu-id="59753-136">-EnumsAsStrings</span><span class="sxs-lookup"><span data-stu-id="59753-136">-EnumsAsStrings</span></span>

<span data-ttu-id="59753-137">Fornece uma opção de serialização alternativa que converte todas as enumerações em sua representação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="59753-137">Provides an alternative serialization option that converts all enumerations to their string representation.</span></span>

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

### <span data-ttu-id="59753-138">-EscapeHandling</span><span class="sxs-lookup"><span data-stu-id="59753-138">-EscapeHandling</span></span>

<span data-ttu-id="59753-139">Controla como determinados caracteres são ignorados na saída JSON resultante.</span><span class="sxs-lookup"><span data-stu-id="59753-139">Controls how certain characters are escaped in the resulting JSON output.</span></span> <span data-ttu-id="59753-140">Por padrão, somente caracteres de controle (como nova linha) são ignorados.</span><span class="sxs-lookup"><span data-stu-id="59753-140">By default, only control characters (like newline) are escaped.</span></span>

<span data-ttu-id="59753-141">Os valores aceitáveis são:</span><span class="sxs-lookup"><span data-stu-id="59753-141">Acceptable values are:</span></span>

- <span data-ttu-id="59753-142">Caracteres de controle somente padrão são de escape.</span><span class="sxs-lookup"><span data-stu-id="59753-142">Default - Only control characters are escaped.</span></span>
- <span data-ttu-id="59753-143">EscapeNonAscii-todos os caracteres que não são ASCII e de controle são ignorados.</span><span class="sxs-lookup"><span data-stu-id="59753-143">EscapeNonAscii - All non-ASCII and control characters are escaped.</span></span>
- <span data-ttu-id="59753-144">EscapeHtml-HTML ( `<` ,,, `>` `&` `'` , `"` ) e caracteres de controle são ignorados.</span><span class="sxs-lookup"><span data-stu-id="59753-144">EscapeHtml - HTML (`<`, `>`, `&`, `'`, `"`) and control characters are escaped.</span></span>

<span data-ttu-id="59753-145">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="59753-145">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: Newtonsoft.Json.StringEscapeHandling
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59753-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="59753-146">-InputObject</span></span>

<span data-ttu-id="59753-147">Especifica os objetos para converter em formato JSON.</span><span class="sxs-lookup"><span data-stu-id="59753-147">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="59753-148">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="59753-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="59753-149">Também é possível canalizar um objeto para `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="59753-149">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="59753-150">O parâmetro **InputObject** é necessário, mas seu valor pode ser nulo ( `$null` ) ou uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="59753-150">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="59753-151">Quando o objeto de entrada é, o não `$null` `ConvertTo-Json` gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="59753-151">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="59753-152">Quando o objeto de entrada é uma cadeia de caracteres vazia, `ConvertTo-Json` retorna uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="59753-152">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="59753-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="59753-153">CommonParameters</span></span>

<span data-ttu-id="59753-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="59753-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="59753-155">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="59753-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="59753-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="59753-156">INPUTS</span></span>

### <span data-ttu-id="59753-157">System.Object</span><span class="sxs-lookup"><span data-stu-id="59753-157">System.Object</span></span>

<span data-ttu-id="59753-158">Você pode canalizar qualquer objeto para `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="59753-158">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="59753-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="59753-159">OUTPUTS</span></span>

### <span data-ttu-id="59753-160">System.String</span><span class="sxs-lookup"><span data-stu-id="59753-160">System.String</span></span>

## <span data-ttu-id="59753-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="59753-161">NOTES</span></span>

<span data-ttu-id="59753-162">O `ConvertTo-Json` cmdlet é implementado usando [Newtonsoft JSON.net](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="59753-162">The `ConvertTo-Json` cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

## <span data-ttu-id="59753-163">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="59753-163">RELATED LINKS</span></span>

<span data-ttu-id="59753-164">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="59753-164">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="59753-165">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="59753-165">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="59753-166">Get-Content</span><span class="sxs-lookup"><span data-stu-id="59753-166">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="59753-167">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="59753-167">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="59753-168">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="59753-168">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="59753-169">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="59753-169">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="59753-170">NewtonSoft.Jsem. StringEscapeHandling</span><span class="sxs-lookup"><span data-stu-id="59753-170">NewtonSoft.Json.StringEscapeHandling</span></span>](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
