---
ms.date: 09/12/2016
ms.topic: reference
title: Colocar a ajuda baseada em comentários em scripts
description: Colocar a ajuda baseada em comentários em scripts
ms.openlocfilehash: b0d32b7ab063269085899a643b0c3a17da2073fc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645445"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="5f288-103">Colocar a ajuda baseada em comentários em scripts</span><span class="sxs-lookup"><span data-stu-id="5f288-103">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="5f288-104">Este tópico explica onde posicionar a ajuda baseada em comentários para um script para que o `Get-Help` cmdlet associe o tópico de ajuda baseado em comentário a scripts e não a nenhuma função que possa estar no script.</span><span class="sxs-lookup"><span data-stu-id="5f288-104">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="5f288-105">Onde posicionar Comment-Based ajuda para um script</span><span class="sxs-lookup"><span data-stu-id="5f288-105">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="5f288-106">No início do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="5f288-106">At the beginning of the script file.</span></span>

  <span data-ttu-id="5f288-107">A ajuda do script pode ser precedida no script somente por comentários e linhas em branco.</span><span class="sxs-lookup"><span data-stu-id="5f288-107">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="5f288-108">No final do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="5f288-108">At the end of the script file.</span></span>

  <span data-ttu-id="5f288-109">Se o primeiro item no corpo do script (após a ajuda) for uma declaração de função, deve haver pelo menos duas linhas em branco entre o final da ajuda do script e a declaração da função.</span><span class="sxs-lookup"><span data-stu-id="5f288-109">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="5f288-110">Caso contrário, a ajuda será interpretada como sendo ajuda para a função, não ajuda para o script.</span><span class="sxs-lookup"><span data-stu-id="5f288-110">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="5f288-111">Exemplos de posicionamento de ajuda em um script</span><span class="sxs-lookup"><span data-stu-id="5f288-111">Examples of Help Placement in a Script</span></span>

<span data-ttu-id="5f288-112">Os exemplos a seguir mostram cada uma das opções de posicionamento da ajuda baseada em comentários para um script.</span><span class="sxs-lookup"><span data-stu-id="5f288-112">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="5f288-113">Ajuda no início de um script</span><span class="sxs-lookup"><span data-stu-id="5f288-113">Help at the Beginning of a Script</span></span>

<span data-ttu-id="5f288-114">O exemplo a seguir mostra o comentário baseado no início de um script.</span><span class="sxs-lookup"><span data-stu-id="5f288-114">The following example shows comment-based at the beginning of a script.</span></span>

```powershell
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="5f288-115">Ajuda no final de um script</span><span class="sxs-lookup"><span data-stu-id="5f288-115">Help at the End of a Script</span></span>

 <span data-ttu-id="5f288-116">O exemplo a seguir mostra o comentário baseado no final de um script.</span><span class="sxs-lookup"><span data-stu-id="5f288-116">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>
```
