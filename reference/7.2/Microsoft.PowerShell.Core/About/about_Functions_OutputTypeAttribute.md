---
description: Descreve um atributo que informa o tipo de objeto que a função retorna.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: 82f1615c4a2fe2a24f104d8e5637103dea6e5a0a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603566"
---
# <a name="about-functions-outputtypeattribute"></a><span data-ttu-id="14ab5-103">Sobre o Functions OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="14ab5-103">About Functions OutputTypeAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="14ab5-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="14ab5-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="14ab5-105">Descreve um atributo que informa o tipo de objeto que a função retorna.</span><span class="sxs-lookup"><span data-stu-id="14ab5-105">Describes an attribute that reports the type of object that the function returns.</span></span>

## <a name="long-description"></a><span data-ttu-id="14ab5-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="14ab5-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="14ab5-107">O atributo OutputType lista os tipos .NET de objetos que as funções retorna.</span><span class="sxs-lookup"><span data-stu-id="14ab5-107">The OutputType attribute lists the .NET types of objects that the functions returns.</span></span> <span data-ttu-id="14ab5-108">Você pode usar seu parâmetro opcional ParameterSetName para listar diferentes tipos de saída para cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="14ab5-108">You can use its optional ParameterSetName parameter to list different output types for each parameter set.</span></span>

<span data-ttu-id="14ab5-109">O atributo OutputType tem suporte em funções simples e avançadas.</span><span class="sxs-lookup"><span data-stu-id="14ab5-109">The OutputType attribute is supported on simple and advanced functions.</span></span> <span data-ttu-id="14ab5-110">Ele é independente do atributo CmdletBinding.</span><span class="sxs-lookup"><span data-stu-id="14ab5-110">It is independent of the CmdletBinding attribute.</span></span>

<span data-ttu-id="14ab5-111">O atributo OutputType fornece o valor da Propriedade OutputType do objeto **System. Management. Automation. FunctionInfo** que o `Get-Command` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="14ab5-111">The OutputType attribute provides the value of the OutputType property of the **System.Management.Automation.FunctionInfo** object that the `Get-Command` cmdlet returns.</span></span>

<span data-ttu-id="14ab5-112">O valor do atributo OutputType é apenas uma observação de documentação.</span><span class="sxs-lookup"><span data-stu-id="14ab5-112">The OutputType attribute value is only a documentation note.</span></span> <span data-ttu-id="14ab5-113">Ele não é derivado do código de função ou comparado à saída real da função.</span><span class="sxs-lookup"><span data-stu-id="14ab5-113">It is not derived from the function code or compared to the actual function output.</span></span> <span data-ttu-id="14ab5-114">Como tal, o valor pode ser impreciso.</span><span class="sxs-lookup"><span data-stu-id="14ab5-114">As such, the value might be inaccurate.</span></span>

## <a name="syntax"></a><span data-ttu-id="14ab5-115">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14ab5-115">SYNTAX</span></span>

<span data-ttu-id="14ab5-116">O atributo OutputType de Functions tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="14ab5-116">The OutputType attribute of functions has the following syntax:</span></span>

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

<span data-ttu-id="14ab5-117">O parâmetro **ParameterSetName** é opcional.</span><span class="sxs-lookup"><span data-stu-id="14ab5-117">The **ParameterSetName** parameter is optional.</span></span>

<span data-ttu-id="14ab5-118">Você pode listar vários tipos no atributo OutputType.</span><span class="sxs-lookup"><span data-stu-id="14ab5-118">You can list multiple types in the OutputType attribute.</span></span>

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

<span data-ttu-id="14ab5-119">Você pode usar o parâmetro **ParameterSetName** para indicar que conjuntos de parâmetros diferentes retornam tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="14ab5-119">You can use the **ParameterSetName** parameter to indicate that different parameter sets return different types.</span></span>

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

<span data-ttu-id="14ab5-120">Coloque as instruções de atributo OutputType na lista de atributos que precede a `Param` instrução.</span><span class="sxs-lookup"><span data-stu-id="14ab5-120">Place the OutputType attribute statements in the attributes list that precedes the `Param` statement.</span></span>

<span data-ttu-id="14ab5-121">O exemplo a seguir mostra o posicionamento do atributo OutputType em uma função simples.</span><span class="sxs-lookup"><span data-stu-id="14ab5-121">The following example shows the placement of the OutputType attribute in a simple function.</span></span>

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

<span data-ttu-id="14ab5-122">O exemplo a seguir mostra o posicionamento do atributo OutputType em funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="14ab5-122">The following example shows the placement of the OutputType attribute in advanced functions.</span></span>

```powershell
function AdvancedFunction1
{
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}

function AdvancedFunction2
{
  [CmdletBinding(SupportsShouldProcess=<Boolean>)]
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}
```

## <a name="examples"></a><span data-ttu-id="14ab5-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="14ab5-123">EXAMPLES</span></span>

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a><span data-ttu-id="14ab5-124">Exemplo 1: criar uma função que tenha o OutputType da cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="14ab5-124">Example 1: Create a function that has the OutputType of String</span></span>

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

<span data-ttu-id="14ab5-125">Para ver a propriedade de tipo de saída resultante, use o `Get-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14ab5-125">To see the resulting output type property, use the `Get-Command` cmdlet.</span></span>

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a><span data-ttu-id="14ab5-126">Exemplo 2: usar o atributo de saída para indicar tipos de saída dinâmicos</span><span class="sxs-lookup"><span data-stu-id="14ab5-126">Example 2: Use the Output attribute to indicate dynamic output types</span></span>

<span data-ttu-id="14ab5-127">A função avançada a seguir usa o atributo OutputType para indicar que a função retorna tipos diferentes dependendo do conjunto de parâmetros usado no comando Function.</span><span class="sxs-lookup"><span data-stu-id="14ab5-127">The following advanced function uses the OutputType attribute to indicate that the function returns different types depending on the parameter set used in the function command.</span></span>

```powershell
function Get-User
{
  [CmdletBinding(DefaultParameterSetName="ID")]

  [OutputType("System.Int32", ParameterSetName="ID")]
  [OutputType([String], ParameterSetName="Name")]

  Param (
    [parameter(Mandatory=$true, ParameterSetName="ID")]
    [Int[]]
    $UserID,

    [parameter(Mandatory=$true, ParameterSetName="Name")]
    [String[]]
    $UserName
  )

  <function body>
}
```

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a><span data-ttu-id="14ab5-128">Exemplo 3: mostra quando uma saída real difere do OutputType</span><span class="sxs-lookup"><span data-stu-id="14ab5-128">Example 3: Shows when an actual output differs from the OutputType</span></span>

<span data-ttu-id="14ab5-129">O exemplo a seguir demonstra que o valor da propriedade de tipo de saída exibe o valor do atributo OutputType, mesmo quando ele é impreciso.</span><span class="sxs-lookup"><span data-stu-id="14ab5-129">The following example demonstrates that the output type property value displays the value of the OutputType attribute, even when it is inaccurate.</span></span>

<span data-ttu-id="14ab5-130">A `Get-Time` função retorna uma cadeia de caracteres que contém a forma abreviada da hora em qualquer objeto DateTime.</span><span class="sxs-lookup"><span data-stu-id="14ab5-130">The `Get-Time` function returns a string that contains the short form of the time in any DateTime object.</span></span> <span data-ttu-id="14ab5-131">No entanto, o atributo OutputType relata que retorna um objeto **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="14ab5-131">However, the OutputType attribute reports that it returns a **System.DateTime** object.</span></span>

```powershell
function Get-Time
{
  [OutputType([DateTime])]
  Param (
    [parameter(Mandatory=$true)]
    [Datetime]$DateTime
  )

  $DateTime.ToShortTimeString()
}
```

<span data-ttu-id="14ab5-132">O `GetType()` método confirma que a função retorna uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="14ab5-132">The `GetType()` method confirms that the function returns a string.</span></span>

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

<span data-ttu-id="14ab5-133">No entanto, a Propriedade OutputType, que obtém seu valor do atributo OutputType, relata que a função retorna um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="14ab5-133">However, the OutputType property, which gets its value from the OutputType attribute, reports that the function returns a **DateTime** object.</span></span>

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a><span data-ttu-id="14ab5-134">Exemplo 4: uma função que não deveria ter A saída</span><span class="sxs-lookup"><span data-stu-id="14ab5-134">Example 4: A function  that shouldn't have output</span></span>

<span data-ttu-id="14ab5-135">O exemplo a seguir mostra uma função personalizada que deve executar e ação, mas não retornar nada.</span><span class="sxs-lookup"><span data-stu-id="14ab5-135">The following example shows a custom function that should perform and action but not return anything.</span></span>

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a><span data-ttu-id="14ab5-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="14ab5-136">NOTES</span></span>

<span data-ttu-id="14ab5-137">O valor da Propriedade OutputType de um objeto **FunctionInfo** é uma matriz de objetos **System. Management. Automation. PSTypeName** , cada um com propriedades Name e Type.</span><span class="sxs-lookup"><span data-stu-id="14ab5-137">The value of the OutputType property of a **FunctionInfo** object is an array of **System.Management.Automation.PSTypeName** objects, each of which have Name and Type properties.</span></span>

<span data-ttu-id="14ab5-138">Para obter apenas o nome de cada tipo de saída, use um comando com o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="14ab5-138">To get only the name of each output type, use a command with the following format.</span></span>

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

<span data-ttu-id="14ab5-139">O valor da Propriedade OutputType pode ser nulo.</span><span class="sxs-lookup"><span data-stu-id="14ab5-139">The value of the OutputType property can be null.</span></span> <span data-ttu-id="14ab5-140">Use um valor nulo quando a saída não for um tipo .NET, como um objeto **WMI** ou uma exibição formatada de um objeto.</span><span class="sxs-lookup"><span data-stu-id="14ab5-140">Use a null value when the output is a not a .NET type, such as a **WMI** object or a formatted view of an object.</span></span>

## <a name="see-also"></a><span data-ttu-id="14ab5-141">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="14ab5-141">SEE ALSO</span></span>

[<span data-ttu-id="14ab5-142">about_Functions</span><span class="sxs-lookup"><span data-stu-id="14ab5-142">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="14ab5-143">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="14ab5-143">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="14ab5-144">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="14ab5-144">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="14ab5-145">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="14ab5-145">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="14ab5-146">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="14ab5-146">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

