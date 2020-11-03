---
description: Explica os tópicos avançados de trabalho agendado, incluindo a estrutura de arquivos que é subjacente aos trabalhos agendados.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Advanced
ms.openlocfilehash: 7b09a72e8ad7e68641c73d2f7e59065dbf8f889b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195818"
---
# <a name="about-scheduled-jobs-advanced"></a><span data-ttu-id="bfdc3-104">Sobre os trabalhos agendados avançado</span><span class="sxs-lookup"><span data-stu-id="bfdc3-104">About Scheduled Jobs Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="bfdc3-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="bfdc3-105">Short description</span></span>

<span data-ttu-id="bfdc3-106">Explica os tópicos avançados de trabalho agendado, incluindo a estrutura de arquivos que é subjacente aos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-106">Explains advanced scheduled job topics, including the file structure that underlies scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="bfdc3-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="bfdc3-107">Long description</span></span>

<span data-ttu-id="bfdc3-108">Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="bfdc3-108">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="scheduled-job-directories-and-files"></a><span data-ttu-id="bfdc3-109">Diretórios e arquivos de trabalho agendados</span><span class="sxs-lookup"><span data-stu-id="bfdc3-109">Scheduled job directories and files</span></span>

<span data-ttu-id="bfdc3-110">Os trabalhos agendados do PowerShell são trabalhos do PowerShell e tarefas de Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-110">PowerShell scheduled jobs are both PowerShell jobs and Task Scheduler tasks.</span></span>
<span data-ttu-id="bfdc3-111">Cada trabalho agendado é registrado no Agendador de Tarefas e salvo em disco no formato XML de serialização Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-111">Each scheduled job is registered in Task Scheduler and saved on disk in Microsoft .NET Framework Serialization XML format.</span></span>

<span data-ttu-id="bfdc3-112">Quando você cria um trabalho agendado, o PowerShell cria um diretório para o trabalho agendado no `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-112">When you create a scheduled job, PowerShell creates a directory for the scheduled job in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span> <span data-ttu-id="bfdc3-113">O nome do diretório é o mesmo que o nome do trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-113">The directory name is the same as the job name.</span></span>

<span data-ttu-id="bfdc3-114">A seguir está um exemplo de diretório **ScheduledJobs** .</span><span class="sxs-lookup"><span data-stu-id="bfdc3-114">The following is a sample **ScheduledJobs** directory.</span></span>

```powershell
Get-ChildItem $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs
```

```Output
Directory: C:\Users\User01\AppData\Local
               \Microsoft\Windows\PowerShell\ScheduledJobs

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         9/29/2011  10:03 AM            ArchiveProjects
d----         9/30/2011   1:18 PM            Inventory
d----        10/20/2011   9:15 AM            Backup-Scripts
d----         11/7/2011  10:40 AM            ProcessJob
d----         11/2/2011  10:25 AM            SecureJob
d----         9/27/2011   1:29 PM            Test-HelpFiles
d----         9/26/2011   4:22 PM            DeployPackage
```

<span data-ttu-id="bfdc3-115">Cada trabalho agendado tem seu próprio diretório.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-115">Each scheduled job has its own directory.</span></span> <span data-ttu-id="bfdc3-116">O diretório contém o arquivo XML de trabalho agendado e um subdiretório de **saída** .</span><span class="sxs-lookup"><span data-stu-id="bfdc3-116">The directory contains the scheduled job XML file and an **Output** subdirectory.</span></span>

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell"
$Path += "\ScheduledJobs\ProcessJob"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/1/2011   3:00 PM            Output
-a---         11/1/2011   3:43 PM       7281 ScheduledJobDefinition.xml
```

<span data-ttu-id="bfdc3-117">O diretório de **saída** para um trabalho agendado contém seu histórico de execução.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-117">The **Output** directory for a scheduled job contains its execution history.</span></span>
<span data-ttu-id="bfdc3-118">Cada vez que um gatilho de trabalho inicia um trabalho agendado, o PowerShell cria um diretório nomeado com carimbo de data/hora no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-118">Each time a job trigger starts a scheduled job, PowerShell creates a timestamp-named directory in the output directory.</span></span> <span data-ttu-id="bfdc3-119">O diretório timestamp contém os resultados do trabalho em um arquivo de **Results.xml** e o status do trabalho em um arquivo **Status.xml** .</span><span class="sxs-lookup"><span data-stu-id="bfdc3-119">The timestamp directory contains the results of the job in a **Results.xml** file and the job status in a **Status.xml** file.</span></span>

<span data-ttu-id="bfdc3-120">O comando a seguir mostra os diretórios de histórico de execução para o trabalho agendado do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="bfdc3-120">The following command shows the execution history directories for the **ProcessJob** scheduled job.</span></span>

```powershell
$Path = "$home\AppData\Local\Microsoft"
$Path += "\Windows\PowerShell\ScheduledJobs\ProcessJob\Output"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft
               \Windows\PowerShell\ScheduledJobs\ProcessJob\Output

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/2/2011   3:00 AM            20111102-030002-260
d----         11/3/2011   3:00 AM            20111103-030002-277
d----         11/4/2011   3:00 AM            20111104-030002-209
d----         11/5/2011   3:00 AM            20111105-030002-251
d----         11/6/2011   3:00 AM            20111106-030002-174
d----         11/7/2011  12:00 AM            20111107-000001-914
d----         11/7/2011   3:00 AM            20111107-030002-376
```

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell\"
$Path += "ScheduledJobs\ProcessJob\Output\20111102-030002-260"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output\20111102-030002-260

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         11/2/2011   3:00 AM     581106 Results.xml
-a---         11/2/2011   3:00 AM       9451 Status.xml
```

<span data-ttu-id="bfdc3-121">Você pode abrir e examinar os arquivos de **ScheduledJobDefinition.xml** , **Results.xml** e **Status.xml** ou usar o `Select-XML` cmdlet para analisar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-121">You can open and examine the **ScheduledJobDefinition.xml** , **Results.xml** and **Status.xml** files or use the `Select-XML` cmdlet to parse the files.</span></span>

> [!WARNING]
> <span data-ttu-id="bfdc3-122">Não edite os arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-122">Do not edit the XML files.</span></span> <span data-ttu-id="bfdc3-123">Se qualquer arquivo XML contiver XML inválido, o PowerShell excluirá o trabalho agendado e seu histórico de execução, incluindo os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-123">If any XML file contains invalid XML, PowerShell deletes the scheduled job and its execution history, including job results.</span></span>

## <a name="start-a-scheduled-job-immediately"></a><span data-ttu-id="bfdc3-124">Iniciar um trabalho agendado imediatamente</span><span class="sxs-lookup"><span data-stu-id="bfdc3-124">Start a scheduled job immediately</span></span>

<span data-ttu-id="bfdc3-125">Você pode iniciar um trabalho agendado imediatamente de uma das duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="bfdc3-125">You can start a scheduled job immediately in one of two ways:</span></span>

- <span data-ttu-id="bfdc3-126">Execute o `Start-Job` cmdlet para iniciar qualquer trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-126">Run the `Start-Job` cmdlet to start any scheduled job.</span></span>
- <span data-ttu-id="bfdc3-127">Adicione o parâmetro **RunNow** ao `Register-ScheduledJob` comando para iniciar o trabalho assim que o comando for executado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-127">Add the **RunNow** parameter to your `Register-ScheduledJob` command to start the job as soon as the command is run.</span></span>

<span data-ttu-id="bfdc3-128">Os trabalhos que são iniciados usando o `Start-Job` cmdlet são trabalhos em segundo plano padrão do PowerShell, não instâncias do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-128">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="bfdc3-129">Como todos os trabalhos em segundo plano, esses trabalhos são iniciados imediatamente, eles não estão sujeitos a opções de trabalho ou afetados por gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-129">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers.</span></span> <span data-ttu-id="bfdc3-130">A saída do trabalho não é salva no diretório de **saída** do diretório de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-130">The job output isn't saved in the **Output** directory of the scheduled job directory.</span></span>

<span data-ttu-id="bfdc3-131">O comando a seguir usa o parâmetro **definitionname** do `Start-Job` cmdlet para iniciar o trabalho agendado do ProcessJob.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-131">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the ProcessJob scheduled job.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="bfdc3-132">Para gerenciar o trabalho e obter os resultados do trabalho, use os cmdlets do trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-132">To manage the job and get the job results, use the job cmdlets.</span></span> <span data-ttu-id="bfdc3-133">Para obter mais informações sobre os cmdlets de trabalho, consulte [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="bfdc3-133">For more information about the job cmdlets, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bfdc3-134">Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-134">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="bfdc3-135">Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="bfdc3-135">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

## <a name="rename-a-scheduled-job"></a><span data-ttu-id="bfdc3-136">Renomear um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="bfdc3-136">Rename a scheduled job</span></span>

<span data-ttu-id="bfdc3-137">Para renomear um trabalho agendado, use o parâmetro Name do `Set-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-137">To rename a scheduled job, use the Name parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="bfdc3-138">Quando você renomeia um trabalho agendado, o PowerShell altera o nome do trabalho agendado e o diretório de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-138">When you rename a scheduled job, PowerShell changes the name of the scheduled job and the scheduled job directory.</span></span> <span data-ttu-id="bfdc3-139">No entanto, ele não altera os nomes de instâncias do trabalho agendado que já foram executados.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-139">However, it doesn't change the names of instances of the scheduled job that have already run.</span></span>

## <a name="get-start-and-end-times"></a><span data-ttu-id="bfdc3-140">Obter horários de início e término</span><span class="sxs-lookup"><span data-stu-id="bfdc3-140">Get start and end times</span></span>

<span data-ttu-id="bfdc3-141">Para obter as datas e as horas em que as instâncias de trabalho foram iniciadas e encerradas, use as propriedades **PSBeginTime** e **PSEndTime** do objeto ScheduledJob que `Get-Job` retorna para trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-141">To get the dates and times that job instances started and ended, use the **PSBeginTime** and **PSEndTime** properties of the ScheduledJob object that `Get-Job` returns for scheduled jobs.</span></span>

<span data-ttu-id="bfdc3-142">O exemplo a seguir usa o parâmetro **Property** do `Format-Table` cmdlet para exibir as propriedades **PSBeginTime** e **PSEndTime** de cada instância de trabalho em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-142">The following example uses the **Property** parameter of the `Format-Table` cmdlet to display the **PSBeginTime** and **PSEndTime** properties of each job instance in a table.</span></span> <span data-ttu-id="bfdc3-143">Uma propriedade calculada denominada **Label** exibe o tempo decorrido de cada instância de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-143">A calculated property named **Label** displays the elapsed time of each job instance.</span></span>

```powershell
Get-job -Name UpdateHelpJob | 
  Format-Table -Property ID, PSBeginTime, PSEndTime,
@{Label="Elapsed Time";Expression={$.PsEndTime - $.PSBeginTime}}
```

```Output
Id   PSBeginTime             PSEndTime                Elapsed Time
--   -----------             ---------                ------------
 2   11/3/2011 3:00:01 AM    11/3/2011 3:00:39 AM     00:00:38.0053854
 3   11/4/2011 3:00:02 AM    11/4/2011 3:01:01 AM     00:00:59.1188475
 4   11/5/2011 3:00:02 AM    11/5/2011 3:00:50 AM     00:00:48.3692034
 5   11/6/2011 3:00:01 AM    11/6/2011 3:00:54 AM     00:00:52.8013036
 6   11/7/2011 3:00:01 AM    11/7/2011 3:00:38 AM     00:00:37.1930350
 7   11/8/2011 3:00:01 AM    11/8/2011 3:00:57 AM     00:00:56.2570556
 8   11/9/2011 3:00:03 AM    11/9/2011 3:00:55 AM     00:00:51.8142222
 9   11/10/2011 3:00:02 AM   11/10/2011 3:00:42 AM    00:00:40.7195954
```

## <a name="manage-execution-history"></a><span data-ttu-id="bfdc3-144">Gerenciar histórico de execução</span><span class="sxs-lookup"><span data-stu-id="bfdc3-144">Manage execution history</span></span>

<span data-ttu-id="bfdc3-145">Você pode determinar o número de resultados da instância de trabalho que são salvos para cada trabalho agendado e excluir o histórico de execução e os resultados de trabalho salvos de qualquer trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-145">You can determine the number of job instance results that are saved for each scheduled job and delete the execution history and saved job results of any scheduled job.</span></span>

<span data-ttu-id="bfdc3-146">A propriedade **ExecutionHistoryLength** de um trabalho agendado determina quantos resultados da instância de trabalho são salvos para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-146">The **ExecutionHistoryLength** property of a scheduled job determines how many job instance results are saved for the scheduled job.</span></span> <span data-ttu-id="bfdc3-147">Quando o número de resultados salvos excede o valor da propriedade **ExecutionHistoryLength** , o PowerShell exclui os resultados da instância mais antiga para liberar espaço para os resultados da instância mais recente.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-147">When the number of saved results exceeds the value of the **ExecutionHistoryLength** property, PowerShell deletes the results of the oldest instance to make room for the results of the newest instance.</span></span>

<span data-ttu-id="bfdc3-148">Por padrão, o PowerShell salva o histórico de execução e os resultados de 32 instâncias de cada trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-148">By default, PowerShell saves the execution history and results of 32 instances of each scheduled job.</span></span> <span data-ttu-id="bfdc3-149">Para alterar esse valor, use os parâmetros **MaxResultCount** dos `Register-ScheduledJob` `Set-ScheduledJob` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-149">To change that value, use the **MaxResultCount** parameters of the `Register-ScheduledJob` or `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="bfdc3-150">Para excluir o histórico de execução e todos os resultados de um trabalho agendado, use o parâmetro **ClearExecutionHistory** do `Set-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-150">To delete the execution history and all results for a scheduled job, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="bfdc3-151">Excluir esse histórico de execução não impede que o PowerShell salve os resultados de novas instâncias do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-151">Deleting this execution history does not prevent PowerShell from saving the results of new instances of the scheduled job.</span></span>

<span data-ttu-id="bfdc3-152">O exemplo a seguir usa nivelamento para criar `$JobParms` que são valores de parâmetro que são passados para o `Register-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-152">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="bfdc3-153">Para obter mais informações, consulte [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="bfdc3-153">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="bfdc3-154">O `Register-ScheduledJob` usa `@JobParms` para criar um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-154">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="bfdc3-155">O comando usa o parâmetro **MaxResultCount** com um valor de 12 para salvar apenas os 12 resultados mais recentes da instância de trabalho do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-155">The command uses the **MaxResultCount** parameter with a value of 12 to save only the 12 newest job instance results of the scheduled job.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="bfdc3-156">O comando a seguir usa o parâmetro **MaxResultCount** do `Set-ScheduledJob` cmdlet para aumentar o número de resultados da instância salva para</span><span class="sxs-lookup"><span data-stu-id="bfdc3-156">The following command uses the **MaxResultCount** parameter of the `Set-ScheduledJob` cmdlet to increase the number of saved instance results to</span></span>
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

<span data-ttu-id="bfdc3-157">O comando a seguir exclui o histórico de execução e os resultados salvos atuais do trabalho agendado do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="bfdc3-157">The following command deletes the execution history and the current saved results of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="bfdc3-158">O comando a seguir obtém os valores das propriedades Name e **ExecutionHistoryLength** de todos os trabalhos agendados no computador e os exibe em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="bfdc3-158">The following command gets the values of the name and **ExecutionHistoryLength** properties of all scheduled jobs on the computer and displays them in a table.</span></span>

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a><span data-ttu-id="bfdc3-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="bfdc3-159">See also</span></span>

[<span data-ttu-id="bfdc3-160">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="bfdc3-160">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="bfdc3-161">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="bfdc3-161">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="bfdc3-162">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="bfdc3-162">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="bfdc3-163">about_Splatting. MD</span><span class="sxs-lookup"><span data-stu-id="bfdc3-163">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="bfdc3-164">Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="bfdc3-164">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="bfdc3-165">Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="bfdc3-165">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
