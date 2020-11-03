---
description: Descreve uma instrução que você pode usar para fechar imediatamente as `foreach` instruções,, `for` ,, `while` `do` `switch` ou `trap` .
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: 8716f81163cfd34684c3ef7071f7827f2e9b5bcf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195780"
---
# <a name="about-break"></a><span data-ttu-id="3ea8c-104">Sobre interrupção</span><span class="sxs-lookup"><span data-stu-id="3ea8c-104">About Break</span></span>

## <a name="short-description"></a><span data-ttu-id="3ea8c-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="3ea8c-105">Short description</span></span>

<span data-ttu-id="3ea8c-106">Descreve uma instrução que você pode usar para fechar imediatamente as `foreach` instruções,, `for` ,, `while` `do` `switch` ou `trap` .</span><span class="sxs-lookup"><span data-stu-id="3ea8c-106">Describes a statement you can use to immediately exit `foreach`, `for`, `while`, `do`, `switch`, or `trap` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="3ea8c-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="3ea8c-107">Long description</span></span>

<span data-ttu-id="3ea8c-108">A `break` instrução fornece uma maneira de sair do bloco de controle atual.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-108">The `break` statement provides a way to exit the current control block.</span></span>
<span data-ttu-id="3ea8c-109">A execução continua na próxima instrução após o bloco de controle.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-109">Execution continues at the next statement after the control block.</span></span> <span data-ttu-id="3ea8c-110">A instrução dá suporte a rótulos.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-110">The statement supports labels.</span></span> <span data-ttu-id="3ea8c-111">Um rótulo é um nome que você atribui a uma instrução em um script.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-111">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-break-in-loops"></a><span data-ttu-id="3ea8c-112">Usando quebras em loops</span><span class="sxs-lookup"><span data-stu-id="3ea8c-112">Using break in loops</span></span>

<span data-ttu-id="3ea8c-113">Quando uma `break` instrução é exibida em um loop, como um `foreach` loop,, `for` `do` ou `while` , o PowerShell sai imediatamente do loop.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-113">When a `break` statement appears in a loop, such as a `foreach`, `for`, `do`, or `while` loop, PowerShell immediately exits the loop.</span></span>

<span data-ttu-id="3ea8c-114">Uma `break` instrução pode incluir um rótulo que permite que você saia de loops inseridos.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-114">A `break` statement can include a label that lets you exit embedded loops.</span></span> <span data-ttu-id="3ea8c-115">Um rótulo pode especificar qualquer palavra-chave loop, como `foreach` , `for` ou, `while` em um script.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-115">A label can specify any loop keyword, such as `foreach`, `for`, or `while`, in a script.</span></span>

<span data-ttu-id="3ea8c-116">O exemplo a seguir mostra como usar uma `break` instrução para sair de uma `for` instrução:</span><span class="sxs-lookup"><span data-stu-id="3ea8c-116">The following example shows how to use a `break` statement to exit a `for` statement:</span></span>

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

<span data-ttu-id="3ea8c-117">Neste exemplo, a `break` instrução sai do `for` loop quando a `$i` variável é igual a 1.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-117">In this example, the `break` statement exits the `for` loop when the `$i` variable equals 1.</span></span> <span data-ttu-id="3ea8c-118">Embora a `for` instrução seja avaliada como **true** até que `$i` seja maior que 10, o PowerShell atinge a instrução break na primeira vez em que o `for` loop é executado.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-118">Even though the `for` statement evaluates to **True** until `$i` is greater than 10, PowerShell reaches the break statement the first time the `for` loop is run.</span></span>

<span data-ttu-id="3ea8c-119">É mais comum usar a `break` instrução em um loop em que uma condição interna deve ser atendida.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-119">It is more common to use the `break` statement in a loop where an inner condition must be met.</span></span> <span data-ttu-id="3ea8c-120">Considere o seguinte `foreach` exemplo de instrução:</span><span class="sxs-lookup"><span data-stu-id="3ea8c-120">Consider the following `foreach` statement example:</span></span>

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

<span data-ttu-id="3ea8c-121">Neste exemplo, a `foreach` instrução itera a `$varB` matriz.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-121">In this example, the `foreach` statement iterates the `$varB` array.</span></span> <span data-ttu-id="3ea8c-122">A `if` instrução é avaliada como falsa as duas primeiras vezes em que o loop é executado e a variável `$i` é incrementada em 1.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-122">The `if` statement evaluates to False the first two times the loop is run and the variable `$i` is incremented by 1.</span></span> <span data-ttu-id="3ea8c-123">A terceira vez em que o loop é executado, `$i` é igual a 2 e a `$val` variável é igual a 30.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-123">The third time the loop is run, `$i` equals 2, and the `$val` variable equals 30.</span></span> <span data-ttu-id="3ea8c-124">Neste ponto, a `break` instrução é executada e o `foreach` loop é encerrado.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-124">At this point, the `break` statement runs, and the `foreach` loop exits.</span></span>

### <a name="using-a-labeled-break-in-a-loop"></a><span data-ttu-id="3ea8c-125">Usando uma quebra rotulada em um loop</span><span class="sxs-lookup"><span data-stu-id="3ea8c-125">Using a labeled break in a loop</span></span>

<span data-ttu-id="3ea8c-126">Uma `break` instrução pode incluir um rótulo.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-126">A `break` statement can include a label.</span></span> <span data-ttu-id="3ea8c-127">Se você usar a `break` palavra-chave com um rótulo, o PowerShell sairá do loop rotulado em vez de sair do loop atual.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-127">If you use the `break` keyword with a label, PowerShell exits the labeled loop instead of exiting the current loop.</span></span>
<span data-ttu-id="3ea8c-128">O rótulo é um ponto-e-vírgula seguido de um nome que você atribui.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-128">The label is a colon followed by a name that you assign.</span></span> <span data-ttu-id="3ea8c-129">O rótulo deve ser o primeiro token em uma instrução e deve ser seguido pela palavra-chave de loop, como `while` .</span><span class="sxs-lookup"><span data-stu-id="3ea8c-129">The label must be the first token in a statement, and it must be followed by the looping keyword, such as `while`.</span></span>

<span data-ttu-id="3ea8c-130">`break` move a execução para fora do loop rotulado.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-130">`break` moves execution out of the labeled loop.</span></span> <span data-ttu-id="3ea8c-131">Em loops inseridos, isso tem um resultado diferente do que a `break` palavra-chave tem quando ela é usada por si mesma.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-131">In embedded loops, this has a different result than the `break` keyword has when it is used by itself.</span></span> <span data-ttu-id="3ea8c-132">Este exemplo tem uma `while` instrução com uma `for` instrução:</span><span class="sxs-lookup"><span data-stu-id="3ea8c-132">This example has a `while` statement with a `for` statement:</span></span>

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

<span data-ttu-id="3ea8c-133">Se a condição 2 for avaliada como **true** , a execução do script será ignorada até a instrução após o loop rotulado.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-133">If condition 2 evaluates to **True** , the execution of the script skips down to the statement after the labeled loop.</span></span> <span data-ttu-id="3ea8c-134">No exemplo, a execução começa novamente com a instrução `$a = $c` .</span><span class="sxs-lookup"><span data-stu-id="3ea8c-134">In the example, execution starts again with the statement `$a = $c`.</span></span>

<span data-ttu-id="3ea8c-135">Você pode aninhar muitos loops rotulados, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-135">You can nest many labeled loops, as shown in the following example.</span></span>

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

<span data-ttu-id="3ea8c-136">Se a `$b` variável for avaliada como true, a execução do script será retomada após o loop rotulado "Red".</span><span class="sxs-lookup"><span data-stu-id="3ea8c-136">If the `$b` variable evaluates to True, execution of the script resumes after the loop that is labeled "red".</span></span> <span data-ttu-id="3ea8c-137">Se a `$c` variável for avaliada como true, a execução do controle de script será retomada após o loop rotulado "amarelo".</span><span class="sxs-lookup"><span data-stu-id="3ea8c-137">If the `$c` variable evaluates to True, execution of the script control resumes after the loop that is labeled "yellow".</span></span>

<span data-ttu-id="3ea8c-138">Se a `$a` variável for avaliada como true, a execução será retomada após o loop mais interno.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-138">If the `$a` variable evaluates to True, execution resumes after the innermost loop.</span></span> <span data-ttu-id="3ea8c-139">Nenhum rótulo é necessário.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-139">No label is needed.</span></span>

<span data-ttu-id="3ea8c-140">O PowerShell não limita a distância com que os rótulos podem retomar a execução.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-140">PowerShell does not limit how far labels can resume execution.</span></span> <span data-ttu-id="3ea8c-141">O rótulo pode até passar o controle entre os limites de chamada de script e de função.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-141">The label can even pass control across script and function call boundaries.</span></span>

## <a name="using-break-in-a-switch-statement"></a><span data-ttu-id="3ea8c-142">Usando break em uma instrução switch</span><span class="sxs-lookup"><span data-stu-id="3ea8c-142">Using break in a switch statement</span></span>

<span data-ttu-id="3ea8c-143">Em um `switch` constructo, `break` faz com que o PowerShell saia do `switch` bloco de código.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-143">In a `switch`construct, `break` causes PowerShell to exit the `switch` code block.</span></span>

<span data-ttu-id="3ea8c-144">A `break` palavra-chave é usada para sair da `switch` construção.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-144">The `break` keyword is used to leave the `switch` construct.</span></span> <span data-ttu-id="3ea8c-145">Por exemplo, a instrução a seguir `switch` usa `break` instruções para testar a condição mais específica:</span><span class="sxs-lookup"><span data-stu-id="3ea8c-145">For example, the following `switch` statement uses `break` statements to test for the most specific condition:</span></span>

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

<span data-ttu-id="3ea8c-146">Neste exemplo, a `$var` variável é criada e inicializada com um valor de cadeia de caracteres de `word2` .</span><span class="sxs-lookup"><span data-stu-id="3ea8c-146">In this example, the `$var` variable is created and initialized to a string value of `word2`.</span></span> <span data-ttu-id="3ea8c-147">A `switch` instrução usa a classe **Regex** para corresponder o valor da variável primeiro com o termo `word2` .</span><span class="sxs-lookup"><span data-stu-id="3ea8c-147">The `switch` statement uses the **Regex** class to match the variable value first with the term `word2`.</span></span> <span data-ttu-id="3ea8c-148">Como o valor da variável e o primeiro teste na `switch` instrução correspondem, o primeiro bloco de código na `switch` instrução é executado.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-148">Because the variable value and the first test in the `switch` statement match, the first code block in the `switch` statement runs.</span></span>

<span data-ttu-id="3ea8c-149">Quando o PowerShell atinge a primeira `break` instrução, a `switch` instrução é encerrada.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-149">When PowerShell reaches the first `break` statement, the `switch` statement exits.</span></span> <span data-ttu-id="3ea8c-150">Se as quatro `break` instruções forem removidas do exemplo, todas as quatro condições serão atendidas.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-150">If the four `break` statements are removed from the example, all four conditions are met.</span></span> <span data-ttu-id="3ea8c-151">Este exemplo usa a `break` instrução para exibir resultados quando a condição mais específica é atendida.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-151">This example uses the `break` statement to display results when the most specific condition is met.</span></span>

## <a name="using-break-in-a-trap-statement"></a><span data-ttu-id="3ea8c-152">Usando break em uma instrução Trap</span><span class="sxs-lookup"><span data-stu-id="3ea8c-152">Using break in a trap statement</span></span>

<span data-ttu-id="3ea8c-153">Se a instrução final executada no corpo de uma `trap` instrução for `break` , o objeto de erro será suprimido e a exceção será lançada novamente.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-153">If the final statement executed in the body of a `trap` statement is `break`, the error object is suppressed and the exception is re-thrown.</span></span>

<span data-ttu-id="3ea8c-154">O exemplo a seguir cria uma exceção **DivideByZeroException** que é interceptada usando a `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-154">The following example create a **DivideByZeroException** exception that is trapped using the `trap` statement.</span></span>

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

Observe que a execução é interrompida na exceção. <span data-ttu-id="3ea8c-156">O `After loop` nunca é atingido.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-156">The `After loop` is never reached.</span></span>
<span data-ttu-id="3ea8c-157">A exceção é gerada novamente após a `trap` execução.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-157">The exception is re-thrown after the `trap` executes.</span></span>

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
Attempted to divide by zero.
At line:10 char:6
+      "1 / $i = " + (1 / $i--)
+      ~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : RuntimeException
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="3ea8c-158">Não usar quebra fora de um loop, comutador ou interceptação</span><span class="sxs-lookup"><span data-stu-id="3ea8c-158">Do not use break outside of a loop, switch, or trap</span></span>

<span data-ttu-id="3ea8c-159">Quando `break` é usado fora de um Construct que dá suporte diretamente a ele (loops, `switch` , `trap` ), _o PowerShell pesquisa a pilha de chamadas_ para uma construção delimitadora.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-159">When `break` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="3ea8c-160">Se não for possível localizar uma construção delimitadora, o runspace atual será encerrado silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-160">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="3ea8c-161">Isso significa que as funções e os scripts que usam inadvertidamente `break` fora de uma construção delimitadora que dá suporte a ela podem encerrar inadvertidamente seus _chamadores_ .</span><span class="sxs-lookup"><span data-stu-id="3ea8c-161">This means that functions and scripts that inadvertently use a `break` outside of an enclosing construct that supports it can inadvertently terminate their _callers_ .</span></span>

<span data-ttu-id="3ea8c-162">Usar `break` dentro de um pipeline `break` , como um `ForEach-Object` bloco de script, não apenas sai do pipeline, ele potencialmente encerra todo o runspace.</span><span class="sxs-lookup"><span data-stu-id="3ea8c-162">Using `break` inside a pipeline `break`, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ea8c-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="3ea8c-163">See also</span></span>

[<span data-ttu-id="3ea8c-164">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="3ea8c-164">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="3ea8c-165">about_Continue</span><span class="sxs-lookup"><span data-stu-id="3ea8c-165">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="3ea8c-166">about_For</span><span class="sxs-lookup"><span data-stu-id="3ea8c-166">about_For</span></span>](about_For.md)

[<span data-ttu-id="3ea8c-167">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="3ea8c-167">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="3ea8c-168">about_Switch</span><span class="sxs-lookup"><span data-stu-id="3ea8c-168">about_Switch</span></span>](about_Switch.md)

[<span data-ttu-id="3ea8c-169">about_Throw</span><span class="sxs-lookup"><span data-stu-id="3ea8c-169">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="3ea8c-170">about_Trap</span><span class="sxs-lookup"><span data-stu-id="3ea8c-170">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="3ea8c-171">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="3ea8c-171">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

[<span data-ttu-id="3ea8c-172">about_While</span><span class="sxs-lookup"><span data-stu-id="3ea8c-172">about_While</span></span>](about_While.md)
