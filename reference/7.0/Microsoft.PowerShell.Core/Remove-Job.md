---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 52db5da9057023ce9a687e1d11b0534afaabdad9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193433"
---
# <span data-ttu-id="a2601-103">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a2601-103">Remove-Job</span></span>

## <span data-ttu-id="a2601-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a2601-104">SYNOPSIS</span></span>
<span data-ttu-id="a2601-105">Exclui um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2601-105">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="a2601-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2601-106">SYNTAX</span></span>

### <span data-ttu-id="a2601-107">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="a2601-107">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Force] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2601-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="a2601-108">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2601-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="a2601-109">NameParameterSet</span></span>

```
Remove-Job [-Force] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2601-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="a2601-110">InstanceIdParameterSet</span></span>

```
Remove-Job [-Force] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2601-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="a2601-111">FilterParameterSet</span></span>

```
Remove-Job [-Force] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2601-112">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="a2601-112">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2601-113">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="a2601-113">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a2601-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2601-114">DESCRIPTION</span></span>

<span data-ttu-id="a2601-115">O `Remove-Job` cmdlet exclui trabalhos em segundo plano do PowerShell que foram iniciados pelo `Start-Job` cmdlet ou por cmdlets como `Invoke-Command` o que dão suporte ao parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="a2601-115">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="a2601-116">Você pode usar `Remove-Job` para excluir todos os trabalhos ou excluir trabalhos selecionados.</span><span class="sxs-lookup"><span data-stu-id="a2601-116">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="a2601-117">Os trabalhos são identificados por seu **nome** , **ID** , **ID de instância** , **comando** ou **estado** .</span><span class="sxs-lookup"><span data-stu-id="a2601-117">The jobs are identified by their **Name** , **ID** , **Instance ID** , **Command** , or **State** .</span></span> <span data-ttu-id="a2601-118">Ou, um objeto de trabalho pode ser enviado ao pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-118">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="a2601-119">Sem parâmetros ou valores de parâmetro, `Remove-Job` não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="a2601-119">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="a2601-120">Como o PowerShell 3,0, `Remove-Job` o pode excluir tipos de trabalhos personalizados, como trabalhos agendados e trabalhos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2601-120">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="a2601-121">Por exemplo, `Remove-Job` exclui o trabalho agendado, todas as instâncias do trabalho agendado no disco e os resultados de todas as instâncias de trabalho disparadas.</span><span class="sxs-lookup"><span data-stu-id="a2601-121">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="a2601-122">Se você tentar excluir um trabalho em execução, o `Remove-Job` falhará.</span><span class="sxs-lookup"><span data-stu-id="a2601-122">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="a2601-123">Use o `Stop-Job` cmdlet para interromper um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="a2601-123">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="a2601-124">Ou use `Remove-Job` com o parâmetro **Force** para excluir um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="a2601-124">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="a2601-125">Os trabalhos permanecem no cache de trabalhos globais até que você exclua o trabalho em segundo plano ou feche a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2601-125">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="a2601-126">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a2601-126">EXAMPLES</span></span>

### <span data-ttu-id="a2601-127">Exemplo 1: excluir um trabalho usando seu nome</span><span class="sxs-lookup"><span data-stu-id="a2601-127">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="a2601-128">Este exemplo usa uma variável e o pipeline para excluir um trabalho por nome.</span><span class="sxs-lookup"><span data-stu-id="a2601-128">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="a2601-129">`Get-Job` usa o parâmetro **Name** para especificar o trabalho, **BatchJob** .</span><span class="sxs-lookup"><span data-stu-id="a2601-129">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob** .</span></span> <span data-ttu-id="a2601-130">O objeto de trabalho é armazenado na `$batch` variável.</span><span class="sxs-lookup"><span data-stu-id="a2601-130">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="a2601-131">O objeto no `$batch` é enviado ao pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-131">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="a2601-132">Uma alternativa é usar o parâmetro **Job** , como `Remove-Job -Job $batch` .</span><span class="sxs-lookup"><span data-stu-id="a2601-132">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="a2601-133">Exemplo 2: excluir todos os trabalhos em uma sessão</span><span class="sxs-lookup"><span data-stu-id="a2601-133">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="a2601-134">Neste exemplo, todos os trabalhos na sessão atual do PowerShell são excluídos.</span><span class="sxs-lookup"><span data-stu-id="a2601-134">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="a2601-135">`Get-Job` Obtém todos os trabalhos na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2601-135">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="a2601-136">Os objetos de trabalho são enviados ao pipeline para o `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-136">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="a2601-137">Exemplo 3: excluir trabalhos não iniciados</span><span class="sxs-lookup"><span data-stu-id="a2601-137">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="a2601-138">Este exemplo exclui todos os trabalhos da sessão atual do PowerShell que não foram iniciadas.</span><span class="sxs-lookup"><span data-stu-id="a2601-138">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="a2601-139">`Remove-Job` usa o parâmetro **State** para especificar o status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2601-139">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="a2601-140">Exemplo 4: excluir trabalhos usando um nome amigável</span><span class="sxs-lookup"><span data-stu-id="a2601-140">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="a2601-141">Este exemplo exclui todos os trabalhos da sessão atual com nomes amigáveis que terminam com \* batch \* \*, incluindo os trabalhos que estão em execução.</span><span class="sxs-lookup"><span data-stu-id="a2601-141">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="a2601-142">`Remove-Job` usa o parâmetro **Name** para especificar um padrão de nome de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2601-142">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="a2601-143">O padrão inclui o curinga asterisco ( `*` ) para localizar todos os nomes de trabalho que terminam com o **lote** .</span><span class="sxs-lookup"><span data-stu-id="a2601-143">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch** .</span></span> <span data-ttu-id="a2601-144">O parâmetro **Force** exclui trabalhos que executam o.</span><span class="sxs-lookup"><span data-stu-id="a2601-144">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="a2601-145">Exemplo 5: excluir um trabalho criado por Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a2601-145">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="a2601-146">Este exemplo remove um trabalho que foi iniciado em um computador remoto usando `Invoke-Command` com o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="a2601-146">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="a2601-147">Como o exemplo usa o parâmetro **AsJob** , o objeto de trabalho é criado no computador local.</span><span class="sxs-lookup"><span data-stu-id="a2601-147">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="a2601-148">No entanto, o trabalho é executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a2601-148">But, the job runs on a remote computer.</span></span> <span data-ttu-id="a2601-149">Como resultado, você deve usar comandos locais para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2601-149">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="a2601-150">`Invoke-Command` executa um trabalho no computador **SERVER01** .</span><span class="sxs-lookup"><span data-stu-id="a2601-150">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="a2601-151">O parâmetro **AsJob** executa o **scriptblock** como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a2601-151">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="a2601-152">O objeto de trabalho é armazenado na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="a2601-152">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="a2601-153">O `$job` objeto Variable é enviado ao pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-153">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="a2601-154">Exemplo 6: excluir um trabalho que foi criado por Invoke-Command e Start-Job</span><span class="sxs-lookup"><span data-stu-id="a2601-154">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="a2601-155">Este exemplo mostra como remover um trabalho em um computador remoto que foi iniciado usando o `Invoke-Command` para executar o `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-155">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="a2601-156">O objeto de trabalho é criado no computador remoto e os comandos remotos são usados para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2601-156">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="a2601-157">Uma conexão persistente é necessária ao executar um `Start-Job` comando remoto.</span><span class="sxs-lookup"><span data-stu-id="a2601-157">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="a2601-158">`New-PSSession` Cria uma **PSSession** , uma conexão persistente, para o computador **Server01** .</span><span class="sxs-lookup"><span data-stu-id="a2601-158">`New-PSSession` creates a **PSSession** , a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="a2601-159">A conexão é salva na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="a2601-159">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="a2601-160">`Invoke-Command` conecta-se à sessão salva em `$S` .</span><span class="sxs-lookup"><span data-stu-id="a2601-160">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="a2601-161">O **scriptblock** usa `Start-Job` para iniciar um trabalho remoto.</span><span class="sxs-lookup"><span data-stu-id="a2601-161">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="a2601-162">O trabalho executa um `Get-Process` comando e usa o parâmetro **Name** para especificar um nome de trabalho amigável, **MyJob** .</span><span class="sxs-lookup"><span data-stu-id="a2601-162">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob** .</span></span>

<span data-ttu-id="a2601-163">`Invoke-Command` usa a `$S` sessão e executa o `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-163">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="a2601-164">O parâmetro **Name** especifica que o trabalho chamado **MyJob** é excluído.</span><span class="sxs-lookup"><span data-stu-id="a2601-164">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="a2601-165">Exemplo 7: excluir um trabalho usando sua InstanceId</span><span class="sxs-lookup"><span data-stu-id="a2601-165">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="a2601-166">Este exemplo remove um trabalho com base em sua **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="a2601-166">This example removes a job based on its **InstanceId** .</span></span>

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

<span data-ttu-id="a2601-167">`Start-Job` inicia um trabalho em segundo plano e o objeto de trabalho é salvo na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="a2601-167">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="a2601-168">O objeto no `$job` é enviado ao pipeline para `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="a2601-168">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="a2601-169">O parâmetro **Property** usa um asterisco ( `*` ) para especificar que todas as propriedades do objeto sejam exibidas em uma lista.</span><span class="sxs-lookup"><span data-stu-id="a2601-169">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="a2601-170">`Remove-Job` usa o parâmetro **InstanceId** para especificar o trabalho a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="a2601-170">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="a2601-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2601-171">PARAMETERS</span></span>

### <span data-ttu-id="a2601-172">-Command</span><span class="sxs-lookup"><span data-stu-id="a2601-172">-Command</span></span>

<span data-ttu-id="a2601-173">Exclui os trabalhos que incluem as palavras especificadas no comando.</span><span class="sxs-lookup"><span data-stu-id="a2601-173">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="a2601-174">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a2601-174">You can enter a comma-separated array.</span></span>

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

### <span data-ttu-id="a2601-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a2601-175">-Confirm</span></span>

<span data-ttu-id="a2601-176">Solicita que você confirme antes que o `Remove-Job` seja executado.</span><span class="sxs-lookup"><span data-stu-id="a2601-176">Prompts you for confirmation before `Remove-Job` is run.</span></span>

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

### <span data-ttu-id="a2601-177">-Filter</span><span class="sxs-lookup"><span data-stu-id="a2601-177">-Filter</span></span>

<span data-ttu-id="a2601-178">Exclui os trabalhos que atendem a todas as condições estabelecidas na tabela de hash associada.</span><span class="sxs-lookup"><span data-stu-id="a2601-178">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="a2601-179">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2601-179">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="a2601-180">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="a2601-180">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="a2601-181">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-181">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="a2601-182">Este parâmetro é introduzido no PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a2601-182">This parameter is introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a2601-183">-Force</span><span class="sxs-lookup"><span data-stu-id="a2601-183">-Force</span></span>

<span data-ttu-id="a2601-184">Exclui um trabalho mesmo que o estado do trabalho esteja **em execução** .</span><span class="sxs-lookup"><span data-stu-id="a2601-184">Deletes a job even if the job's state is **Running** .</span></span> <span data-ttu-id="a2601-185">Se o parâmetro **Force** não for especificado, o `Remove-Job` não excluirá os trabalhos em execução.</span><span class="sxs-lookup"><span data-stu-id="a2601-185">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, NameParameterSet, InstanceIdParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2601-186">-Id</span><span class="sxs-lookup"><span data-stu-id="a2601-186">-Id</span></span>

<span data-ttu-id="a2601-187">Exclui trabalhos em segundo plano com a **ID** especificada. Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a2601-187">Deletes background jobs with the specified **Id** . You can enter a comma-separated array.</span></span> <span data-ttu-id="a2601-188">A **ID** do trabalho é um inteiro exclusivo que identifica um trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a2601-188">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="a2601-189">Para localizar a **ID** de um trabalho, use `Get-Job` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a2601-189">To find a job's **Id** , use `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="a2601-190">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a2601-190">-InstanceId</span></span>

<span data-ttu-id="a2601-191">Exclui trabalhos com a **InstanceId** especificada.</span><span class="sxs-lookup"><span data-stu-id="a2601-191">Deletes jobs with the specified **InstanceId** .</span></span> <span data-ttu-id="a2601-192">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a2601-192">You can enter a comma-separated array.</span></span> <span data-ttu-id="a2601-193">Uma **InstanceId** é um GUID exclusivo que identifica um trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2601-193">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="a2601-194">Para localizar a **InstanceId** de um trabalho, use `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-194">To find a job's **InstanceId** , use `Get-Job`.</span></span>

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

### <span data-ttu-id="a2601-195">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="a2601-195">-Job</span></span>

<span data-ttu-id="a2601-196">Especifica os trabalhos a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="a2601-196">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="a2601-197">Insira uma variável que contenha os trabalhos ou um comando que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="a2601-197">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="a2601-198">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a2601-198">You can enter a comma-separated array.</span></span>

<span data-ttu-id="a2601-199">Você pode enviar objetos de trabalho para o pipeline para o `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-199">You can send job objects down the pipeline to `Remove-Job`.</span></span>

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

### <span data-ttu-id="a2601-200">-Name</span><span class="sxs-lookup"><span data-stu-id="a2601-200">-Name</span></span>

<span data-ttu-id="a2601-201">Somente exclui trabalhos com o nome amigável especificado.</span><span class="sxs-lookup"><span data-stu-id="a2601-201">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="a2601-202">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a2601-202">Wildcards are permitted.</span></span> <span data-ttu-id="a2601-203">Você pode inserir uma matriz separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a2601-203">You can enter a comma-separated array.</span></span>

<span data-ttu-id="a2601-204">Nomes amigáveis para trabalhos não têm garantia de serem exclusivos, mesmo em uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2601-204">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="a2601-205">Use os parâmetros **WhatIf** e **Confirm** ao excluir arquivos por nome.</span><span class="sxs-lookup"><span data-stu-id="a2601-205">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

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

### <span data-ttu-id="a2601-206">-Estado</span><span class="sxs-lookup"><span data-stu-id="a2601-206">-State</span></span>

<span data-ttu-id="a2601-207">Somente exclui trabalhos com o estado especificado.</span><span class="sxs-lookup"><span data-stu-id="a2601-207">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="a2601-208">Para excluir trabalhos com um estado de **em execução** , use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="a2601-208">To delete jobs with a state of **Running** , use the **Force** parameter.</span></span>

<span data-ttu-id="a2601-209">Valores aceitos:</span><span class="sxs-lookup"><span data-stu-id="a2601-209">Accepted values:</span></span>

- <span data-ttu-id="a2601-210">AtBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a2601-210">AtBreakpoint</span></span>
- <span data-ttu-id="a2601-211">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="a2601-211">Blocked</span></span>
- <span data-ttu-id="a2601-212">Concluído</span><span class="sxs-lookup"><span data-stu-id="a2601-212">Completed</span></span>
- <span data-ttu-id="a2601-213">Desconectado</span><span class="sxs-lookup"><span data-stu-id="a2601-213">Disconnected</span></span>
- <span data-ttu-id="a2601-214">Com falha</span><span class="sxs-lookup"><span data-stu-id="a2601-214">Failed</span></span>
- <span data-ttu-id="a2601-215">NotStarted</span><span class="sxs-lookup"><span data-stu-id="a2601-215">NotStarted</span></span>
- <span data-ttu-id="a2601-216">Executando</span><span class="sxs-lookup"><span data-stu-id="a2601-216">Running</span></span>
- <span data-ttu-id="a2601-217">Parado</span><span class="sxs-lookup"><span data-stu-id="a2601-217">Stopped</span></span>
- <span data-ttu-id="a2601-218">Parando</span><span class="sxs-lookup"><span data-stu-id="a2601-218">Stopping</span></span>
- <span data-ttu-id="a2601-219">Suspenso</span><span class="sxs-lookup"><span data-stu-id="a2601-219">Suspended</span></span>
- <span data-ttu-id="a2601-220">Suspensão</span><span class="sxs-lookup"><span data-stu-id="a2601-220">Suspending</span></span>

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

### <span data-ttu-id="a2601-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a2601-221">-WhatIf</span></span>

<span data-ttu-id="a2601-222">Mostra o que aconteceria se `Remove-Job` for executado.</span><span class="sxs-lookup"><span data-stu-id="a2601-222">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="a2601-223">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a2601-223">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a2601-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a2601-224">CommonParameters</span></span>

<span data-ttu-id="a2601-225">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2601-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2601-226">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2601-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2601-227">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a2601-227">INPUTS</span></span>

### <span data-ttu-id="a2601-228">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="a2601-228">System.Management.Automation.Job</span></span>

<span data-ttu-id="a2601-229">Você pode enviar um objeto de trabalho para baixo do pipeline para `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="a2601-229">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="a2601-230">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a2601-230">OUTPUTS</span></span>

### <span data-ttu-id="a2601-231">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a2601-231">None</span></span>

<span data-ttu-id="a2601-232">`Remove-Job` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a2601-232">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="a2601-233">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a2601-233">NOTES</span></span>

<span data-ttu-id="a2601-234">Um trabalho do PowerShell cria um novo processo.</span><span class="sxs-lookup"><span data-stu-id="a2601-234">A PowerShell job creates a new process.</span></span> <span data-ttu-id="a2601-235">Quando o trabalho é concluído, o processo é encerrado.</span><span class="sxs-lookup"><span data-stu-id="a2601-235">When the job completes, the process exits.</span></span> <span data-ttu-id="a2601-236">Quando `Remove-Job` é executado, o estado do trabalho é removido.</span><span class="sxs-lookup"><span data-stu-id="a2601-236">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="a2601-237">Se um trabalho parar antes da conclusão e seu processo não tiver sido encerrado, o processo será encerrado de modo forçado.</span><span class="sxs-lookup"><span data-stu-id="a2601-237">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="a2601-238">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a2601-238">RELATED LINKS</span></span>

[<span data-ttu-id="a2601-239">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="a2601-239">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="a2601-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="a2601-240">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="a2601-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="a2601-241">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="a2601-242">Get-Job</span><span class="sxs-lookup"><span data-stu-id="a2601-242">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="a2601-243">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a2601-243">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="a2601-244">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="a2601-244">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="a2601-245">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a2601-245">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="a2601-246">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="a2601-246">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="a2601-247">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a2601-247">Wait-Job</span></span>](Wait-Job.md)
