---
description: Executa uma lista de instruções uma ou mais vezes, sujeito a uma condição while ou until.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: ac8ddca01611f4477d424426ccedf9a39af85a82
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195758"
---
# <a name="about-do"></a><span data-ttu-id="14ece-104">Sobre o</span><span class="sxs-lookup"><span data-stu-id="14ece-104">About Do</span></span>

## <a name="short-description"></a><span data-ttu-id="14ece-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="14ece-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="14ece-106">Executa uma lista de instruções uma ou mais vezes, sujeito a uma condição while ou until.</span><span class="sxs-lookup"><span data-stu-id="14ece-106">Runs a statement list one or more times, subject to a While or Until condition.</span></span>

## <a name="long-description"></a><span data-ttu-id="14ece-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="14ece-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="14ece-108">A palavra-chave do funciona com a palavra-chave while ou a palavra-chave until para executar as instruções em um bloco de script, sujeito a uma condição.</span><span class="sxs-lookup"><span data-stu-id="14ece-108">The Do keyword works with the While keyword or the Until keyword to run the statements in a script block, subject to a condition.</span></span> <span data-ttu-id="14ece-109">Ao contrário do loop while relacionado, o bloco de script em um loop do sempre é executado pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="14ece-109">Unlike the related While loop, the script block in a Do loop always runs at least once.</span></span>

<span data-ttu-id="14ece-110">Um loop do **-while** é uma variedade do loop While.</span><span class="sxs-lookup"><span data-stu-id="14ece-110">A **Do-While** loop is a variety of the While loop.</span></span> <span data-ttu-id="14ece-111">Em um loop **do-while** , a condição é avaliada após a execução do bloco de script.</span><span class="sxs-lookup"><span data-stu-id="14ece-111">In a **Do-While** loop, the condition is evaluated after the script block has run.</span></span> <span data-ttu-id="14ece-112">Como em um loop while, o bloco de script é repetido, desde que a condição seja avaliada como true.</span><span class="sxs-lookup"><span data-stu-id="14ece-112">As in a While loop, the script block is repeated as long as the condition evaluates to true.</span></span>

<span data-ttu-id="14ece-113">Como um loop **do-while** , um loop **do-until** sempre é executado pelo menos uma vez antes que a condição seja avaliada.</span><span class="sxs-lookup"><span data-stu-id="14ece-113">Like a **Do-While** loop, a **Do-Until** loop always runs at least once before the condition is evaluated.</span></span> <span data-ttu-id="14ece-114">No entanto, o bloco de script é executado somente enquanto a condição é falsa.</span><span class="sxs-lookup"><span data-stu-id="14ece-114">However, the script block runs only while the condition is false.</span></span>

<span data-ttu-id="14ece-115">As palavras-chave de controle de fluxo de *continuação* e *interrupção* podem ser usadas em um loop **do-while** ou em um loop **do-until** .</span><span class="sxs-lookup"><span data-stu-id="14ece-115">The *Continue* and *Break* flow control keywords can be used in a **Do-While** loop or in a **Do-Until** loop.</span></span>

### <a name="syntax"></a><span data-ttu-id="14ece-116">Syntax</span><span class="sxs-lookup"><span data-stu-id="14ece-116">Syntax</span></span>

<span data-ttu-id="14ece-117">O seguinte mostra a sintaxe da instrução do **-while** :</span><span class="sxs-lookup"><span data-stu-id="14ece-117">The following shows the syntax of the **Do-While** statement:</span></span>

```powershell
do {<statement list>} while (<condition>)
```

<span data-ttu-id="14ece-118">O seguinte mostra a sintaxe da instrução do **-until** :</span><span class="sxs-lookup"><span data-stu-id="14ece-118">The following shows the syntax of the **Do-Until** statement:</span></span>

```powershell
do {<statement list>} until (<condition>)
```

<span data-ttu-id="14ece-119">A lista de instruções contém uma ou mais instruções que são executadas cada vez que o loop é inserido ou repetido.</span><span class="sxs-lookup"><span data-stu-id="14ece-119">The statement list contains one or more statements that run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="14ece-120">A parte da condição da instrução é resolvida como true ou false.</span><span class="sxs-lookup"><span data-stu-id="14ece-120">The condition portion of the statement resolves to true or false.</span></span>

### <a name="example"></a><span data-ttu-id="14ece-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="14ece-121">Example</span></span>

<span data-ttu-id="14ece-122">O exemplo a seguir de uma instrução do conta os itens em uma matriz até alcançar um item com um valor de 0.</span><span class="sxs-lookup"><span data-stu-id="14ece-122">The following example of a Do statement counts the items in an array until it reaches an item with a value of 0.</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

<span data-ttu-id="14ece-123">O exemplo a seguir usa a palavra-chave until.</span><span class="sxs-lookup"><span data-stu-id="14ece-123">The following example uses the Until keyword.</span></span> <span data-ttu-id="14ece-124">Observe que o operador não igual a ( `-ne` ) é substituído pelo operador Equals to ( `-eq` ).</span><span class="sxs-lookup"><span data-stu-id="14ece-124">Notice that the not equal to operator (`-ne`) is replaced by the equal to operator (`-eq`).</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

<span data-ttu-id="14ece-125">O exemplo a seguir grava todos os valores de uma matriz, ignorando qualquer valor menor que zero.</span><span class="sxs-lookup"><span data-stu-id="14ece-125">The following example writes all the values of an array, skipping any value that is less than zero.</span></span>

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a><span data-ttu-id="14ece-126">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="14ece-126">SEE ALSO</span></span>

[<span data-ttu-id="14ece-127">about_While</span><span class="sxs-lookup"><span data-stu-id="14ece-127">about_While</span></span>](about_While.md)

[<span data-ttu-id="14ece-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="14ece-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="14ece-129">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="14ece-129">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="14ece-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="14ece-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="14ece-131">about_Break</span><span class="sxs-lookup"><span data-stu-id="14ece-131">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="14ece-132">about_Continue</span><span class="sxs-lookup"><span data-stu-id="14ece-132">about_Continue</span></span>](about_Continue.md)
