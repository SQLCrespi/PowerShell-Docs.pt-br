---
description: Descreve a `Sequence` palavra-chave que executa as atividades selecionadas sequencialmente.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195805"
---
# <a name="about-sequence"></a><span data-ttu-id="bf8dc-104">Sobre a sequência</span><span class="sxs-lookup"><span data-stu-id="bf8dc-104">About Sequence</span></span>

## <a name="short-description"></a><span data-ttu-id="bf8dc-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="bf8dc-105">Short description</span></span>

<span data-ttu-id="bf8dc-106">Descreve a `Sequence` palavra-chave que executa as atividades selecionadas sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-106">Describes the `Sequence` keyword that runs selected activities sequentially.</span></span>

## <a name="long-description"></a><span data-ttu-id="bf8dc-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="bf8dc-107">Long description</span></span>

<span data-ttu-id="bf8dc-108">A `Sequence` palavra-chave executa as atividades de fluxo de trabalho selecionadas em sequência.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-108">The `Sequence` keyword runs selected workflow activities sequentially.</span></span> <span data-ttu-id="bf8dc-109">As atividades de fluxo de trabalho são executadas na ordem em que aparecem e não são executadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-109">Workflow activities run in the order that they appear and do not run concurrently.</span></span> <span data-ttu-id="bf8dc-110">A `Sequence` palavra-chave só é válida em um fluxo de trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-110">The `Sequence` keyword is only valid in a PowerShell Workflow.</span></span>

<span data-ttu-id="bf8dc-111">A `Sequence` palavra-chave é usada em um `Parallel` bloco de script para executar os comandos selecionados em sequência.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-111">The `Sequence` keyword is used in a `Parallel` script block to run selected commands sequentially.</span></span>

<span data-ttu-id="bf8dc-112">Como as atividades de fluxo de trabalho são executadas em sequência por padrão, a `Sequence` palavra-chave só é eficaz em um `Parallel` bloco de script.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-112">Because workflow activities run sequentially by default, the `Sequence` keyword is only effective in a `Parallel` script block.</span></span> <span data-ttu-id="bf8dc-113">Se a `Sequence` palavra-chave não estiver incluída em um `Parallel` bloco de script, ela será válida, mas ineficaz.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-113">If the `Sequence` keyword isn't included in a `Parallel` script block, it's valid but ineffective.</span></span>

<span data-ttu-id="bf8dc-114">O `Sequence` bloco de script permite executar mais comandos em paralelo, permitindo que você execute os comandos dependentes sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-114">The `Sequence` script block lets you run more commands in parallel by allowing you to run dependent commands sequentially.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf8dc-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf8dc-115">Syntax</span></span>

### <a name="workflow-using-sequence"></a><span data-ttu-id="bf8dc-116">Fluxo de trabalho usando sequência</span><span class="sxs-lookup"><span data-stu-id="bf8dc-116">Workflow using Sequence</span></span>

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a><span data-ttu-id="bf8dc-117">Fluxo de trabalho usando Parallel e Sequence</span><span class="sxs-lookup"><span data-stu-id="bf8dc-117">Workflow using Parallel and Sequence</span></span>

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a><span data-ttu-id="bf8dc-118">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="bf8dc-118">Detailed description</span></span>

<span data-ttu-id="bf8dc-119">Os comandos em um bloco de script `Parallel` podem ser executados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-119">The commands in a `Parallel` script block can run concurrently.</span></span> <span data-ttu-id="bf8dc-120">A ordem de execução não é determinada.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-120">The order in which they run is not determined.</span></span> <span data-ttu-id="bf8dc-121">Esse recurso melhora o desempenho de um fluxo de trabalho de script.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-121">This feature improves the performance of a script workflow.</span></span>

<span data-ttu-id="bf8dc-122">Você pode usar um `Sequence` bloco de script para executar as atividades selecionadas sequencialmente, embora as atividades apareçam em um `Parallel` bloco de script.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-122">You can use a `Sequence` script block to run selected activities sequentially, even though the activities appear in a `Parallel` script block.</span></span>

<span data-ttu-id="bf8dc-123">As atividades em um `Sequence` bloco de script são executadas consecutivamente na ordem em que estão listadas.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-123">The activities in a `Sequence` script block run consecutively in the order that they are listed.</span></span> <span data-ttu-id="bf8dc-124">Uma atividade em um `Sequence` bloco de script só inicia após a conclusão da atividade anterior.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-124">An activity in a `Sequence` script block starts only after the previous activity completes.</span></span>

<span data-ttu-id="bf8dc-125">No entanto, quando o `Sequence` bloco de script aparece em um `Parallel` bloco de script, a ordem na qual o `Sequence` bloco de script é executado não é determinada.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-125">However, when the `Sequence` script block appears in a `Parallel` script block, the order in which the `Sequence` script block runs isn't determined.</span></span> <span data-ttu-id="bf8dc-126">Ele pode ser executado antes, depois ou simultaneamente com outras atividades no bloco de `Parallel` script.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-126">It might run before, after, or concurrent with other activities in the `Parallel` script block.</span></span>

<span data-ttu-id="bf8dc-127">Por exemplo, o fluxo de trabalho a seguir inclui um `Parallel` bloco de script que executa atividades que obtêm processos e serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-127">For example, the following workflow includes a `Parallel` script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="bf8dc-128">O `Parallel` bloco de script contém um `Sequence` bloco de script que obtém informações de um arquivo e usa as informações como entrada para um script.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-128">The `Parallel` script block contains a `Sequence` script block that gets information from a file and uses the information as input to a script.</span></span>

<span data-ttu-id="bf8dc-129">Os `Get-Process` `Get-Service` comandos, e relacionados ao hotfix são independentes um do outro.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-129">The `Get-Process`, `Get-Service`, and hotfix-related commands are independent of each other.</span></span> <span data-ttu-id="bf8dc-130">Os comandos podem ser executados simultaneamente ou em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-130">The commands can run concurrently or in any order.</span></span> <span data-ttu-id="bf8dc-131">No entanto, o comando que obtém as informações do hotfix deve ser executado antes do comando que o utiliza.</span><span class="sxs-lookup"><span data-stu-id="bf8dc-131">But, the command that gets the hotfix information must run before the command that uses it.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="bf8dc-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="bf8dc-132">See also</span></span>

[<span data-ttu-id="bf8dc-133">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="bf8dc-133">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="bf8dc-134">about_ForEach-paralelo</span><span class="sxs-lookup"><span data-stu-id="bf8dc-134">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="bf8dc-135">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="bf8dc-135">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="bf8dc-136">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="bf8dc-136">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="bf8dc-137">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="bf8dc-137">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="bf8dc-138">Criar um fluxo de trabalho pelo uso de um script do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf8dc-138">Creating a Workflow by Using a Windows PowerShell Script</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
