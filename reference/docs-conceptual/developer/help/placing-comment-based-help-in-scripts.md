---
title: Colocando a ajuda baseada em comentários em scripts | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361175"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="0dc29-102">Colocar a ajuda baseada em comentários em scripts</span><span class="sxs-lookup"><span data-stu-id="0dc29-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="0dc29-103">Este tópico explica onde posicionar a ajuda baseada em comentários para um script para que o cmdlet `Get-Help` associe o tópico de ajuda baseado em comentário a scripts e não a nenhuma função que possa estar no script.</span><span class="sxs-lookup"><span data-stu-id="0dc29-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="0dc29-104">Onde posicionar a ajuda baseada em comentários para um script</span><span class="sxs-lookup"><span data-stu-id="0dc29-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="0dc29-105">No início do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="0dc29-105">At the beginning of the script file.</span></span> <span data-ttu-id="0dc29-106">A ajuda do script pode ser precedida no script somente por comentários e linhas em branco.</span><span class="sxs-lookup"><span data-stu-id="0dc29-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="0dc29-107">No final do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="0dc29-107">At the end of the script file.</span></span>

  <span data-ttu-id="0dc29-108">Se o primeiro item no corpo do script (após a ajuda) for uma declaração de função, deve haver pelo menos duas linhas em branco entre o final da ajuda do script e a declaração da função.</span><span class="sxs-lookup"><span data-stu-id="0dc29-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="0dc29-109">Caso contrário, a ajuda será interpretada como sendo ajuda para a função, não ajuda para o script.</span><span class="sxs-lookup"><span data-stu-id="0dc29-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="0dc29-110">Exemplos de posicionamento de ajuda em um script</span><span class="sxs-lookup"><span data-stu-id="0dc29-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="0dc29-111">Os exemplos a seguir mostram cada uma das opções de posicionamento da ajuda baseada em comentários para um script.</span><span class="sxs-lookup"><span data-stu-id="0dc29-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="0dc29-112">Ajuda no início de um script</span><span class="sxs-lookup"><span data-stu-id="0dc29-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="0dc29-113">O exemplo a seguir mostra o comentário baseado no início de um script.</span><span class="sxs-lookup"><span data-stu-id="0dc29-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="0dc29-114">Ajuda no final de um script</span><span class="sxs-lookup"><span data-stu-id="0dc29-114">Help at the End of a Script</span></span>

 <span data-ttu-id="0dc29-115">O exemplo a seguir mostra o comentário baseado no final de um script.</span><span class="sxs-lookup"><span data-stu-id="0dc29-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```