---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: 618e00d8db5eadfa8658203ef435a23cfea25be3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194367"
---
# <span data-ttu-id="130fc-103">Test-Json</span><span class="sxs-lookup"><span data-stu-id="130fc-103">Test-Json</span></span>

## <span data-ttu-id="130fc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="130fc-104">SYNOPSIS</span></span>
<span data-ttu-id="130fc-105">Testa se uma cadeia de caracteres é um documento JSON válido</span><span class="sxs-lookup"><span data-stu-id="130fc-105">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="130fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="130fc-106">SYNTAX</span></span>

```
Test-Json [-Json] <string> [[-Schema] <string>] [<CommonParameters>]
```

## <span data-ttu-id="130fc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="130fc-107">DESCRIPTION</span></span>

<span data-ttu-id="130fc-108">O `Test-Json` cmdlet testa se uma cadeia de caracteres é um documento JavaScript Object Notation (JSON) válido e pode, opcionalmente, verificar esse documento JSON em relação a um esquema fornecido.</span><span class="sxs-lookup"><span data-stu-id="130fc-108">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="130fc-109">A cadeia de caracteres verificada pode ser usada com o `ConvertFrom-Json` cmdlet converter uma cadeia de caracteres formatada em JSON em um objeto JSON, que é facilmente gerenciado no PowerShell ou enviado a outro programa ou serviço Web que acessa a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="130fc-109">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="130fc-110">Muitos sites usam JSON em vez de XML para serializar dados para a comunicação entre servidores e aplicativos baseados na web.</span><span class="sxs-lookup"><span data-stu-id="130fc-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="130fc-111">Esse cmdlet foi introduzido no PowerShell 6,1</span><span class="sxs-lookup"><span data-stu-id="130fc-111">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="130fc-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="130fc-112">EXAMPLES</span></span>

### <span data-ttu-id="130fc-113">Exemplo 1: testar se um objeto é um JSON válido</span><span class="sxs-lookup"><span data-stu-id="130fc-113">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="130fc-114">Este exemplo testa se a cadeia de caracteres de entrada é um documento JSON válido.</span><span class="sxs-lookup"><span data-stu-id="130fc-114">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="130fc-115">Exemplo 2: testar um objeto em relação a um esquema fornecido</span><span class="sxs-lookup"><span data-stu-id="130fc-115">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="130fc-116">Este exemplo usa uma cadeia de caracteres que contém um esquema JSON e o compara a uma cadeia de caracteres de entrada.</span><span class="sxs-lookup"><span data-stu-id="130fc-116">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

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

<span data-ttu-id="130fc-117">Neste exemplo, obtemos um erro porque o esquema espera um inteiro para a **idade** , mas a entrada JSON que testamos usa um valor de cadeia de caracteres em vez disso.</span><span class="sxs-lookup"><span data-stu-id="130fc-117">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="130fc-118">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="130fc-118">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

## <span data-ttu-id="130fc-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="130fc-119">PARAMETERS</span></span>

### <span data-ttu-id="130fc-120">-JSON</span><span class="sxs-lookup"><span data-stu-id="130fc-120">-Json</span></span>

<span data-ttu-id="130fc-121">Especifica a cadeia de caracteres JSON para testar a validade.</span><span class="sxs-lookup"><span data-stu-id="130fc-121">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="130fc-122">Insira uma variável que contenha a cadeia de caracteres ou digite um comando ou expressão que obtenha essa cadeia.</span><span class="sxs-lookup"><span data-stu-id="130fc-122">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="130fc-123">Você também pode canalizar uma cadeia de caracteres para `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="130fc-123">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="130fc-124">O parâmetro **JSON** é necessário.</span><span class="sxs-lookup"><span data-stu-id="130fc-124">The **Json** parameter is required.</span></span>

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

### <span data-ttu-id="130fc-125">-Esquema</span><span class="sxs-lookup"><span data-stu-id="130fc-125">-Schema</span></span>

<span data-ttu-id="130fc-126">Especifica um esquema para validar a entrada JSON.</span><span class="sxs-lookup"><span data-stu-id="130fc-126">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="130fc-127">Se for passado, `Test-Json` validará que a entrada JSON está de acordo com a especificação especificada pelo parâmetro de **esquema** e retornará `$True` somente se a entrada estiver em conformidade com o esquema fornecido.</span><span class="sxs-lookup"><span data-stu-id="130fc-127">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="130fc-128">Para obter mais informações, consulte [esquema JSON](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="130fc-128">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="130fc-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="130fc-129">CommonParameters</span></span>

<span data-ttu-id="130fc-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="130fc-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="130fc-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="130fc-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="130fc-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="130fc-132">INPUTS</span></span>

### <span data-ttu-id="130fc-133">System.String</span><span class="sxs-lookup"><span data-stu-id="130fc-133">System.String</span></span>

<span data-ttu-id="130fc-134">É possível canalizar uma cadeia de caracteres JSON para `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="130fc-134">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="130fc-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="130fc-135">OUTPUTS</span></span>

### <span data-ttu-id="130fc-136">Booliano</span><span class="sxs-lookup"><span data-stu-id="130fc-136">Boolean</span></span>

## <span data-ttu-id="130fc-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="130fc-137">NOTES</span></span>

<span data-ttu-id="130fc-138">O `Test-Json` cmdlet é implementado usando a [classe NJsonSchema](https://github.com/RSuter/NJsonSchema).</span><span class="sxs-lookup"><span data-stu-id="130fc-138">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="130fc-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="130fc-139">RELATED LINKS</span></span>

<span data-ttu-id="130fc-140">[Uma introdução ao JavaScript Object Notation (JSON) em JavaScript e .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="130fc-140">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="130fc-141">Detalhes adicionais do esquema JSON</span><span class="sxs-lookup"><span data-stu-id="130fc-141">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="130fc-142">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="130fc-142">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="130fc-143">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="130fc-143">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="130fc-144">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="130fc-144">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
