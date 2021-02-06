---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: 525b123d48b0f88ca3eef85a3f95cc303a981ca3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603352"
---
# <span data-ttu-id="20d87-102">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="20d87-102">ConvertFrom-Json</span></span>

## <span data-ttu-id="20d87-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="20d87-103">SYNOPSIS</span></span>
<span data-ttu-id="20d87-104">Converte uma cadeia de caracteres formatada em JSON em um objeto personalizado ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="20d87-104">Converts a JSON-formatted string to a custom object or a hash table.</span></span>

## <span data-ttu-id="20d87-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20d87-105">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="20d87-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20d87-106">DESCRIPTION</span></span>

<span data-ttu-id="20d87-107">O `ConvertFrom-Json` cmdlet converte uma cadeia de caracteres formatada JavaScript Object Notation (JSON) em um objeto **PSCustomObject** personalizado que tem uma propriedade para cada campo na cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="20d87-107">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="20d87-108">JSON utilizado comumente por sites da web para fornecer uma representação textual de objetos.</span><span class="sxs-lookup"><span data-stu-id="20d87-108">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="20d87-109">O padrão JSON não proíbe o uso que seja proibido com um **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="20d87-109">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="20d87-110">Por exemplo, se a cadeia de caracteres JSON contiver chaves duplicadas, somente a última chave será usada por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="20d87-110">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="20d87-111">Consulte outros exemplos abaixo.</span><span class="sxs-lookup"><span data-stu-id="20d87-111">See other examples below.</span></span>

<span data-ttu-id="20d87-112">Para gerar uma cadeia de caracteres JSON de qualquer objeto, use o `ConvertTo-Json` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="20d87-112">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="20d87-113">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="20d87-113">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="20d87-114">A partir do PowerShell 6, esse cmdlet dá suporte a JSON com comentários.</span><span class="sxs-lookup"><span data-stu-id="20d87-114">Beginning with PowerShell 6, this cmdlet supports JSON with comments.</span></span> <span data-ttu-id="20d87-115">Os comentários aceitos são iniciados com duas barras "/" ( `//` ).</span><span class="sxs-lookup"><span data-stu-id="20d87-115">Accepted comments are started with two forward slashes (`//`).</span></span> <span data-ttu-id="20d87-116">O comentário não será representado nos dados e poderá ser gravado no arquivo sem corromper os dados ou gerar um erro como fazia no PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="20d87-116">The comment will not be represented in the data and can be written in the file without corrupting the data or throwing an error as it did in PowerShell 5.1.</span></span>

## <span data-ttu-id="20d87-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="20d87-117">EXAMPLES</span></span>

### <span data-ttu-id="20d87-118">Exemplo 1: converter um objeto DateTime em um objeto JSON</span><span class="sxs-lookup"><span data-stu-id="20d87-118">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="20d87-119">Esse comando usa os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto **DateTime** do `Get-Date` cmdlet em um objeto JSON, em seguida, em um **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="20d87-119">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

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

<span data-ttu-id="20d87-120">O exemplo usa o `Select-Object` cmdlet para obter todas as propriedades do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="20d87-120">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="20d87-121">Ele usa o `ConvertTo-Json` cmdlet para converter o objeto **DateTime** em uma cadeia de caracteres formatada como um objeto JSON e o `ConvertFrom-Json` cmdlet para converter a cadeia de caracteres formatada em JSON em um objeto **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="20d87-121">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="20d87-122">Exemplo 2: obter cadeias de caracteres JSON de um serviço Web e convertê-las em objetos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="20d87-122">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="20d87-123">Esse comando usa o `Invoke-WebRequest` cmdlet para obter cadeias de caracteres JSON de um serviço Web e, em seguida, usa o `ConvertFrom-Json` cmdlet para converter o conteúdo JSON em objetos que podem ser gerenciados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20d87-123">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="20d87-124">Você também pode usar o `Invoke-RestMethod` cmdlet, que converte automaticamente o conteúdo JSON em objetos.</span><span class="sxs-lookup"><span data-stu-id="20d87-124">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="20d87-125">Exemplo 3: converter uma cadeia de caracteres JSON em um objeto personalizado</span><span class="sxs-lookup"><span data-stu-id="20d87-125">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="20d87-126">Este exemplo mostra como usar o `ConvertFrom-Json` cmdlet para converter um arquivo JSON em um objeto personalizado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20d87-126">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="20d87-127">O comando usa Get-Content cmdlet para obter as cadeias de caracteres em um arquivo JSON.</span><span class="sxs-lookup"><span data-stu-id="20d87-127">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="20d87-128">Em seguida, ele usa o operador de pipeline para enviar a cadeia de caracteres delimitada ao `ConvertFrom-Json` cmdlet, que converte-o em um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="20d87-128">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

### <span data-ttu-id="20d87-129">Exemplo 4: converter uma cadeia de caracteres JSON em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="20d87-129">Example 4: Convert a JSON string to a hash table</span></span>

<span data-ttu-id="20d87-130">Esse comando mostra um exemplo em que a `-AsHashtable` opção pode superar as limitações do comando.</span><span class="sxs-lookup"><span data-stu-id="20d87-130">This command shows an example where the `-AsHashtable` switch can overcome limitations of the command.</span></span>

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

<span data-ttu-id="20d87-131">A cadeia de caracteres JSON contém dois pares chave-valor com chaves que diferem apenas em maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="20d87-131">The JSON string contains two key value pairs with keys that differ only in casing.</span></span> <span data-ttu-id="20d87-132">Sem a opção, o comando teria gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="20d87-132">Without the switch, the command would have thrown an error.</span></span>

### <span data-ttu-id="20d87-133">Exemplo 5: viagem de ida e volta de uma única matriz de elemento</span><span class="sxs-lookup"><span data-stu-id="20d87-133">Example 5: Round-trip a single element array</span></span>

<span data-ttu-id="20d87-134">Esse comando mostra um exemplo em que a `-NoEnumerate` opção é usada para fazer ida e volta de uma matriz JSON de um único elemento.</span><span class="sxs-lookup"><span data-stu-id="20d87-134">This command shows an example where the `-NoEnumerate` switch is used to round-trip a single element JSON array.</span></span>

```powershell
Write-Output "With -NoEnumerate: $('[1]' | ConvertFrom-Json -NoEnumerate | ConvertTo-Json -Compress)"
Write-Output "Without -NoEnumerate: $('[1]' | ConvertFrom-Json | ConvertTo-Json -Compress)"
```

```Output
With -NoEnumerate: [1]
Without -NoEnumerate: 1
```

<span data-ttu-id="20d87-135">A cadeia de caracteres JSON contém uma matriz com um único elemento.</span><span class="sxs-lookup"><span data-stu-id="20d87-135">The JSON string contains an array with a single element.</span></span> <span data-ttu-id="20d87-136">Sem a opção, converter o JSON em um PSObject e, em seguida, convertê-lo novamente com os `ConvertTo-Json` resultados do comando em um único inteiro.</span><span class="sxs-lookup"><span data-stu-id="20d87-136">Without the switch, converting the JSON to a PSObject and then converting it back with the `ConvertTo-Json` command results in a single integer.</span></span>

## <span data-ttu-id="20d87-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20d87-137">PARAMETERS</span></span>

### <span data-ttu-id="20d87-138">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="20d87-138">-AsHashtable</span></span>

<span data-ttu-id="20d87-139">Converte o JSON em um objeto de tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="20d87-139">Converts the JSON to a hash table object.</span></span> <span data-ttu-id="20d87-140">Essa opção foi introduzida no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="20d87-140">This switch was introduced in PowerShell 6.0.</span></span> <span data-ttu-id="20d87-141">Há vários cenários em que ele pode superar algumas limitações do `ConvertFrom-Json` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="20d87-141">There are several scenarios where it can overcome some limitations of the `ConvertFrom-Json` cmdlet.</span></span>

- <span data-ttu-id="20d87-142">Se o JSON contiver uma lista com chaves que diferem apenas em maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="20d87-142">If the JSON contains a list with keys that only differ in casing.</span></span> <span data-ttu-id="20d87-143">Sem a opção, essas chaves seriam vistas como chaves idênticas e, portanto, apenas a última seria usada.</span><span class="sxs-lookup"><span data-stu-id="20d87-143">Without the switch, those keys would be seen as identical keys and therefore only the last one would get used.</span></span>
- <span data-ttu-id="20d87-144">Se o JSON contiver uma chave que seja uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="20d87-144">If the JSON contains a key that is an empty string.</span></span> <span data-ttu-id="20d87-145">Sem a opção, o cmdlet geraria um erro, pois um não `PSCustomObject` permite isso, mas uma tabela de hash faz.</span><span class="sxs-lookup"><span data-stu-id="20d87-145">Without the switch, the cmdlet would throw an error since a `PSCustomObject` does not allow for that but a hash table does.</span></span> <span data-ttu-id="20d87-146">Um exemplo de caso de uso onde isso pode ocorrer são `project.lock.json` os arquivos.</span><span class="sxs-lookup"><span data-stu-id="20d87-146">An example use case where this can occurs are `project.lock.json` files.</span></span>
- <span data-ttu-id="20d87-147">As tabelas de hash podem ser processadas mais rapidamente para determinadas estruturas de dados.</span><span class="sxs-lookup"><span data-stu-id="20d87-147">Hash tables can be processed faster for certain data structures.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="20d87-148">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="20d87-148">-Depth</span></span>

<span data-ttu-id="20d87-149">Obtém ou define a profundidade máxima que a entrada JSON pode ter.</span><span class="sxs-lookup"><span data-stu-id="20d87-149">Gets or sets the maximum depth the JSON input is allowed to have.</span></span> <span data-ttu-id="20d87-150">Por padrão, é 1024.</span><span class="sxs-lookup"><span data-stu-id="20d87-150">By default, it is 1024.</span></span>

<span data-ttu-id="20d87-151">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="20d87-151">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="20d87-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="20d87-152">-InputObject</span></span>

<span data-ttu-id="20d87-153">Especifica as cadeias de caracteres JSON a converter em objetos JSON.</span><span class="sxs-lookup"><span data-stu-id="20d87-153">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="20d87-154">Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia.</span><span class="sxs-lookup"><span data-stu-id="20d87-154">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="20d87-155">Você também pode canalizar uma cadeia de caracteres para `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="20d87-155">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="20d87-156">O parâmetro **InputObject** é obrigatório, mas seu valor pode ser uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="20d87-156">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="20d87-157">Quando o objeto de entrada é uma cadeia de caracteres vazia, o não `ConvertFrom-Json` gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="20d87-157">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="20d87-158">O valor **InputObject** não pode ser `$null` .</span><span class="sxs-lookup"><span data-stu-id="20d87-158">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="20d87-159">-Noenumerate</span><span class="sxs-lookup"><span data-stu-id="20d87-159">-NoEnumerate</span></span>

<span data-ttu-id="20d87-160">Especifica que a saída não é enumerada.</span><span class="sxs-lookup"><span data-stu-id="20d87-160">Specifies that output is not enumerated.</span></span>

<span data-ttu-id="20d87-161">Definir esse parâmetro faz com que as matrizes sejam enviadas como um único objeto em vez de enviar cada elemento separadamente.</span><span class="sxs-lookup"><span data-stu-id="20d87-161">Setting this parameter causes arrays to be sent as a single object instead of sending every element separately.</span></span> <span data-ttu-id="20d87-162">Isso garante que o JSON possa ser arredondado via `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="20d87-162">This guarantees that JSON can be round-tripped via `ConvertTo-Json`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="20d87-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20d87-163">CommonParameters</span></span>

<span data-ttu-id="20d87-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="20d87-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20d87-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="20d87-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20d87-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="20d87-166">INPUTS</span></span>

### <span data-ttu-id="20d87-167">System.String</span><span class="sxs-lookup"><span data-stu-id="20d87-167">System.String</span></span>

<span data-ttu-id="20d87-168">É possível canalizar uma cadeia de caracteres JSON para `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="20d87-168">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="20d87-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="20d87-169">OUTPUTS</span></span>

### <span data-ttu-id="20d87-170">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="20d87-170">PSCustomObject</span></span>

### <span data-ttu-id="20d87-171">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="20d87-171">System.Collections.Hashtable</span></span>

## <span data-ttu-id="20d87-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="20d87-172">NOTES</span></span>

<span data-ttu-id="20d87-173">Esse cmdlet é implementado usando [Newtonsoft JSON.net](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="20d87-173">This cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

<span data-ttu-id="20d87-174">A partir do PowerShell 6, o `ConvertTo-Json` tenta converter cadeias de caracteres formatadas como carimbos de **Data/** hora em valores DateTime.</span><span class="sxs-lookup"><span data-stu-id="20d87-174">Beginning in PowerShell 6, `ConvertTo-Json` attempts to convert strings formatted as timestamps to **DateTime** values.</span></span> <span data-ttu-id="20d87-175">O valor convertido é uma `[datetime]` instância com um `Kind` conjunto de propriedades da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="20d87-175">The converted value is a `[datetime]` instance with a `Kind` property set as follows:</span></span>

- <span data-ttu-id="20d87-176">`Unspecified`, se não houver informações de fuso horário na cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="20d87-176">`Unspecified`, if there is no time zone information in the input string.</span></span>
- <span data-ttu-id="20d87-177">`Utc`, se as informações de fuso horário forem à direita `Z` .</span><span class="sxs-lookup"><span data-stu-id="20d87-177">`Utc`, if the time zone information is a trailing `Z`.</span></span>
- <span data-ttu-id="20d87-178">`Local`, se as informações de fuso horário forem dadas como um _deslocamento_ UTC à direita como `+02:00` .</span><span class="sxs-lookup"><span data-stu-id="20d87-178">`Local`, if the time zone information is given as a trailing UTC _offset_ like `+02:00`.</span></span> <span data-ttu-id="20d87-179">O deslocamento é convertido corretamente no fuso horário configurado do chamador.</span><span class="sxs-lookup"><span data-stu-id="20d87-179">The offset is properly converted to the caller's configured time zone.</span></span> <span data-ttu-id="20d87-180">A formatação de saída padrão não indica o deslocamento de fuso horário original.</span><span class="sxs-lookup"><span data-stu-id="20d87-180">The default output formatting does not indicate the original time zone offset.</span></span>

## <span data-ttu-id="20d87-181">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="20d87-181">RELATED LINKS</span></span>

<span data-ttu-id="20d87-182">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="20d87-182">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="20d87-183">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="20d87-183">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="20d87-184">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="20d87-184">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="20d87-185">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="20d87-185">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
