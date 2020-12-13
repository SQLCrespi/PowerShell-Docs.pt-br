---
ms.date: 09/12/2016
ms.topic: reference
title: Colocar a ajuda baseada em comentários em funções
description: Colocar a ajuda baseada em comentários em funções
ms.openlocfilehash: 3bd72f0c71d8f6ad54c43c99f044423c072fdeeb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658205"
---
# <a name="placing-comment-based-help-in-functions"></a><span data-ttu-id="f7d54-103">Colocar a ajuda baseada em comentários em funções</span><span class="sxs-lookup"><span data-stu-id="f7d54-103">Placing Comment-Based Help in Functions</span></span>

<span data-ttu-id="f7d54-104">Este tópico explica onde posicionar a ajuda baseada em comentários para uma função, de modo que o `Get-Help` cmdlet associe o tópico de ajuda baseado em comentário com a função correta.</span><span class="sxs-lookup"><span data-stu-id="f7d54-104">This topic explains where to place comment-based help for a function so that the `Get-Help` cmdlet associates the comment-based help topic with the correct function.</span></span>

## <a name="where-to-place-comment-based-help-for-a-function"></a><span data-ttu-id="f7d54-105">Onde posicionar Comment-Based ajuda para uma função</span><span class="sxs-lookup"><span data-stu-id="f7d54-105">Where to Place Comment-Based Help for a Function</span></span>

- <span data-ttu-id="f7d54-106">No início do corpo da função.</span><span class="sxs-lookup"><span data-stu-id="f7d54-106">At the beginning of the function body.</span></span>

- <span data-ttu-id="f7d54-107">No final do corpo da função.</span><span class="sxs-lookup"><span data-stu-id="f7d54-107">At the end of the function body.</span></span>

- <span data-ttu-id="f7d54-108">Antes da `Function` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="f7d54-108">Before the `Function` keyword.</span></span> <span data-ttu-id="f7d54-109">Quando a função está em um módulo de script ou script, não pode haver mais de uma linha em branco entre a última linha da ajuda baseada em comentários e a `Function` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="f7d54-109">When the function is in a script or script module, there cannot be more than one blank line between the last line of the comment-based help and the `Function` keyword.</span></span> <span data-ttu-id="f7d54-110">Caso contrário, `Get-Help` o associa a ajuda ao script, não com a função.</span><span class="sxs-lookup"><span data-stu-id="f7d54-110">Otherwise, `Get-Help` associates the help with the script, not with the function.</span></span>

## <a name="examples-of-help-placement-in-a-function"></a><span data-ttu-id="f7d54-111">Exemplos de posicionamento de ajuda em uma função</span><span class="sxs-lookup"><span data-stu-id="f7d54-111">Examples of Help Placement in a Function</span></span>

<span data-ttu-id="f7d54-112">Os exemplos a seguir mostram cada uma das três opções de posicionamento para a ajuda baseada em comentários para uma função.</span><span class="sxs-lookup"><span data-stu-id="f7d54-112">The following examples show each of the three placement options for comment-based help for a function.</span></span>

### <a name="help-at-the-beginning-of-a-function-body"></a><span data-ttu-id="f7d54-113">Ajuda no início de um corpo de função</span><span class="sxs-lookup"><span data-stu-id="f7d54-113">Help at the Beginning of a Function Body</span></span>

<span data-ttu-id="f7d54-114">O exemplo a seguir mostra o comentário baseado no início de um corpo de função.</span><span class="sxs-lookup"><span data-stu-id="f7d54-114">The following example shows comment-based at the beginning of a function body.</span></span>

```powershell
function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}
```

### <a name="help-at-the-end-of-a-function-body"></a><span data-ttu-id="f7d54-115">Ajuda no final de um corpo de função</span><span class="sxs-lookup"><span data-stu-id="f7d54-115">Help at the End of a Function Body</span></span>

 <span data-ttu-id="f7d54-116">O exemplo a seguir mostra o comentário baseado no final de um corpo de função.</span><span class="sxs-lookup"><span data-stu-id="f7d54-116">The following example shows comment-based at the end of a function body.</span></span>

```powershell
function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}
```

### <a name="help-before-the-function-keyword"></a><span data-ttu-id="f7d54-117">Ajuda antes da palavra-chave Function</span><span class="sxs-lookup"><span data-stu-id="f7d54-117">Help Before the Function Keyword</span></span>

 <span data-ttu-id="f7d54-118">Os exemplos a seguir mostram o comentário baseado na linha antes da palavra-chave Function.</span><span class="sxs-lookup"><span data-stu-id="f7d54-118">The following examples shows comment-based on the line before the function keyword.</span></span>

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
