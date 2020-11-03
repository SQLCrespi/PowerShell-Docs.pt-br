---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: f2159a2de3432aec14fb395b93ed476f349616a8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193852"
---
# <span data-ttu-id="97313-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="97313-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="97313-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="97313-104">SYNOPSIS</span></span>
<span data-ttu-id="97313-105">Converte uma cadeia de caracteres formatada em JSON em um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="97313-105">Converts a JSON-formatted string to a custom object.</span></span>

## <span data-ttu-id="97313-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97313-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="97313-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97313-107">DESCRIPTION</span></span>

<span data-ttu-id="97313-108">O `ConvertFrom-Json` cmdlet converte uma cadeia de caracteres formatada JavaScript Object Notation (JSON) em um objeto **PSCustomObject** personalizado que tem uma propriedade para cada campo na cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="97313-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="97313-109">JSON utilizado comumente por sites da web para fornecer uma representação textual de objetos.</span><span class="sxs-lookup"><span data-stu-id="97313-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="97313-110">O padrão JSON não proíbe o uso que seja proibido com um **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="97313-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject** .</span></span> <span data-ttu-id="97313-111">Por exemplo, se a cadeia de caracteres JSON contiver chaves duplicadas, somente a última chave será usada por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97313-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="97313-112">Consulte outros exemplos abaixo.</span><span class="sxs-lookup"><span data-stu-id="97313-112">See other examples below.</span></span>

<span data-ttu-id="97313-113">Para gerar uma cadeia de caracteres JSON de qualquer objeto, use o `ConvertTo-Json` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97313-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="97313-114">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="97313-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="97313-115">Este cmdlet não dá suporte a JSON com comentários.</span><span class="sxs-lookup"><span data-stu-id="97313-115">This cmdlet doesn't support JSON with comments.</span></span>

## <span data-ttu-id="97313-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="97313-116">EXAMPLES</span></span>

### <span data-ttu-id="97313-117">Exemplo 1: converter um objeto DateTime em um objeto JSON</span><span class="sxs-lookup"><span data-stu-id="97313-117">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="97313-118">Esse comando usa os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto **DateTime** do `Get-Date` cmdlet em um objeto JSON, em seguida, em um **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="97313-118">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject** .</span></span>

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

<span data-ttu-id="97313-119">O exemplo usa o `Select-Object` cmdlet para obter todas as propriedades do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="97313-119">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="97313-120">Ele usa o `ConvertTo-Json` cmdlet para converter o objeto **DateTime** em uma cadeia de caracteres formatada como um objeto JSON e o `ConvertFrom-Json` cmdlet para converter a cadeia de caracteres formatada em JSON em um objeto **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="97313-120">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="97313-121">Exemplo 2: obter cadeias de caracteres JSON de um serviço Web e convertê-las em objetos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="97313-121">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="97313-122">Esse comando usa o `Invoke-WebRequest` cmdlet para obter cadeias de caracteres JSON de um serviço Web e, em seguida, usa o `ConvertFrom-Json` cmdlet para converter o conteúdo JSON em objetos que podem ser gerenciados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97313-122">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="97313-123">Você também pode usar o `Invoke-RestMethod` cmdlet, que converte automaticamente o conteúdo JSON em objetos.</span><span class="sxs-lookup"><span data-stu-id="97313-123">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="97313-124">Exemplo 3: converter uma cadeia de caracteres JSON em um objeto personalizado</span><span class="sxs-lookup"><span data-stu-id="97313-124">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="97313-125">Este exemplo mostra como usar o `ConvertFrom-Json` cmdlet para converter um arquivo JSON em um objeto personalizado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97313-125">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="97313-126">O comando usa Get-Content cmdlet para obter as cadeias de caracteres em um arquivo JSON.</span><span class="sxs-lookup"><span data-stu-id="97313-126">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="97313-127">Em seguida, ele usa o operador de pipeline para enviar a cadeia de caracteres delimitada ao `ConvertFrom-Json` cmdlet, que converte-o em um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="97313-127">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

## <span data-ttu-id="97313-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97313-128">PARAMETERS</span></span>

### <span data-ttu-id="97313-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="97313-129">-InputObject</span></span>

<span data-ttu-id="97313-130">Especifica as cadeias de caracteres JSON a converter em objetos JSON.</span><span class="sxs-lookup"><span data-stu-id="97313-130">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="97313-131">Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia.</span><span class="sxs-lookup"><span data-stu-id="97313-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="97313-132">Você também pode canalizar uma cadeia de caracteres para `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="97313-132">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="97313-133">O parâmetro **InputObject** é obrigatório, mas seu valor pode ser uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="97313-133">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="97313-134">Quando o objeto de entrada é uma cadeia de caracteres vazia, o não `ConvertFrom-Json` gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="97313-134">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="97313-135">O valor **InputObject** não pode ser `$null` .</span><span class="sxs-lookup"><span data-stu-id="97313-135">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="97313-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="97313-136">CommonParameters</span></span>

<span data-ttu-id="97313-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97313-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97313-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="97313-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97313-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="97313-139">INPUTS</span></span>

### <span data-ttu-id="97313-140">System.String</span><span class="sxs-lookup"><span data-stu-id="97313-140">System.String</span></span>

<span data-ttu-id="97313-141">É possível canalizar uma cadeia de caracteres JSON para `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="97313-141">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="97313-142">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="97313-142">OUTPUTS</span></span>

### <span data-ttu-id="97313-143">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="97313-143">PSCustomObject</span></span>

## <span data-ttu-id="97313-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="97313-144">NOTES</span></span>

<span data-ttu-id="97313-145">O `ConvertFrom-Json` cmdlet é implementado usando a [classe JavaScriptSerializer](/dotnet/api/system.web.script.serialization.javascriptserializer).</span><span class="sxs-lookup"><span data-stu-id="97313-145">The `ConvertFrom-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="97313-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="97313-146">RELATED LINKS</span></span>

<span data-ttu-id="97313-147">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="97313-147">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="97313-148">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="97313-148">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="97313-149">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="97313-149">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="97313-150">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="97313-150">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
