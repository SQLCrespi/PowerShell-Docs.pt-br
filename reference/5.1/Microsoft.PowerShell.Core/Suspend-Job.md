---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 9b18782fae77fa0776aa2cfaa39b74a2292099d9
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388457"
---
# <span data-ttu-id="1a818-103">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-103">Suspend-Job</span></span>

## <span data-ttu-id="1a818-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1a818-104">SYNOPSIS</span></span>
<span data-ttu-id="1a818-105">Interrompe temporariamente tarefas de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-105">Temporarily stops workflow jobs.</span></span>

## <span data-ttu-id="1a818-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a818-106">SYNTAX</span></span>

### <span data-ttu-id="1a818-107">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="1a818-107">SessionIdParameterSet (Default)</span></span>

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1a818-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="1a818-108">JobParameterSet</span></span>

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1a818-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="1a818-109">NameParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1a818-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="1a818-110">InstanceIdParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1a818-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="1a818-111">FilterParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1a818-112">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="1a818-112">StateParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1a818-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a818-113">DESCRIPTION</span></span>

<span data-ttu-id="1a818-114">O `Suspend-Job` cmdlet suspende trabalhos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-114">The `Suspend-Job` cmdlet suspends workflow jobs.</span></span> <span data-ttu-id="1a818-115">Suspender significa interromper temporariamente ou pausar um trabalho de fluxo de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1a818-115">Suspend means to temporarily interrupt or pause a workflow job.</span></span> <span data-ttu-id="1a818-116">Este cmdlet permite que os usuários que estão executando fluxos de trabalho suspendam o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-116">This cmdlet allows users who are running workflows to suspend the workflow.</span></span> <span data-ttu-id="1a818-117">Ele complementa a atividade suspender fluxo de trabalho https://go.microsoft.com/fwlink/?LinkId=267141 , que é um comando no fluxo de trabalho que suspende o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-117">It complements the Suspend-Workflowhttps://go.microsoft.com/fwlink/?LinkId=267141 activity, which is a command in the workflow that suspends the workflow.</span></span>

<span data-ttu-id="1a818-118">O `Suspend-Job` cmdlet funciona apenas em trabalhos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-118">The `Suspend-Job` cmdlet works only on workflow jobs.</span></span> <span data-ttu-id="1a818-119">Ele não funciona em trabalhos em segundo plano padrão, como os que são iniciados usando o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a818-119">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="1a818-120">Para identificar uma tarefa de fluxo de trabalho, procure um valor de PSWorkflowJob na propriedade **PSJobTypeName** do trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-120">To identify a workflow job, look for a value of PSWorkflowJob in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="1a818-121">Para determinar se um determinado tipo de trabalho personalizado dá suporte ao `Suspend-Job` cmdlet, consulte os tópicos da ajuda para o tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="1a818-121">To determine whether a particular custom job type supports the `Suspend-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="1a818-122">Quando você suspende uma tarefa de fluxo de trabalho, essa tarefa é executada até o próximo ponto de verificação, suspendida e então retorna imediatamente como resultado um objeto de tarefa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-122">When you suspend a workflow job, the workflow job runs to the next checkpoint, suspends, and immediately returns a workflow job object.</span></span> <span data-ttu-id="1a818-123">Para aguardar a suspensão ser concluída antes de obter o trabalho, use o parâmetro **Wait** do `Suspend-Job` ou o `Wait-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a818-123">To wait for the suspension to complete before getting the job, use the **Wait** parameter of `Suspend-Job` or the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="1a818-124">Quando a tarefa de fluxo de trabalho é suspensa, o valor da propriedade **State** do trabalho é suspenso.</span><span class="sxs-lookup"><span data-stu-id="1a818-124">When the workflow job is suspended, the value of the **State** property of the job is Suspended.</span></span>

<span data-ttu-id="1a818-125">Suspender corretamente o trabalho depende dos pontos de verificação.</span><span class="sxs-lookup"><span data-stu-id="1a818-125">Suspending correctly relies on checkpoints.</span></span> <span data-ttu-id="1a818-126">O estado, os metadados e a saída atuais do trabalho são salvos no ponto de verificação, de modo que o trabalho do Workflow possa ser retomado sem perda de estado ou dados.</span><span class="sxs-lookup"><span data-stu-id="1a818-126">The current job state, metadata, and output are saved in the checkpoint so the workflow job can be resumed without loss of state or data.</span></span> <span data-ttu-id="1a818-127">Se o trabalho do Workflow não tiver pontos de verificação, ele não poderá ser suspenso corretamente.</span><span class="sxs-lookup"><span data-stu-id="1a818-127">If the workflow job does not have checkpoints, it cannot be suspended correctly.</span></span> <span data-ttu-id="1a818-128">Para adicionar pontos de verificação a um fluxo de trabalho em execução, use o parâmetro comum de fluxo de trabalho **PSPersist**.</span><span class="sxs-lookup"><span data-stu-id="1a818-128">To add checkpoints to a workflow that you are running, use the **PSPersist** workflow common parameter.</span></span> <span data-ttu-id="1a818-129">Você pode usar o parâmetro **Force** para suspender qualquer trabalho de workflow imediatamente e para suspender um trabalho de workflow que não tem pontos de verificação, mas a ação pode causar perda de estado e dados.</span><span class="sxs-lookup"><span data-stu-id="1a818-129">You can use the **Force** parameter to suspend any workflow job immediately and to suspend a workflow job that does not have checkpoints, but the action could cause loss of state and data.</span></span>

<span data-ttu-id="1a818-130">Antes de você usar um cmdlet de trabalho em um tipo de trabalho personalizado, como um trabalho de Workflow ( **PSWorkflowJob** ), importe o módulo que dá suporte ao tipo de trabalho personalizado, seja usando o `Import-Module` cmdlet ou usando um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="1a818-130">Before you use a Job cmdlet on a custom job type, such as a workflow job ( **PSWorkflowJob** ) import the module that supports the custom job type, either by using the `Import-Module` cmdlet or using or using a cmdlet in the module.</span></span>

<span data-ttu-id="1a818-131">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1a818-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="1a818-132">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1a818-132">EXAMPLES</span></span>

### <span data-ttu-id="1a818-133">Exemplo 1: suspender uma tarefa de fluxo de trabalho por nome</span><span class="sxs-lookup"><span data-stu-id="1a818-133">Example 1: Suspend a workflow job by name</span></span>

<span data-ttu-id="1a818-134">Este exemplo mostra como suspender uma tarefa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-134">This example shows how to suspend a workflow job.</span></span>

<span data-ttu-id="1a818-135">O primeiro comando cria o `Get-SystemLog` fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-135">The first command creates the `Get-SystemLog` workflow.</span></span> <span data-ttu-id="1a818-136">O fluxo de trabalho usa a `CheckPoint-Workflow` atividade para definir um ponto de verificação no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-136">The workflow uses the `CheckPoint-Workflow` activity to define a checkpoint in the workflow.</span></span>

<span data-ttu-id="1a818-137">O segundo comando usa o parâmetro **AsJob** , que é comum a todos os fluxos de trabalho para executar o `Get-SystemLog` Workflow como uma tarefa em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1a818-137">The second command uses the **AsJob** parameter that is common to all workflows to run the `Get-SystemLog` workflow as a background job.</span></span> <span data-ttu-id="1a818-138">O comando usa o parâmetro comum de fluxo de trabalho **JobName** para especificar um nome amigável para a tarefa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-138">The command uses the **JobName** workflow common parameter to specify a friendly name for the workflow job.</span></span>

<span data-ttu-id="1a818-139">O terceiro comando usa o `Get-Job` cmdlet para obter o `Get-SystemLogJob` trabalho de Workflow.</span><span class="sxs-lookup"><span data-stu-id="1a818-139">The third command uses the `Get-Job` cmdlet to get the `Get-SystemLogJob` workflow job.</span></span> <span data-ttu-id="1a818-140">A saída mostra que o valor da propriedade **PSJobTypeName** é PSWorkflowJob.</span><span class="sxs-lookup"><span data-stu-id="1a818-140">The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.</span></span>

<span data-ttu-id="1a818-141">O quarto comando usa o `Suspend-Job` cmdlet para suspender o `Get-SystemLogJob` trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-141">The fourth command uses the `Suspend-Job` cmdlet to suspend the `Get-SystemLogJob` job.</span></span> <span data-ttu-id="1a818-142">O trabalho é executado até o ponto de verificação e então é suspenso.</span><span class="sxs-lookup"><span data-stu-id="1a818-142">The job runs to the checkpoint and then suspends.</span></span>

```
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```


### <span data-ttu-id="1a818-143">Exemplo 2: suspender e retomar um trabalho de Workflow</span><span class="sxs-lookup"><span data-stu-id="1a818-143">Example 2: Suspend and resume a workflow job</span></span>

<span data-ttu-id="1a818-144">Este exemplo mostra como suspender e retomar uma tarefa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-144">This example shows how to suspend and resume a workflow job.</span></span>

<span data-ttu-id="1a818-145">O primeiro comando suspende o trabalho LogWorkflowJob. O comando retorna imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1a818-145">The first command suspends the LogWorkflowJob job.The command returns immediately.</span></span> <span data-ttu-id="1a818-146">A saída mostra que a tarefa de fluxo de trabalho ainda está em execução, mesmo que esteja sendo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1a818-146">The output shows that the workflow job is still running, even though it is being suspended.</span></span>

<span data-ttu-id="1a818-147">O segundo comando usa o `Get-Job` cmdlet para obter o trabalho LogWorkflowJob.</span><span class="sxs-lookup"><span data-stu-id="1a818-147">The second command uses the `Get-Job` cmdlet to get the LogWorkflowJob job.</span></span> <span data-ttu-id="1a818-148">A saída mostra que a tarefa de fluxo de trabalho foi suspensa com êxito.</span><span class="sxs-lookup"><span data-stu-id="1a818-148">The output shows that the workflow job suspended successfully.</span></span>

<span data-ttu-id="1a818-149">O terceiro comando usa o `Get-Job` cmdlet para obter o trabalho LogWorkflowJob e o `Resume-Job` cmdlet para retomá-lo.</span><span class="sxs-lookup"><span data-stu-id="1a818-149">The third command uses the `Get-Job` cmdlet to get the LogWorkflowJob job and the `Resume-Job` cmdlet to resume it.</span></span> <span data-ttu-id="1a818-150">A saída mostra que a tarefa de fluxo de trabalho foi retomada com êxito e está agora sendo executada.</span><span class="sxs-lookup"><span data-stu-id="1a818-150">The output shows that the workflow job resumed successfully and is now running.</span></span>

```
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```


### <span data-ttu-id="1a818-151">Exemplo 3: suspender uma tarefa de fluxo de trabalho em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="1a818-151">Example 3: Suspend a workflow job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

<span data-ttu-id="1a818-152">Esse comando usa o `Invoke-Command` cmdlet para suspender um trabalho de fluxo de trabalhos no computador remoto Srv01.</span><span class="sxs-lookup"><span data-stu-id="1a818-152">This command uses the `Invoke-Command` cmdlet to suspend a workflow job on the Srv01 remote computer.</span></span> <span data-ttu-id="1a818-153">O valor do parâmetro de **filtro** é uma tabela de hash que especifica um valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="1a818-153">The value of the **Filter** parameter is a hash table that specifies a CustomID value.</span></span>
<span data-ttu-id="1a818-154">Este **CustomID** é composto de metadados do trabalho ( **PSPrivateMetadata** ).</span><span class="sxs-lookup"><span data-stu-id="1a818-154">This **CustomID** is job metadata ( **PSPrivateMetadata** ).</span></span>

### <span data-ttu-id="1a818-155">Exemplo 4: aguardar a suspensão do trabalho de fluxo</span><span class="sxs-lookup"><span data-stu-id="1a818-155">Example 4: Wait for the workflow job to suspend</span></span>

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

<span data-ttu-id="1a818-156">Este comando suspende a tarefa de fluxo de trabalho VersionCheck.</span><span class="sxs-lookup"><span data-stu-id="1a818-156">This command suspends the VersionCheck workflow job.</span></span> <span data-ttu-id="1a818-157">O comando usa o parâmetro **Wait** para aguardar até a tarefa de fluxo de trabalho ser suspensa.</span><span class="sxs-lookup"><span data-stu-id="1a818-157">The command uses the **Wait** parameter to wait until the workflow job is suspended.</span></span> <span data-ttu-id="1a818-158">Quando a tarefa de fluxo de trabalho é executada no próximo ponto de verificação e é suspensa, o comando é concluído e retorna o objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-158">When the workflow job runs to the next checkpoint and is suspended, the command finishes and returns the job object.</span></span>

### <span data-ttu-id="1a818-159">Exemplo 5: forçar uma tarefa de fluxo de trabalho a suspender</span><span class="sxs-lookup"><span data-stu-id="1a818-159">Example 5: Force a workflow job to suspend</span></span>

```
PS C:\> Suspend-Job Maintenance -Force
```

<span data-ttu-id="1a818-160">Este comando suspende à força a tarefa de fluxo de trabalho Maintenance.</span><span class="sxs-lookup"><span data-stu-id="1a818-160">This command suspends the Maintenance workflow job forcibly.</span></span> <span data-ttu-id="1a818-161">O trabalho de manutenção não tem pontos de verificação.</span><span class="sxs-lookup"><span data-stu-id="1a818-161">The Maintenance job does not have checkpoints.</span></span> <span data-ttu-id="1a818-162">Ele não pode ser suspenso corretamente e pode não ser retomado corretamente.</span><span class="sxs-lookup"><span data-stu-id="1a818-162">It cannot be suspended correctly and might not resume correctly.</span></span>

## <span data-ttu-id="1a818-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a818-163">PARAMETERS</span></span>

### <span data-ttu-id="1a818-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="1a818-164">-Filter</span></span>

<span data-ttu-id="1a818-165">Especifica uma tabela de hash de condições.</span><span class="sxs-lookup"><span data-stu-id="1a818-165">Specifies a hash table of conditions.</span></span> <span data-ttu-id="1a818-166">Esse cmdlet suspende trabalhos que atendem a todas as condições.</span><span class="sxs-lookup"><span data-stu-id="1a818-166">This cmdlet suspends jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="1a818-167">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-167">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-168">-Force</span><span class="sxs-lookup"><span data-stu-id="1a818-168">-Force</span></span>

<span data-ttu-id="1a818-169">Suspende a tarefa de fluxo de trabalho imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1a818-169">Suspends the workflow job immediately.</span></span> <span data-ttu-id="1a818-170">Essa ação pode causar perda de estado e dados.</span><span class="sxs-lookup"><span data-stu-id="1a818-170">This action could cause a loss of state and data.</span></span>

<span data-ttu-id="1a818-171">Por padrão, `Suspend-Job` permite que o trabalho de workflow seja executado até o próximo ponto de verificação e, em seguida, o suspende.</span><span class="sxs-lookup"><span data-stu-id="1a818-171">By default, `Suspend-Job` lets the workflow job run until the next checkpoint and then suspends it.</span></span>
<span data-ttu-id="1a818-172">Você também pode usar esse parâmetro para suspender tarefas de fluxo de trabalho que não têm pontos de verificação.</span><span class="sxs-lookup"><span data-stu-id="1a818-172">You can also use this parameter to suspend workflow jobs that do not have checkpoints.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-173">-Id</span><span class="sxs-lookup"><span data-stu-id="1a818-173">-Id</span></span>

<span data-ttu-id="1a818-174">Especifica as IDs de trabalhos que esse cmdlet suspende.</span><span class="sxs-lookup"><span data-stu-id="1a818-174">Specifies the IDs of jobs that this cmdlet suspends.</span></span>

<span data-ttu-id="1a818-175">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="1a818-175">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="1a818-176">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="1a818-176">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="1a818-177">Você pode digitar uma ou mais IDs, separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="1a818-177">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="1a818-178">Para localizar a ID de um trabalho, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a818-178">To find the ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-179">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="1a818-179">-InstanceId</span></span>

<span data-ttu-id="1a818-180">Especifica as IDs de instância dos trabalhos que esse cmdlet suspende.</span><span class="sxs-lookup"><span data-stu-id="1a818-180">Specifies the instance IDs of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="1a818-181">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1a818-181">The default is all jobs.</span></span>

<span data-ttu-id="1a818-182">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="1a818-182">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="1a818-183">Para localizar a ID de instância de um trabalho, use `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="1a818-183">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-184">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="1a818-184">-Job</span></span>

<span data-ttu-id="1a818-185">Especifica os trabalhos de fluxo de trabalho que este cmdlet interrompe.</span><span class="sxs-lookup"><span data-stu-id="1a818-185">Specifies the workflow jobs that this cmdlet stops.</span></span> <span data-ttu-id="1a818-186">Insira uma variável que contenha as tarefas de fluxo de trabalho ou um comando que as obtenha.</span><span class="sxs-lookup"><span data-stu-id="1a818-186">Enter a variable that contains the workflow jobs or a command that gets the workflow jobs.</span></span> <span data-ttu-id="1a818-187">Você também pode canalizar trabalhos de fluxo de trabalho para o `Suspend-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a818-187">You can also pipe workflow jobs to the `Suspend-Job` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-188">-Name</span><span class="sxs-lookup"><span data-stu-id="1a818-188">-Name</span></span>

<span data-ttu-id="1a818-189">Especifica nomes amigáveis de trabalhos que esse cmdlet suspende.</span><span class="sxs-lookup"><span data-stu-id="1a818-189">Specifies friendly names of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="1a818-190">Insira um ou mais nomes de tarefas de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-190">Enter one or more workflow job names.</span></span>
<span data-ttu-id="1a818-191">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="1a818-191">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-192">-Estado</span><span class="sxs-lookup"><span data-stu-id="1a818-192">-State</span></span>

<span data-ttu-id="1a818-193">Especifica um estado de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-193">Specifies a job state.</span></span> <span data-ttu-id="1a818-194">Este cmdlet interrompe apenas os trabalhos no estado especificado.</span><span class="sxs-lookup"><span data-stu-id="1a818-194">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="1a818-195">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="1a818-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1a818-196">NotStarted</span><span class="sxs-lookup"><span data-stu-id="1a818-196">NotStarted</span></span>
- <span data-ttu-id="1a818-197">Executando</span><span class="sxs-lookup"><span data-stu-id="1a818-197">Running</span></span>
- <span data-ttu-id="1a818-198">Concluído</span><span class="sxs-lookup"><span data-stu-id="1a818-198">Completed</span></span>
- <span data-ttu-id="1a818-199">Falhou</span><span class="sxs-lookup"><span data-stu-id="1a818-199">Failed</span></span>
- <span data-ttu-id="1a818-200">Parado</span><span class="sxs-lookup"><span data-stu-id="1a818-200">Stopped</span></span>
- <span data-ttu-id="1a818-201">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="1a818-201">Blocked</span></span>
- <span data-ttu-id="1a818-202">Suspenso</span><span class="sxs-lookup"><span data-stu-id="1a818-202">Suspended</span></span>
- <span data-ttu-id="1a818-203">Desconectado</span><span class="sxs-lookup"><span data-stu-id="1a818-203">Disconnected</span></span>
- <span data-ttu-id="1a818-204">Suspensão</span><span class="sxs-lookup"><span data-stu-id="1a818-204">Suspending</span></span>
- <span data-ttu-id="1a818-205">Parando</span><span class="sxs-lookup"><span data-stu-id="1a818-205">Stopping</span></span>

<span data-ttu-id="1a818-206">`Suspend-Job` suspende somente trabalhos de fluxo de trabalho no estado **executando** .</span><span class="sxs-lookup"><span data-stu-id="1a818-206">`Suspend-Job` suspends only workflow jobs in the **Running** state.</span></span>

<span data-ttu-id="1a818-207">Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="1a818-207">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="1a818-208">-Wait</span></span>

<span data-ttu-id="1a818-209">Indica que esse cmdlet suprime o prompt de comando até que o trabalho de fluxo de trabalhos esteja no estado suspenso.</span><span class="sxs-lookup"><span data-stu-id="1a818-209">Indicates that this cmdlet suppresses the command prompt until the workflow job is in the suspended state.</span></span> <span data-ttu-id="1a818-210">Por padrão, `Suspend-Job` retorna imediatamente, mesmo que o trabalho de fluxo de trabalhos ainda não esteja no estado suspenso.</span><span class="sxs-lookup"><span data-stu-id="1a818-210">By default, `Suspend-Job` returns immediately, even if the workflow job is not yet in the suspended state.</span></span>

<span data-ttu-id="1a818-211">O parâmetro **Wait** é equivalente a canalizar um `Suspend-Job` comando para o `Wait-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a818-211">The **Wait** parameter is equivalent to piping a `Suspend-Job` command to the `Wait-Job` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-212">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1a818-212">-Confirm</span></span>

<span data-ttu-id="1a818-213">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a818-213">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-214">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1a818-214">-WhatIf</span></span>

<span data-ttu-id="1a818-215">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="1a818-215">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1a818-216">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="1a818-216">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a818-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1a818-217">CommonParameters</span></span>

<span data-ttu-id="1a818-218">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1a818-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a818-219">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1a818-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a818-220">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1a818-220">INPUTS</span></span>

### <span data-ttu-id="1a818-221">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="1a818-221">System.Management.Automation.Job</span></span>

<span data-ttu-id="1a818-222">Você pode canalizar todos os tipos de trabalhos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a818-222">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="1a818-223">No entanto, se `Suspend-Job` o obtiver um trabalho de um tipo sem suporte, ele retornará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="1a818-223">However, if `Suspend-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="1a818-224">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1a818-224">OUTPUTS</span></span>

### <span data-ttu-id="1a818-225">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="1a818-225">System.Management.Automation.Job</span></span>
<span data-ttu-id="1a818-226">Esse cmdlet retorna os trabalhos que ele suspendeu.</span><span class="sxs-lookup"><span data-stu-id="1a818-226">This cmdlet returns the jobs that it suspended.</span></span>

## <span data-ttu-id="1a818-227">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1a818-227">NOTES</span></span>

- <span data-ttu-id="1a818-228">O mecanismo e o local para salvar um trabalho suspenso podem variar, dependendo do tipo do trabalho.</span><span class="sxs-lookup"><span data-stu-id="1a818-228">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="1a818-229">Por exemplo, tarefas de fluxo de trabalho suspensas são salvas em um repositório de arquivo simples por padrão, mas também podem ser salvas em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1a818-229">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a database.</span></span>
- <span data-ttu-id="1a818-230">Se você enviar um trabalho de workflow que não esteja no estado executando, `Suspend-Job` o exibirá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="1a818-230">If you submit a workflow job that is not in the Running state, `Suspend-Job` displays a warning message.</span></span> <span data-ttu-id="1a818-231">Para suprimir o aviso, use o parâmetro de **aviso** comum com um valor de SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="1a818-231">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="1a818-232">Se um trabalho não for de um tipo que dá suporte à suspensão, `Suspend-Job` o retornará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="1a818-232">If a job is not of a type that supports suspending, `Suspend-Job` returns a terminating error.</span></span>

- <span data-ttu-id="1a818-233">Para localizar os trabalhos de fluxo de trabalho que estão suspensos, incluindo aqueles que foram suspensos por esse cmdlet, use o parâmetro **State** do `Get-Job` cmdlet para obter trabalhos de fluxo de trabalho no estado suspenso.</span><span class="sxs-lookup"><span data-stu-id="1a818-233">To find the workflow jobs that are suspended, including those that were suspended by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get workflow jobs in the Suspended state.</span></span>
- <span data-ttu-id="1a818-234">Alguns tipos de trabalho têm opções ou propriedades que impedem que o Windows PowerShell suspenda o trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="1a818-234">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="1a818-235">Se as tentativas de suspender o trabalho falharem, verifique se as opções e as propriedades do trabalho permitem a suspensão.</span><span class="sxs-lookup"><span data-stu-id="1a818-235">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="1a818-236">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1a818-236">RELATED LINKS</span></span>

[<span data-ttu-id="1a818-237">Get-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-237">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="1a818-238">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-238">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="1a818-239">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-239">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="1a818-240">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-240">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="1a818-241">Start-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-241">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="1a818-242">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-242">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="1a818-243">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-243">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="1a818-244">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="1a818-244">Wait-Job</span></span>](Wait-Job.md)
