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
# <span data-ttu-id="2c828-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="2c828-103">ConvertTo-Json</span></span>

## <span data-ttu-id="2c828-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2c828-104">SYNOPSIS</span></span>
<span data-ttu-id="2c828-105">Converte um objeto em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="2c828-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="2c828-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c828-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## <span data-ttu-id="2c828-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2c828-107">DESCRIPTION</span></span>

<span data-ttu-id="2c828-108">O `ConvertTo-Json` cmdlet converte qualquer objeto .net em uma cadeia de caracteres no formato JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="2c828-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="2c828-109">As propriedades são convertidas em nomes de campo, os valores de campo são convertidos em valores de propriedade e os métodos são removidos.</span><span class="sxs-lookup"><span data-stu-id="2c828-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="2c828-110">Você pode usar o `ConvertFrom-Json` cmdlet para converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c828-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="2c828-111">Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.</span><span class="sxs-lookup"><span data-stu-id="2c828-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="2c828-112">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="2c828-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="2c828-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2c828-113">EXAMPLES</span></span>

### <span data-ttu-id="2c828-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2c828-114">Example 1</span></span>

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

<span data-ttu-id="2c828-115">Esse comando usa o `ConvertTo-Json` cmdlet para converter um objeto GregorianCalendar em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="2c828-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="2c828-116">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="2c828-116">Example 2</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="2c828-117">Esse comando mostra o efeito de usar o parâmetro **compress** de `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="2c828-117">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="2c828-118">A compactação afeta apenas a aparência da cadeia de caracteres, não sua validade.</span><span class="sxs-lookup"><span data-stu-id="2c828-118">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="2c828-119">Exemplo 3:</span><span class="sxs-lookup"><span data-stu-id="2c828-119">Example 3</span></span>

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

<span data-ttu-id="2c828-120">Este exemplo usa o `ConvertTo-Json` cmdlet para converter um objeto **System. DateTime** do `Get-Date` cmdlet em uma cadeia de caracteres formatada em JSON.</span><span class="sxs-lookup"><span data-stu-id="2c828-120">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="2c828-121">O comando usa o `Select-Object` cmdlet para obter todos ( `*` ) das propriedades do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="2c828-121">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="2c828-122">A saída mostra a cadeia de caracteres JSON `ConvertTo-Json` retornada.</span><span class="sxs-lookup"><span data-stu-id="2c828-122">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="2c828-123">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="2c828-123">Example 4</span></span>

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

<span data-ttu-id="2c828-124">Este exemplo mostra como usar os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto em uma cadeia de caracteres JSON e um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="2c828-124">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="2c828-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c828-125">PARAMETERS</span></span>

### <span data-ttu-id="2c828-126">-Compactar</span><span class="sxs-lookup"><span data-stu-id="2c828-126">-Compress</span></span>

<span data-ttu-id="2c828-127">Omite o espaço em branco e a formatação recuada na cadeia de saída.</span><span class="sxs-lookup"><span data-stu-id="2c828-127">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="2c828-128">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="2c828-128">-Depth</span></span>

<span data-ttu-id="2c828-129">Especifica quantos níveis de objetos contidos estão incluídos na representação JSON.</span><span class="sxs-lookup"><span data-stu-id="2c828-129">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="2c828-130">O valor padrão é 2.</span><span class="sxs-lookup"><span data-stu-id="2c828-130">The default value is 2.</span></span>

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

### <span data-ttu-id="2c828-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2c828-131">-InputObject</span></span>

<span data-ttu-id="2c828-132">Especifica os objetos para converter em formato JSON.</span><span class="sxs-lookup"><span data-stu-id="2c828-132">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="2c828-133">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="2c828-133">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="2c828-134">Também é possível canalizar um objeto para `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="2c828-134">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="2c828-135">O parâmetro **InputObject** é necessário, mas seu valor pode ser nulo ( `$null` ) ou uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="2c828-135">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="2c828-136">Quando o objeto de entrada é, o não `$null` `ConvertTo-Json` gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="2c828-136">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="2c828-137">Quando o objeto de entrada é uma cadeia de caracteres vazia, `ConvertTo-Json` retorna uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="2c828-137">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="2c828-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2c828-138">CommonParameters</span></span>

<span data-ttu-id="2c828-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2c828-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c828-140">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2c828-140">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2c828-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2c828-141">INPUTS</span></span>

### <span data-ttu-id="2c828-142">System.Object</span><span class="sxs-lookup"><span data-stu-id="2c828-142">System.Object</span></span>

<span data-ttu-id="2c828-143">Você pode canalizar qualquer objeto para `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="2c828-143">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="2c828-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2c828-144">OUTPUTS</span></span>

### <span data-ttu-id="2c828-145">System.String</span><span class="sxs-lookup"><span data-stu-id="2c828-145">System.String</span></span>

## <span data-ttu-id="2c828-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2c828-146">NOTES</span></span>

<span data-ttu-id="2c828-147">O `ConvertTo-Json` cmdlet é implementado usando a [classe JavaScriptSerializer](/dotnet/api/system.web.script.serialization.javascriptserializer).</span><span class="sxs-lookup"><span data-stu-id="2c828-147">The `ConvertTo-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="2c828-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2c828-148">RELATED LINKS</span></span>

<span data-ttu-id="2c828-149">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="2c828-149">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="2c828-150">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="2c828-150">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="2c828-151">Get-Content</span><span class="sxs-lookup"><span data-stu-id="2c828-151">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="2c828-152">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="2c828-152">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="2c828-153">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="2c828-153">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="2c828-154">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="2c828-154">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
