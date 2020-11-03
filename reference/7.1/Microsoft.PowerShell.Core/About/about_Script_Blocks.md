---
description: Define o que é um bloco de script e explica como usar blocos de script na linguagem de programação do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Blocks
ms.openlocfilehash: 28bc5377e1787ddb646480eacc219c5bbb63dc37
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196310"
---
# <a name="about-script-blocks"></a><span data-ttu-id="8263d-104">Sobre blocos de script</span><span class="sxs-lookup"><span data-stu-id="8263d-104">About Script Blocks</span></span>

## <a name="short-description"></a><span data-ttu-id="8263d-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="8263d-105">Short description</span></span>

<span data-ttu-id="8263d-106">Define o que é um bloco de script e explica como usar blocos de script na linguagem de programação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8263d-106">Defines what a script block is and explains how to use script blocks in the PowerShell programming language.</span></span>

## <a name="long-description"></a><span data-ttu-id="8263d-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="8263d-107">Long description</span></span>

<span data-ttu-id="8263d-108">Na linguagem de programação do PowerShell, um bloco de script é uma coleção de instruções ou expressões que podem ser usadas como uma única unidade.</span><span class="sxs-lookup"><span data-stu-id="8263d-108">In the PowerShell programming language, a script block is a collection of statements or expressions that can be used as a single unit.</span></span>
<span data-ttu-id="8263d-109">Um bloco de script pode aceitar argumentos e valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="8263d-109">A script block can accept arguments and return values.</span></span>

<span data-ttu-id="8263d-110">Sintaticamente, um bloco de script é uma lista de instruções entre chaves, conforme mostrado na seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="8263d-110">Syntactically, a script block is a statement list in braces, as shown in the following syntax:</span></span>

```
{<statement list>}
```

<span data-ttu-id="8263d-111">Um bloco de script retorna a saída de todos os comandos no bloco de script, seja como um único objeto ou como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="8263d-111">A script block returns the output of all the commands in the script block, either as a single object or as an array.</span></span>

<span data-ttu-id="8263d-112">Você também pode especificar um valor de retorno usando a `return` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="8263d-112">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="8263d-113">A `return` palavra-chave não afeta ou elimina outra saída retornada do bloco de script.</span><span class="sxs-lookup"><span data-stu-id="8263d-113">The `return` keyword does not affect or suppress other output returned from your script block.</span></span> <span data-ttu-id="8263d-114">No entanto, a `return` palavra-chave sai do bloco de script nessa linha.</span><span class="sxs-lookup"><span data-stu-id="8263d-114">However, the `return` keyword exits the script block at that line.</span></span> <span data-ttu-id="8263d-115">Para obter mais informações, consulte [about_Return](about_Return.md).</span><span class="sxs-lookup"><span data-stu-id="8263d-115">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="8263d-116">Como o functions, um bloco de script pode incluir parâmetros.</span><span class="sxs-lookup"><span data-stu-id="8263d-116">Like functions, a script block can include parameters.</span></span> <span data-ttu-id="8263d-117">Use a palavra-chave param para atribuir parâmetros nomeados, conforme mostrado na sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="8263d-117">Use the Param keyword to assign named parameters, as shown in the following syntax:</span></span>

```
{
Param([type]$Parameter1 [,[type]$Parameter2])
<statement list>
}
```

> [!NOTE]
> <span data-ttu-id="8263d-118">Em um bloco de script, ao contrário de uma função, você não pode especificar parâmetros fora das chaves.</span><span class="sxs-lookup"><span data-stu-id="8263d-118">In a script block, unlike a function, you cannot specify parameters outside the braces.</span></span>

<span data-ttu-id="8263d-119">Como as funções, os blocos de script podem incluir as `DynamicParam` `Begin` `Process` `End` palavras-chave,, e.</span><span class="sxs-lookup"><span data-stu-id="8263d-119">Like functions, script blocks can include the `DynamicParam`, `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="8263d-120">Para obter mais informações, consulte [about_Functions](about_Functions.md) e [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="8263d-120">For more information, see [about_Functions](about_Functions.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="using-script-blocks"></a><span data-ttu-id="8263d-121">Usando blocos de script</span><span class="sxs-lookup"><span data-stu-id="8263d-121">Using Script Blocks</span></span>

<span data-ttu-id="8263d-122">Um bloco de script é uma instância de um tipo de estrutura Microsoft .NET `System.Management.Automation.ScriptBlock` .</span><span class="sxs-lookup"><span data-stu-id="8263d-122">A script block is an instance of a Microsoft .NET Framework type `System.Management.Automation.ScriptBlock`.</span></span> <span data-ttu-id="8263d-123">Os comandos podem ter valores de parâmetro de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="8263d-123">Commands can have script block parameter values.</span></span> <span data-ttu-id="8263d-124">Por exemplo, o `Invoke-Command` cmdlet tem um `ScriptBlock` parâmetro que usa um valor de bloco de script, como mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="8263d-124">For example, the `Invoke-Command` cmdlet has a `ScriptBlock` parameter that takes a script block value, as shown in this example:</span></span>

```powershell
Invoke-Command -ScriptBlock { Get-Process }
```

```Output
Handles  NPM(K)    PM(K)     WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----     ----- -----   ------     -- -----------
999          28    39100     45020   262    15.88   1844 communicator
721          28    32696     36536   222    20.84   4028 explorer
...
```

<span data-ttu-id="8263d-125">`Invoke-Command` também pode executar blocos de script que têm blocos de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8263d-125">`Invoke-Command` can also execute script blocks that have parameter blocks.</span></span>
<span data-ttu-id="8263d-126">Os parâmetros são atribuídos por position usando o parâmetro **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="8263d-126">Parameters are assigned by position using the **ArgumentList** parameter.</span></span>

```powershell
Invoke-Command -ScriptBlock { param($p1, $p2)
"p1: $p1"
"p2: $p2"
} -ArgumentList "First", "Second"
```

```Output
p1: First
p2: Second
```

<span data-ttu-id="8263d-127">O bloco de script no exemplo anterior usa a `param` palavra-chave para criar parâmetros `$p1` e `$p2` .</span><span class="sxs-lookup"><span data-stu-id="8263d-127">The script block in the preceding example uses the `param` keyword to create a parameters `$p1` and `$p2`.</span></span> <span data-ttu-id="8263d-128">A cadeia de caracteres "First" é associada ao primeiro parâmetro ( `$p1` ) e "Second" está associado a ( `$p2` ).</span><span class="sxs-lookup"><span data-stu-id="8263d-128">The string "First" is bound to the first parameter (`$p1`) and "Second" is bound to (`$p2`).</span></span>

<span data-ttu-id="8263d-129">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="8263d-129">For more information about the behavior of **ArgumentList** , see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="8263d-130">Você pode usar variáveis para armazenar e executar blocos de script.</span><span class="sxs-lookup"><span data-stu-id="8263d-130">You can use variables to store and execute script blocks.</span></span> <span data-ttu-id="8263d-131">O exemplo a seguir armazena um bloco de script em uma variável e o passa para `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="8263d-131">The example below stores a script block in a variable and passes it to `Invoke-Command`.</span></span>

```powershell
$a = { Get-Service BITS }
Invoke-Command -ScriptBlock $a
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  BITS               Background Intelligent Transfer Ser...
```

<span data-ttu-id="8263d-132">O operador de chamada é outra maneira de executar blocos de script armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="8263d-132">The call operator is another way to execute script blocks stored in a variable.</span></span>
<span data-ttu-id="8263d-133">Como `Invoke-Command` , o operador de chamada executa o bloco de script em um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="8263d-133">Like `Invoke-Command`, the call operator executes the script block in a child scope.</span></span> <span data-ttu-id="8263d-134">O operador Call pode facilitar o uso de parâmetros com seus blocos de script.</span><span class="sxs-lookup"><span data-stu-id="8263d-134">The call operator can make it easier for you to use parameters with your script blocks.</span></span>

```powershell
$a ={ param($p1, $p2)
"p1: $p1"
"p2: $p2"
}
&$a -p2 "First" -p1 "Second"
```

```Output
p1: Second
p2: First
```

<span data-ttu-id="8263d-135">Você pode armazenar a saída de seus blocos de script em uma variável usando a atribuição.</span><span class="sxs-lookup"><span data-stu-id="8263d-135">You can store the output from your script blocks in a variable using assignment.</span></span>

```
PS>  $a = { 1 + 1}
PS>  $b = &$a
PS>  $b
2
```

```
PS>  $a = { 1 + 1}
PS>  $b = Invoke-Command $a
PS>  $b
2
```

<span data-ttu-id="8263d-136">Para obter mais informações sobre o operador de chamada, consulte [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="8263d-136">For more information about the call operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="using-delay-bind-script-blocks-with-parameters"></a><span data-ttu-id="8263d-137">Usando blocos de script de associação de atraso com parâmetros</span><span class="sxs-lookup"><span data-stu-id="8263d-137">Using delay-bind script blocks with parameters</span></span>

<span data-ttu-id="8263d-138">Um parâmetro tipado que aceita entrada de pipeline ( `by Value` ) ou ( `by PropertyName` ) permite o uso de blocos de script de **ligação de atraso** no parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8263d-138">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
<span data-ttu-id="8263d-139">No bloco de script **Delay-BIND** , você pode referenciar o objeto piped in usando a variável de pipeline `$_` .</span><span class="sxs-lookup"><span data-stu-id="8263d-139">Within the **delay-bind** script block, you can reference the piped in object using the pipeline variable `$_`.</span></span>

```powershell
# Renames config.log to old_config.log
dir config.log | Rename-Item -NewName {"old_" + $_.Name}
```

<span data-ttu-id="8263d-140">Em cmdlets mais complexos, os blocos de script de ligação de atraso permitem a reutilização de um piped no objeto para popular outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="8263d-140">In more complex cmdlets, delay-bind script blocks allow the reuse of one piped in object to populate other parameters.</span></span>

<span data-ttu-id="8263d-141">Observações sobre blocos de script de **Associação de atraso** como parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8263d-141">Notes on **delay-bind** script blocks as parameters:</span></span>

- <span data-ttu-id="8263d-142">Você deve especificar explicitamente os nomes de parâmetro usados com blocos **de script de ligação atrasada** .</span><span class="sxs-lookup"><span data-stu-id="8263d-142">You must explicitly specify any parameter names you use with **delay-bind** script blocks.</span></span>
- <span data-ttu-id="8263d-143">O parâmetro não deve ser sem tipo, e o tipo do parâmetro não pode ser `[scriptblock]` ou `[object]` .</span><span class="sxs-lookup"><span data-stu-id="8263d-143">The parameter must not be untyped, and the parameter's type cannot be `[scriptblock]` or `[object]`.</span></span>
- <span data-ttu-id="8263d-144">Você receberá um erro se usar um bloco de script de **ligação de atraso** sem fornecer entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="8263d-144">You receive an error if you use a **delay-bind** script block without providing pipeline input.</span></span>

  ```powershell
  Rename-Item -NewName {$_.Name + ".old"}
  ```

  ```Output
  Rename-Item : Cannot evaluate parameter 'NewName' because its argument is
  specified as a script block and there is no input. A script block cannot
  be evaluated without input.
  At line:1 char:23
  +  Rename-Item -NewName {$_.Name + ".old"}
  +                       ~~~~~~~~~~~~~~~~~~
      + CategoryInfo          : MetadataError: (:) [Rename-Item],
        ParameterBindingException
      + FullyQualifiedErrorId : ScriptBlockArgumentNoInput,
        Microsoft.PowerShell.Commands.RenameItemCommand
  ```

## <a name="see-also"></a><span data-ttu-id="8263d-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8263d-145">See Also</span></span>

[<span data-ttu-id="8263d-146">about_Functions</span><span class="sxs-lookup"><span data-stu-id="8263d-146">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="8263d-147">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="8263d-147">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="8263d-148">about_Operators</span><span class="sxs-lookup"><span data-stu-id="8263d-148">about_Operators</span></span>](about_Operators.md)

