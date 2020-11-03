---
description: Descreve a `Suspend-Workflow` atividade, que suspende o fluxo de trabalho no qual a atividade é exibida.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Fluxo de trabalho about_Suspend
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195800"
---
# <a name="about-suspend-workflow"></a><span data-ttu-id="ed3b5-104">Sobre Suspend-Workflow</span><span class="sxs-lookup"><span data-stu-id="ed3b5-104">About Suspend-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="ed3b5-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="ed3b5-105">Short description</span></span>

<span data-ttu-id="ed3b5-106">Descreve a `Suspend-Workflow` atividade, que suspende o fluxo de trabalho no qual a atividade é exibida.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-106">Describes the `Suspend-Workflow` activity, which suspends the workflow in which the activity appears.</span></span>

## <a name="long-description"></a><span data-ttu-id="ed3b5-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="ed3b5-107">Long description</span></span>

<span data-ttu-id="ed3b5-108">A `Suspend-Workflow` atividade interrompe temporariamente o processamento de fluxo de trabalho de dentro do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-108">The `Suspend-Workflow` activity temporarily stops workflow processing from within the workflow.</span></span> <span data-ttu-id="ed3b5-109">Antes de suspender, o fluxo de trabalho do Windows PowerShell usa um ponto de verificação para que o estado e os dados do fluxo de trabalho sejam preservados e o fluxo de trabalho possa continuar do ponto de suspensão.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-109">Before suspending, Windows PowerShell Workflow takes a checkpoint so the workflow's state and data are preserved and the workflow can resume from the suspension point.</span></span>

<span data-ttu-id="ed3b5-110">Para retomar o fluxo de trabalho, o usuário que executa o fluxo de trabalho usa o `Resume-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-110">To resume the workflow, the user running the workflow uses the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="ed3b5-111">Não é possível retomar um fluxo de trabalho de dentro do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-111">You can't resume a workflow from within the workflow.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed3b5-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed3b5-112">Syntax</span></span>

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a><span data-ttu-id="ed3b5-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="ed3b5-113">Detailed description</span></span>

<span data-ttu-id="ed3b5-114">O `Suspend-Workflow` interrompe temporariamente o fluxo de trabalho e retorna um objeto de Job que representa o trabalho de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-114">The `Suspend-Workflow` temporarily stops the workflow and returns a job object that represents the workflow job.</span></span> <span data-ttu-id="ed3b5-115">Um objeto de trabalho é retornado mesmo que você não tenha executado o fluxo de trabalho como um Job.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-115">A job object is returned even if you didn't run the workflow as a job.</span></span> <span data-ttu-id="ed3b5-116">Por exemplo, como usando o parâmetro comum de fluxo de trabalho **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="ed3b5-116">For example, such as by using the **AsJob** workflow common parameter.</span></span> <span data-ttu-id="ed3b5-117">O estado do trabalho é **suspenso** .</span><span class="sxs-lookup"><span data-stu-id="ed3b5-117">The job state is **Suspended** .</span></span>

<span data-ttu-id="ed3b5-118">Você pode usar os cmdlets de trabalho do para gerenciar o trabalho suspenso de Workflow.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-118">You can use the job cmdlets to manage the suspended workflow job.</span></span> <span data-ttu-id="ed3b5-119">Use o cmdlet para retomar o trabalho de workflow `Resume-Job` .</span><span class="sxs-lookup"><span data-stu-id="ed3b5-119">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span>

<span data-ttu-id="ed3b5-120">Quando você retomar o trabalho de fluxo de trabalho, o workflow será retomado no comando que segue a `Suspend-Workflow` atividade.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-120">When you resume the workflow job, the workflow resumes at the command that follows the `Suspend-Workflow` activity.</span></span>

<span data-ttu-id="ed3b5-121">Por exemplo, o fluxo de trabalho a seguir inclui a `Suspend-Workflow` atividade.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-121">For example, the following workflow includes the `Suspend-Workflow` activity.</span></span>
<span data-ttu-id="ed3b5-122">Quando você executa o fluxo de trabalho, ele executa a `Get-Date` atividade, salva sua saída na `$a` variável e, em seguida, suspende o fluxo de trabalho e retorna um objeto de Job que representa o fluxo de trabalho suspenso.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-122">When you run the workflow, it runs the `Get-Date` activity, saves its output in the `$a` variable, and then suspends the workflow, and returns a job object that represents the suspended workflow.</span></span> <span data-ttu-id="ed3b5-123">O tipo de trabalho é **PSWorkflowJob** .</span><span class="sxs-lookup"><span data-stu-id="ed3b5-123">The job type is **PSWorkflowJob** .</span></span>

<span data-ttu-id="ed3b5-124">Você pode usar os cmdlets de trabalho, como `Get-Job` , para gerenciar o trabalho de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-124">You can use the job cmdlets, such as `Get-Job`, to manage the workflow job.</span></span>

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a><span data-ttu-id="ed3b5-125">Retomando um trabalho de fluxo</span><span class="sxs-lookup"><span data-stu-id="ed3b5-125">Resuming a workflow job</span></span>

<span data-ttu-id="ed3b5-126">Use o cmdlet para retomar o trabalho de workflow `Resume-Job` .</span><span class="sxs-lookup"><span data-stu-id="ed3b5-126">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="ed3b5-127">O cmdlet `Resume-Job` retorna o objeto de trabalho do fluxo de trabalho imediatamente, mesmo se ele ainda não puder ser retomado.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-127">The `Resume-Job` cmdlet returns the workflow job object immediately, even though it might not yet be resumed.</span></span> <span data-ttu-id="ed3b5-128">Para aguardar o trabalho ser retomado, use o parâmetro **Wait** ou use o `Get-Job` cmdlet para obter o objeto de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-128">To wait for the job to be resumed, use the **Wait** parameter, or use the `Get-Job` cmdlet to get the current job object.</span></span>

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a><span data-ttu-id="ed3b5-129">Obtendo a saída de um trabalho de fluxo</span><span class="sxs-lookup"><span data-stu-id="ed3b5-129">Getting the output of a workflow job</span></span>

<span data-ttu-id="ed3b5-130">Para obter a saída de um trabalho de workflow, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-130">To get the output of a workflow job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="ed3b5-131">A saída mostra que o fluxo de trabalho foi retomado no comando que seguiu o `Suspend-Workflow` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-131">The output shows that the workflow resumed at the command that followed the `Suspend-Workflow` cmdlet.</span></span> <span data-ttu-id="ed3b5-132">O valor da `$a` variável, que foi populada antes da suspensão, está disponível para o fluxo de trabalho quando ele é retomado.</span><span class="sxs-lookup"><span data-stu-id="ed3b5-132">The value of the `$a` variable, which was populated before the suspension, is available to the workflow when it resumes.</span></span>

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a><span data-ttu-id="ed3b5-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed3b5-133">See also</span></span>

[<span data-ttu-id="ed3b5-134">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="ed3b5-134">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="ed3b5-135">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed3b5-135">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="ed3b5-136">Cmdlets [PSWorkflow](xref:PSWorkflow)</span><span class="sxs-lookup"><span data-stu-id="ed3b5-136">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="ed3b5-137">Guia de fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="ed3b5-137">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="ed3b5-138">Escrevendo um Fluxo de Trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed3b5-138">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
