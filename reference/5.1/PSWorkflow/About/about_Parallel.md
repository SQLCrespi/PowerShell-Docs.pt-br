---
description: Descreve a palavra-chave Parallel, que executa as atividades em um fluxo de trabalho em paralelo.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195807"
---
# <a name="about-parallel"></a><span data-ttu-id="9d2de-104">Sobre paralelo</span><span class="sxs-lookup"><span data-stu-id="9d2de-104">About Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="9d2de-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9d2de-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9d2de-106">Descreve a palavra-chave Parallel, que executa as atividades em um fluxo de trabalho em paralelo.</span><span class="sxs-lookup"><span data-stu-id="9d2de-106">Describes the Parallel keyword, which runs the activities in a workflow in parallel.</span></span>

## <a name="long-description"></a><span data-ttu-id="9d2de-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="9d2de-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9d2de-108">A palavra-chave Parallel executa atividades de fluxo de trabalho em paralelo.</span><span class="sxs-lookup"><span data-stu-id="9d2de-108">The Parallel keyword runs workflow activities in parallel.</span></span> <span data-ttu-id="9d2de-109">Essa palavra-chave é válida somente no fluxo de trabalho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d2de-109">This keyword is valid only in  Windows PowerShell  Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="9d2de-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9d2de-110">SYNTAX</span></span>

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a><span data-ttu-id="9d2de-111">DESCRIÇÃO DETALHADA</span><span class="sxs-lookup"><span data-stu-id="9d2de-111">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="9d2de-112">Os comandos de um bloco de script Parallel podem ser executados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="9d2de-112">The commands in a Parallel script block can run concurrently.</span></span> <span data-ttu-id="9d2de-113">A ordem de execução não é determinada.</span><span class="sxs-lookup"><span data-stu-id="9d2de-113">The order in which they run is not determined.</span></span>

<span data-ttu-id="9d2de-114">Por exemplo, o fluxo de trabalho a seguir contém um bloco de script Parallel que executa atividades que obtêm processos e serviços do computador.</span><span class="sxs-lookup"><span data-stu-id="9d2de-114">For example, the following workflow includes a Parallel script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="9d2de-115">Como os comandos Get-Process e Get-Service são independentes um do outro, eles podem ser executados simultaneamente e em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="9d2de-115">Because the Get-Process and Get-Service commands are independent of each other, they can run concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

<span data-ttu-id="9d2de-116">A execução de comandos em paralelo é muito eficiente e reduz o tempo necessário para concluir um fluxo de trabalho significativamente.</span><span class="sxs-lookup"><span data-stu-id="9d2de-116">Running commands in parallel is very efficient and reduces the time it takes to complete a workflow significantly.</span></span>

<span data-ttu-id="9d2de-117">Para executar comandos selecionados em um bloco de script paralelo em ordem sequencial, use a palavra-chave Sequence.</span><span class="sxs-lookup"><span data-stu-id="9d2de-117">To run selected commands in a Parallel script block in sequential order, use the Sequence keyword.</span></span> <span data-ttu-id="9d2de-118">Para obter mais informações, consulte about_Sequence.</span><span class="sxs-lookup"><span data-stu-id="9d2de-118">For more information, see about_Sequence.</span></span>

<span data-ttu-id="9d2de-119">Para executar um bloco de script paralelo em itens de uma coleção, use as palavras-chave ForEach ou ForEach-Parallel.</span><span class="sxs-lookup"><span data-stu-id="9d2de-119">To run a Parallel script block on items in a collection, use the ForEach or ForEach -Parallel keywords.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d2de-120">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9d2de-120">SEE ALSO</span></span>

<span data-ttu-id="9d2de-121">["Escrevendo um fluxo de trabalho de script"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="9d2de-121">["Writing a Script Workflow"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))</span></span>

[<span data-ttu-id="9d2de-122">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="9d2de-122">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="9d2de-123">about_ForEach-paralelo</span><span class="sxs-lookup"><span data-stu-id="9d2de-123">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="9d2de-124">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="9d2de-124">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="9d2de-125">about_Sequence</span><span class="sxs-lookup"><span data-stu-id="9d2de-125">about_Sequence</span></span>](about_Sequence.md)

[<span data-ttu-id="9d2de-126">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="9d2de-126">about_Workflows</span></span>](about_workflows.md)
