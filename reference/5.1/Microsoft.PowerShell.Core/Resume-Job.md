---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193510"
---
# <span data-ttu-id="0e31e-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-103">Resume-Job</span></span>

## <span data-ttu-id="0e31e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0e31e-104">SYNOPSIS</span></span>
<span data-ttu-id="0e31e-105">Reinicia um trabalho suspenso.</span><span class="sxs-lookup"><span data-stu-id="0e31e-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="0e31e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e31e-106">SYNTAX</span></span>

### <span data-ttu-id="0e31e-107">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="0e31e-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e31e-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="0e31e-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e31e-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="0e31e-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e31e-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0e31e-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e31e-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="0e31e-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e31e-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="0e31e-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e31e-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e31e-113">DESCRIPTION</span></span>
<span data-ttu-id="0e31e-114">O cmdlet **retomar-Job** retoma um trabalho de fluxo que foi suspenso, por exemplo, usando o cmdlet Suspend-Job ou a atividade About_Suspend-Workflow.</span><span class="sxs-lookup"><span data-stu-id="0e31e-114">The **Resume-Job** cmdlet resumes a workflow job that was suspended, such as by using the Suspend-Job cmdlet or the about_Suspend-Workflow activity.</span></span>
<span data-ttu-id="0e31e-115">Quando uma tarefa de fluxo de trabalho é retomada, o mecanismo de trabalho reconstrói o estado, os metadados e a saída de recursos salvos, como pontos de verificação.</span><span class="sxs-lookup"><span data-stu-id="0e31e-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span>
<span data-ttu-id="0e31e-116">O trabalho é reiniciado sem qualquer perda de estado ou dados.</span><span class="sxs-lookup"><span data-stu-id="0e31e-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="0e31e-117">O estado do trabalho é alterado de **Suspended** para **Running** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-117">The job state is changed from **Suspended** to **Running** .</span></span>

<span data-ttu-id="0e31e-118">Use os parâmetros de **retomar-Job** para selecionar trabalhos por nome, ID, ID de instância ou canal de um objeto de trabalho, como um retornado pelo cmdlet Get-Job, para **retomar-Job** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-118">Use the parameters of **Resume-Job** to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the Get-Job cmdlet, to **Resume-Job** .</span></span>
<span data-ttu-id="0e31e-119">Você também pode usar um filtro de propriedade para selecionar um trabalho a ser retomado.</span><span class="sxs-lookup"><span data-stu-id="0e31e-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="0e31e-120">Por padrão, o **Resume-Job** retorna resultados imediatamente, mesmo existindo a possibilidade de nem todos os trabalhos terem sido retomados ainda.</span><span class="sxs-lookup"><span data-stu-id="0e31e-120">By default, **Resume-Job** returns immediately, even though all jobs might not yet be resumed.</span></span>
<span data-ttu-id="0e31e-121">Para suprimir o prompt de comando até todos os trabalhos especificados serem reiniciados, use o parâmetro *Wait* .</span><span class="sxs-lookup"><span data-stu-id="0e31e-121">To suppress the command prompt until all specified jobs are resumed, use the *Wait* parameter.</span></span>

<span data-ttu-id="0e31e-122">O cmdlet **Resume-Job** funciona somente em tipos de trabalho personalizados, como tarefas de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-122">The **Resume-Job** cmdlet works only on custom job types, such as workflow jobs.</span></span>
<span data-ttu-id="0e31e-123">Ele não funciona em trabalhos em segundo plano padrão, como os que são iniciados usando o cmdlet Start-Job.</span><span class="sxs-lookup"><span data-stu-id="0e31e-123">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>
<span data-ttu-id="0e31e-124">Se você enviar um trabalho de um tipo sem suporte, o **Resume-Job** gera um erro de terminação e deixará de ser executado.</span><span class="sxs-lookup"><span data-stu-id="0e31e-124">If you submit a job of an unsupported type, **Resume-Job** generates a terminating error and stops running.</span></span>

<span data-ttu-id="0e31e-125">Para identificar uma tarefa de fluxo de trabalho, procure um valor de **PSWorkflowJob** na propriedade **PSJobTypeName** do trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="0e31e-126">Para determinar se um determinado tipo de trabalho personalizado dá suporte ao cmdlet **resume-Job** , consulte os tópicos da ajuda para o tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="0e31e-126">To determine whether a particular custom job type supports the **Resume-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="0e31e-127">Antes de usar um cmdlet de trabalho em um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado, seja usando o cmdlet Import-Module ou obtendo ou usando um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="0e31e-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the Import-Module cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="0e31e-128">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0e31e-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0e31e-129">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0e31e-129">EXAMPLES</span></span>

### <span data-ttu-id="0e31e-130">Exemplo 1: retomar um trabalho por ID</span><span class="sxs-lookup"><span data-stu-id="0e31e-130">Example 1: Resume a job by ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

<span data-ttu-id="0e31e-131">Os comandos neste exemplo confirmam que o trabalho é uma tarefa de fluxo de trabalho suspensa e, em seguida, reiniciam o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span>

### <span data-ttu-id="0e31e-132">Exemplo 2: retomar um trabalho por nome</span><span class="sxs-lookup"><span data-stu-id="0e31e-132">Example 2: Resume a job by name</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

<span data-ttu-id="0e31e-133">Este comando usa o parâmetro *Name* para retomar vários trabalhos de fluxo de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="0e31e-133">This command uses the *Name* parameter to resume several workflow jobs on the local computer.</span></span>

### <span data-ttu-id="0e31e-134">Exemplo 3: usar valores de propriedade personalizada</span><span class="sxs-lookup"><span data-stu-id="0e31e-134">Example 3: Use custom property values</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

<span data-ttu-id="0e31e-135">Este comando usa o valor de uma propriedade personalizada para identificar a tarefa de fluxo de trabalho a retomar.</span><span class="sxs-lookup"><span data-stu-id="0e31e-135">This command uses the value of a custom property to identify the workflow job to resume.</span></span>
<span data-ttu-id="0e31e-136">Ele usa o parâmetro *Filter* para identificar a tarefa de fluxo de trabalho pela sua propriedade **CustomID** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-136">It uses the *Filter* parameter to identify the workflow job by its **CustomID** property.</span></span>
<span data-ttu-id="0e31e-137">Ele também usa o parâmetro *State* para verificar se a tarefa de fluxo de trabalho está suspensa, antes de tentar retomá-la.</span><span class="sxs-lookup"><span data-stu-id="0e31e-137">It also uses the *State* parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

### <span data-ttu-id="0e31e-138">Exemplo 4: retomar todos os trabalhos suspensos em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="0e31e-138">Example 4: Resume all suspended jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="0e31e-139">Este comando retoma todos os trabalhos suspensos no computador remoto Srv01.</span><span class="sxs-lookup"><span data-stu-id="0e31e-139">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

<span data-ttu-id="0e31e-140">O comando usa o cmdlet Invoke-Command para executar um comando no computador Srv01.</span><span class="sxs-lookup"><span data-stu-id="0e31e-140">The command uses the Invoke-Command cmdlet to run a command on the Srv01 computer.</span></span>
<span data-ttu-id="0e31e-141">O comando remoto usa o parâmetro *State* do cmdlet **Get-Job** para obter todos os trabalhos suspensos no computador.</span><span class="sxs-lookup"><span data-stu-id="0e31e-141">The remote command uses the *State* parameter of the **Get-Job** cmdlet to get all suspended jobs on the computer.</span></span>
<span data-ttu-id="0e31e-142">Um operador de pipeline (|) envia os trabalhos suspensos para o cmdlet **Resume-Job** , que retoma sua execução.</span><span class="sxs-lookup"><span data-stu-id="0e31e-142">A pipeline operator (|) sends the suspended jobs to the **Resume-Job** cmdlet, which resumes them.</span></span>

### <span data-ttu-id="0e31e-143">Exemplo 5: aguardar a retomada dos trabalhos</span><span class="sxs-lookup"><span data-stu-id="0e31e-143">Example 5: Wait for jobs to resume</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

<span data-ttu-id="0e31e-144">Esse comando usa o parâmetro *Wait* para direcionar **retomar-Job** para retornar somente depois que todos os trabalhos especificados forem retomados.</span><span class="sxs-lookup"><span data-stu-id="0e31e-144">This command uses the *Wait* parameter to direct **Resume-Job** to return only after all specified jobs are resumed.</span></span>
<span data-ttu-id="0e31e-145">O parâmetro *Wait* é especialmente útil em scripts que assumem que os trabalhos são retomados antes do script continuar.</span><span class="sxs-lookup"><span data-stu-id="0e31e-145">The *Wait* parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

### <span data-ttu-id="0e31e-146">Exemplo 6: retomar um fluxo de trabalho que se suspende</span><span class="sxs-lookup"><span data-stu-id="0e31e-146">Example 6: Resume a workflow that suspends itself</span></span>

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
PS C:\> Receive-Job -Name Job8
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
        PSComputerName    : Server01
```

<span data-ttu-id="0e31e-147">O cmdlet **retomar-Job** permite que você retome um trabalho de workflow que foi suspenso usando a atividade **suspender-Workflow** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-147">The **Resume-Job** cmdlet lets you resume a workflow job that was suspend by using the **Suspend-Workflow** activity.</span></span>
<span data-ttu-id="0e31e-148">Essa atividade suspende um fluxo de trabalho de dentro de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-148">This activity suspends a workflow from within a workflow.</span></span>
<span data-ttu-id="0e31e-149">Isso só é válido em fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-149">It is valid only in workflows.</span></span>

<span data-ttu-id="0e31e-150">Para obter informações sobre o Suspend-Workflow, consulte about_Suspend-Workflow.</span><span class="sxs-lookup"><span data-stu-id="0e31e-150">For information about the Suspend-Workflow, see about_Suspend-Workflow.</span></span>

## <span data-ttu-id="0e31e-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e31e-151">PARAMETERS</span></span>

### <span data-ttu-id="0e31e-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="0e31e-152">-Filter</span></span>
<span data-ttu-id="0e31e-153">Especifica uma tabela de hash de condições.</span><span class="sxs-lookup"><span data-stu-id="0e31e-153">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="0e31e-154">Esse cmdlet retoma os trabalhos que atendem a todas as condições na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="0e31e-154">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="0e31e-155">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-155">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="0e31e-156">-Id</span><span class="sxs-lookup"><span data-stu-id="0e31e-156">-Id</span></span>
<span data-ttu-id="0e31e-157">Especifica uma matriz de IDs para trabalhos que esse cmdlet retoma.</span><span class="sxs-lookup"><span data-stu-id="0e31e-157">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="0e31e-158">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0e31e-158">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="0e31e-159">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0e31e-159">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="0e31e-160">Você pode digitar uma ou mais IDs, separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="0e31e-160">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="0e31e-161">Para localizar a ID de um trabalho, execute **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-161">To find the ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="0e31e-162">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0e31e-162">-InstanceId</span></span>
<span data-ttu-id="0e31e-163">Especifica uma matriz de IDs de instância dos trabalhos que esse cmdlet retoma.</span><span class="sxs-lookup"><span data-stu-id="0e31e-163">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="0e31e-164">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="0e31e-164">The default is all jobs.</span></span>

<span data-ttu-id="0e31e-165">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="0e31e-165">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="0e31e-166">Para localizar a ID de instância de um trabalho, execute **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-166">To find the instance ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="0e31e-167">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="0e31e-167">-Job</span></span>
<span data-ttu-id="0e31e-168">Especifica os trabalhos a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="0e31e-168">Specifies the jobs to be resumed.</span></span>
<span data-ttu-id="0e31e-169">Insira uma variável que contenha os trabalhos ou um comando que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="0e31e-169">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="0e31e-170">Também é possível direcionar trabalhos para o cmdlet **Resume-Job** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-170">You can also pipe jobs to the **Resume-Job** cmdlet.</span></span>

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

### <span data-ttu-id="0e31e-171">-Name</span><span class="sxs-lookup"><span data-stu-id="0e31e-171">-Name</span></span>
<span data-ttu-id="0e31e-172">Especifica uma matriz de nomes amigáveis de trabalhos que esse cmdlet retoma.</span><span class="sxs-lookup"><span data-stu-id="0e31e-172">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="0e31e-173">Insira um ou mais nomes de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-173">Enter one or more job names.</span></span>
<span data-ttu-id="0e31e-174">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e31e-174">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0e31e-175">-Estado</span><span class="sxs-lookup"><span data-stu-id="0e31e-175">-State</span></span>
<span data-ttu-id="0e31e-176">Especifica o estado dos trabalhos a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="0e31e-176">Specifies the state of jobs to resume.</span></span>
<span data-ttu-id="0e31e-177">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="0e31e-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0e31e-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="0e31e-178">NotStarted</span></span>
- <span data-ttu-id="0e31e-179">Executando</span><span class="sxs-lookup"><span data-stu-id="0e31e-179">Running</span></span>
- <span data-ttu-id="0e31e-180">Concluído</span><span class="sxs-lookup"><span data-stu-id="0e31e-180">Completed</span></span>
- <span data-ttu-id="0e31e-181">Falhou</span><span class="sxs-lookup"><span data-stu-id="0e31e-181">Failed</span></span>
- <span data-ttu-id="0e31e-182">Parado</span><span class="sxs-lookup"><span data-stu-id="0e31e-182">Stopped</span></span>
- <span data-ttu-id="0e31e-183">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="0e31e-183">Blocked</span></span>
- <span data-ttu-id="0e31e-184">Suspenso</span><span class="sxs-lookup"><span data-stu-id="0e31e-184">Suspended</span></span>
- <span data-ttu-id="0e31e-185">Desconectado</span><span class="sxs-lookup"><span data-stu-id="0e31e-185">Disconnected</span></span>
- <span data-ttu-id="0e31e-186">Suspensão</span><span class="sxs-lookup"><span data-stu-id="0e31e-186">Suspending</span></span>
- <span data-ttu-id="0e31e-187">Parando</span><span class="sxs-lookup"><span data-stu-id="0e31e-187">Stopping</span></span>

<span data-ttu-id="0e31e-188">Esse cmdlet retoma apenas os trabalhos no estado **suspenso** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-188">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="0e31e-189">Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="0e31e-189">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="0e31e-190">-Wait</span><span class="sxs-lookup"><span data-stu-id="0e31e-190">-Wait</span></span>
<span data-ttu-id="0e31e-191">Indica que esse cmdlet suprime o prompt de comando até que todos os resultados do trabalho sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="0e31e-191">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span>
<span data-ttu-id="0e31e-192">Por padrão, esse cmdlet retorna imediatamente os resultados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0e31e-192">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="0e31e-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e31e-193">-Confirm</span></span>
<span data-ttu-id="0e31e-194">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e31e-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e31e-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e31e-195">-WhatIf</span></span>
<span data-ttu-id="0e31e-196">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0e31e-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0e31e-197">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0e31e-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e31e-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e31e-198">CommonParameters</span></span>
<span data-ttu-id="0e31e-199">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e31e-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e31e-200">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0e31e-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e31e-201">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0e31e-201">INPUTS</span></span>

### <span data-ttu-id="0e31e-202">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-202">System.Management.Automation.Job</span></span>
<span data-ttu-id="0e31e-203">Você pode canalizar todos os tipos de trabalhos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e31e-203">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="0e31e-204">Se **retomar-Job** obtiver um trabalho de um tipo sem suporte, ele retornará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="0e31e-204">If **Resume-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="0e31e-205">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0e31e-205">OUTPUTS</span></span>

### <span data-ttu-id="0e31e-206">Nenhum, System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-206">None, System.Management.Automation.Job</span></span>
<span data-ttu-id="0e31e-207">Esse cmdlet retorna os trabalhos que ele tenta retomar, se você usar o parâmetro *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="0e31e-207">This cmdlet returns the jobs that it tries to resume, if you use the *PassThru* parameter.</span></span>
<span data-ttu-id="0e31e-208">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0e31e-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0e31e-209">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0e31e-209">NOTES</span></span>

* <span data-ttu-id="0e31e-210">**Resume-o trabalho** só pode retomar trabalhos suspensos.</span><span class="sxs-lookup"><span data-stu-id="0e31e-210">**Resume-Job** can only resume jobs that are suspended.</span></span> <span data-ttu-id="0e31e-211">Se você enviar um trabalho em um estado diferente, o **Resume-Job** executa a operação de retomada no trabalho, mas gera um aviso para notificá-lo de que o trabalho não pôde ser retomado.</span><span class="sxs-lookup"><span data-stu-id="0e31e-211">If you submit a job in a different state, **Resume-Job** runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="0e31e-212">Para suprimir o aviso, use o parâmetro de *aviso* comum com um valor de SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="0e31e-212">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>
* <span data-ttu-id="0e31e-213">Se um trabalho não for de um tipo que dá suporte à retomada, como um trabalho de Workflow ( **PSWorkflowJob** ), **retomar-Job** retornará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="0e31e-213">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), **Resume-Job** returns a terminating error.</span></span>
* <span data-ttu-id="0e31e-214">O mecanismo e o local para salvar um trabalho suspenso podem variar, dependendo do tipo do trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e31e-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="0e31e-215">Por exemplo, tarefas de fluxo de trabalho suspensas são salvas em um repositório de arquivo simples por padrão, mas também podem ser salvas em um banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="0e31e-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
* <span data-ttu-id="0e31e-216">Quando você retoma um trabalho, o estado do trabalho muda de **Suspended** para **Running** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-216">When you resume a job, the job state changes from **Suspended** to **Running** .</span></span> <span data-ttu-id="0e31e-217">Para localizar os trabalhos que estão em execução, incluindo aqueles que foram retomados por esse cmdlet, use o parâmetro *State* do cmdlet **Get-Job** para obter trabalhos no estado **executando** .</span><span class="sxs-lookup"><span data-stu-id="0e31e-217">To find the jobs that are running, including those that were resumed by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get jobs in the **Running** state.</span></span>
* <span data-ttu-id="0e31e-218">Alguns tipos de trabalho têm opções ou propriedades que impedem que o Windows PowerShell suspenda o trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="0e31e-218">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="0e31e-219">Se as tentativas de suspender o trabalho falharem, verifique se as opções e as propriedades do trabalho permitem a suspensão.</span><span class="sxs-lookup"><span data-stu-id="0e31e-219">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="0e31e-220">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0e31e-220">RELATED LINKS</span></span>

[<span data-ttu-id="0e31e-221">Get-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-221">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="0e31e-222">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-222">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="0e31e-223">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-223">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="0e31e-224">Start-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-224">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="0e31e-225">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-225">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="0e31e-226">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-226">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="0e31e-227">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="0e31e-227">Wait-Job</span></span>](Wait-Job.md)
