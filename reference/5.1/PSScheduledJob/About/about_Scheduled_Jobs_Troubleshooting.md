---
description: Explica como resolver problemas com trabalhos agendados
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_troubleshooting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Troubleshooting
ms.openlocfilehash: aac2133cee4abdd7e50e7b433104b9578d74b0a8
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685846"
---
# <a name="about-scheduled-jobs-troubleshooting"></a><span data-ttu-id="2d142-104">Sobre a solução de problemas de trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="2d142-104">About Scheduled Jobs Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="2d142-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="2d142-105">Short description</span></span>

<span data-ttu-id="2d142-106">Explica como resolver problemas com trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="2d142-106">Explains how to resolve problems with scheduled jobs</span></span>

## <a name="long-description"></a><span data-ttu-id="2d142-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="2d142-107">Long description</span></span>

<span data-ttu-id="2d142-108">Este documento descreve alguns dos problemas que você pode enfrentar ao usar os recursos de trabalho agendado do PowerShell e ele sugere soluções para esses problemas.</span><span class="sxs-lookup"><span data-stu-id="2d142-108">This document describes some of the problems that you might experience when using the scheduled job features of PowerShell and it suggests solutions to these problems.</span></span>

<span data-ttu-id="2d142-109">Antes de usar os trabalhos agendados do PowerShell, consulte [about_Scheduled_Jobs](about_Scheduled_Jobs.md) e os trabalhos agendados relacionados sobre tópicos.</span><span class="sxs-lookup"><span data-stu-id="2d142-109">Before using PowerShell scheduled jobs, see [about_Scheduled_Jobs](about_Scheduled_Jobs.md) and the related scheduled jobs about topics.</span></span>

<span data-ttu-id="2d142-110">Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="2d142-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="cant-find-job-results"></a><span data-ttu-id="2d142-111">Não é possível localizar os resultados do trabalho</span><span class="sxs-lookup"><span data-stu-id="2d142-111">Can't find job results</span></span>

### <a name="basic-method-for-getting-job-results-in-powershell"></a><span data-ttu-id="2d142-112">Método básico para obter resultados de trabalho no PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d142-112">Basic method for getting job results in PowerShell</span></span>

<span data-ttu-id="2d142-113">Quando um trabalho agendado é executado, ele cria uma instância do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d142-113">When a scheduled job runs, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="2d142-114">Para exibir, gerenciar e obter os resultados das instâncias de trabalho agendadas, use os cmdlets de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d142-114">To view, manage, and get the results of scheduled job instances, use the Job cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="2d142-115">Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="2d142-115">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="2d142-116">Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="2d142-116">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="2d142-117">Para obter uma lista de todas as instâncias de um trabalho agendado, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d142-117">To get a list of all instances of a scheduled job, use the `Get-Job` cmdlet.</span></span>

```powershell
Import-Module PSScheduledJob
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State         HasMoreData     Location
--     ----         -------------   -----         -----------     --------
43     ProcessJob   PSScheduledJob  Completed     False           localhost
44     ProcessJob   PSScheduledJob  Completed     False           localhost
45     ProcessJob   PSScheduledJob  Completed     False           localhost
46     ProcessJob   PSScheduledJob  Completed     False           localhost
47     ProcessJob   PSScheduledJob  Completed     False           localhost
48     ProcessJob   PSScheduledJob  Completed     False           localhost
49     ProcessJob   PSScheduledJob  Completed     False           localhost
50     ProcessJob   PSScheduledJob  Completed     False           localhost
```

<span data-ttu-id="2d142-118">O `Get-Job` cmdlet envia objetos **ProcessJob** para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="2d142-118">The `Get-Job` cmdlet sends **ProcessJob** objects down the pipeline.</span></span> <span data-ttu-id="2d142-119">O `Format-Table` cmdlet exibe as propriedades **Name**, **ID** e **PSBeginTime** de uma instância de trabalho agendada em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2d142-119">The `Format-Table` cmdlet displays the **Name**, **ID**, and **PSBeginTime** properties of a scheduled job instance in a table.</span></span>

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, PSBeginTime -Auto
```

```Output
Name       Id PSBeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

<span data-ttu-id="2d142-120">Para obter os resultados de uma instância de um trabalho agendado, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d142-120">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="2d142-121">O comando a seguir obtém os resultados da instância mais recente do ProcessJob (ID = 50).</span><span class="sxs-lookup"><span data-stu-id="2d142-121">The following command gets the results of the newest instance of the ProcessJob (ID = 50).</span></span>

```powershell
Receive-Job -ID 50
```

### <a name="basic-method-for-finding-job-results-on-disk"></a><span data-ttu-id="2d142-122">Método básico para localizar resultados de trabalho em disco</span><span class="sxs-lookup"><span data-stu-id="2d142-122">Basic method for finding job results on disk</span></span>

<span data-ttu-id="2d142-123">Para gerenciar trabalhos agendados, use os cmdlets de trabalho, como `Get-Job` e `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="2d142-123">To manage scheduled jobs, use the job cmdlets, such as `Get-Job` and `Receive-Job`.</span></span>

<span data-ttu-id="2d142-124">Se o não `Get-Job` obtiver a instância de trabalho ou não `Receive-Job` obtiver os resultados do trabalho, você poderá pesquisar os arquivos de histórico de execução do trabalho em disco.</span><span class="sxs-lookup"><span data-stu-id="2d142-124">If `Get-Job` does not get the job instance or `Receive-Job` does not get the job results, you can search the execution history files for the job on disk.</span></span>
<span data-ttu-id="2d142-125">O histórico de execução contém um registro de todas as instâncias de trabalho disparadas.</span><span class="sxs-lookup"><span data-stu-id="2d142-125">The execution history contains a record of all triggered job instances.</span></span>

<span data-ttu-id="2d142-126">Verifique se há um diretório nomeado com carimbo de data/hora no diretório para um trabalho agendado no seguinte caminho:</span><span class="sxs-lookup"><span data-stu-id="2d142-126">Verify that there is a timestamp-named directory in the directory for a scheduled job in the following path:</span></span>

`$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="2d142-127">Por exemplo: </span><span class="sxs-lookup"><span data-stu-id="2d142-127">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="2d142-128">Por exemplo, o `Get-ChildItem` cmdlet obtém o histórico de execução em disco do trabalho agendado do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="2d142-128">For example, the `Get-ChildItem` cmdlet gets the on-disk execution history of the **ProcessJob** scheduled job.</span></span>

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output

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

<span data-ttu-id="2d142-129">Cada diretório nomeado por carimbo de data/hora representa uma instância de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d142-129">Each timestamp-named directory represents a job instance.</span></span> <span data-ttu-id="2d142-130">Os resultados de cada instância de trabalho são salvos em um arquivo de **Results.xml** no diretório nomeado por carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="2d142-130">The results of each job instance are saved in a **Results.xml** file in the timestamp-named directory.</span></span>

<span data-ttu-id="2d142-131">Por exemplo, o comando a seguir obtém os arquivos de **Results.xml** para cada instância salva do trabalho agendado **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="2d142-131">For example, the following command gets the **Results.xml** files for every saved instance of the **ProcessJob** scheduled job.</span></span> <span data-ttu-id="2d142-132">Se o arquivo de **Results.xml** estiver ausente, o PowerShell não poderá retornar ou exibir os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d142-132">If the **Results.xml** file is missing, PowerShell cannot return or display the job results.</span></span>

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output\*\Results.xml'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\Appdata\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output
```

<span data-ttu-id="2d142-133">O cmdlet Job pode não ser capaz de obter instâncias de trabalho agendadas ou seus resultados porque o módulo **PSScheduledJob** não é importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="2d142-133">The job cmdlet might not be able to get scheduled job instances or their results because the **PSScheduledJob** module is not imported into the session.</span></span>

> [!NOTE]
> <span data-ttu-id="2d142-134">Antes de usar um cmdlet de trabalho em instâncias de trabalho agendadas, verifique se o módulo **PSScheduledJob** está incluído na sessão.</span><span class="sxs-lookup"><span data-stu-id="2d142-134">Before using a job cmdlet on scheduled job instances, verify that the **PSScheduledJob** module is included in the session.</span></span> <span data-ttu-id="2d142-135">Sem o módulo **PSScheduledJob** , os cmdlets de trabalho não podem obter instâncias de trabalho agendadas ou seus resultados.</span><span class="sxs-lookup"><span data-stu-id="2d142-135">Without the **PSScheduledJob** module, the job cmdlets cannot get scheduled job instances or their results.</span></span>

<span data-ttu-id="2d142-136">Para importar o módulo **PSScheduledJob** :</span><span class="sxs-lookup"><span data-stu-id="2d142-136">To import the **PSScheduledJob** module:</span></span>

```powershell
Import-Module PSScheduledJob
```

### <a name="receive-job-cmdlet-might-already-have-returned-the-results"></a><span data-ttu-id="2d142-137">Receive-Job cmdlet já pode ter retornado os resultados</span><span class="sxs-lookup"><span data-stu-id="2d142-137">Receive-Job cmdlet might already have returned the results</span></span>

<span data-ttu-id="2d142-138">Se o `Receive-Job` não retornar resultados da instância de trabalho, pode ser porque um `Receive-Job` comando foi executado para essa instância de trabalho na sessão atual sem o parâmetro **Keep** .</span><span class="sxs-lookup"><span data-stu-id="2d142-138">If `Receive-Job` does not return job instance results, it might be because a `Receive-Job` command has been run for that job instance in the current session without the **Keep** parameter.</span></span>

<span data-ttu-id="2d142-139">Quando você usa `Receive-Job` sem o parâmetro **Keep** , `Receive-Job` o retorna os resultados do trabalho e define a propriedade **HasMoreData** da instância do trabalho como **false**.</span><span class="sxs-lookup"><span data-stu-id="2d142-139">When you use `Receive-Job` without the **Keep** parameter, `Receive-Job` returns the job results and sets the job instance's **HasMoreData** property to **False**.</span></span> <span data-ttu-id="2d142-140">O valor **false** significa que `Receive-Job` retornou os resultados do trabalho e a instância não tem mais resultados a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="2d142-140">The **False** value means that `Receive-Job` returned the job's results and the instance has no more results to return.</span></span> <span data-ttu-id="2d142-141">Essa configuração é apropriada para trabalhos em segundo plano padrão, mas não para instâncias de trabalhos agendados, que são salvos em disco.</span><span class="sxs-lookup"><span data-stu-id="2d142-141">This setting is appropriate for standard background jobs, but not for instances of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="2d142-142">Para obter os resultados da instância de trabalho novamente, inicie uma nova sessão do PowerShell digitando `PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="2d142-142">To get the job instance results again, start a new PowerShell session by typing `PowerShell`.</span></span> <span data-ttu-id="2d142-143">Importe o módulo **PSScheduledJob** e tente o `Receive-Job` comando novamente.</span><span class="sxs-lookup"><span data-stu-id="2d142-143">Import the **PSScheduledJob** module, and try the `Receive-Job` command again.</span></span>

```powershell
Receive-Job -ID 50
```

```Output
#No results
```

```powershell
PowerShell.exe
```

```Output
Windows PowerShell
Copyright (C) 2012 Microsoft Corporation. All rights reserved.
```

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="using-keep-parameter-to-get-results-more-than-one-time-in-a-session"></a><span data-ttu-id="2d142-144">Usando o parâmetro Keep para obter resultados mais de uma vez em uma sessão</span><span class="sxs-lookup"><span data-stu-id="2d142-144">Using Keep parameter to get results more than one time in a session</span></span>

<span data-ttu-id="2d142-145">Para obter o resultado de uma instância de trabalho mais de uma vez em uma sessão, use o parâmetro **Keep** do `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d142-145">To get the result of a job instance more than one time in a session, use the **Keep** parameter of the `Receive-Job` cmdlet.</span></span>

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

```powershell
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="the-scheduled-job-might-be-corrupted"></a><span data-ttu-id="2d142-146">O trabalho agendado pode estar corrompido</span><span class="sxs-lookup"><span data-stu-id="2d142-146">The scheduled job might be corrupted</span></span>

<span data-ttu-id="2d142-147">Se um trabalho agendado for corrompido, o PowerShell excluirá o trabalho agendado corrompido e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="2d142-147">If a scheduled job becomes corrupted, PowerShell deletes the corrupted scheduled job and its results.</span></span> <span data-ttu-id="2d142-148">Você não pode recuperar os resultados de um trabalho agendado corrompido.</span><span class="sxs-lookup"><span data-stu-id="2d142-148">You cannot recover the results of a corrupted scheduled job.</span></span>

<span data-ttu-id="2d142-149">Para determinar se um trabalho agendado ainda existe, use o `Get-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d142-149">To determine if a scheduled job still exists, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
Get-ScheduledJob
```

### <a name="the-number-of-results-might-have-exceeded-the-executionhistorylength"></a><span data-ttu-id="2d142-150">O número de resultados pode ter excedido o ExecutionHistoryLength</span><span class="sxs-lookup"><span data-stu-id="2d142-150">The number of results might have exceeded the ExecutionHistoryLength</span></span>

<span data-ttu-id="2d142-151">A propriedade **ExecutionHistoryLength** de um trabalho agendado determina quantas instâncias de trabalho e seus resultados são salvos em disco.</span><span class="sxs-lookup"><span data-stu-id="2d142-151">The **ExecutionHistoryLength** property of a scheduled job determines how many job instances, and their results, are saved to disk.</span></span> <span data-ttu-id="2d142-152">O valor padrão é 32.</span><span class="sxs-lookup"><span data-stu-id="2d142-152">The default value is 32.</span></span>
<span data-ttu-id="2d142-153">Quando o número de instâncias de um trabalho agendado exceder esse valor, o PowerShell excluirá a instância de trabalho mais antiga para liberar espaço para cada nova instância de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d142-153">When the number of instances of a scheduled job exceeds this value, PowerShell deletes the oldest job instance to make room for each new job instance.</span></span>

<span data-ttu-id="2d142-154">Para obter o valor da propriedade **ExecutionHistoryLength** de um trabalho agendado, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="2d142-154">To get the value of the **ExecutionHistoryLength** property of a scheduled job, use the following command format:</span></span>

```powershell
(Get-ScheduledJob <JobName>).ExecutionHistoryLength
```

<span data-ttu-id="2d142-155">Por exemplo, o comando a seguir obtém o valor da propriedade **ExecutionHistoryLength** do trabalho agendado **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="2d142-155">For example, the following command gets the value of the **ExecutionHistoryLength** property of the **ProcessJob** scheduled job.</span></span>

```powershell
(Get-ScheduledJob ProcessJob).ExecutionHistoryLength
```

<span data-ttu-id="2d142-156">Para definir ou alterar o valor da propriedade **ExecutionHistoryLength** , use o parâmetro **MaxResultCount** dos `Register-ScheduledJob` `Set-ScheduledJob` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="2d142-156">To set or change the value of the **ExecutionHistoryLength** property, use the **MaxResultCount** parameter of the `Register-ScheduledJob` and `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="2d142-157">O comando a seguir aumenta o valor da propriedade **ExecutionHistoryLength** para 50.</span><span class="sxs-lookup"><span data-stu-id="2d142-157">The following command increases the value of the **ExecutionHistoryLength** property to 50.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 50
```

### <a name="the-job-instance-results-might-have-been-deleted"></a><span data-ttu-id="2d142-158">Os resultados da instância de trabalho podem ter sido excluídos</span><span class="sxs-lookup"><span data-stu-id="2d142-158">The job instance results might have been deleted</span></span>

<span data-ttu-id="2d142-159">O parâmetro **ClearExecutionHistory** do `Set-ScheduledJob` cmdlet exclui o histórico de execução de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d142-159">The **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet deletes the execution history of a job.</span></span> <span data-ttu-id="2d142-160">Você pode usar esse recurso para liberar espaço em disco ou excluir resultados que não são necessários, ou já usados, analisados ou salvos em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="2d142-160">You can use this feature to free up disk space or delete results that are not needed, or already used, analyzed or saved in a different location.</span></span>

<span data-ttu-id="2d142-161">Para excluir o histórico de execução de um trabalho agendado, use o parâmetro **ClearExecutionHistory** do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d142-161">To delete the execution history of a scheduled job, use the **ClearExecutionHistory** parameter of the scheduled job.</span></span>

<span data-ttu-id="2d142-162">O comando a seguir exclui o histórico de execução do trabalho agendado do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="2d142-162">The following command deletes the execution history of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="2d142-163">Além disso, o `Remove-Job` cmdlet exclui os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d142-163">Also, the `Remove-Job` cmdlet deletes job results.</span></span> <span data-ttu-id="2d142-164">Quando você usa `Remove-Job` o para excluir um trabalho agendado, ele exclui todas as instâncias do trabalho em disco, incluindo o histórico de execução e todos os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2d142-164">When you use `Remove-Job` to delete a scheduled job, it deletes all instances of the job on disk, including the execution history and all job results.</span></span>

### <a name="jobs-started-by-using-the-start-job-cmdlet-are-not-saved-to-disk"></a><span data-ttu-id="2d142-165">Os trabalhos iniciados usando o cmdlet Start-Job não são salvos em disco</span><span class="sxs-lookup"><span data-stu-id="2d142-165">Jobs started by using the Start-Job cmdlet are not saved to disk</span></span>

<span data-ttu-id="2d142-166">Quando você usa o `Start-Job` para iniciar um trabalho agendado, em vez de usar um gatilho de trabalho, `Start-Job` o inicia um trabalho em segundo plano padrão.</span><span class="sxs-lookup"><span data-stu-id="2d142-166">When you use `Start-Job` to start a scheduled job, instead of using a job trigger, `Start-Job` starts a standard background job.</span></span> <span data-ttu-id="2d142-167">O trabalho em segundo plano e seus resultados não são armazenados no histórico de execução do trabalho em disco.</span><span class="sxs-lookup"><span data-stu-id="2d142-167">The background job and its results are not stored in the execution history of the job on disk.</span></span>

<span data-ttu-id="2d142-168">Você pode usar o `Get-Job` cmdlet para obter o trabalho e o `Receive-Job` cmdlet para obter os resultados do trabalho, mas os resultados estarão disponíveis somente até você recebê-los, a menos que você use o parâmetro Keep do `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d142-168">You can use the `Get-Job` cmdlet to get the job and the `Receive-Job` cmdlet to get the job results, but the results are available only until you receive them, unless you use the Keep parameter of the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="2d142-169">Além disso, os trabalhos em segundo plano e seus resultados são específicos da sessão; elas existem somente na sessão em que são criadas.</span><span class="sxs-lookup"><span data-stu-id="2d142-169">Also, background jobs and their results are session-specific; they exist only in the session in which they are created.</span></span> <span data-ttu-id="2d142-170">Se você excluir o trabalho com `Remove-Job` , feche a sessão ou feche o PowerShell, a instância de trabalho e seus resultados serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="2d142-170">If you delete the job with `Remove-Job`, close the session or close PowerShell, the job instance and its results are deleted.</span></span>

## <a name="scheduled-job-doesnt-run"></a><span data-ttu-id="2d142-171">O trabalho agendado não é executado</span><span class="sxs-lookup"><span data-stu-id="2d142-171">Scheduled job doesn't run</span></span>

<span data-ttu-id="2d142-172">Os trabalhos agendados não serão executados automaticamente se o trabalho for disparado ou se o trabalho agendado estiver desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2d142-172">Scheduled jobs don't run automatically if the job triggers or the scheduled job are disabled.</span></span>

<span data-ttu-id="2d142-173">Use o `Get-ScheduledJob` cmdlet para obter o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d142-173">Use the `Get-ScheduledJob` cmdlet to get the scheduled job.</span></span> <span data-ttu-id="2d142-174">Verifique se o valor da propriedade **habilitado** do trabalho agendado é **true**.</span><span class="sxs-lookup"><span data-stu-id="2d142-174">Verify that the value of the **Enabled** property of the scheduled job is **True**.</span></span>

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command         Enabled
--         ----            --------        -------         -------
4          ProcessJob      {1, 2}          Get-Process     True
```

```powershell
(Get-ScheduledJob ProcessJob).Enabled
```

```Output
True
```

<span data-ttu-id="2d142-175">Use o `Get-JobTrigger` cmdlet para obter os gatilhos de trabalho do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d142-175">Use the `Get-JobTrigger` cmdlet to get the job triggers of the scheduled job.</span></span>
<span data-ttu-id="2d142-176">Verifique se o valor da propriedade **Enabled** do gatilho do trabalho é **true**.</span><span class="sxs-lookup"><span data-stu-id="2d142-176">Verify that the value of the **Enabled** property of the job trigger is **True**.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Get-JobTrigger
```

```Output
Id      Frequency    Time                   DaysOfWeek            Enabled
--      ---------    ----                   ----------            -------
1       Weekly       11/7/2011 5:00:00 AM   {Monday, Thursday}    True
2       Daily        11/7/2011 3:00:00 PM                         True
```

```powershell
Get-ScheduledJob ProcessJob|Get-JobTrigger|Format-Table ID, Enabled -Auto
```

```Output
Id Enabled
-- -------
1    True
2    True
```

### <a name="scheduled-jobs-dont-run-automatically-if-job-triggers-are-invalid"></a><span data-ttu-id="2d142-177">Os trabalhos agendados não serão executados automaticamente se os gatilhos de trabalho forem inválidos</span><span class="sxs-lookup"><span data-stu-id="2d142-177">Scheduled jobs don't run automatically if job triggers are invalid</span></span>

<span data-ttu-id="2d142-178">Por exemplo, um gatilho de trabalho pode especificar uma data no passado ou uma data que não ocorre, como a quinta segunda-feira do mês.</span><span class="sxs-lookup"><span data-stu-id="2d142-178">For example, a job trigger might specify a date in the past or a date that does not occur, such as the 5th Monday of the month.</span></span>

<span data-ttu-id="2d142-179">Os trabalhos agendados não serão executados automaticamente se as condições do gatilho de trabalho ou as opções de trabalho não forem satisfeitas.</span><span class="sxs-lookup"><span data-stu-id="2d142-179">Scheduled jobs do not run automatically if the conditions of the job trigger or the job options are not satisfied.</span></span>

<span data-ttu-id="2d142-180">Por exemplo, um trabalho agendado que é executado somente quando um usuário específico faz logon no computador não será executado se esse usuário não fizer logon ou se conectar somente remotamente.</span><span class="sxs-lookup"><span data-stu-id="2d142-180">For example, a scheduled job that runs only when a particular user logs on to the computer will not run if that user does not log on or only connects remotely.</span></span>

<span data-ttu-id="2d142-181">Examine as opções do trabalho agendado e verifique se eles estão satisfeitos.</span><span class="sxs-lookup"><span data-stu-id="2d142-181">Examine the options of the scheduled job and make sure that they are satisfied.</span></span>
<span data-ttu-id="2d142-182">Por exemplo, um trabalho agendado que exige que o computador fique ocioso ou exija uma conexão de rede, ou tem um longo **IdleDuration** ou um breve **IdleTimeout** pode nunca ser executado.</span><span class="sxs-lookup"><span data-stu-id="2d142-182">For example, a scheduled job that requires that the computer be idle or requires a network connection, or has a long **IdleDuration** or a brief **IdleTimeout** might never run.</span></span>

<span data-ttu-id="2d142-183">Use o `Get-ScheduledJobOption` cmdlet para examinar as opções de trabalho e seus valores.</span><span class="sxs-lookup"><span data-stu-id="2d142-183">Use the `Get-ScheduledJobOption` cmdlet to examine the job options and their values.</span></span>

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="2d142-184">Para obter descrições das opções de trabalho agendado, consulte [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span><span class="sxs-lookup"><span data-stu-id="2d142-184">For descriptions of the scheduled job options, see [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

### <a name="the-scheduled-job-instance-might-have-failed"></a><span data-ttu-id="2d142-185">A instância do trabalho agendado pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="2d142-185">The scheduled job instance might have failed</span></span>

<span data-ttu-id="2d142-186">Se um comando de trabalho agendado falhar, o PowerShell o relatará imediatamente gerando uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="2d142-186">If a scheduled job command fails, PowerShell reports it immediately by generating an error message.</span></span> <span data-ttu-id="2d142-187">No entanto, se o trabalho falhar quando Agendador de Tarefas tentar executá-lo, o erro não estará disponível para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d142-187">However, if the job fails when Task Scheduler tries to run it, the error is not available to PowerShell.</span></span>

<span data-ttu-id="2d142-188">Use os métodos a seguir para detectar e corrigir falhas de trabalho:</span><span class="sxs-lookup"><span data-stu-id="2d142-188">Use the following methods to detect and correct job failures:</span></span>

<span data-ttu-id="2d142-189">Verifique se há erros na Agendador de Tarefas log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2d142-189">Check the Task Scheduler event log for errors.</span></span> <span data-ttu-id="2d142-190">Para verificar o log, use Visualizador de Eventos ou um comando do PowerShell, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d142-190">To check the log, use Event Viewer or a PowerShell command such as the following:</span></span>

```powershell
Get-WinEvent -LogName Microsoft-Windows-TaskScheduler/Operational |
 Where {$_.Message -like "fail"}
```

<span data-ttu-id="2d142-191">Verifique o registro de trabalho em Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="2d142-191">Check the job record in Task Scheduler.</span></span> <span data-ttu-id="2d142-192">Os trabalhos agendados do PowerShell são armazenados na seguinte pasta agendada de tarefas:</span><span class="sxs-lookup"><span data-stu-id="2d142-192">PowerShell scheduled jobs are stored in the following Task Scheduled folder:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`

### <a name="the-scheduled-job-might-not-run-because-of-insufficient-permission"></a><span data-ttu-id="2d142-193">O trabalho agendado pode não ser executado por causa de permissão insuficiente</span><span class="sxs-lookup"><span data-stu-id="2d142-193">The scheduled job might not run because of insufficient permission</span></span>

<span data-ttu-id="2d142-194">Os trabalhos agendados são executados com as permissões do usuário que criou o trabalho ou as permissões do usuário que é especificado pelo parâmetro de **credencial** no `Register-ScheduledJob` `Set-ScheduledJob` comando ou.</span><span class="sxs-lookup"><span data-stu-id="2d142-194">Scheduled jobs run with the permissions of the user who created the job or the permissions of the user who is specified by the **Credential** parameter in the `Register-ScheduledJob` or `Set-ScheduledJob` command.</span></span>

<span data-ttu-id="2d142-195">Se esse usuário não tiver permissão para executar os comandos ou scripts, o trabalho falhará.</span><span class="sxs-lookup"><span data-stu-id="2d142-195">If that user does not have permission to run the commands or scripts, the job fails.</span></span>

## <a name="cant-get-scheduled-job-or-scheduled-job-is-corrupted"></a><span data-ttu-id="2d142-196">Não é possível obter o trabalho agendado ou o trabalho agendado está corrompido</span><span class="sxs-lookup"><span data-stu-id="2d142-196">Can't get scheduled job or scheduled job is corrupted</span></span>

<span data-ttu-id="2d142-197">Em raras ocasiões, os trabalhos agendados podem se tornar corrompidos ou conter contradição internas que não podem ser resolvidas.</span><span class="sxs-lookup"><span data-stu-id="2d142-197">On rare occasions, scheduled jobs can become corrupted or contain internal contradictions that cannot be resolved.</span></span> <span data-ttu-id="2d142-198">Normalmente, isso ocorre quando os arquivos XML para o trabalho agendado são editados manualmente, resultando em XML inválido.</span><span class="sxs-lookup"><span data-stu-id="2d142-198">Typically, this happens when the XML files for the scheduled job are manually edited, resulting in invalid XML.</span></span>

<span data-ttu-id="2d142-199">Quando um trabalho agendado está corrompido, o PowerShell tenta excluir o trabalho agendado, seu histórico de execução e seus resultados do disco.</span><span class="sxs-lookup"><span data-stu-id="2d142-199">When a scheduled job is corrupted, PowerShell attempts to delete the scheduled job, its execution history, and its results from disk.</span></span>

<span data-ttu-id="2d142-200">Se não for possível remover o trabalho agendado, você receberá uma mensagem de erro de trabalho corrompida toda vez que executar o `Get-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d142-200">If it cannot remove the scheduled job, you will get a corrupted job error message each time you run the `Get-ScheduledJob` cmdlet.</span></span>

<span data-ttu-id="2d142-201">Para remover um trabalho agendado corrompido, use um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="2d142-201">To remove a corrupted scheduled job, use either one of the following methods:</span></span>

<span data-ttu-id="2d142-202">Exclua o `<ScheduledJobName>` diretório para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d142-202">Delete the `<ScheduledJobName>` directory for the scheduled job.</span></span> <span data-ttu-id="2d142-203">Não exclua o diretório **ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="2d142-203">Don't delete the **ScheduledJob** directory.</span></span>

<span data-ttu-id="2d142-204">O local do diretório:</span><span class="sxs-lookup"><span data-stu-id="2d142-204">The directory's location:</span></span>

`$env:UserProfile\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

<span data-ttu-id="2d142-205">Por exemplo: </span><span class="sxs-lookup"><span data-stu-id="2d142-205">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>.`

<span data-ttu-id="2d142-206">Use Agendador de Tarefas para excluir o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2d142-206">Use Task Scheduler to delete the scheduled job.</span></span> <span data-ttu-id="2d142-207">As tarefas agendadas do PowerShell aparecem no seguinte caminho de Agendador de Tarefas:</span><span class="sxs-lookup"><span data-stu-id="2d142-207">PowerShell scheduled tasks appear in the following Task Scheduler path:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

## <a name="job-cmdlets-cant-consistently-find-scheduled-jobs"></a><span data-ttu-id="2d142-208">Os cmdlets de trabalho não podem encontrar trabalhos agendados de forma consistente</span><span class="sxs-lookup"><span data-stu-id="2d142-208">Job cmdlets can't consistently find scheduled jobs</span></span>

<span data-ttu-id="2d142-209">Quando o módulo **PSScheduledJob** não está na sessão atual, os cmdlets de trabalho não podem obter trabalhos agendados, iniciá-los ou obter seus resultados.</span><span class="sxs-lookup"><span data-stu-id="2d142-209">When the **PSScheduledJob** module isn't in the current session, the job cmdlets cannot get scheduled jobs, start them, or get their results.</span></span>

<span data-ttu-id="2d142-210">Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou execute ou obtenha qualquer cmdlet no módulo, como o `Get-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d142-210">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or run or get any cmdlet in the module, such as the `Get-ScheduledJob` cmdlet.</span></span>
<span data-ttu-id="2d142-211">A partir do PowerShell 3,0, os módulos são importados automaticamente quando você obtém ou usa qualquer cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="2d142-211">Beginning in PowerShell 3.0, modules are imported automatically when you get or use any cmdlet in the module.</span></span>

<span data-ttu-id="2d142-212">Quando o módulo **PSScheduledJob** não está na sessão atual, a sequência de comandos a seguir é possível.</span><span class="sxs-lookup"><span data-stu-id="2d142-212">When the **PSScheduledJob** module isn't in the current session, the following command sequence is possible.</span></span>

```powershell
Get-Job ProcessJob
```

```Output
Get-Job : The command cannot find the job because the job name
ProcessJob was not found.
Verify the value of the Name parameter, and then try the command again.
+ CategoryInfo          : ObjectNotFound: (ProcessJob:String) [Get-Job],
PSArgumentException
+ FullyQualifiedErrorId : JobWithSpecifiedNameNotFound,Microsoft.PowerShell.
Commands.GetJobCommand
```

```powershell
Get-Job
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command      Enabled
--         ----            --------        -------      -------
4          ProcessJob      {1}             Get-Process  True
```

```powershell
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State       HasMoreData     Location
--     ----         -------------   -----       -----------     --------
43     ProcessJob   PSScheduledJob  Completed   True            localhost
44     ProcessJob   PSScheduledJob  Completed   True            localhost
45     ProcessJob   PSScheduledJob  Completed   True            localhost
46     ProcessJob   PSScheduledJob  Completed   True            localhost
47     ProcessJob   PSScheduledJob  Completed   True            localhost
48     ProcessJob   PSScheduledJob  Completed   True            localhost
49     ProcessJob   PSScheduledJob  Completed   True            localhost
50     ProcessJob   PSScheduledJob  Completed   True            localhost
```

<span data-ttu-id="2d142-213">Esse comportamento ocorre porque o `Get-ScheduledJob` comando importa automaticamente o módulo **PSScheduledJob** e executa o comando.</span><span class="sxs-lookup"><span data-stu-id="2d142-213">This behavior occurs because the `Get-ScheduledJob` command automatically imports the **PSScheduledJob** module, and then runs the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d142-214">Confira também</span><span class="sxs-lookup"><span data-stu-id="2d142-214">See also</span></span>

[<span data-ttu-id="2d142-215">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="2d142-215">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="2d142-216">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="2d142-216">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="2d142-217">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="2d142-217">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

<span data-ttu-id="2d142-218">Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="2d142-218">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="2d142-219">Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="2d142-219">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
