---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 52613dae3ba73227818c6c0dec40183ba20ce2a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598226"
---
# <span data-ttu-id="dd005-102">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="dd005-102">Remove-Job</span></span>

## <span data-ttu-id="dd005-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="dd005-103">SYNOPSIS</span></span>
<span data-ttu-id="dd005-104">Exclui um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd005-104">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="dd005-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dd005-105">SYNTAX</span></span>

### <span data-ttu-id="dd005-106">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="dd005-106">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Force] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dd005-107">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd005-107">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dd005-108">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd005-108">NameParameterSet</span></span>

```
Remove-Job [-Force] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dd005-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd005-109">InstanceIdParameterSet</span></span>

```
Remove-Job [-Force] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dd005-110">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd005-110">FilterParameterSet</span></span>

```
Remove-Job [-Force] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dd005-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd005-111">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dd005-112">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd005-112">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="dd005-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dd005-113">DESCRIPTION</span></span>

<span data-ttu-id="dd005-114">O `Remove-Job` cmdlet exclui trabalhos em segundo plano do PowerShell que foram iniciados pelo `Start-Job` cmdlet ou por cmdlets como `Invoke-Command` o que dão suporte ao parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="dd005-114">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="dd005-115">Você pode usar `Remove-Job` para excluir todos os trabalhos ou excluir trabalhos selecionados.</span><span class="sxs-lookup"><span data-stu-id="dd005-115">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="dd005-116">Os trabalhos são identificados por seu **nome**, **ID**, **ID de instância**, **comando** ou **estado**.</span><span class="sxs-lookup"><span data-stu-id="dd005-116">The jobs are identified by their **Name**, **ID**, **Instance ID**, **Command**, or **State**.</span></span> <span data-ttu-id="dd005-117">Ou, um objeto de trabalho pode ser enviado ao pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-117">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="dd005-118">Sem parâmetros ou valores de parâmetro, `Remove-Job` não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="dd005-118">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="dd005-119">Como o PowerShell 3,0, `Remove-Job` o pode excluir tipos de trabalhos personalizados, como trabalhos agendados e trabalhos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd005-119">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="dd005-120">Por exemplo, `Remove-Job` exclui o trabalho agendado, todas as instâncias do trabalho agendado no disco e os resultados de todas as instâncias de trabalho disparadas.</span><span class="sxs-lookup"><span data-stu-id="dd005-120">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="dd005-121">Se você tentar excluir um trabalho em execução, o `Remove-Job` falhará.</span><span class="sxs-lookup"><span data-stu-id="dd005-121">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="dd005-122">Use o `Stop-Job` cmdlet para interromper um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="dd005-122">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="dd005-123">Ou use `Remove-Job` com o parâmetro **Force** para excluir um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="dd005-123">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="dd005-124">Os trabalhos permanecem no cache de trabalhos globais até que você exclua o trabalho em segundo plano ou feche a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd005-124">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="dd005-125">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="dd005-125">EXAMPLES</span></span>

### <span data-ttu-id="dd005-126">Exemplo 1: excluir um trabalho usando seu nome</span><span class="sxs-lookup"><span data-stu-id="dd005-126">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="dd005-127">Este exemplo usa uma variável e o pipeline para excluir um trabalho por nome.</span><span class="sxs-lookup"><span data-stu-id="dd005-127">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="dd005-128">`Get-Job` usa o parâmetro **Name** para especificar o trabalho, **BatchJob**.</span><span class="sxs-lookup"><span data-stu-id="dd005-128">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob**.</span></span> <span data-ttu-id="dd005-129">O objeto de trabalho é armazenado na `$batch` variável.</span><span class="sxs-lookup"><span data-stu-id="dd005-129">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="dd005-130">O objeto no `$batch` é enviado ao pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-130">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="dd005-131">Uma alternativa é usar o parâmetro **Job** , como `Remove-Job -Job $batch` .</span><span class="sxs-lookup"><span data-stu-id="dd005-131">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="dd005-132">Exemplo 2: excluir todos os trabalhos em uma sessão</span><span class="sxs-lookup"><span data-stu-id="dd005-132">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="dd005-133">Neste exemplo, todos os trabalhos na sessão atual do PowerShell são excluídos.</span><span class="sxs-lookup"><span data-stu-id="dd005-133">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="dd005-134">`Get-Job` Obtém todos os trabalhos na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd005-134">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="dd005-135">Os objetos de trabalho são enviados ao pipeline para o `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-135">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="dd005-136">Exemplo 3: excluir trabalhos não iniciados</span><span class="sxs-lookup"><span data-stu-id="dd005-136">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="dd005-137">Este exemplo exclui todos os trabalhos da sessão atual do PowerShell que não foram iniciadas.</span><span class="sxs-lookup"><span data-stu-id="dd005-137">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="dd005-138">`Remove-Job` usa o parâmetro **State** para especificar o status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd005-138">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="dd005-139">Exemplo 4: excluir trabalhos usando um nome amigável</span><span class="sxs-lookup"><span data-stu-id="dd005-139">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="dd005-140">Este exemplo exclui todos os trabalhos da sessão atual com nomes amigáveis que terminam com \* batch \* \*, incluindo os trabalhos que estão em execução.</span><span class="sxs-lookup"><span data-stu-id="dd005-140">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="dd005-141">`Remove-Job` usa o parâmetro **Name** para especificar um padrão de nome de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd005-141">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="dd005-142">O padrão inclui o curinga asterisco ( `*` ) para localizar todos os nomes de trabalho que terminam com o **lote**.</span><span class="sxs-lookup"><span data-stu-id="dd005-142">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch**.</span></span> <span data-ttu-id="dd005-143">O parâmetro **Force** exclui trabalhos que executam o.</span><span class="sxs-lookup"><span data-stu-id="dd005-143">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="dd005-144">Exemplo 5: excluir um trabalho criado por Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="dd005-144">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="dd005-145">Este exemplo remove um trabalho que foi iniciado em um computador remoto usando `Invoke-Command` com o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="dd005-145">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="dd005-146">Como o exemplo usa o parâmetro **AsJob** , o objeto de trabalho é criado no computador local.</span><span class="sxs-lookup"><span data-stu-id="dd005-146">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="dd005-147">No entanto, o trabalho é executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="dd005-147">But, the job runs on a remote computer.</span></span> <span data-ttu-id="dd005-148">Como resultado, você deve usar comandos locais para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd005-148">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="dd005-149">`Invoke-Command` executa um trabalho no computador **SERVER01** .</span><span class="sxs-lookup"><span data-stu-id="dd005-149">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="dd005-150">O parâmetro **AsJob** executa o **scriptblock** como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="dd005-150">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="dd005-151">O objeto de trabalho é armazenado na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="dd005-151">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="dd005-152">O `$job` objeto Variable é enviado ao pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-152">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="dd005-153">Exemplo 6: excluir um trabalho que foi criado por Invoke-Command e Start-Job</span><span class="sxs-lookup"><span data-stu-id="dd005-153">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="dd005-154">Este exemplo mostra como remover um trabalho em um computador remoto que foi iniciado usando o `Invoke-Command` para executar o `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-154">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="dd005-155">O objeto de trabalho é criado no computador remoto e os comandos remotos são usados para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd005-155">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="dd005-156">Uma conexão persistente é necessária ao executar um `Start-Job` comando remoto.</span><span class="sxs-lookup"><span data-stu-id="dd005-156">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="dd005-157">`New-PSSession` Cria uma **PSSession**, uma conexão persistente, para o computador **Server01** .</span><span class="sxs-lookup"><span data-stu-id="dd005-157">`New-PSSession` creates a **PSSession**, a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="dd005-158">A conexão é salva na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="dd005-158">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="dd005-159">`Invoke-Command` conecta-se à sessão salva em `$S` .</span><span class="sxs-lookup"><span data-stu-id="dd005-159">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="dd005-160">O **scriptblock** usa `Start-Job` para iniciar um trabalho remoto.</span><span class="sxs-lookup"><span data-stu-id="dd005-160">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="dd005-161">O trabalho executa um `Get-Process` comando e usa o parâmetro **Name** para especificar um nome de trabalho amigável, **MyJob**.</span><span class="sxs-lookup"><span data-stu-id="dd005-161">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob**.</span></span>

<span data-ttu-id="dd005-162">`Invoke-Command` usa a `$S` sessão e executa o `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-162">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="dd005-163">O parâmetro **Name** especifica que o trabalho chamado **MyJob** é excluído.</span><span class="sxs-lookup"><span data-stu-id="dd005-163">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="dd005-164">Exemplo 7: excluir um trabalho usando sua InstanceId</span><span class="sxs-lookup"><span data-stu-id="dd005-164">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="dd005-165">Este exemplo remove um trabalho com base em sua **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="dd005-165">This example removes a job based on its **InstanceId**.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="dd005-166">`Start-Job` inicia um trabalho em segundo plano e o objeto de trabalho é salvo na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="dd005-166">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="dd005-167">O objeto no `$job` é enviado ao pipeline para `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="dd005-167">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="dd005-168">O parâmetro **Property** usa um asterisco ( `*` ) para especificar que todas as propriedades do objeto sejam exibidas em uma lista.</span><span class="sxs-lookup"><span data-stu-id="dd005-168">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="dd005-169">`Remove-Job` usa o parâmetro **InstanceId** para especificar o trabalho a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="dd005-169">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="dd005-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dd005-170">PARAMETERS</span></span>

### <span data-ttu-id="dd005-171">-Command</span><span class="sxs-lookup"><span data-stu-id="dd005-171">-Command</span></span>

<span data-ttu-id="dd005-172">Exclui os trabalhos que incluem as palavras especificadas no comando.</span><span class="sxs-lookup"><span data-stu-id="dd005-172">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="dd005-173">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="dd005-173">You can enter a comma-separated array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dd005-174">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dd005-174">-Confirm</span></span>

<span data-ttu-id="dd005-175">Solicita que você confirme antes que o `Remove-Job` seja executado.</span><span class="sxs-lookup"><span data-stu-id="dd005-175">Prompts you for confirmation before `Remove-Job` is run.</span></span>

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

### <span data-ttu-id="dd005-176">-Filter</span><span class="sxs-lookup"><span data-stu-id="dd005-176">-Filter</span></span>

<span data-ttu-id="dd005-177">Exclui os trabalhos que atendem a todas as condições estabelecidas na tabela de hash associada.</span><span class="sxs-lookup"><span data-stu-id="dd005-177">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="dd005-178">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd005-178">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="dd005-179">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="dd005-179">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="dd005-180">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-180">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="dd005-181">Este parâmetro é introduzido no PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="dd005-181">This parameter is introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dd005-182">-Force</span><span class="sxs-lookup"><span data-stu-id="dd005-182">-Force</span></span>

<span data-ttu-id="dd005-183">Exclui um trabalho mesmo que o estado do trabalho esteja **em execução**.</span><span class="sxs-lookup"><span data-stu-id="dd005-183">Deletes a job even if the job's state is **Running**.</span></span> <span data-ttu-id="dd005-184">Se o parâmetro **Force** não for especificado, o `Remove-Job` não excluirá os trabalhos em execução.</span><span class="sxs-lookup"><span data-stu-id="dd005-184">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, InstanceIdParameterSet, NameParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd005-185">-Id</span><span class="sxs-lookup"><span data-stu-id="dd005-185">-Id</span></span>

<span data-ttu-id="dd005-186">Exclui trabalhos em segundo plano com a **ID** especificada. Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="dd005-186">Deletes background jobs with the specified **Id**. You can enter a comma-separated array.</span></span> <span data-ttu-id="dd005-187">A **ID** do trabalho é um inteiro exclusivo que identifica um trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="dd005-187">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="dd005-188">Para localizar a **ID** de um trabalho, use `Get-Job` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="dd005-188">To find a job's **Id**, use `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="dd005-189">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="dd005-189">-InstanceId</span></span>

<span data-ttu-id="dd005-190">Exclui trabalhos com a **InstanceId** especificada.</span><span class="sxs-lookup"><span data-stu-id="dd005-190">Deletes jobs with the specified **InstanceId**.</span></span> <span data-ttu-id="dd005-191">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="dd005-191">You can enter a comma-separated array.</span></span> <span data-ttu-id="dd005-192">Uma **InstanceId** é um GUID exclusivo que identifica um trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd005-192">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="dd005-193">Para localizar a **InstanceId** de um trabalho, use `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-193">To find a job's **InstanceId**, use `Get-Job`.</span></span>

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

### <span data-ttu-id="dd005-194">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="dd005-194">-Job</span></span>

<span data-ttu-id="dd005-195">Especifica os trabalhos a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="dd005-195">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="dd005-196">Insira uma variável que contenha os trabalhos ou um comando que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="dd005-196">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="dd005-197">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="dd005-197">You can enter a comma-separated array.</span></span>

<span data-ttu-id="dd005-198">Você pode enviar objetos de trabalho para o pipeline para o `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-198">You can send job objects down the pipeline to `Remove-Job`.</span></span>

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

### <span data-ttu-id="dd005-199">-Name</span><span class="sxs-lookup"><span data-stu-id="dd005-199">-Name</span></span>

<span data-ttu-id="dd005-200">Somente exclui trabalhos com o nome amigável especificado.</span><span class="sxs-lookup"><span data-stu-id="dd005-200">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="dd005-201">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="dd005-201">Wildcards are permitted.</span></span> <span data-ttu-id="dd005-202">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="dd005-202">You can enter a comma-separated array.</span></span>

<span data-ttu-id="dd005-203">Nomes amigáveis para trabalhos não têm garantia de serem exclusivos, mesmo em uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd005-203">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="dd005-204">Use os parâmetros **WhatIf** e **Confirm** ao excluir arquivos por nome.</span><span class="sxs-lookup"><span data-stu-id="dd005-204">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="dd005-205">-Estado</span><span class="sxs-lookup"><span data-stu-id="dd005-205">-State</span></span>

<span data-ttu-id="dd005-206">Somente exclui trabalhos com o estado especificado.</span><span class="sxs-lookup"><span data-stu-id="dd005-206">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="dd005-207">Para excluir trabalhos com um estado de **em execução**, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="dd005-207">To delete jobs with a state of **Running**, use the **Force** parameter.</span></span>

<span data-ttu-id="dd005-208">Valores aceitos:</span><span class="sxs-lookup"><span data-stu-id="dd005-208">Accepted values:</span></span>

- <span data-ttu-id="dd005-209">AtBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dd005-209">AtBreakpoint</span></span>
- <span data-ttu-id="dd005-210">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="dd005-210">Blocked</span></span>
- <span data-ttu-id="dd005-211">Concluído</span><span class="sxs-lookup"><span data-stu-id="dd005-211">Completed</span></span>
- <span data-ttu-id="dd005-212">Desconectado</span><span class="sxs-lookup"><span data-stu-id="dd005-212">Disconnected</span></span>
- <span data-ttu-id="dd005-213">Failed (Falha)</span><span class="sxs-lookup"><span data-stu-id="dd005-213">Failed</span></span>
- <span data-ttu-id="dd005-214">NotStarted</span><span class="sxs-lookup"><span data-stu-id="dd005-214">NotStarted</span></span>
- <span data-ttu-id="dd005-215">Executando</span><span class="sxs-lookup"><span data-stu-id="dd005-215">Running</span></span>
- <span data-ttu-id="dd005-216">Parado</span><span class="sxs-lookup"><span data-stu-id="dd005-216">Stopped</span></span>
- <span data-ttu-id="dd005-217">Parando</span><span class="sxs-lookup"><span data-stu-id="dd005-217">Stopping</span></span>
- <span data-ttu-id="dd005-218">Suspenso</span><span class="sxs-lookup"><span data-stu-id="dd005-218">Suspended</span></span>
- <span data-ttu-id="dd005-219">Suspensão</span><span class="sxs-lookup"><span data-stu-id="dd005-219">Suspending</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dd005-220">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dd005-220">-WhatIf</span></span>

<span data-ttu-id="dd005-221">Mostra o que aconteceria se `Remove-Job` for executado.</span><span class="sxs-lookup"><span data-stu-id="dd005-221">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="dd005-222">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="dd005-222">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="dd005-223">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dd005-223">CommonParameters</span></span>

<span data-ttu-id="dd005-224">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dd005-224">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dd005-225">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dd005-225">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dd005-226">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="dd005-226">INPUTS</span></span>

### <span data-ttu-id="dd005-227">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="dd005-227">System.Management.Automation.Job</span></span>

<span data-ttu-id="dd005-228">Você pode enviar um objeto de trabalho para baixo do pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="dd005-228">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="dd005-229">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="dd005-229">OUTPUTS</span></span>

### <span data-ttu-id="dd005-230">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dd005-230">None</span></span>

<span data-ttu-id="dd005-231">`Remove-Job` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="dd005-231">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="dd005-232">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="dd005-232">NOTES</span></span>

<span data-ttu-id="dd005-233">Um trabalho do PowerShell cria um novo processo.</span><span class="sxs-lookup"><span data-stu-id="dd005-233">A PowerShell job creates a new process.</span></span> <span data-ttu-id="dd005-234">Quando o trabalho é concluído, o processo é encerrado.</span><span class="sxs-lookup"><span data-stu-id="dd005-234">When the job completes, the process exits.</span></span> <span data-ttu-id="dd005-235">Quando `Remove-Job` é executado, o estado do trabalho é removido.</span><span class="sxs-lookup"><span data-stu-id="dd005-235">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="dd005-236">Se um trabalho parar antes da conclusão e seu processo não tiver sido encerrado, o processo será encerrado de modo forçado.</span><span class="sxs-lookup"><span data-stu-id="dd005-236">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="dd005-237">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="dd005-237">RELATED LINKS</span></span>

[<span data-ttu-id="dd005-238">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="dd005-238">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="dd005-239">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="dd005-239">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="dd005-240">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="dd005-240">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="dd005-241">Get-Job</span><span class="sxs-lookup"><span data-stu-id="dd005-241">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="dd005-242">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="dd005-242">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="dd005-243">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="dd005-243">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="dd005-244">Start-Job</span><span class="sxs-lookup"><span data-stu-id="dd005-244">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="dd005-245">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="dd005-245">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="dd005-246">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="dd005-246">Wait-Job</span></span>](Wait-Job.md)

