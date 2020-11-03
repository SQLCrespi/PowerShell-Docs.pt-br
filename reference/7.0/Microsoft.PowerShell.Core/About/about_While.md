---
description: Descreve uma instrução de linguagem que você pode usar para executar um bloco de comando com base nos resultados de um teste condicional.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_while?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_While
ms.openlocfilehash: 4008c1c8738b6911949d79882cc6909be2edbe97
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195877"
---
# <a name="about-while"></a><span data-ttu-id="74181-104">Sobre while</span><span class="sxs-lookup"><span data-stu-id="74181-104">About While</span></span>

## <a name="short-description"></a><span data-ttu-id="74181-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="74181-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="74181-106">Descreve uma instrução de linguagem que você pode usar para executar um bloco de comando com base nos resultados de um teste condicional.</span><span class="sxs-lookup"><span data-stu-id="74181-106">Describes a language statement that you can use to run a command block based on the results of a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="74181-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="74181-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="74181-108">A instrução while (também conhecida como um loop while) é uma construção de linguagem para a criação de um loop que executa comandos em um bloco de comando, desde que um teste condicional seja avaliado como true.</span><span class="sxs-lookup"><span data-stu-id="74181-108">The While statement (also known as a While loop) is a language construct for creating a loop that runs commands in a command block as long as a conditional test evaluates to true.</span></span> <span data-ttu-id="74181-109">A instrução while é mais fácil de construir do que uma instrução for, pois sua sintaxe é menos complicada.</span><span class="sxs-lookup"><span data-stu-id="74181-109">The While statement is easier to construct than a For statement because its syntax is less complicated.</span></span> <span data-ttu-id="74181-110">Além disso, é mais flexível do que a instrução foreach porque você especifica um teste condicional na instrução while para controlar quantas vezes o loop é executado.</span><span class="sxs-lookup"><span data-stu-id="74181-110">In addition, it is more flexible than the Foreach statement because you specify a conditional test in the While statement to control how many times the loop runs.</span></span>

<span data-ttu-id="74181-111">O seguinte mostra a sintaxe da instrução While:</span><span class="sxs-lookup"><span data-stu-id="74181-111">The following shows the While statement syntax:</span></span>

```powershell
while (<condition>){<statement list>}
```

<span data-ttu-id="74181-112">Quando você executa uma instrução while, o PowerShell avalia a `<condition>` seção da instrução antes de inserir a `<statement list>` seção.</span><span class="sxs-lookup"><span data-stu-id="74181-112">When you run a While statement, PowerShell evaluates the `<condition>` section of the statement before entering the `<statement list>` section.</span></span> <span data-ttu-id="74181-113">A parte da condição da instrução é resolvida como true ou false.</span><span class="sxs-lookup"><span data-stu-id="74181-113">The condition portion of the statement resolves to either true or false.</span></span> <span data-ttu-id="74181-114">Desde que a condição permaneça verdadeira, o PowerShell executa a `<statement list>` seção novamente.</span><span class="sxs-lookup"><span data-stu-id="74181-114">As long as the condition remains true, PowerShell reruns the `<statement list>` section.</span></span>

<span data-ttu-id="74181-115">A `<statement list>` seção da instrução contém um ou mais comandos que são executados cada vez que o loop é inserido ou repetido.</span><span class="sxs-lookup"><span data-stu-id="74181-115">The `<statement list>` section of the statement contains one or more commands that are run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="74181-116">Por exemplo, a instrução While a seguir exibe os números de 1 a 3 se a variável $val não foi criada ou se a variável $val foi criada e inicializada como 0.</span><span class="sxs-lookup"><span data-stu-id="74181-116">For example, the following While statement displays the numbers 1 through 3 if the $val variable has not been created or if the $val variable has been created and initialized to 0.</span></span>

```powershell
while($val -ne 3)
{
    $val++
    Write-Host $val
}
```

<span data-ttu-id="74181-117">Neste exemplo, a condição ($val não é igual a 3) é true enquanto $val \= 0, 1, 2.</span><span class="sxs-lookup"><span data-stu-id="74181-117">In this example, the condition ($val is not equal to 3) is true while $val \= 0, 1, 2.</span></span> <span data-ttu-id="74181-118">Cada vez pelo loop, $val é incrementado em 1 usando o \+ \+ operador de incremento unário ($Val \+ \+ ).</span><span class="sxs-lookup"><span data-stu-id="74181-118">Each time through the loop, $val is incremented by 1 using the \+\+ unary increment operator ($val\+\+).</span></span> <span data-ttu-id="74181-119">A última hora pelo loop, $val \= 3.</span><span class="sxs-lookup"><span data-stu-id="74181-119">The last time through the loop, $val \= 3.</span></span> <span data-ttu-id="74181-120">Quando $val é igual a 3, a instrução Condition é avaliada como false e o loop é encerrado.</span><span class="sxs-lookup"><span data-stu-id="74181-120">When $val equals 3, the condition statement evaluates to false, and the loop exits.</span></span>

<span data-ttu-id="74181-121">Para escrever convenientemente esse comando no prompt de comando do PowerShell, você pode inseri-lo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="74181-121">To conveniently write this command at the PowerShell command prompt, you can enter it in the following way:</span></span>

```powershell
while($val -ne 3){$val++; Write-Host $val}
```

<span data-ttu-id="74181-122">Observe que o ponto e vírgula separa o primeiro comando que adiciona 1 a $val do segundo comando que grava o valor de $val no console.</span><span class="sxs-lookup"><span data-stu-id="74181-122">Notice that the semicolon separates the first command that adds 1 to $val from the second command that writes the value of $val to the console.</span></span>

## <a name="see-also"></a><span data-ttu-id="74181-123">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="74181-123">SEE ALSO</span></span>

[<span data-ttu-id="74181-124">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="74181-124">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="74181-125">about_Do</span><span class="sxs-lookup"><span data-stu-id="74181-125">about_Do</span></span>](about_Do.md)

[<span data-ttu-id="74181-126">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="74181-126">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="74181-127">about_For</span><span class="sxs-lookup"><span data-stu-id="74181-127">about_For</span></span>](about_For.md)

[<span data-ttu-id="74181-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="74181-128">about_Language_Keywords</span></span>](about_Language_Keywords.md)
