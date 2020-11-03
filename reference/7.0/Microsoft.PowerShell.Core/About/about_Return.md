---
description: Sai do escopo atual, que pode ser uma função, um script ou um bloco de script.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Return
ms.openlocfilehash: d1cfdf66cbcbc1bb93d6eaef238e9e5d39b56187
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196269"
---
# <a name="about-return"></a><span data-ttu-id="d1d58-104">Sobre o retorno</span><span class="sxs-lookup"><span data-stu-id="d1d58-104">About Return</span></span>

## <a name="short-description"></a><span data-ttu-id="d1d58-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="d1d58-105">Short description</span></span>

<span data-ttu-id="d1d58-106">Sai do escopo atual, que pode ser uma função, um script ou um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="d1d58-106">Exits the current scope, which can be a function, script, or script block.</span></span>

## <a name="long-description"></a><span data-ttu-id="d1d58-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="d1d58-107">Long description</span></span>

<span data-ttu-id="d1d58-108">A `return` palavra-chave sai de uma função, script ou bloco de script.</span><span class="sxs-lookup"><span data-stu-id="d1d58-108">The `return` keyword exits a function, script, or script block.</span></span> <span data-ttu-id="d1d58-109">Ele pode ser usado para sair de um escopo em um ponto específico, para retornar um valor ou para indicar que o final do escopo foi atingido.</span><span class="sxs-lookup"><span data-stu-id="d1d58-109">It can be used to exit a scope at a specific point, to return a value, or to indicate that the end of the scope has been reached.</span></span>

<span data-ttu-id="d1d58-110">Os usuários que estão familiarizados com linguagens como C ou C \# podem querer usar a `return` palavra-chave para tornar a lógica de deixar um escopo explícito.</span><span class="sxs-lookup"><span data-stu-id="d1d58-110">Users who are familiar with languages like C or C\# might want to use the `return` keyword to make the logic of leaving a scope explicit.</span></span>

<span data-ttu-id="d1d58-111">No PowerShell, os resultados de cada instrução são retornados como saída, mesmo sem uma instrução que contenha a palavra-chave Return.</span><span class="sxs-lookup"><span data-stu-id="d1d58-111">In PowerShell, the results of each statement are returned as output, even without a statement that contains the Return keyword.</span></span> <span data-ttu-id="d1d58-112">Linguagens como C ou C \# retornam apenas o valor ou valores que são especificados pela `return` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="d1d58-112">Languages like C or C\# return only the value or values that are specified by the `return` keyword.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d58-113">A partir do PowerShell 5,0, o PowerShell adicionou o idioma para definir classes, usando a sintaxe formal.</span><span class="sxs-lookup"><span data-stu-id="d1d58-113">Beginning in PowerShell 5.0, PowerShell added language for defining classes, by using formal syntax.</span></span>  <span data-ttu-id="d1d58-114">No contexto de uma classe do PowerShell, nada é a saída de um método, exceto o que você especifica usando uma `return` instrução.</span><span class="sxs-lookup"><span data-stu-id="d1d58-114">In the context of a PowerShell class, nothing is output from a method except what you specify using a `return` statement.</span></span> <span data-ttu-id="d1d58-115">Você pode ler mais sobre classes do PowerShell no [about_Classes](about_Classes.md).</span><span class="sxs-lookup"><span data-stu-id="d1d58-115">You can read more about PowerShell classes in [about_Classes](about_Classes.md).</span></span>

### <a name="syntax"></a><span data-ttu-id="d1d58-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1d58-116">Syntax</span></span>

<span data-ttu-id="d1d58-117">A sintaxe para a `return` palavra-chave é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="d1d58-117">The syntax for the `return` keyword is as follows:</span></span>

```
return [<expression>]
```

<span data-ttu-id="d1d58-118">A `return` palavra-chave pode aparecer sozinha ou pode ser seguida por um valor ou expressão, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d1d58-118">The `return` keyword can appear alone, or it can be followed by a value or expression, as follows:</span></span>

```powershell
return
return $a
return (2 + $a)
```

### <a name="examples"></a><span data-ttu-id="d1d58-119">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d1d58-119">Examples</span></span>

<span data-ttu-id="d1d58-120">O exemplo a seguir usa a `return` palavra-chave para sair de uma função em um ponto específico se uma condicional for atendida.</span><span class="sxs-lookup"><span data-stu-id="d1d58-120">The following example uses the `return` keyword to exit a function at a specific point if a conditional is met.</span></span> <span data-ttu-id="d1d58-121">Números ímpares não são multiplicados porque a instrução de retorno é encerrada antes que essa instrução possa ser executada.</span><span class="sxs-lookup"><span data-stu-id="d1d58-121">Odd numbers are not multiplied because the return statement exits before that statement can execute.</span></span>

```powershell
function MultiplyEven
{
    param($number)

    if ($number % 2) { return "$number is not even" }
    $number * 2
}

1..10 | ForEach-Object {MultiplyEven -Number $_}
```

```output
1 is not even
4
3 is not even
8
5 is not even
12
7 is not even
16
9 is not even
20
```

<span data-ttu-id="d1d58-122">No PowerShell, os valores podem ser retornados mesmo se a `return` palavra-chave não for usada.</span><span class="sxs-lookup"><span data-stu-id="d1d58-122">In PowerShell, values can be returned even if the `return` keyword is not used.</span></span>
<span data-ttu-id="d1d58-123">Os resultados de cada instrução são retornados.</span><span class="sxs-lookup"><span data-stu-id="d1d58-123">The results of each statement are returned.</span></span> <span data-ttu-id="d1d58-124">Por exemplo, as instruções a seguir retornam o valor da `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="d1d58-124">For example, the following statements return the value of the `$a` variable:</span></span>

```powershell
$a
return
```

<span data-ttu-id="d1d58-125">A instrução a seguir também retorna o valor de `$a` :</span><span class="sxs-lookup"><span data-stu-id="d1d58-125">The following statement also returns the value of `$a`:</span></span>

```powershell
return $a
```

<span data-ttu-id="d1d58-126">O exemplo a seguir inclui uma instrução destinada a permitir que o usuário saiba que a função está executando um cálculo:</span><span class="sxs-lookup"><span data-stu-id="d1d58-126">The following example includes a statement intended to let the user know that the function is performing a calculation:</span></span>

```powershell
function calculation {
    param ($value)

    "Please wait. Working on calculation..."
    $value += 73
    return $value
}

$a = calculation 14
```

<span data-ttu-id="d1d58-127">O "Aguarde.</span><span class="sxs-lookup"><span data-stu-id="d1d58-127">The "Please wait.</span></span> <span data-ttu-id="d1d58-128">Trabalhando no cálculo... " a cadeia de caracteres não é exibida.</span><span class="sxs-lookup"><span data-stu-id="d1d58-128">Working on calculation..." string is not displayed.</span></span> <span data-ttu-id="d1d58-129">Em vez disso, ele é atribuído à `$a` variável, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d1d58-129">Instead, it is assigned to the `$a` variable, as in the following example:</span></span>

```
PS> $a
Please wait. Working on calculation...
87
```

<span data-ttu-id="d1d58-130">A cadeia de caracteres informativa e o resultado do cálculo são retornados pela função e atribuídos à `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="d1d58-130">Both the informational string and the result of the calculation are returned by the function and assigned to the `$a` variable.</span></span>

<span data-ttu-id="d1d58-131">Se você quiser exibir uma mensagem em sua função, a partir do PowerShell 5,0, poderá usar o `Information` fluxo.</span><span class="sxs-lookup"><span data-stu-id="d1d58-131">If you would like to display a message within your function, beginning in PowerShell 5.0, you can use the `Information` stream.</span></span> <span data-ttu-id="d1d58-132">O código a seguir corrige o exemplo acima usando o `Write-Information` cmdlet com um `InformationAction` de **continue** .</span><span class="sxs-lookup"><span data-stu-id="d1d58-132">The code below corrects the above example using the `Write-Information` cmdlet with a `InformationAction` of **Continue** .</span></span>

```powershell
function calculation {
    param ($value)

    Write-Information "Please wait. Working on calculation..." -InformationAction Continue
    $value += 73
    return $value
}

$a = calculation 14
```

```output
Please wait. Working on calculation...
C:\PS> $a
87
```

### <a name="return-values-and-the-pipeline"></a><span data-ttu-id="d1d58-133">Valores de retorno e o pipeline</span><span class="sxs-lookup"><span data-stu-id="d1d58-133">Return values and the Pipeline</span></span>

<span data-ttu-id="d1d58-134">Quando você retorna uma coleção de seu bloco de script ou função, o PowerShell automaticamente desacumula os membros e os transmite um por vez por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="d1d58-134">When you return a collection from your script block or function, PowerShell automatically unrolls the members and passes them one at a time through the pipeline.</span></span> <span data-ttu-id="d1d58-135">Isso ocorre devido ao processamento de uma vez por tempo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d58-135">This is due to PowerShell's one-at-a-time processing.</span></span> <span data-ttu-id="d1d58-136">Para obter mais informações, consulte [about_Pipelines](about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="d1d58-136">For more information, see [about_pipelines](about_pipelines.md).</span></span>

<span data-ttu-id="d1d58-137">Esse conceito é ilustrado pela seguinte função de exemplo que retorna uma matriz de números.</span><span class="sxs-lookup"><span data-stu-id="d1d58-137">This concept is illustrated by the following sample function that returns an array of numbers.</span></span> <span data-ttu-id="d1d58-138">A saída da função é canalizada para o `Measure-Object` cmdlet que conta o número de objetos no pipeline.</span><span class="sxs-lookup"><span data-stu-id="d1d58-138">The output from the function is piped to the `Measure-Object` cmdlet which counts the number of objects in the pipeline.</span></span>

```powershell
function Test-Return
{
    $array = 1,2,3
    return $array
}
Test-Return | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="d1d58-139">Para forçar um bloco de script ou uma função a retornar a coleção como um único objeto para o pipeline, use um dos dois métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="d1d58-139">To force a script block or function to return collection as a single object to the pipeline, use one of the following two methods:</span></span>

- <span data-ttu-id="d1d58-140">Expressão de matriz unário</span><span class="sxs-lookup"><span data-stu-id="d1d58-140">Unary array expression</span></span>

  <span data-ttu-id="d1d58-141">Utilizando uma expressão unário, você pode enviar o valor de retorno para baixo no pipeline como um único objeto, conforme ilustrado pelo exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="d1d58-141">Utilizing a unary expression you can send your return value down the pipeline as a single object as illustrated by the following example.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1,2,3
      return (, $array)
  }
  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

- <span data-ttu-id="d1d58-142">`Write-Output` com o parâmetro **Noenumerate** .</span><span class="sxs-lookup"><span data-stu-id="d1d58-142">`Write-Output` with **NoEnumerate** parameter.</span></span>

  <span data-ttu-id="d1d58-143">Você também pode usar o `Write-Output` cmdlet com o parâmetro **noenumerate** .</span><span class="sxs-lookup"><span data-stu-id="d1d58-143">You can also use the `Write-Output` cmdlet with the **NoEnumerate** parameter.</span></span> <span data-ttu-id="d1d58-144">O exemplo a seguir usa o `Measure-Object` cmdlet para contar os objetos enviados ao pipeline da função de exemplo pela `return` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="d1d58-144">The example below uses the `Measure-Object` cmdlet to count the objects sent to the pipeline from the sample function by the `return` keyword.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1, 2, 3
      return Write-Output -NoEnumerate $array
  }

  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

## <a name="see-also"></a><span data-ttu-id="d1d58-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="d1d58-145">See also</span></span>

[<span data-ttu-id="d1d58-146">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="d1d58-146">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="d1d58-147">about_Functions</span><span class="sxs-lookup"><span data-stu-id="d1d58-147">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="d1d58-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="d1d58-148">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="d1d58-149">about_Classes</span><span class="sxs-lookup"><span data-stu-id="d1d58-149">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="d1d58-150">Write-Information</span><span class="sxs-lookup"><span data-stu-id="d1d58-150">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)

[<span data-ttu-id="d1d58-151">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="d1d58-151">about_Script_Blocks</span></span>](about_Script_Blocks.md)
