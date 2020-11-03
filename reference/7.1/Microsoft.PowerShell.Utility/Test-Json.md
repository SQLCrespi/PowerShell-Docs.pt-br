---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 79cf0d9a8107cbf843eba5c58e4b4e9ad30ad285
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193254"
---
# <span data-ttu-id="32243-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="32243-103">Test-Json</span></span>

## <span data-ttu-id="32243-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="32243-104">SYNOPSIS</span></span>
<span data-ttu-id="32243-105">Testa se uma cadeia de caracteres é um documento JSON válido</span><span class="sxs-lookup"><span data-stu-id="32243-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="32243-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32243-106">SYNTAX</span></span>

### <span data-ttu-id="32243-107">__AllParameterSets (padrão)</span><span class="sxs-lookup"><span data-stu-id="32243-107">__AllParameterSets (Default)</span></span>
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### <span data-ttu-id="32243-108">Esquemastring</span><span class="sxs-lookup"><span data-stu-id="32243-108">SchemaString</span></span>
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### <span data-ttu-id="32243-109">Esquema de esquemas</span><span class="sxs-lookup"><span data-stu-id="32243-109">SchemaFile</span></span>
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## <span data-ttu-id="32243-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32243-110">DESCRIPTION</span></span>

<span data-ttu-id="32243-111">O `Test-Json` cmdlet testa se uma cadeia de caracteres é um documento JavaScript Object Notation (JSON) válido e pode, opcionalmente, verificar esse documento JSON em relação a um esquema fornecido.</span><span class="sxs-lookup"><span data-stu-id="32243-111">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="32243-112">A cadeia de caracteres verificada pode ser usada com o `ConvertFrom-Json` cmdlet converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell ou enviado a outro programa ou serviço Web que acessa a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="32243-112">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="32243-113">Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.</span><span class="sxs-lookup"><span data-stu-id="32243-113">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="32243-114">Esse cmdlet foi introduzido no PowerShell 6,1</span><span class="sxs-lookup"><span data-stu-id="32243-114">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="32243-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="32243-115">EXAMPLES</span></span>

### <span data-ttu-id="32243-116">Exemplo 1: testar se um objeto é um JSON válido</span><span class="sxs-lookup"><span data-stu-id="32243-116">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="32243-117">Este exemplo testa se a cadeia de caracteres de entrada é um documento JSON válido.</span><span class="sxs-lookup"><span data-stu-id="32243-117">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="32243-118">Exemplo 2: testar um objeto em relação a um esquema fornecido</span><span class="sxs-lookup"><span data-stu-id="32243-118">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="32243-119">Este exemplo usa uma cadeia de caracteres que contém um esquema JSON e o compara a uma cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="32243-119">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

```powershell
$schema = @'
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "name",
    "age"
  ],
  "properties": {
    "name": {
      "$id": "#/properties/name",
      "type": "string",
      "title": "The Name Schema",
      "default": "",
      "examples": [
        "Ashley"
      ],
      "pattern": "^(.*)$"
    },
    "age": {
      "$id": "#/properties/age",
      "type": "integer",
      "title": "The Age Schema",
      "default": 0,
      "examples": [
        25
      ]
    }
  }
}
'@
"{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
```

```Output
Test-Json : IntegerExpected: #/age
At line:1 char:37
+ "{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
+                                     ~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (:) [Test-Json], Exception
+ FullyQualifiedErrorId : InvalidJsonAgainstSchema,Microsoft.PowerShell.Commands.TestJsonCommand
False
```

<span data-ttu-id="32243-120">Neste exemplo, obtemos um erro porque o esquema espera um inteiro para a **idade** , mas a entrada JSON que testamos usa um valor de cadeia de caracteres em vez disso.</span><span class="sxs-lookup"><span data-stu-id="32243-120">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="32243-121">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="32243-121">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

### <span data-ttu-id="32243-122">Exemplo 3: testar um objeto em relação a um esquema do arquivo</span><span class="sxs-lookup"><span data-stu-id="32243-122">Example 3: Test an object against a schema from file</span></span>

<span data-ttu-id="32243-123">O esquema JSON pode fazer referência a definições usando a `$ref` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="32243-123">JSON schema can reference definitions using `$ref` keyword.</span></span> <span data-ttu-id="32243-124">O `$ref` pode resolver para um URI que faz referência a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="32243-124">The `$ref` can resolve to a URI that references another file.</span></span> <span data-ttu-id="32243-125">O `SchemaFile` parâmetro aceita o caminho literal para o arquivo de esquema JSON e permite que os arquivos JSON sejam validados em relação a tais esquemas.</span><span class="sxs-lookup"><span data-stu-id="32243-125">The `SchemaFile` parameter accepts literal path to the JSON schema file and allows JSON files to be validated against such schemas.</span></span>

<span data-ttu-id="32243-126">Neste exemplo, temos um `schema.json` arquivo que faz referência a `definitions.json` .</span><span class="sxs-lookup"><span data-stu-id="32243-126">In this example we have `schema.json` file which references `definitions.json`.</span></span>

```powershell
PS> Get-Content schema.json

{
  "description":"A person",
  "type":"object",
  "properties":{
    "name":{
      "$ref":"definitions.json#/definitions/name"
    },
    "hobbies":{
      "$ref":"definitions.json#/definitions/hobbies"
    }
  }
}

PS> Get-Content definitions.json

{
  "definitions":{
    "name":{
      "type":"string"
    },
    "hobbies":{
      "type":"array",
      "items":{
        "type":"string"
      }
    }
  }
}

'{"name": "James", "hobbies": [".NET", "Blogging"]}' | Test-Json -SchemaFile 'schema.json'
```

```Output
True
```

<span data-ttu-id="32243-127">Para obter mais informações, consulte [Estruturando um esquema complexo](https://json-schema.org/understanding-json-schema/structuring.html).</span><span class="sxs-lookup"><span data-stu-id="32243-127">For more information, see [Structuring a complex schema](https://json-schema.org/understanding-json-schema/structuring.html).</span></span>

## <span data-ttu-id="32243-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32243-128">PARAMETERS</span></span>

### <span data-ttu-id="32243-129">-JSON</span><span class="sxs-lookup"><span data-stu-id="32243-129">-Json</span></span>

<span data-ttu-id="32243-130">Especifica a cadeia de caracteres JSON para testar a validade.</span><span class="sxs-lookup"><span data-stu-id="32243-130">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="32243-131">Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia.</span><span class="sxs-lookup"><span data-stu-id="32243-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="32243-132">Você também pode canalizar uma cadeia de caracteres para `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="32243-132">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="32243-133">O parâmetro **JSON** é necessário.</span><span class="sxs-lookup"><span data-stu-id="32243-133">The **Json** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="32243-134">-Esquema</span><span class="sxs-lookup"><span data-stu-id="32243-134">-Schema</span></span>

<span data-ttu-id="32243-135">Especifica um esquema para validar a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="32243-135">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="32243-136">Se for passado, `Test-Json` validará que a entrada JSON está de acordo com a especificação especificada pelo parâmetro de **esquema** e retornará `$True` somente se a entrada estiver em conformidade com o esquema fornecido.</span><span class="sxs-lookup"><span data-stu-id="32243-136">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="32243-137">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="32243-137">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaString
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32243-138">-Esquema de</span><span class="sxs-lookup"><span data-stu-id="32243-138">-SchemaFile</span></span>

<span data-ttu-id="32243-139">Especifica um arquivo de esquema usado para validar a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="32243-139">Specifies a schema file used to validate the JSON input.</span></span> <span data-ttu-id="32243-140">Quando usado, o `Test-Json` retorna `$True` somente se a entrada JSON estiver em conformidade com o esquema definido no arquivo especificado pelo parâmetro **SchemaFile** .</span><span class="sxs-lookup"><span data-stu-id="32243-140">When used, the `Test-Json` returns `$True` only if the JSON input conforms to the Schema defined in the file specified by the **SchemaFile** parameter.</span></span>

<span data-ttu-id="32243-141">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="32243-141">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32243-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32243-142">CommonParameters</span></span>

<span data-ttu-id="32243-143">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="32243-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32243-144">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="32243-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32243-145">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="32243-145">INPUTS</span></span>

### <span data-ttu-id="32243-146">System.String</span><span class="sxs-lookup"><span data-stu-id="32243-146">System.String</span></span>

<span data-ttu-id="32243-147">É possível canalizar uma cadeia de caracteres JSON para `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="32243-147">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="32243-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="32243-148">OUTPUTS</span></span>

### <span data-ttu-id="32243-149">Booliano</span><span class="sxs-lookup"><span data-stu-id="32243-149">Boolean</span></span>

## <span data-ttu-id="32243-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="32243-150">NOTES</span></span>

<span data-ttu-id="32243-151">O `Test-Json` cmdlet é implementado usando a [classe NJsonSchema](https://github.com/RSuter/NJsonSchema).</span><span class="sxs-lookup"><span data-stu-id="32243-151">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="32243-152">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="32243-152">RELATED LINKS</span></span>

<span data-ttu-id="32243-153">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="32243-153">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="32243-154">Detalhes adicionais do esquema JSON</span><span class="sxs-lookup"><span data-stu-id="32243-154">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="32243-155">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="32243-155">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="32243-156">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="32243-156">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="32243-157">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="32243-157">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
