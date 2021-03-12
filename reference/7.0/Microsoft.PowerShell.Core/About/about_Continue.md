---
description: Descreve como a `continue` instrução retorna imediatamente o fluxo do programa para a parte superior de um loop de programa, uma `switch` instrução ou uma `trap` instrução.
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: 8b499169929b35fcb4b0b09c5040780a5f3781cf
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193863"
---
# <a name="about-continue"></a><span data-ttu-id="e123b-103">Sobre o Continue</span><span class="sxs-lookup"><span data-stu-id="e123b-103">About Continue</span></span>

## <a name="short-description"></a><span data-ttu-id="e123b-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="e123b-104">Short description</span></span>

<span data-ttu-id="e123b-105">Descreve como a `continue` instrução retorna imediatamente o fluxo do programa para a parte superior de um loop de programa, uma `switch` instrução ou uma `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="e123b-105">Describes how the `continue` statement immediately returns the program flow to the top of a program loop, a `switch` statement, or a `trap` statement.</span></span>

## <a name="long-description"></a><span data-ttu-id="e123b-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="e123b-106">Long description</span></span>

<span data-ttu-id="e123b-107">A `continue` instrução fornece uma maneira de sair do bloco de controle atual, mas continuar a execução, em vez de sair completamente.</span><span class="sxs-lookup"><span data-stu-id="e123b-107">The `continue` statement provides a way to exit the current control block but continue execution, rather than exit completely.</span></span> <span data-ttu-id="e123b-108">A instrução dá suporte a rótulos.</span><span class="sxs-lookup"><span data-stu-id="e123b-108">The statement supports labels.</span></span>
<span data-ttu-id="e123b-109">Um rótulo é um nome que você atribui a uma instrução em um script.</span><span class="sxs-lookup"><span data-stu-id="e123b-109">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-continue-in-loops"></a><span data-ttu-id="e123b-110">Usando continuar em loops</span><span class="sxs-lookup"><span data-stu-id="e123b-110">Using continue in loops</span></span>

<span data-ttu-id="e123b-111">Uma instrução sem rótulo `continue` retorna imediatamente o fluxo do programa para a parte superior do loop mais interno que é controlado por `for` uma `foreach` instrução,, `do` ou `while` .</span><span class="sxs-lookup"><span data-stu-id="e123b-111">An unlabeled `continue` statement immediately returns the program flow to the top of the innermost loop that is controlled by a `for`, `foreach`, `do`, or `while` statement.</span></span> <span data-ttu-id="e123b-112">A iteração atual do loop é encerrada e o loop continua com a próxima iteração.</span><span class="sxs-lookup"><span data-stu-id="e123b-112">The current iteration of the loop is terminated and the loop continues with the next iteration.</span></span>

<span data-ttu-id="e123b-113">No exemplo a seguir, o fluxo do programa retorna para a parte superior do `while` loop se a `$ctr` variável for igual a 5.</span><span class="sxs-lookup"><span data-stu-id="e123b-113">In the following example, program flow returns to the top of the `while` loop if the `$ctr` variable is equal to 5.</span></span> <span data-ttu-id="e123b-114">Como resultado, todos os números entre 1 e 10 são exibidos, exceto 5:</span><span class="sxs-lookup"><span data-stu-id="e123b-114">As a result, all the numbers between 1 and 10 are displayed except for 5:</span></span>

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

<span data-ttu-id="e123b-115">Ao usar um `for` loop, a execução continua na `<Repeat>` instrução, seguida pelo `<Condition>` teste.</span><span class="sxs-lookup"><span data-stu-id="e123b-115">When using a `for` loop, execution continues at the `<Repeat>` statement, followed by the `<Condition>` test.</span></span> <span data-ttu-id="e123b-116">No exemplo a seguir, um loop infinito não ocorrerá porque o decréscimo de `$i` ocorre após a `continue` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="e123b-116">In the example below, an infinite loop will not occur because the decrement of `$i` occurs after the `continue` keyword.</span></span>

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

### <a name="using-a-labeled-continue-in-a-loop"></a><span data-ttu-id="e123b-117">Usando uma continuação rotulada em um loop</span><span class="sxs-lookup"><span data-stu-id="e123b-117">Using a labeled continue in a loop</span></span>

<span data-ttu-id="e123b-118">Uma instrução rotulada `continue` encerra a execução da iteração e transfere o controle para o rótulo de iteração ou instrução de delimitação de destino `switch` .</span><span class="sxs-lookup"><span data-stu-id="e123b-118">A labeled `continue` statement terminates execution of the iteration and transfers control to the targeted enclosing iteration or `switch` statement label.</span></span>

<span data-ttu-id="e123b-119">No exemplo a seguir, o mais interno `for` é encerrado quando `$condition` é **verdadeiro** e a iteração continua com o segundo `for` loop em `labelB` .</span><span class="sxs-lookup"><span data-stu-id="e123b-119">In the following example, the innermost `for` is terminated when `$condition` is **True** and iteration continues with the second `for` loop at `labelB`.</span></span>

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

## <a name="using-continue-in-a-switch-statement"></a><span data-ttu-id="e123b-120">Usando continue em uma instrução switch</span><span class="sxs-lookup"><span data-stu-id="e123b-120">Using continue in a switch statement</span></span>

<span data-ttu-id="e123b-121">Uma instrução sem rótulo `continue` em um `switch` encerra a execução da `switch` iteração atual e transfere o controle para a parte superior do `switch` para obter o próximo item de entrada.</span><span class="sxs-lookup"><span data-stu-id="e123b-121">An unlabeled `continue` statement within a `switch` terminates execution of the current `switch` iteration and transfers control to the top of the `switch` to get the next input item.</span></span>

<span data-ttu-id="e123b-122">Quando há um único item de entrada, `continue` ele sai da `switch` instrução inteira.</span><span class="sxs-lookup"><span data-stu-id="e123b-122">When there is a single input item `continue` exits the entire `switch` statement.</span></span>
<span data-ttu-id="e123b-123">Quando a `switch` entrada é uma coleção, o `switch` testa cada elemento da coleção.</span><span class="sxs-lookup"><span data-stu-id="e123b-123">When the `switch` input is a collection, the `switch` tests each element of the collection.</span></span> <span data-ttu-id="e123b-124">O `continue` sai da iteração atual e `switch` continua com o próximo elemento.</span><span class="sxs-lookup"><span data-stu-id="e123b-124">The `continue` exits the current iteration and the `switch` continues with the next element.</span></span>

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

## <a name="using-continue-in-a-trap-statement"></a><span data-ttu-id="e123b-125">Usando continuar em uma instrução de interceptação</span><span class="sxs-lookup"><span data-stu-id="e123b-125">Using continue in a trap statement</span></span>

<span data-ttu-id="e123b-126">Se a instrução final executada no corpo de uma `trap` instrução for `continue` , o erro interceptado será silenciosamente ignorado e a execução continuará com a instrução imediatamente após aquela que causou `trap` a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="e123b-126">If the final statement executed in the body a `trap` statement is `continue`, the trapped error is silently ignored and execution continues with the statement immediately following the one that caused `trap` to occur.</span></span>

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="e123b-127">Não usar continuar fora de um loop, comutador ou interceptação</span><span class="sxs-lookup"><span data-stu-id="e123b-127">Do not use continue outside of a loop, switch, or trap</span></span>

<span data-ttu-id="e123b-128">Quando `continue` é usado fora de um Construct que dá suporte diretamente a ele (loops, `switch` , `trap` ), _o PowerShell pesquisa a pilha de chamadas_ para uma construção delimitadora.</span><span class="sxs-lookup"><span data-stu-id="e123b-128">When `continue` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="e123b-129">Se não for possível localizar uma construção delimitadora, o runspace atual será encerrado silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="e123b-129">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="e123b-130">Isso significa que as funções e os scripts que usam inadvertidamente `continue` fora de uma construção delimitadora que dá suporte a ela podem encerrar inadvertidamente seus _chamadores_.</span><span class="sxs-lookup"><span data-stu-id="e123b-130">This means that functions and scripts that inadvertently use a `continue` outside of an enclosing construct that supports it, can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="e123b-131">Usar `continue` dentro de um pipeline, como um `ForEach-Object` bloco de script, não apenas sai do pipeline, ele potencialmente encerra todo o runspace.</span><span class="sxs-lookup"><span data-stu-id="e123b-131">Using `continue` inside a pipeline, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="e123b-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="e123b-132">See also</span></span>

[<span data-ttu-id="e123b-133">about_Break</span><span class="sxs-lookup"><span data-stu-id="e123b-133">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="e123b-134">about_For</span><span class="sxs-lookup"><span data-stu-id="e123b-134">about_For</span></span>](about_For.md)

[<span data-ttu-id="e123b-135">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="e123b-135">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="e123b-136">about_Throw</span><span class="sxs-lookup"><span data-stu-id="e123b-136">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="e123b-137">about_Trap</span><span class="sxs-lookup"><span data-stu-id="e123b-137">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="e123b-138">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="e123b-138">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
