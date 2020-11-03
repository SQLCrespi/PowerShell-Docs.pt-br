---
description: Descreve como criar e usar uma variável de tipo de referência. Você pode usar variáveis de tipo de referência para permitir que uma função altere o valor de uma variável que é passada para ela.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: f011ec44e93d379e6d6a84eaeed37862c888baa1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196341"
---
# <a name="about-ref"></a><span data-ttu-id="cb2e5-105">Sobre ref</span><span class="sxs-lookup"><span data-stu-id="cb2e5-105">About Ref</span></span>

## <a name="short-description"></a><span data-ttu-id="cb2e5-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="cb2e5-106">Short description</span></span>
<span data-ttu-id="cb2e5-107">Descreve como criar e usar uma variável de tipo de referência.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-107">Describes how to create and use a reference type variable.</span></span> <span data-ttu-id="cb2e5-108">Você pode usar variáveis de tipo de referência para permitir que uma função altere o valor de uma variável que é passada para ela.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-108">You can use reference type variables to permit a function to change the value of a variable that is passed to it.</span></span>

## <a name="long-description"></a><span data-ttu-id="cb2e5-109">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="cb2e5-109">Long description</span></span>

<span data-ttu-id="cb2e5-110">Você pode passar variáveis para funções *por referência* ou *por valor* .</span><span class="sxs-lookup"><span data-stu-id="cb2e5-110">You can pass variables to functions *by reference* or *by value* .</span></span>

<span data-ttu-id="cb2e5-111">Ao passar uma variável *por valor* , você está passando uma cópia dos dados.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-111">When you pass a variable *by value* , you are passing a copy of the data.</span></span>

<span data-ttu-id="cb2e5-112">No exemplo a seguir, a função altera o valor da variável passada para ela.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-112">In the following example, the function changes the value of the variable passed to it.</span></span> <span data-ttu-id="cb2e5-113">No PowerShell, os inteiros são tipos de valor para que sejam passados por valor.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-113">In PowerShell, integers are value types so they are passed by value.</span></span>
<span data-ttu-id="cb2e5-114">Portanto, o valor de `$var` é inalterado fora do escopo da função.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-114">Therefore, the value of `$var` is unchanged outside the scope of the function.</span></span>

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

<span data-ttu-id="cb2e5-115">No exemplo a seguir, uma variável que contém um `Hashtable` é passada para uma função.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-115">In the following example, a variable containing a `Hashtable` is passed to a function.</span></span> <span data-ttu-id="cb2e5-116">`Hashtable` é um tipo de objeto, portanto, por padrão, ele é passado para a função *por referência* .</span><span class="sxs-lookup"><span data-stu-id="cb2e5-116">`Hashtable` is an object type so by default it is passed to the function *by reference* .</span></span>

<span data-ttu-id="cb2e5-117">Ao passar uma variável *por referência* , a função pode alterar os dados e essa alteração persiste após a execução da função.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-117">When passing a variable *by reference* , the function can change the data and that change persists after the function executes.</span></span>

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

<span data-ttu-id="cb2e5-118">A função adiciona um novo par chave-valor que persiste fora do escopo da função.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-118">The function adds a new key-value pair that persists outside of the function's scope.</span></span>

### <a name="writing-functions-to-accept-reference-parameters"></a><span data-ttu-id="cb2e5-119">Gravando funções para aceitar parâmetros de referência</span><span class="sxs-lookup"><span data-stu-id="cb2e5-119">Writing functions to accept reference parameters</span></span>

<span data-ttu-id="cb2e5-120">Você pode codificar suas funções para obter um parâmetro como uma referência, independentemente do tipo de dados passado.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-120">You can code your functions to take a parameter as a reference, regardless of the type of data passed.</span></span> <span data-ttu-id="cb2e5-121">Isso requer que você especifique o tipo de parâmetros como `System.Management.Automation.PSReference` , ou `[ref]` .</span><span class="sxs-lookup"><span data-stu-id="cb2e5-121">This requires that you specify the parameters type as `System.Management.Automation.PSReference`, or `[ref]`.</span></span>

<span data-ttu-id="cb2e5-122">Ao usar referências, você deve usar a `Value` Propriedade do `System.Management.Automation.PSReference` tipo para acessar seus dados.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-122">When using references, you must use the `Value` property of the `System.Management.Automation.PSReference` type to access your data.</span></span>

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

<span data-ttu-id="cb2e5-123">Para passar uma variável para um parâmetro que espera uma referência, você deve digitar Cast a Variable como uma referência.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-123">To pass a variable to a parameter that expects a reference, you must type cast your variable as a reference.</span></span>

> [!NOTE]
> <span data-ttu-id="cb2e5-124">Os colchetes e os parênteses são necessários.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-124">The brackets and parenthesis are BOTH required.</span></span>

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a><span data-ttu-id="cb2e5-125">Passando referências para métodos .NET</span><span class="sxs-lookup"><span data-stu-id="cb2e5-125">Passing references to .NET methods</span></span>

<span data-ttu-id="cb2e5-126">Alguns métodos .NET podem exigir que você passe uma variável como referência.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-126">Some .NET methods may require you to pass a variable as a reference.</span></span> <span data-ttu-id="cb2e5-127">Quando a definição do método usa as palavras-chave `in` , `out` , ou `ref` em um parâmetro, ela espera uma referência.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-127">When the method's definition uses the keywords `in`, `out`, or `ref` on a parameter, it expects a reference.</span></span>

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

<span data-ttu-id="cb2e5-128">O `TryParse` método tenta analisar uma cadeia de caracteres como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-128">The `TryParse` method attempts to parse a string as an integer.</span></span> <span data-ttu-id="cb2e5-129">Se o método for bem-sucedido, ele retornará `$true` e o resultado será armazenado na variável que você passou **por referência** .</span><span class="sxs-lookup"><span data-stu-id="cb2e5-129">If the method succeeds, it returns `$true`, and the result is stored in the variable you passed **by reference** .</span></span>

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a><span data-ttu-id="cb2e5-130">Referências e escopos</span><span class="sxs-lookup"><span data-stu-id="cb2e5-130">References and scopes</span></span>

<span data-ttu-id="cb2e5-131">As referências permitem que o valor de uma variável no escopo pai seja alterado em um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-131">References allow the value of a variable in the parent scope to be changed within a child scope.</span></span>

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

<span data-ttu-id="cb2e5-132">Somente a variável do tipo de referência foi alterada.</span><span class="sxs-lookup"><span data-stu-id="cb2e5-132">Only the reference type's variable was changed.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb2e5-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="cb2e5-133">See also</span></span>

[<span data-ttu-id="cb2e5-134">about_Variables</span><span class="sxs-lookup"><span data-stu-id="cb2e5-134">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="cb2e5-135">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="cb2e5-135">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="cb2e5-136">about_Functions</span><span class="sxs-lookup"><span data-stu-id="cb2e5-136">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="cb2e5-137">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="cb2e5-137">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="cb2e5-138">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="cb2e5-138">about_Scopes</span></span>](about_scopes.md)

