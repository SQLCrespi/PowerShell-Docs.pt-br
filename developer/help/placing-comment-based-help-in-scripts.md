---
title: Colocando a Ajuda baseada em comentário em Scripts | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083222"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="7660a-102">Colocar a ajuda baseada em comentários em scripts</span><span class="sxs-lookup"><span data-stu-id="7660a-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="7660a-103">Este tópico explica onde colocar a Ajuda baseada em comentário para um script para que o `Get-Help` cmdlet associa o tópico da Ajuda baseada em comentários com scripts e não todas as funções que podem ser no script.</span><span class="sxs-lookup"><span data-stu-id="7660a-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="7660a-104">Onde colocar a Ajuda baseada em comentário para um Script</span><span class="sxs-lookup"><span data-stu-id="7660a-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="7660a-105">No início do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="7660a-105">At the beginning of the script file.</span></span> <span data-ttu-id="7660a-106">Ajuda de script pode ser precedidas no script somente por linhas em branco e comentários.</span><span class="sxs-lookup"><span data-stu-id="7660a-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="7660a-107">No final do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="7660a-107">At the end of the script file.</span></span>

  <span data-ttu-id="7660a-108">Se o primeiro item no corpo do script (após a Ajuda) é uma declaração de função, deve haver pelo menos duas linhas em branco entre o final do script de Ajuda e a declaração da função.</span><span class="sxs-lookup"><span data-stu-id="7660a-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="7660a-109">Caso contrário, a Ajuda é interpretada como ajuda para a função, não a Ajuda para o script.</span><span class="sxs-lookup"><span data-stu-id="7660a-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="7660a-110">Exemplos de posicionamento de Ajuda em um Script</span><span class="sxs-lookup"><span data-stu-id="7660a-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="7660a-111">Os exemplos a seguir mostram a cada uma das opções de posicionamento para ajuda baseada em comentário para um script.</span><span class="sxs-lookup"><span data-stu-id="7660a-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="7660a-112">Ajuda no início de um Script</span><span class="sxs-lookup"><span data-stu-id="7660a-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="7660a-113">O exemplo a seguir mostra a baseada em comentário no início de um script.</span><span class="sxs-lookup"><span data-stu-id="7660a-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="7660a-114">Ajuda do final de um Script</span><span class="sxs-lookup"><span data-stu-id="7660a-114">Help at the End of a Script</span></span>

 <span data-ttu-id="7660a-115">O exemplo a seguir mostra a baseada em comentários no final de um script.</span><span class="sxs-lookup"><span data-stu-id="7660a-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```