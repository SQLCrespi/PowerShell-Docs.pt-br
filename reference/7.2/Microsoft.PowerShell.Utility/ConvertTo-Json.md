---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: d598fe2b1aefdae046b0f1a0893bf4fc407fa7a7
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "99603351"
---
# <span data-ttu-id="5b877-102">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="5b877-102">ConvertTo-Json</span></span>

## <span data-ttu-id="5b877-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5b877-103">SYNOPSIS</span></span>
<span data-ttu-id="5b877-104">Converte um objeto em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="5b877-104">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="5b877-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5b877-105">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## <span data-ttu-id="5b877-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5b877-106">DESCRIPTION</span></span>

<span data-ttu-id="5b877-107">O `ConvertTo-Json` cmdlet converte qualquer objeto .net em uma cadeia de caracteres no formato JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="5b877-107">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="5b877-108">As propriedades são convertidas em nomes de campo, os valores de campo são convertidos em valores de propriedade e os métodos são removidos.</span><span class="sxs-lookup"><span data-stu-id="5b877-108">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="5b877-109">Você pode usar o `ConvertFrom-Json` cmdlet para converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b877-109">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="5b877-110">Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.</span><span class="sxs-lookup"><span data-stu-id="5b877-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="5b877-111">A partir do PowerShell 7,2, `ConvertTo-Json` o emitirá um aviso se a profundidade do objeto de entrada exceder a profundidade especificada para o comando.</span><span class="sxs-lookup"><span data-stu-id="5b877-111">As of PowerShell 7.2, `ConvertTo-Json` emits a warning if the depth of the input object exceeds the depth specified for the command.</span></span> <span data-ttu-id="5b877-112">Isso impede a perda de dados indesejados durante a conversão de objetos.</span><span class="sxs-lookup"><span data-stu-id="5b877-112">This prevents unwanted data loss when converting objects.</span></span>

<span data-ttu-id="5b877-113">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5b877-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="5b877-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5b877-114">EXAMPLES</span></span>

### <span data-ttu-id="5b877-115">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="5b877-115">Example 1</span></span>

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

<span data-ttu-id="5b877-116">Esse comando usa o `ConvertTo-Json` cmdlet para converter um objeto GregorianCalendar em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="5b877-116">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="5b877-117">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="5b877-117">Example 2</span></span>

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

<span data-ttu-id="5b877-118">Este exemplo mostra a saída do `ConvertTo-Json` cmdlet com e sem o parâmetro de opção **asarray** .</span><span class="sxs-lookup"><span data-stu-id="5b877-118">This example shows the output from `ConvertTo-Json` cmdlet with and without the **AsArray** switch parameter.</span></span> <span data-ttu-id="5b877-119">Você pode ver que a segunda parte da saída é encapsulada em colchetes de matriz.</span><span class="sxs-lookup"><span data-stu-id="5b877-119">You can see the second portion of the output is wrapped in array brackets.</span></span>

### <span data-ttu-id="5b877-120">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="5b877-120">Example 3</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="5b877-121">Esse comando mostra o efeito de usar o parâmetro **compress** de `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="5b877-121">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="5b877-122">A compactação afeta apenas a aparência da cadeia de caracteres, não sua validade.</span><span class="sxs-lookup"><span data-stu-id="5b877-122">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="5b877-123">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="5b877-123">Example 4</span></span>

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

<span data-ttu-id="5b877-124">Este exemplo usa o `ConvertTo-Json` cmdlet para converter um objeto **System. DateTime** do `Get-Date` cmdlet em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="5b877-124">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="5b877-125">O comando usa o `Select-Object` cmdlet para obter todos ( `*` ) das propriedades do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="5b877-125">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="5b877-126">A saída mostra a cadeia de caracteres JSON `ConvertTo-Json` retornada.</span><span class="sxs-lookup"><span data-stu-id="5b877-126">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="5b877-127">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="5b877-127">Example 5</span></span>

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

<span data-ttu-id="5b877-128">Este exemplo mostra como usar os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto em uma cadeia de caracteres JSON e um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="5b877-128">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="5b877-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5b877-129">PARAMETERS</span></span>

### <span data-ttu-id="5b877-130">-Asarray</span><span class="sxs-lookup"><span data-stu-id="5b877-130">-AsArray</span></span>

<span data-ttu-id="5b877-131">Gera o objeto em colchetes de matriz, mesmo que a entrada seja um único objeto.</span><span class="sxs-lookup"><span data-stu-id="5b877-131">Outputs the object in array brackets, even if the input is a single object.</span></span>

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

### <span data-ttu-id="5b877-132">-Compactar</span><span class="sxs-lookup"><span data-stu-id="5b877-132">-Compress</span></span>

<span data-ttu-id="5b877-133">Omite o espaço em branco e a formatação recuada na cadeia de saída.</span><span class="sxs-lookup"><span data-stu-id="5b877-133">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="5b877-134">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="5b877-134">-Depth</span></span>

<span data-ttu-id="5b877-135">Especifica quantos níveis de objetos contidos estão incluídos na representação JSON.</span><span class="sxs-lookup"><span data-stu-id="5b877-135">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="5b877-136">O valor padrão é 2.</span><span class="sxs-lookup"><span data-stu-id="5b877-136">The default value is 2.</span></span> <span data-ttu-id="5b877-137">A partir do PowerShell 7,2, `ConvertTo-Json` emitirá um aviso se o número de níveis em um objeto de entrada exceder esse número.</span><span class="sxs-lookup"><span data-stu-id="5b877-137">As of PowerShell 7.2, `ConvertTo-Json` emits a warning if the number of levels in an input object exceeds this number.</span></span>

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

### <span data-ttu-id="5b877-138">-EnumsAsStrings</span><span class="sxs-lookup"><span data-stu-id="5b877-138">-EnumsAsStrings</span></span>

<span data-ttu-id="5b877-139">Fornece uma opção de serialização alternativa que converte todas as enumerações em sua representação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5b877-139">Provides an alternative serialization option that converts all enumerations to their string representation.</span></span>

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

### <span data-ttu-id="5b877-140">-EscapeHandling</span><span class="sxs-lookup"><span data-stu-id="5b877-140">-EscapeHandling</span></span>

<span data-ttu-id="5b877-141">Controla como determinados caracteres são ignorados na saída JSON resultante.</span><span class="sxs-lookup"><span data-stu-id="5b877-141">Controls how certain characters are escaped in the resulting JSON output.</span></span> <span data-ttu-id="5b877-142">Por padrão, somente caracteres de controle (como nova linha) são ignorados.</span><span class="sxs-lookup"><span data-stu-id="5b877-142">By default, only control characters (like newline) are escaped.</span></span>

<span data-ttu-id="5b877-143">Os valores aceitáveis são:</span><span class="sxs-lookup"><span data-stu-id="5b877-143">Acceptable values are:</span></span>

- <span data-ttu-id="5b877-144">Caracteres de controle somente padrão são de escape.</span><span class="sxs-lookup"><span data-stu-id="5b877-144">Default - Only control characters are escaped.</span></span>
- <span data-ttu-id="5b877-145">EscapeNonAscii-todos os caracteres que não são ASCII e de controle são ignorados.</span><span class="sxs-lookup"><span data-stu-id="5b877-145">EscapeNonAscii - All non-ASCII and control characters are escaped.</span></span>
- <span data-ttu-id="5b877-146">EscapeHtml-HTML ( `<` ,,, `>` `&` `'` , `"` ) e caracteres de controle são ignorados.</span><span class="sxs-lookup"><span data-stu-id="5b877-146">EscapeHtml - HTML (`<`, `>`, `&`, `'`, `"`) and control characters are escaped.</span></span>

<span data-ttu-id="5b877-147">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="5b877-147">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="5b877-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5b877-148">-InputObject</span></span>

<span data-ttu-id="5b877-149">Especifica os objetos para converter em formato JSON.</span><span class="sxs-lookup"><span data-stu-id="5b877-149">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="5b877-150">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="5b877-150">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="5b877-151">Também é possível canalizar um objeto para `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="5b877-151">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="5b877-152">O parâmetro **InputObject** é necessário, mas seu valor pode ser nulo ( `$null` ) ou uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="5b877-152">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="5b877-153">Quando o objeto de entrada é, o não `$null` `ConvertTo-Json` gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5b877-153">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="5b877-154">Quando o objeto de entrada é uma cadeia de caracteres vazia, `ConvertTo-Json` retorna uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="5b877-154">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="5b877-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5b877-155">CommonParameters</span></span>

<span data-ttu-id="5b877-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5b877-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5b877-157">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5b877-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5b877-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5b877-158">INPUTS</span></span>

### <span data-ttu-id="5b877-159">System.Object</span><span class="sxs-lookup"><span data-stu-id="5b877-159">System.Object</span></span>

<span data-ttu-id="5b877-160">Você pode canalizar qualquer objeto para `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="5b877-160">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="5b877-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5b877-161">OUTPUTS</span></span>

### <span data-ttu-id="5b877-162">System.String</span><span class="sxs-lookup"><span data-stu-id="5b877-162">System.String</span></span>

## <span data-ttu-id="5b877-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5b877-163">NOTES</span></span>

<span data-ttu-id="5b877-164">O `ConvertTo-Json` cmdlet é implementado usando [Newtonsoft JSON.net](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="5b877-164">The `ConvertTo-Json` cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

## <span data-ttu-id="5b877-165">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5b877-165">RELATED LINKS</span></span>

<span data-ttu-id="5b877-166">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="5b877-166">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="5b877-167">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="5b877-167">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="5b877-168">Get-Content</span><span class="sxs-lookup"><span data-stu-id="5b877-168">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="5b877-169">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="5b877-169">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="5b877-170">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="5b877-170">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="5b877-171">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="5b877-171">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="5b877-172">NewtonSoft.Jsem. StringEscapeHandling</span><span class="sxs-lookup"><span data-stu-id="5b877-172">NewtonSoft.Json.StringEscapeHandling</span></span>](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
