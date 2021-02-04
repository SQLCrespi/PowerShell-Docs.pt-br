---
description: Descreve como a `continue` instrução retorna imediatamente o fluxo do programa para a parte superior de um loop de programa, uma `switch` instrução ou uma `trap` instrução.
keywords: powershell, cmdlet
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: 96758fb110ec1496ebbc073cdacfd3dcc15ae486
ms.sourcegitcommit: 0c31814bed14ff715dc7d4aace07cbdc6df2438e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97614074"
---
# <a name="about-continue"></a><span data-ttu-id="c2cc6-104">Sobre o Continue</span><span class="sxs-lookup"><span data-stu-id="c2cc6-104">About Continue</span></span>

## <a name="short-description"></a><span data-ttu-id="c2cc6-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="c2cc6-105">Short description</span></span>

<span data-ttu-id="c2cc6-106">Descreve como a `continue` instrução retorna imediatamente o fluxo do programa para a parte superior de um loop de programa, uma `switch` instrução ou uma `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-106">Describes how the `continue` statement immediately returns the program flow to the top of a program loop, a `switch` statement, or a `trap` statement.</span></span>

## <a name="long-description"></a><span data-ttu-id="c2cc6-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="c2cc6-107">Long description</span></span>

<span data-ttu-id="c2cc6-108">A `continue` instrução fornece uma maneira de sair do bloco de controle atual, mas continuar a execução, em vez de sair completamente.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-108">The `continue` statement provides a way to exit the current control block but continue execution, rather than exit completely.</span></span> <span data-ttu-id="c2cc6-109">A instrução dá suporte a rótulos.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-109">The statement supports labels.</span></span>
<span data-ttu-id="c2cc6-110">Um rótulo é um nome que você atribui a uma instrução em um script.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-110">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-continue-in-loops"></a><span data-ttu-id="c2cc6-111">Usando continuar em loops</span><span class="sxs-lookup"><span data-stu-id="c2cc6-111">Using continue in loops</span></span>

<span data-ttu-id="c2cc6-112">Uma instrução sem rótulo `continue` retorna imediatamente o fluxo do programa para a parte superior do loop mais interno que é controlado por `for` uma `foreach` instrução,, `do` ou `while` .</span><span class="sxs-lookup"><span data-stu-id="c2cc6-112">An unlabeled `continue` statement immediately returns the program flow to the top of the innermost loop that is controlled by a `for`, `foreach`, `do`, or `while` statement.</span></span> <span data-ttu-id="c2cc6-113">A iteração atual do loop é encerrada e o loop continua com a próxima iteração.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-113">The current iteration of the loop is terminated and the loop continues with the next iteration.</span></span>

<span data-ttu-id="c2cc6-114">No exemplo a seguir, o fluxo do programa retorna para a parte superior do `while` loop se a `$ctr` variável for igual a 5.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-114">In the following example, program flow returns to the top of the `while` loop if the `$ctr` variable is equal to 5.</span></span> <span data-ttu-id="c2cc6-115">Como resultado, todos os números entre 1 e 10 são exibidos, exceto 5:</span><span class="sxs-lookup"><span data-stu-id="c2cc6-115">As a result, all the numbers between 1 and 10 are displayed except for 5:</span></span>

```powershell
while ($ctr -lt 10)
{
    $ctr += 1
    if ($ctr -eq 5)
    {
        continue
    }

    Write-Host -Object $ctr
}
```

<span data-ttu-id="c2cc6-116">Ao usar um `for` loop, a execução continua na `<Repeat>` instrução, seguida pelo `<Condition>` teste.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-116">When using a `for` loop, execution continues at the `<Repeat>` statement, followed by the `<Condition>` test.</span></span> <span data-ttu-id="c2cc6-117">No exemplo a seguir, um loop infinito não ocorrerá porque o decréscimo de `$i` ocorre após a `continue` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-117">In the example below, an infinite loop will not occur because the decrement of `$i` occurs after the `continue` keyword.</span></span>

```powershell
#   <Init>  <Condition> <Repeat>
for ($i = 0; $i -lt 10; $i++)
{
    Write-Host -Object $i
    if ($i -eq 5)
    {
        continue
        # Will not result in an infinite loop.
        $i--
    }
}
```

### <a name="using-a-labeled-continue-in-a-loop"></a><span data-ttu-id="c2cc6-118">Usando uma continuação rotulada em um loop</span><span class="sxs-lookup"><span data-stu-id="c2cc6-118">Using a labeled continue in a loop</span></span>

<span data-ttu-id="c2cc6-119">Uma instrução rotulada `continue` encerra a execução da iteração e transfere o controle para o rótulo de iteração ou instrução de delimitação de destino `switch` .</span><span class="sxs-lookup"><span data-stu-id="c2cc6-119">A labeled `continue` statement terminates execution of the iteration and transfers control to the targeted enclosing iteration or `switch` statement label.</span></span>

<span data-ttu-id="c2cc6-120">No exemplo a seguir, o mais interno `for` é encerrado quando `$condition` é **verdadeiro** e a iteração continua com o segundo `for` loop em `labelB` .</span><span class="sxs-lookup"><span data-stu-id="c2cc6-120">In the following example, the innermost `for` is terminated when `$condition` is **True** and iteration continues with the second `for` loop at `labelB`.</span></span>

```powershell
:labelA for ($i = 1; $i -le 10; $i++) {
    :labelB for ($j = 1; $j -le 10; $j++) {
        :labelC for ($k = 1; $k -le 10; $k++) {
            if ($condition) {
                continue labelB
            } else {
                $condition = Update-Condition
            }
        }
    }
}
```

## <a name="using-continue-in-a-switch-statement"></a><span data-ttu-id="c2cc6-121">Usando continue em uma instrução switch</span><span class="sxs-lookup"><span data-stu-id="c2cc6-121">Using continue in a switch statement</span></span>

<span data-ttu-id="c2cc6-122">Uma instrução sem rótulo `continue` em um `switch` encerra a execução da `switch` iteração atual e transfere o controle para a parte superior do `switch` para obter o próximo item de entrada.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-122">An unlabeled `continue` statement within a `switch` terminates execution of the current `switch` iteration and transfers control to the top of the `switch` to get the next input item.</span></span>

<span data-ttu-id="c2cc6-123">Quando há um único item de entrada, `continue` ele sai da `switch` instrução inteira.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-123">When there is a single input item `continue` exits the entire `switch` statement.</span></span>
<span data-ttu-id="c2cc6-124">Quando a `switch` entrada é uma coleção, o `switch` testa cada elemento da coleção.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-124">When the `switch` input is a collection, the `switch` tests each element of the collection.</span></span> <span data-ttu-id="c2cc6-125">O `continue` sai da iteração atual e `switch` continua com o próximo elemento.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-125">The `continue` exits the current iteration and the `switch` continues with the next element.</span></span>

```powershell
switch (1,2,3) {
  2 { continue }  # moves on to the next element, 3
  default { $_ }
}
```

```Output
1
3
```

## <a name="using-continue-in-a-trap-statement"></a><span data-ttu-id="c2cc6-126">Usando continuar em uma instrução de interceptação</span><span class="sxs-lookup"><span data-stu-id="c2cc6-126">Using continue in a trap statement</span></span>

<span data-ttu-id="c2cc6-127">Se a instrução final executada no corpo de uma `trap` instrução for `continue` , o erro interceptado será silenciosamente ignorado e a execução continuará com a instrução imediatamente após aquela que causou `trap` a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-127">If the final statement executed in the body a `trap` statement is `continue`, the trapped error is silently ignored and execution continues with the statement immediately following the one that caused `trap` to occur.</span></span>

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="c2cc6-128">Não usar continuar fora de um loop, comutador ou interceptação</span><span class="sxs-lookup"><span data-stu-id="c2cc6-128">Do not use continue outside of a loop, switch, or trap</span></span>

<span data-ttu-id="c2cc6-129">Quando `continue` é usado fora de um Construct que dá suporte diretamente a ele (loops, `switch` , `trap` ), _o PowerShell pesquisa a pilha de chamadas_ para uma construção delimitadora.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-129">When `continue` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="c2cc6-130">Se não for possível localizar uma construção delimitadora, o runspace atual será encerrado silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-130">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="c2cc6-131">Isso significa que as funções e os scripts que usam inadvertidamente `continue` fora de uma construção delimitadora que dá suporte a ela podem encerrar inadvertidamente seus _chamadores_.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-131">This means that functions and scripts that inadvertently use a `continue` outside of an enclosing construct that supports it, can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="c2cc6-132">Usar `continue` dentro de um pipeline, como um `ForEach-Object` bloco de script, não apenas sai do pipeline, ele potencialmente encerra todo o runspace.</span><span class="sxs-lookup"><span data-stu-id="c2cc6-132">Using `continue` inside a pipeline, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2cc6-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="c2cc6-133">See also</span></span>

[<span data-ttu-id="c2cc6-134">about_Break</span><span class="sxs-lookup"><span data-stu-id="c2cc6-134">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="c2cc6-135">about_For</span><span class="sxs-lookup"><span data-stu-id="c2cc6-135">about_For</span></span>](about_For.md)

[<span data-ttu-id="c2cc6-136">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="c2cc6-136">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="c2cc6-137">about_Throw</span><span class="sxs-lookup"><span data-stu-id="c2cc6-137">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="c2cc6-138">about_Trap</span><span class="sxs-lookup"><span data-stu-id="c2cc6-138">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="c2cc6-139">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="c2cc6-139">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
