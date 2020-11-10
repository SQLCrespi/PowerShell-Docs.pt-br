---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: 0cf439651d3382ce5abf3e5de4812df92cb8492d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389837"
---
# <span data-ttu-id="b8207-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="b8207-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="b8207-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b8207-104">SYNOPSIS</span></span>
<span data-ttu-id="b8207-105">Converte uma cadeia de caracteres formatada em JSON em um objeto personalizado ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b8207-105">Converts a JSON-formatted string to a custom object or a hash table.</span></span>

## <span data-ttu-id="b8207-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8207-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="b8207-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b8207-107">DESCRIPTION</span></span>

<span data-ttu-id="b8207-108">O `ConvertFrom-Json` cmdlet converte uma cadeia de caracteres formatada JavaScript Object Notation (JSON) em um objeto **PSCustomObject** personalizado que tem uma propriedade para cada campo na cadeia de caracteres JSON.</span><span class="sxs-lookup"><span data-stu-id="b8207-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="b8207-109">JSON utilizado comumente por sites da web para fornecer uma representação textual de objetos.</span><span class="sxs-lookup"><span data-stu-id="b8207-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="b8207-110">O padrão JSON não proíbe o uso que seja proibido com um **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="b8207-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="b8207-111">Por exemplo, se a cadeia de caracteres JSON contiver chaves duplicadas, somente a última chave será usada por esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b8207-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="b8207-112">Consulte outros exemplos abaixo.</span><span class="sxs-lookup"><span data-stu-id="b8207-112">See other examples below.</span></span>

<span data-ttu-id="b8207-113">Para gerar uma cadeia de caracteres JSON de qualquer objeto, use o `ConvertTo-Json` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b8207-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="b8207-114">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b8207-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="b8207-115">A partir do PowerShell 6, esse cmdlet dá suporte a JSON com comentários.</span><span class="sxs-lookup"><span data-stu-id="b8207-115">Beginning with PowerShell 6, this cmdlet supports JSON with comments.</span></span> <span data-ttu-id="b8207-116">Os comentários aceitos são iniciados com duas barras "/" ( `//` ).</span><span class="sxs-lookup"><span data-stu-id="b8207-116">Accepted comments are started with two forward slashes (`//`).</span></span> <span data-ttu-id="b8207-117">O comentário não será representado nos dados e poderá ser gravado no arquivo sem corromper os dados ou gerar um erro como fazia no PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="b8207-117">The comment will not be represented in the data and can be written in the file without corrupting the data or throwing an error as it did in PowerShell 5.1.</span></span>

## <span data-ttu-id="b8207-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b8207-118">EXAMPLES</span></span>

### <span data-ttu-id="b8207-119">Exemplo 1: converter um objeto DateTime em um objeto JSON</span><span class="sxs-lookup"><span data-stu-id="b8207-119">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="b8207-120">Esse comando usa os `ConvertTo-Json` `ConvertFrom-Json` cmdlets e para converter um objeto **DateTime** do `Get-Date` cmdlet em um objeto JSON, em seguida, em um **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="b8207-120">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

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

<span data-ttu-id="b8207-121">O exemplo usa o `Select-Object` cmdlet para obter todas as propriedades do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="b8207-121">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="b8207-122">Ele usa o `ConvertTo-Json` cmdlet para converter o objeto **DateTime** em uma cadeia de caracteres formatada como um objeto JSON e o `ConvertFrom-Json` cmdlet para converter a cadeia de caracteres formatada em JSON em um objeto **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="b8207-122">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="b8207-123">Exemplo 2: obter cadeias de caracteres JSON de um serviço Web e convertê-las em objetos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8207-123">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="b8207-124">Esse comando usa o `Invoke-WebRequest` cmdlet para obter cadeias de caracteres JSON de um serviço Web e, em seguida, usa o `ConvertFrom-Json` cmdlet para converter o conteúdo JSON em objetos que podem ser gerenciados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8207-124">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="b8207-125">Você também pode usar o `Invoke-RestMethod` cmdlet, que converte automaticamente o conteúdo JSON em objetos.</span><span class="sxs-lookup"><span data-stu-id="b8207-125">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="b8207-126">Exemplo 3: converter uma cadeia de caracteres JSON em um objeto personalizado</span><span class="sxs-lookup"><span data-stu-id="b8207-126">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="b8207-127">Este exemplo mostra como usar o `ConvertFrom-Json` cmdlet para converter um arquivo JSON em um objeto personalizado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8207-127">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="b8207-128">O comando usa Get-Content cmdlet para obter as cadeias de caracteres em um arquivo JSON.</span><span class="sxs-lookup"><span data-stu-id="b8207-128">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="b8207-129">Em seguida, ele usa o operador de pipeline para enviar a cadeia de caracteres delimitada ao `ConvertFrom-Json` cmdlet, que converte-o em um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="b8207-129">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

### <span data-ttu-id="b8207-130">Exemplo 4: converter uma cadeia de caracteres JSON em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="b8207-130">Example 4: Convert a JSON string to a hash table</span></span>

<span data-ttu-id="b8207-131">Esse comando mostra um exemplo em que a `-AsHashtable` opção pode superar as limitações do comando.</span><span class="sxs-lookup"><span data-stu-id="b8207-131">This command shows an example where the `-AsHashtable` switch can overcome limitations of the command.</span></span>

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

<span data-ttu-id="b8207-132">A cadeia de caracteres JSON contém dois pares chave-valor com chaves que diferem apenas em maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b8207-132">The JSON string contains two key value pairs with keys that differ only in casing.</span></span> <span data-ttu-id="b8207-133">Sem a opção, o comando teria gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="b8207-133">Without the switch, the command would have thrown an error.</span></span>

## <span data-ttu-id="b8207-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8207-134">PARAMETERS</span></span>

### <span data-ttu-id="b8207-135">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="b8207-135">-AsHashtable</span></span>

<span data-ttu-id="b8207-136">Converte o JSON em um objeto de tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b8207-136">Converts the JSON to a hash table object.</span></span> <span data-ttu-id="b8207-137">Essa opção foi introduzida no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="b8207-137">This switch was introduced in PowerShell 6.0.</span></span> <span data-ttu-id="b8207-138">Há vários cenários em que ele pode superar algumas limitações do `ConvertFrom-Json` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b8207-138">There are several scenarios where it can overcome some limitations of the `ConvertFrom-Json` cmdlet.</span></span>

- <span data-ttu-id="b8207-139">Se o JSON contiver uma lista com chaves que diferem apenas em maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b8207-139">If the JSON contains a list with keys that only differ in casing.</span></span> <span data-ttu-id="b8207-140">Sem a opção, essas chaves seriam vistas como chaves idênticas e, portanto, apenas a última seria usada.</span><span class="sxs-lookup"><span data-stu-id="b8207-140">Without the switch, those keys would be seen as identical keys and therefore only the last one would get used.</span></span>
- <span data-ttu-id="b8207-141">Se o JSON contiver uma chave que seja uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="b8207-141">If the JSON contains a key that is an empty string.</span></span> <span data-ttu-id="b8207-142">Sem a opção, o cmdlet geraria um erro, pois um não `PSCustomObject` permite isso, mas uma tabela de hash faz.</span><span class="sxs-lookup"><span data-stu-id="b8207-142">Without the switch, the cmdlet would throw an error since a `PSCustomObject` does not allow for that but a hash table does.</span></span> <span data-ttu-id="b8207-143">Um exemplo de caso de uso onde isso pode ocorrer são `project.lock.json` os arquivos.</span><span class="sxs-lookup"><span data-stu-id="b8207-143">An example use case where this can occurs are `project.lock.json` files.</span></span>
- <span data-ttu-id="b8207-144">As tabelas de hash podem ser processadas mais rapidamente para determinadas estruturas de dados.</span><span class="sxs-lookup"><span data-stu-id="b8207-144">Hash tables can be processed faster for certain data structures.</span></span>

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

### <span data-ttu-id="b8207-145">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="b8207-145">-Depth</span></span>

<span data-ttu-id="b8207-146">Obtém ou define a profundidade máxima que a entrada JSON pode ter.</span><span class="sxs-lookup"><span data-stu-id="b8207-146">Gets or sets the maximum depth the JSON input is allowed to have.</span></span> <span data-ttu-id="b8207-147">Por padrão, é 1024.</span><span class="sxs-lookup"><span data-stu-id="b8207-147">By default, it is 1024.</span></span>

<span data-ttu-id="b8207-148">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="b8207-148">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="b8207-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b8207-149">-InputObject</span></span>

<span data-ttu-id="b8207-150">Especifica as cadeias de caracteres JSON a converter em objetos JSON.</span><span class="sxs-lookup"><span data-stu-id="b8207-150">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="b8207-151">Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia.</span><span class="sxs-lookup"><span data-stu-id="b8207-151">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="b8207-152">Você também pode canalizar uma cadeia de caracteres para `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="b8207-152">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="b8207-153">O parâmetro **InputObject** é obrigatório, mas seu valor pode ser uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="b8207-153">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="b8207-154">Quando o objeto de entrada é uma cadeia de caracteres vazia, o não `ConvertFrom-Json` gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="b8207-154">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="b8207-155">O valor **InputObject** não pode ser `$null` .</span><span class="sxs-lookup"><span data-stu-id="b8207-155">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="b8207-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b8207-156">CommonParameters</span></span>

<span data-ttu-id="b8207-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b8207-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8207-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b8207-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b8207-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b8207-159">INPUTS</span></span>

### <span data-ttu-id="b8207-160">System.String</span><span class="sxs-lookup"><span data-stu-id="b8207-160">System.String</span></span>

<span data-ttu-id="b8207-161">É possível canalizar uma cadeia de caracteres JSON para `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="b8207-161">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="b8207-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b8207-162">OUTPUTS</span></span>

### <span data-ttu-id="b8207-163">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="b8207-163">PSCustomObject</span></span>

### <span data-ttu-id="b8207-164">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="b8207-164">System.Collections.Hashtable</span></span>

## <span data-ttu-id="b8207-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b8207-165">NOTES</span></span>

<span data-ttu-id="b8207-166">Esse cmdlet é implementado usando [Newtonsoft JSON.net](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="b8207-166">This cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

<span data-ttu-id="b8207-167">A partir do PowerShell 6, o `ConvertTo-Json` tenta converter cadeias de caracteres formatadas como carimbos de **Data/** hora em valores DateTime.</span><span class="sxs-lookup"><span data-stu-id="b8207-167">Beginning in PowerShell 6, `ConvertTo-Json` attempts to convert strings formatted as timestamps to **DateTime** values.</span></span> <span data-ttu-id="b8207-168">O valor convertido é uma `[datetime]` instância com um `Kind` conjunto de propriedades da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b8207-168">The converted value is a `[datetime]` instance with a `Kind` property set as follows:</span></span>

- <span data-ttu-id="b8207-169">`Unspecified`, se não houver informações de fuso horário na cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="b8207-169">`Unspecified`, if there is no time zone information in the input string.</span></span>
- <span data-ttu-id="b8207-170">`Utc`, se as informações de fuso horário forem à direita `Z` .</span><span class="sxs-lookup"><span data-stu-id="b8207-170">`Utc`, if the time zone information is a trailing `Z`.</span></span>
- <span data-ttu-id="b8207-171">`Local`, se as informações de fuso horário forem dadas como um _deslocamento_ UTC à direita como `+02:00` .</span><span class="sxs-lookup"><span data-stu-id="b8207-171">`Local`, if the time zone information is given as a trailing UTC _offset_ like `+02:00`.</span></span> <span data-ttu-id="b8207-172">O deslocamento é convertido corretamente no fuso horário configurado do chamador.</span><span class="sxs-lookup"><span data-stu-id="b8207-172">The offset is properly converted to the caller's configured time zone.</span></span> <span data-ttu-id="b8207-173">A formatação de saída padrão não indica o deslocamento de fuso horário original.</span><span class="sxs-lookup"><span data-stu-id="b8207-173">The default output formatting does not indicate the original time zone offset.</span></span>

## <span data-ttu-id="b8207-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b8207-174">RELATED LINKS</span></span>

<span data-ttu-id="b8207-175">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="b8207-175">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="b8207-176">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="b8207-176">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="b8207-177">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="b8207-177">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="b8207-178">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="b8207-178">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
