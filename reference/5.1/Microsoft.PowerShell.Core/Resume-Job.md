---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388528"
---
# <span data-ttu-id="f16ed-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-103">Resume-Job</span></span>

## <span data-ttu-id="f16ed-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f16ed-104">SYNOPSIS</span></span>
<span data-ttu-id="f16ed-105">Reinicia um trabalho suspenso.</span><span class="sxs-lookup"><span data-stu-id="f16ed-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="f16ed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f16ed-106">SYNTAX</span></span>

### <span data-ttu-id="f16ed-107">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="f16ed-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f16ed-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="f16ed-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f16ed-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="f16ed-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f16ed-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="f16ed-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f16ed-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="f16ed-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f16ed-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="f16ed-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f16ed-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f16ed-113">DESCRIPTION</span></span>

<span data-ttu-id="f16ed-114">O `Resume-Job` cmdlet retoma uma tarefa de fluxo de trabalho que foi suspensa, por exemplo, usando o `Suspend-Job` cmdlet ou a atividade [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) .</span><span class="sxs-lookup"><span data-stu-id="f16ed-114">The `Resume-Job` cmdlet resumes a workflow job that was suspended, such as by using the `Suspend-Job` cmdlet or the [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) activity.</span></span> <span data-ttu-id="f16ed-115">Quando uma tarefa de fluxo de trabalho é retomada, o mecanismo de trabalho reconstrói o estado, os metadados e a saída de recursos salvos, como pontos de verificação.</span><span class="sxs-lookup"><span data-stu-id="f16ed-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span> <span data-ttu-id="f16ed-116">O trabalho é reiniciado sem qualquer perda de estado ou dados.</span><span class="sxs-lookup"><span data-stu-id="f16ed-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="f16ed-117">O estado do trabalho é alterado de **Suspended** para **Running**.</span><span class="sxs-lookup"><span data-stu-id="f16ed-117">The job state is changed from **Suspended** to **Running**.</span></span>

<span data-ttu-id="f16ed-118">Use os parâmetros de `Resume-Job` para selecionar trabalhos por nome, ID, ID de instância ou canal de um objeto de trabalho, como um retornado pelo `Get-Job` cmdlet, para `Resume-Job` .</span><span class="sxs-lookup"><span data-stu-id="f16ed-118">Use the parameters of `Resume-Job` to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the `Get-Job` cmdlet, to `Resume-Job`.</span></span> <span data-ttu-id="f16ed-119">Você também pode usar um filtro de propriedade para selecionar um trabalho a ser retomado.</span><span class="sxs-lookup"><span data-stu-id="f16ed-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="f16ed-120">Por padrão, `Resume-Job` retorna imediatamente, embora todos os trabalhos ainda não tenham sido retomados.</span><span class="sxs-lookup"><span data-stu-id="f16ed-120">By default, `Resume-Job` returns immediately, even though all jobs might not yet be resumed.</span></span> <span data-ttu-id="f16ed-121">Para suprimir o prompt de comando até todos os trabalhos especificados serem reiniciados, use o parâmetro **Wait**.</span><span class="sxs-lookup"><span data-stu-id="f16ed-121">To suppress the command prompt until all specified jobs are resumed, use the **Wait** parameter.</span></span>

<span data-ttu-id="f16ed-122">O `Resume-Job` cmdlet funciona apenas em tipos de trabalhos personalizados, como trabalhos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-122">The `Resume-Job` cmdlet works only on custom job types, such as workflow jobs.</span></span> <span data-ttu-id="f16ed-123">Ele não funciona em trabalhos em segundo plano padrão, como os que são iniciados usando o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f16ed-123">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="f16ed-124">Se você enviar um trabalho de um tipo sem suporte, `Resume-Job` o gerará um erro de encerramento e interromperá a execução.</span><span class="sxs-lookup"><span data-stu-id="f16ed-124">If you submit a job of an unsupported type, `Resume-Job` generates a terminating error and stops running.</span></span>

<span data-ttu-id="f16ed-125">Para identificar uma tarefa de fluxo de trabalho, procure um valor de **PSWorkflowJob** na propriedade **PSJobTypeName** do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="f16ed-126">Para determinar se um determinado tipo de trabalho personalizado dá suporte ao `Resume-Job` cmdlet, consulte os tópicos da ajuda para o tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="f16ed-126">To determine whether a particular custom job type supports the `Resume-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="f16ed-127">Antes de usar um cmdlet de trabalho em um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado, seja usando o `Import-Module` cmdlet ou obtendo ou usando um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="f16ed-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the `Import-Module` cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="f16ed-128">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f16ed-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f16ed-129">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f16ed-129">EXAMPLES</span></span>

### <span data-ttu-id="f16ed-130">Exemplo 1: retomar um trabalho por ID</span><span class="sxs-lookup"><span data-stu-id="f16ed-130">Example 1: Resume a job by ID</span></span>

<span data-ttu-id="f16ed-131">Os comandos neste exemplo confirmam que o trabalho é uma tarefa de fluxo de trabalho suspensa e, em seguida, reiniciam o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span> <span data-ttu-id="f16ed-132">O primeiro comando usa o `Get-Job` cmdlet para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-132">The first command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="f16ed-133">A saída mostra que o trabalho é uma tarefa de fluxo de trabalho suspensa.</span><span class="sxs-lookup"><span data-stu-id="f16ed-133">The output shows that the job is a suspended workflow job.</span></span> <span data-ttu-id="f16ed-134">O segundo comando usa o parâmetro **ID** do `Resume-Job` cmdlet para retomar o trabalho com um valor de **ID** de 4.</span><span class="sxs-lookup"><span data-stu-id="f16ed-134">The second command uses the **Id** parameter of the `Resume-Job` cmdlet to resume the job with an **Id** value of 4.</span></span>

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### <span data-ttu-id="f16ed-135">Exemplo 2: retomar um trabalho por nome</span><span class="sxs-lookup"><span data-stu-id="f16ed-135">Example 2: Resume a job by name</span></span>

<span data-ttu-id="f16ed-136">Este comando usa o parâmetro **Name** para retomar vários trabalhos de fluxo de trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="f16ed-136">This command uses the **Name** parameter to resume several workflow jobs on the local computer.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### <span data-ttu-id="f16ed-137">Exemplo 3: usar valores de propriedade personalizada</span><span class="sxs-lookup"><span data-stu-id="f16ed-137">Example 3: Use custom property values</span></span>

<span data-ttu-id="f16ed-138">Este comando usa o valor de uma propriedade personalizada para identificar a tarefa de fluxo de trabalho a retomar.</span><span class="sxs-lookup"><span data-stu-id="f16ed-138">This command uses the value of a custom property to identify the workflow job to resume.</span></span> <span data-ttu-id="f16ed-139">Ele usa o parâmetro **Filter** para identificar a tarefa de fluxo de trabalho pela sua propriedade **CustomID**.</span><span class="sxs-lookup"><span data-stu-id="f16ed-139">It uses the **Filter** parameter to identify the workflow job by its **CustomID** property.</span></span> <span data-ttu-id="f16ed-140">Ele também usa o parâmetro **State** para verificar se a tarefa de fluxo de trabalho está suspensa, antes de tentar retomá-la.</span><span class="sxs-lookup"><span data-stu-id="f16ed-140">It also uses the **State** parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### <span data-ttu-id="f16ed-141">Exemplo 4: retomar todos os trabalhos suspensos em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="f16ed-141">Example 4: Resume all suspended jobs on a remote computer</span></span>

<span data-ttu-id="f16ed-142">Este comando retoma todos os trabalhos suspensos no computador remoto Srv01.</span><span class="sxs-lookup"><span data-stu-id="f16ed-142">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="f16ed-143">O comando usa o `Invoke-Command` cmdlet para executar um comando no computador Srv01.</span><span class="sxs-lookup"><span data-stu-id="f16ed-143">The command uses the `Invoke-Command` cmdlet to run a command on the Srv01 computer.</span></span> <span data-ttu-id="f16ed-144">O comando remoto usa o parâmetro **State** do `Get-Job` cmdlet para obter todos os trabalhos suspensos no computador.</span><span class="sxs-lookup"><span data-stu-id="f16ed-144">The remote command uses the **State** parameter of the `Get-Job` cmdlet to get all suspended jobs on the computer.</span></span> <span data-ttu-id="f16ed-145">Um operador de pipeline ( `|` ) envia os trabalhos suspensos para o `Resume-Job` cmdlet, que os retoma.</span><span class="sxs-lookup"><span data-stu-id="f16ed-145">A pipeline operator (`|`) sends the suspended jobs to the `Resume-Job` cmdlet, which resumes them.</span></span>

### <span data-ttu-id="f16ed-146">Exemplo 5: aguardar a retomada dos trabalhos</span><span class="sxs-lookup"><span data-stu-id="f16ed-146">Example 5: Wait for jobs to resume</span></span>

<span data-ttu-id="f16ed-147">Esse comando usa o parâmetro **Wait** para direcionar `Resume-Job` para retornar somente depois que todos os trabalhos especificados forem retomados.</span><span class="sxs-lookup"><span data-stu-id="f16ed-147">This command uses the **Wait** parameter to direct `Resume-Job` to return only after all specified jobs are resumed.</span></span> <span data-ttu-id="f16ed-148">O parâmetro **Wait** é especialmente útil em scripts que assumem que os trabalhos são retomados antes do script continuar.</span><span class="sxs-lookup"><span data-stu-id="f16ed-148">The **Wait** parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### <span data-ttu-id="f16ed-149">Exemplo 6: retomar um fluxo de trabalho que se suspende</span><span class="sxs-lookup"><span data-stu-id="f16ed-149">Example 6: Resume a workflow that suspends itself</span></span>

<span data-ttu-id="f16ed-150">Este exemplo de código mostra a `Suspend-Workflow` atividade em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-150">This code sample shows the `Suspend-Workflow` activity in a workflow.</span></span>

<span data-ttu-id="f16ed-151">O `Test-Suspend` fluxo de trabalho no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f16ed-151">The `Test-Suspend` workflow on the Server01 computer.</span></span> <span data-ttu-id="f16ed-152">Quando você executa o fluxo de trabalho, o fluxo de trabalho executa a `Get-Date` atividade e armazena o resultado na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="f16ed-152">When you run the workflow, the workflow runs the `Get-Date` activity and stores the result in the `$a` variable.</span></span> <span data-ttu-id="f16ed-153">Em seguida, ele executa a `Suspend-Workflow` atividade.</span><span class="sxs-lookup"><span data-stu-id="f16ed-153">Then it runs the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="f16ed-154">Em resposta, ele usa um ponto de verificação, suspende o fluxo de trabalho e retorna um objeto de tarefa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-154">In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.</span></span> <span data-ttu-id="f16ed-155">`Suspend-Workflow` Retorna um objeto de trabalho do Workflow, mesmo que ele não seja executado explicitamente como um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-155">`Suspend-Workflow` returns a workflow job object even if the workflow is not explicitly run as a job.</span></span>

<span data-ttu-id="f16ed-156">`Resume-Job` retoma o `Test-Suspend` fluxo de trabalho em Job8.</span><span class="sxs-lookup"><span data-stu-id="f16ed-156">`Resume-Job` resumes the `Test-Suspend` workflow in Job8.</span></span> <span data-ttu-id="f16ed-157">Ele usa o parâmetro **Wait** para adiar o prompt de comando até o trabalho ser retomado.</span><span class="sxs-lookup"><span data-stu-id="f16ed-157">It uses the **Wait** parameter to hold the command prompt until the job is resumed.</span></span>

<span data-ttu-id="f16ed-158">O `Receive-Job` cmdlet obtém os resultados do `Test-Suspend` fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-158">The `Receive-Job` cmdlet gets the results of the `Test-Suspend` workflow.</span></span> <span data-ttu-id="f16ed-159">O comando final no fluxo de trabalho retorna um objeto **TimeSpan** que representa o tempo decorrido entre a data e a hora atuais e a data e hora que foram salvas na `$a` variável antes de o fluxo de trabalho ser suspenso.</span><span class="sxs-lookup"><span data-stu-id="f16ed-159">The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the `$a` variable before the workflow was suspended.</span></span>

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

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

<span data-ttu-id="f16ed-160">O `Resume-Job` cmdlet permite que você retome um trabalho de workflow que foi suspenso usando a `Suspend-Workflow` atividade.</span><span class="sxs-lookup"><span data-stu-id="f16ed-160">The `Resume-Job` cmdlet lets you resume a workflow job that was suspend by using the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="f16ed-161">Essa atividade suspende um fluxo de trabalho de dentro de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-161">This activity suspends a workflow from within a workflow.</span></span> <span data-ttu-id="f16ed-162">Isso só é válido em fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-162">It is valid only in workflows.</span></span>

<span data-ttu-id="f16ed-163">Para obter informações sobre o `Suspend-Workflow` , consulte about_Suspend-Workflow] (.. /PSWorkflow/about/about_Suspend-Workflow. MD).</span><span class="sxs-lookup"><span data-stu-id="f16ed-163">For information about the `Suspend-Workflow`, see about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md).</span></span>

## <span data-ttu-id="f16ed-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f16ed-164">PARAMETERS</span></span>

### <span data-ttu-id="f16ed-165">-Filter</span><span class="sxs-lookup"><span data-stu-id="f16ed-165">-Filter</span></span>

<span data-ttu-id="f16ed-166">Especifica uma tabela de hash de condições.</span><span class="sxs-lookup"><span data-stu-id="f16ed-166">Specifies a hash table of conditions.</span></span> <span data-ttu-id="f16ed-167">Esse cmdlet retoma os trabalhos que atendem a todas as condições na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="f16ed-167">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="f16ed-168">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-168">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="f16ed-169">-Id</span><span class="sxs-lookup"><span data-stu-id="f16ed-169">-Id</span></span>

<span data-ttu-id="f16ed-170">Especifica uma matriz de IDs para trabalhos que esse cmdlet retoma.</span><span class="sxs-lookup"><span data-stu-id="f16ed-170">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="f16ed-171">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f16ed-171">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="f16ed-172">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f16ed-172">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="f16ed-173">Você pode digitar uma ou mais IDs, separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="f16ed-173">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="f16ed-174">Para localizar a ID de um trabalho, execute `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="f16ed-174">To find the ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="f16ed-175">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="f16ed-175">-InstanceId</span></span>

<span data-ttu-id="f16ed-176">Especifica uma matriz de IDs de instância dos trabalhos que esse cmdlet retoma.</span><span class="sxs-lookup"><span data-stu-id="f16ed-176">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="f16ed-177">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="f16ed-177">The default is all jobs.</span></span>

<span data-ttu-id="f16ed-178">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="f16ed-178">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="f16ed-179">Para localizar a ID de instância de um trabalho, execute `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="f16ed-179">To find the instance ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="f16ed-180">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="f16ed-180">-Job</span></span>

<span data-ttu-id="f16ed-181">Especifica os trabalhos a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="f16ed-181">Specifies the jobs to be resumed.</span></span> <span data-ttu-id="f16ed-182">Insira uma variável que contenha os trabalhos ou um comando que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="f16ed-182">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="f16ed-183">Você também pode canalizar trabalhos para o `Resume-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f16ed-183">You can also pipe jobs to the `Resume-Job` cmdlet.</span></span>

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

### <span data-ttu-id="f16ed-184">-Name</span><span class="sxs-lookup"><span data-stu-id="f16ed-184">-Name</span></span>

<span data-ttu-id="f16ed-185">Especifica uma matriz de nomes amigáveis de trabalhos que esse cmdlet retoma.</span><span class="sxs-lookup"><span data-stu-id="f16ed-185">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="f16ed-186">Insira um ou mais nomes de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-186">Enter one or more job names.</span></span>
<span data-ttu-id="f16ed-187">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f16ed-187">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f16ed-188">-Estado</span><span class="sxs-lookup"><span data-stu-id="f16ed-188">-State</span></span>

<span data-ttu-id="f16ed-189">Especifica o estado dos trabalhos a serem retomados.</span><span class="sxs-lookup"><span data-stu-id="f16ed-189">Specifies the state of jobs to resume.</span></span> <span data-ttu-id="f16ed-190">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="f16ed-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f16ed-191">NotStarted</span><span class="sxs-lookup"><span data-stu-id="f16ed-191">NotStarted</span></span>
- <span data-ttu-id="f16ed-192">Executando</span><span class="sxs-lookup"><span data-stu-id="f16ed-192">Running</span></span>
- <span data-ttu-id="f16ed-193">Concluído</span><span class="sxs-lookup"><span data-stu-id="f16ed-193">Completed</span></span>
- <span data-ttu-id="f16ed-194">Falhou</span><span class="sxs-lookup"><span data-stu-id="f16ed-194">Failed</span></span>
- <span data-ttu-id="f16ed-195">Parado</span><span class="sxs-lookup"><span data-stu-id="f16ed-195">Stopped</span></span>
- <span data-ttu-id="f16ed-196">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="f16ed-196">Blocked</span></span>
- <span data-ttu-id="f16ed-197">Suspenso</span><span class="sxs-lookup"><span data-stu-id="f16ed-197">Suspended</span></span>
- <span data-ttu-id="f16ed-198">Desconectado</span><span class="sxs-lookup"><span data-stu-id="f16ed-198">Disconnected</span></span>
- <span data-ttu-id="f16ed-199">Suspensão</span><span class="sxs-lookup"><span data-stu-id="f16ed-199">Suspending</span></span>
- <span data-ttu-id="f16ed-200">Parando</span><span class="sxs-lookup"><span data-stu-id="f16ed-200">Stopping</span></span>

<span data-ttu-id="f16ed-201">Esse cmdlet retoma apenas os trabalhos no estado **suspenso** .</span><span class="sxs-lookup"><span data-stu-id="f16ed-201">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="f16ed-202">Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="f16ed-202">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="f16ed-203">-Wait</span><span class="sxs-lookup"><span data-stu-id="f16ed-203">-Wait</span></span>

<span data-ttu-id="f16ed-204">Indica que esse cmdlet suprime o prompt de comando até que todos os resultados do trabalho sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="f16ed-204">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span> <span data-ttu-id="f16ed-205">Por padrão, esse cmdlet retorna imediatamente os resultados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f16ed-205">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="f16ed-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f16ed-206">-Confirm</span></span>

<span data-ttu-id="f16ed-207">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f16ed-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f16ed-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f16ed-208">-WhatIf</span></span>

<span data-ttu-id="f16ed-209">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f16ed-209">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f16ed-210">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f16ed-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f16ed-211">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f16ed-211">CommonParameters</span></span>

<span data-ttu-id="f16ed-212">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f16ed-212">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f16ed-213">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f16ed-213">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f16ed-214">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f16ed-214">INPUTS</span></span>

### <span data-ttu-id="f16ed-215">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-215">System.Management.Automation.Job</span></span>

<span data-ttu-id="f16ed-216">Você pode canalizar todos os tipos de trabalhos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f16ed-216">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="f16ed-217">Se `Resume-Job` o obtiver um trabalho de um tipo sem suporte, ele retornará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="f16ed-217">If `Resume-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="f16ed-218">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f16ed-218">OUTPUTS</span></span>

### <span data-ttu-id="f16ed-219">Nenhum, System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-219">None, System.Management.Automation.Job</span></span>

<span data-ttu-id="f16ed-220">Esse cmdlet retorna os trabalhos que ele tenta retomar, se você usar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="f16ed-220">This cmdlet returns the jobs that it tries to resume, if you use the **PassThru** parameter.</span></span>
<span data-ttu-id="f16ed-221">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f16ed-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f16ed-222">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f16ed-222">NOTES</span></span>

- <span data-ttu-id="f16ed-223">`Resume-Job` Só é possível retomar os trabalhos que estão suspensos.</span><span class="sxs-lookup"><span data-stu-id="f16ed-223">`Resume-Job` can only resume jobs that are suspended.</span></span> <span data-ttu-id="f16ed-224">Se você enviar um trabalho em um estado diferente, `Resume-Job` o executará a operação de retomada no trabalho, mas gerará um aviso para notificá-lo de que o trabalho não pôde ser retomado.</span><span class="sxs-lookup"><span data-stu-id="f16ed-224">If you submit a job in a different state, `Resume-Job` runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="f16ed-225">Para suprimir o aviso, use o parâmetro de **aviso** comum com um valor de SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="f16ed-225">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>
- <span data-ttu-id="f16ed-226">Se um trabalho não for de um tipo que dá suporte à retomada, como um trabalho de Workflow ( **PSWorkflowJob** ), `Resume-Job` retornará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="f16ed-226">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), `Resume-Job` returns a terminating error.</span></span>
- <span data-ttu-id="f16ed-227">O mecanismo e o local para salvar um trabalho suspenso podem variar, dependendo do tipo do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f16ed-227">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="f16ed-228">Por exemplo, tarefas de fluxo de trabalho suspensas são salvas em um repositório de arquivo simples por padrão, mas também podem ser salvas em um banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="f16ed-228">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
- <span data-ttu-id="f16ed-229">Quando você retoma um trabalho, o estado do trabalho muda de **Suspended** para **Running**.</span><span class="sxs-lookup"><span data-stu-id="f16ed-229">When you resume a job, the job state changes from **Suspended** to **Running**.</span></span> <span data-ttu-id="f16ed-230">Para localizar os trabalhos em execução, incluindo aqueles que foram retomados por esse cmdlet, use o parâmetro **State** do `Get-Job` cmdlet para obter trabalhos no estado **executando** .</span><span class="sxs-lookup"><span data-stu-id="f16ed-230">To find the jobs that are running, including those that were resumed by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get jobs in the **Running** state.</span></span>
- <span data-ttu-id="f16ed-231">Alguns tipos de trabalho têm opções ou propriedades que impedem que o Windows PowerShell suspenda o trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="f16ed-231">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="f16ed-232">Se as tentativas de suspender o trabalho falharem, verifique se as opções e as propriedades do trabalho permitem a suspensão.</span><span class="sxs-lookup"><span data-stu-id="f16ed-232">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="f16ed-233">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f16ed-233">RELATED LINKS</span></span>

[<span data-ttu-id="f16ed-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="f16ed-235">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="f16ed-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="f16ed-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="f16ed-238">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-238">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="f16ed-239">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-239">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="f16ed-240">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="f16ed-240">Wait-Job</span></span>](Wait-Job.md)
