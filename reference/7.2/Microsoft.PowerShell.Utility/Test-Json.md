---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: a29eab449e567f78d1e54a6716ca91d87aa08405
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596380"
---
# <span data-ttu-id="db58d-102">Test-Json</span><span class="sxs-lookup"><span data-stu-id="db58d-102">Test-Json</span></span>

## <span data-ttu-id="db58d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="db58d-103">SYNOPSIS</span></span>
<span data-ttu-id="db58d-104">Testa se uma cadeia de caracteres é um documento JSON válido</span><span class="sxs-lookup"><span data-stu-id="db58d-104">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="db58d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="db58d-105">SYNTAX</span></span>

### <span data-ttu-id="db58d-106">__AllParameterSets (padrão)</span><span class="sxs-lookup"><span data-stu-id="db58d-106">__AllParameterSets (Default)</span></span>
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### <span data-ttu-id="db58d-107">Esquemastring</span><span class="sxs-lookup"><span data-stu-id="db58d-107">SchemaString</span></span>
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### <span data-ttu-id="db58d-108">Esquema de esquemas</span><span class="sxs-lookup"><span data-stu-id="db58d-108">SchemaFile</span></span>
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## <span data-ttu-id="db58d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="db58d-109">DESCRIPTION</span></span>

<span data-ttu-id="db58d-110">O `Test-Json` cmdlet testa se uma cadeia de caracteres é um documento JavaScript Object Notation (JSON) válido e pode, opcionalmente, verificar esse documento JSON em relação a um esquema fornecido.</span><span class="sxs-lookup"><span data-stu-id="db58d-110">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="db58d-111">A cadeia de caracteres verificada pode ser usada com o `ConvertFrom-Json` cmdlet converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell ou enviado a outro programa ou serviço Web que acessa a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="db58d-111">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="db58d-112">Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.</span><span class="sxs-lookup"><span data-stu-id="db58d-112">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="db58d-113">Esse cmdlet foi introduzido no PowerShell 6,1</span><span class="sxs-lookup"><span data-stu-id="db58d-113">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="db58d-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="db58d-114">EXAMPLES</span></span>

### <span data-ttu-id="db58d-115">Exemplo 1: testar se um objeto é um JSON válido</span><span class="sxs-lookup"><span data-stu-id="db58d-115">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="db58d-116">Este exemplo testa se a cadeia de caracteres de entrada é um documento JSON válido.</span><span class="sxs-lookup"><span data-stu-id="db58d-116">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="db58d-117">Exemplo 2: testar um objeto em relação a um esquema fornecido</span><span class="sxs-lookup"><span data-stu-id="db58d-117">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="db58d-118">Este exemplo usa uma cadeia de caracteres que contém um esquema JSON e o compara a uma cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="db58d-118">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="db58d-119">Neste exemplo, obtemos um erro porque o esquema espera um inteiro para a **idade** , mas a entrada JSON que testamos usa um valor de cadeia de caracteres em vez disso.</span><span class="sxs-lookup"><span data-stu-id="db58d-119">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="db58d-120">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="db58d-120">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

### <span data-ttu-id="db58d-121">Exemplo 3: testar um objeto em relação a um esquema do arquivo</span><span class="sxs-lookup"><span data-stu-id="db58d-121">Example 3: Test an object against a schema from file</span></span>

<span data-ttu-id="db58d-122">O esquema JSON pode fazer referência a definições usando a `$ref` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="db58d-122">JSON schema can reference definitions using `$ref` keyword.</span></span> <span data-ttu-id="db58d-123">O `$ref` pode resolver para um URI que faz referência a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="db58d-123">The `$ref` can resolve to a URI that references another file.</span></span> <span data-ttu-id="db58d-124">O `SchemaFile` parâmetro aceita o caminho literal para o arquivo de esquema JSON e permite que os arquivos JSON sejam validados em relação a tais esquemas.</span><span class="sxs-lookup"><span data-stu-id="db58d-124">The `SchemaFile` parameter accepts literal path to the JSON schema file and allows JSON files to be validated against such schemas.</span></span>

<span data-ttu-id="db58d-125">Neste exemplo, temos um `schema.json` arquivo que faz referência a `definitions.json` .</span><span class="sxs-lookup"><span data-stu-id="db58d-125">In this example we have `schema.json` file which references `definitions.json`.</span></span>

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

<span data-ttu-id="db58d-126">Para obter mais informações, consulte [Estruturando um esquema complexo](https://json-schema.org/understanding-json-schema/structuring.html).</span><span class="sxs-lookup"><span data-stu-id="db58d-126">For more information, see [Structuring a complex schema](https://json-schema.org/understanding-json-schema/structuring.html).</span></span>

## <span data-ttu-id="db58d-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="db58d-127">PARAMETERS</span></span>

### <span data-ttu-id="db58d-128">-JSON</span><span class="sxs-lookup"><span data-stu-id="db58d-128">-Json</span></span>

<span data-ttu-id="db58d-129">Especifica a cadeia de caracteres JSON para testar a validade.</span><span class="sxs-lookup"><span data-stu-id="db58d-129">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="db58d-130">Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia.</span><span class="sxs-lookup"><span data-stu-id="db58d-130">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="db58d-131">Você também pode canalizar uma cadeia de caracteres para `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="db58d-131">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="db58d-132">O parâmetro **JSON** é necessário.</span><span class="sxs-lookup"><span data-stu-id="db58d-132">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="db58d-133">-Esquema</span><span class="sxs-lookup"><span data-stu-id="db58d-133">-Schema</span></span>

<span data-ttu-id="db58d-134">Especifica um esquema para validar a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="db58d-134">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="db58d-135">Se for passado, `Test-Json` validará que a entrada JSON está de acordo com a especificação especificada pelo parâmetro de **esquema** e retornará `$True` somente se a entrada estiver em conformidade com o esquema fornecido.</span><span class="sxs-lookup"><span data-stu-id="db58d-135">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="db58d-136">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="db58d-136">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

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

### <span data-ttu-id="db58d-137">-Esquema de</span><span class="sxs-lookup"><span data-stu-id="db58d-137">-SchemaFile</span></span>

<span data-ttu-id="db58d-138">Especifica um arquivo de esquema usado para validar a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="db58d-138">Specifies a schema file used to validate the JSON input.</span></span> <span data-ttu-id="db58d-139">Quando usado, o `Test-Json` retorna `$True` somente se a entrada JSON estiver em conformidade com o esquema definido no arquivo especificado pelo parâmetro **SchemaFile** .</span><span class="sxs-lookup"><span data-stu-id="db58d-139">When used, the `Test-Json` returns `$True` only if the JSON input conforms to the Schema defined in the file specified by the **SchemaFile** parameter.</span></span>

<span data-ttu-id="db58d-140">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="db58d-140">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

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

### <span data-ttu-id="db58d-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="db58d-141">CommonParameters</span></span>

<span data-ttu-id="db58d-142">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="db58d-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="db58d-143">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="db58d-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="db58d-144">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="db58d-144">INPUTS</span></span>

### <span data-ttu-id="db58d-145">System.String</span><span class="sxs-lookup"><span data-stu-id="db58d-145">System.String</span></span>

<span data-ttu-id="db58d-146">É possível canalizar uma cadeia de caracteres JSON para `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="db58d-146">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="db58d-147">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="db58d-147">OUTPUTS</span></span>

### <span data-ttu-id="db58d-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="db58d-148">Boolean</span></span>

## <span data-ttu-id="db58d-149">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="db58d-149">NOTES</span></span>

<span data-ttu-id="db58d-150">O `Test-Json` cmdlet é implementado usando a [classe NJsonSchema](https://github.com/RSuter/NJsonSchema).</span><span class="sxs-lookup"><span data-stu-id="db58d-150">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="db58d-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="db58d-151">RELATED LINKS</span></span>

<span data-ttu-id="db58d-152">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="db58d-152">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="db58d-153">Detalhes adicionais do esquema JSON</span><span class="sxs-lookup"><span data-stu-id="db58d-153">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="db58d-154">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="db58d-154">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="db58d-155">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="db58d-155">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="db58d-156">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="db58d-156">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
