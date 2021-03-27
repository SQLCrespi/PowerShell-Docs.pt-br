---
description: Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 9ad4a30bf7596914abc1a604f3b8a27bc5b146b5
ms.sourcegitcommit: ca5a89977913bad9efec6bcc23a792d113ec0396
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "105631027"
---
# <a name="about-jobs"></a><span data-ttu-id="6117e-104">Sobre trabalhos</span><span class="sxs-lookup"><span data-stu-id="6117e-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="6117e-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="6117e-105">Short description</span></span>
<span data-ttu-id="6117e-106">Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6117e-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="6117e-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="6117e-107">Long description</span></span>

<span data-ttu-id="6117e-108">O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="6117e-108">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="6117e-109">Há três tipos de trabalhos fornecidos pelo PowerShell para dar suporte à simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="6117e-109">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="6117e-110">`RemoteJob` -Comandos e scripts executados em uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="6117e-110">`RemoteJob` - Commands and scripts run on a remote session.</span></span> <span data-ttu-id="6117e-111">Para obter informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6117e-111">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="6117e-112">`BackgroundJob` -Comandos e scripts são executados em um processo separado no computador local.</span><span class="sxs-lookup"><span data-stu-id="6117e-112">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span>
- <span data-ttu-id="6117e-113">`PSTaskJob` ou `ThreadJob` -comandos e scripts são executados em um thread separado dentro do mesmo processo no computador local.</span><span class="sxs-lookup"><span data-stu-id="6117e-113">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="6117e-114">Para obter mais informações, consulte [about_Thread_Jobs](about_Thread_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6117e-114">For more information, see [about_Thread_Jobs](about_Thread_Jobs.md).</span></span>

<span data-ttu-id="6117e-115">Executar scripts remotamente, em um computador separado ou em um processo separado, fornece um excelente isolamento.</span><span class="sxs-lookup"><span data-stu-id="6117e-115">Running scripts remotely, on a separate machine or in a separate process, provides great isolation.</span></span> <span data-ttu-id="6117e-116">Os erros que ocorrem no trabalho remoto não afetam outros trabalhos em execução ou a sessão pai que iniciou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-116">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="6117e-117">No entanto, a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto.</span><span class="sxs-lookup"><span data-stu-id="6117e-117">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="6117e-118">Todos os objetos são serializados e desserializados à medida que são passados entre a sessão pai e a sessão remota (trabalho).</span><span class="sxs-lookup"><span data-stu-id="6117e-118">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="6117e-119">A serialização de grandes objetos de dados complexos pode consumir grandes quantidades de recursos de computação e memória e transferir grandes quantidades de dados pela rede.</span><span class="sxs-lookup"><span data-stu-id="6117e-119">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

<span data-ttu-id="6117e-120">Os trabalhos baseados em thread não são tão robustos quanto os trabalhos remotos e em segundo plano, pois eles são executados no mesmo processo em threads diferentes.</span><span class="sxs-lookup"><span data-stu-id="6117e-120">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="6117e-121">Se um trabalho tiver um erro crítico que falha no processo, todos os outros trabalhos no processo serão encerrados.</span><span class="sxs-lookup"><span data-stu-id="6117e-121">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="6117e-122">No entanto, os trabalhos baseados em thread exigem menos sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6117e-122">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="6117e-123">Eles não usam a camada ou serialização de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="6117e-123">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="6117e-124">Os objetos de resultado são retornados como referências a objetos dinâmicos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6117e-124">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="6117e-125">Sem essa sobrecarga, os trabalhos baseados em threads são executados mais rapidamente e usam menos recursos do que os outros tipos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-125">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6117e-126">A sessão pai que criou o trabalho também monitora o status do trabalho e coleta dados do pipeline.</span><span class="sxs-lookup"><span data-stu-id="6117e-126">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="6117e-127">O processo filho do trabalho é encerrado pelo processo pai quando o trabalho atinge um estado concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-127">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="6117e-128">Se a sessão pai for encerrada, todos os trabalhos filho em execução serão encerrados junto com seus processos filho.</span><span class="sxs-lookup"><span data-stu-id="6117e-128">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="6117e-129">Há duas maneiras de solucionar essa situação:</span><span class="sxs-lookup"><span data-stu-id="6117e-129">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="6117e-130">Use `Invoke-Command` para criar trabalhos que são executados em sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="6117e-130">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="6117e-131">Para obter mais informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6117e-131">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="6117e-132">Use `Start-Process` para criar um novo processo em vez de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-132">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="6117e-133">Para obter mais informações, consulte [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="6117e-133">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="6117e-134">Os cmdlets de trabalho</span><span class="sxs-lookup"><span data-stu-id="6117e-134">The job cmdlets</span></span>

|<span data-ttu-id="6117e-135">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6117e-135">Cmdlet</span></span>          |<span data-ttu-id="6117e-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="6117e-136">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="6117e-137">Inicia um trabalho em segundo plano em um computador local.</span><span class="sxs-lookup"><span data-stu-id="6117e-137">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="6117e-138">Obtém os trabalhos em segundo plano que foram iniciados no</span><span class="sxs-lookup"><span data-stu-id="6117e-138">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="6117e-139">sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6117e-139">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="6117e-140">Obtém os resultados de trabalhos em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6117e-140">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="6117e-141">Interrompe um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6117e-141">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="6117e-142">Suprime o prompt de comando até que um ou todos os trabalhos sejam</span><span class="sxs-lookup"><span data-stu-id="6117e-142">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="6117e-143">concluí.</span><span class="sxs-lookup"><span data-stu-id="6117e-143">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="6117e-144">Exclui um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6117e-144">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="6117e-145">O parâmetro **AsJob** cria um trabalho em segundo plano em um</span><span class="sxs-lookup"><span data-stu-id="6117e-145">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="6117e-146">computador remoto.</span><span class="sxs-lookup"><span data-stu-id="6117e-146">remote computer.</span></span> <span data-ttu-id="6117e-147">Você pode usar `Invoke-Command` para executar</span><span class="sxs-lookup"><span data-stu-id="6117e-147">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="6117e-148">qualquer comando de trabalho remotamente, incluindo `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="6117e-148">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="6117e-149">Como iniciar um trabalho no computador local</span><span class="sxs-lookup"><span data-stu-id="6117e-149">How to start a job on the local computer</span></span>

<span data-ttu-id="6117e-150">Para iniciar um trabalho em segundo plano no computador local, use o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6117e-150">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="6117e-151">Para gravar um `Start-Job` comando, coloque o comando que o trabalho executa entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="6117e-151">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="6117e-152">Use o parâmetro **scriptblock** para especificar o comando.</span><span class="sxs-lookup"><span data-stu-id="6117e-152">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="6117e-153">O comando a seguir inicia um trabalho em segundo plano que executa um `Get-Process` comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="6117e-153">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="6117e-154">Quando você inicia um trabalho em segundo plano, o prompt de comando retorna imediatamente, mesmo se o trabalho levar um tempo estendido para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-154">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="6117e-155">É possível continuar a trabalhar na sessão sem interrupção enquanto o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="6117e-155">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="6117e-156">O `Start-Job` comando retorna um objeto que representa o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-156">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="6117e-157">O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados deste.</span><span class="sxs-lookup"><span data-stu-id="6117e-157">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="6117e-158">Você pode salvar o objeto de trabalho em uma variável e, em seguida, usá-lo com outros cmdlets de **trabalho** para gerenciar o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6117e-158">You can save the job object in a variable and then use it with the other **Job** cmdlets to manage the background job.</span></span> <span data-ttu-id="6117e-159">O comando a seguir inicia um objeto de trabalho e salva o objeto de trabalho resultante na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="6117e-159">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="6117e-160">A partir do PowerShell 6,0, você pode usar o operador de segundo plano ( `&` ) no final de um pipeline para iniciar um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6117e-160">Beginning in PowerShell 6.0, you can use the background operator (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="6117e-161">Para obter mais informações, consulte [background Operator](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="6117e-161">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="6117e-162">O uso do operador background é funcionalmente equivalente ao uso do `Start-Job` cmdlet no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="6117e-162">Using the background operator is functionally equivalent to using the `Start-Job` cmdlet in the previous example.</span></span>

```powershell
$job = Get-Process &
```

## <a name="getting-job-objects"></a><span data-ttu-id="6117e-163">Obtendo objetos de trabalho</span><span class="sxs-lookup"><span data-stu-id="6117e-163">Getting job objects</span></span>

<span data-ttu-id="6117e-164">O `Get-Job` cmdlet retorna objetos que representam os trabalhos em segundo plano que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6117e-164">The `Get-Job` cmdlet returns objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="6117e-165">Sem parâmetros, `Get-Job` retorna todos os trabalhos que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6117e-165">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="6117e-166">O objeto de trabalho contém o estado do trabalho, que indica se o trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-166">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="6117e-167">Um trabalho concluído tem um estado de **concluído** ou **com falha**.</span><span class="sxs-lookup"><span data-stu-id="6117e-167">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="6117e-168">Um trabalho também pode ser **bloqueado** ou **em execução**.</span><span class="sxs-lookup"><span data-stu-id="6117e-168">A job might also be **Blocked** or **Running**.</span></span>

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

<span data-ttu-id="6117e-169">Você pode salvar o objeto de trabalho em uma variável e usá-lo para representar o trabalho em um comando posterior.</span><span class="sxs-lookup"><span data-stu-id="6117e-169">You can save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="6117e-170">O comando a seguir obtém o trabalho com a ID 1 e salva-o na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="6117e-170">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="6117e-171">Obtendo os resultados de um trabalho</span><span class="sxs-lookup"><span data-stu-id="6117e-171">Getting the results of a job</span></span>

<span data-ttu-id="6117e-172">Quando você executa um trabalho em segundo plano, os resultados não aparecem imediatamente.</span><span class="sxs-lookup"><span data-stu-id="6117e-172">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="6117e-173">Para obter os resultados de um trabalho em segundo plano, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6117e-173">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="6117e-174">O exemplo a seguir, o `Receive-Job` cmdlet obtém os resultados do trabalho usando o objeto de trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="6117e-174">The following example, the `Receive-Job` cmdlet gets the results of the job using job object in the `$job` variable.</span></span>

```powershell
Receive-Job -Job $job
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
...
```

<span data-ttu-id="6117e-175">Você pode salvar os resultados de um trabalho em uma variável.</span><span class="sxs-lookup"><span data-stu-id="6117e-175">You can save the results of a job in a variable.</span></span> <span data-ttu-id="6117e-176">O comando a seguir salva os resultados do trabalho na `$job` variável para a `$results` variável.</span><span class="sxs-lookup"><span data-stu-id="6117e-176">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="6117e-177">Obtendo e mantendo resultados parciais do trabalho</span><span class="sxs-lookup"><span data-stu-id="6117e-177">Getting and keeping partial job results</span></span>

<span data-ttu-id="6117e-178">O `Receive-Job` cmdlet obtém os resultados de um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6117e-178">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="6117e-179">Se o trabalho estiver concluído, `Receive-Job` Obtém todos os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-179">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="6117e-180">Se o trabalho ainda estiver em execução, `Receive-Job` o obterá os resultados gerados até o momento.</span><span class="sxs-lookup"><span data-stu-id="6117e-180">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="6117e-181">Você pode executar `Receive-Job` comandos novamente para obter os resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="6117e-181">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="6117e-182">Por padrão, `Receive-Job` o exclui os resultados do cache onde os resultados do trabalho são armazenados.</span><span class="sxs-lookup"><span data-stu-id="6117e-182">By default, `Receive-Job` deletes the results from the cache where job results are stored.</span></span> <span data-ttu-id="6117e-183">Ao executar `Receive-Job` novamente, você obtém apenas os novos resultados que chegaram após a primeira execução.</span><span class="sxs-lookup"><span data-stu-id="6117e-183">When you run `Receive-Job` again, you get only the new results that arrived after the first run.</span></span>

<span data-ttu-id="6117e-184">Os comandos a seguir mostram os resultados da `Receive-Job` execução de comandos antes que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-184">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

<span data-ttu-id="6117e-185">Use o parâmetro **Keep** para impedir `Receive-Job` a exclusão dos resultados do trabalho que são retornados.</span><span class="sxs-lookup"><span data-stu-id="6117e-185">Use the **Keep** parameter to prevent `Receive-Job` from deleting the job results that are returned.</span></span> <span data-ttu-id="6117e-186">Os comandos a seguir mostram o efeito de usar o parâmetro **Keep** em um trabalho que ainda não está concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-186">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

### <a name="waiting-for-the-results"></a><span data-ttu-id="6117e-187">Aguardando os resultados</span><span class="sxs-lookup"><span data-stu-id="6117e-187">Waiting for the results</span></span>

<span data-ttu-id="6117e-188">Se você executar um comando que leva muito tempo para ser concluído, poderá usar as propriedades do objeto de trabalho para determinar quando o trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-188">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="6117e-189">O comando a seguir usa o `Get-Job` objeto para obter todos os trabalhos em segundo plano na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6117e-189">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="6117e-190">Os resultados aparecem em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="6117e-190">The results appear in a table.</span></span> <span data-ttu-id="6117e-191">O status do trabalho é exibido na coluna **estado** .</span><span class="sxs-lookup"><span data-stu-id="6117e-191">The status of the job appears in the **State** column.</span></span>

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="6117e-192">Nesse caso, a propriedade **State** revela que o trabalho 2 ainda está em execução.</span><span class="sxs-lookup"><span data-stu-id="6117e-192">In this case, the **State** property reveals that Job 2 is still running.</span></span> <span data-ttu-id="6117e-193">Se você usar o `Receive-Job` cmdlet para obter os resultados do trabalho agora, os resultados ficarão incompletos.</span><span class="sxs-lookup"><span data-stu-id="6117e-193">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="6117e-194">Você pode usar o `Receive-Job` cmdlet repetidamente para obter todos os resultados.</span><span class="sxs-lookup"><span data-stu-id="6117e-194">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="6117e-195">Use a propriedade **State** para determinar quando o trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-195">Use the **State** property to determine when the job is complete.</span></span>

<span data-ttu-id="6117e-196">Você também pode usar o parâmetro **Wait** do `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6117e-196">You can also use the **Wait** parameter of the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="6117e-197">Quando usar esse parâmetro, o cmdlet não retorna o prompt de comando até que o trabalho seja concluído e todos os resultados estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6117e-197">When use use this parameter, the cmdlet does not return the command prompt until the job is completed and all results are available.</span></span>

<span data-ttu-id="6117e-198">Você também pode usar o `Wait-Job` cmdlet para aguardar qualquer ou todos os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-198">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="6117e-199">`Wait-Job` permite que você aguarde um ou mais trabalhos específicos ou todos eles.</span><span class="sxs-lookup"><span data-stu-id="6117e-199">`Wait-Job` lets you wait for one or more specific job or for all jobs.</span></span>
<span data-ttu-id="6117e-200">O comando a seguir usa o `Wait-Job` cmdlet para aguardar um trabalho com **ID**</span><span class="sxs-lookup"><span data-stu-id="6117e-200">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="6117e-201">Como resultado, o prompt do PowerShell é suprimido até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="6117e-201">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="6117e-202">Você também pode aguardar um período de tempo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6117e-202">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="6117e-203">Esse comando usa o parâmetro **Timeout** para limitar a espera de 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="6117e-203">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="6117e-204">Quando o tempo expira, o prompt de comando retorna, mas o trabalho continua a ser executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="6117e-204">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="6117e-205">Interrompendo um trabalho</span><span class="sxs-lookup"><span data-stu-id="6117e-205">Stopping a job</span></span>

<span data-ttu-id="6117e-206">Para interromper um trabalho em segundo plano, use o `Stop-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6117e-206">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="6117e-207">O comando a seguir inicia um trabalho para obter todas as entradas no log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="6117e-207">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="6117e-208">Ele salva o objeto de trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="6117e-208">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="6117e-209">O comando a seguir interrompe o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-209">The following command stops the job.</span></span> <span data-ttu-id="6117e-210">Ele usa um operador de pipeline ( `|` ) para enviar o trabalho na `$job` variável para `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="6117e-210">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="6117e-211">Excluindo um trabalho</span><span class="sxs-lookup"><span data-stu-id="6117e-211">Deleting a job</span></span>

<span data-ttu-id="6117e-212">Para excluir um trabalho em segundo plano, use o `Remove-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6117e-212">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="6117e-213">O comando a seguir exclui o trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="6117e-213">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="6117e-214">Investigando um trabalho com falha</span><span class="sxs-lookup"><span data-stu-id="6117e-214">Investigating a failed job</span></span>

<span data-ttu-id="6117e-215">Os trabalhos podem falhar por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="6117e-215">Jobs can fail for many reasons.</span></span> <span data-ttu-id="6117e-216">o objeto de trabalho contém uma propriedade **Reason** que contém informações sobre a causa da falha.</span><span class="sxs-lookup"><span data-stu-id="6117e-216">the job object contains a **Reason** property that contains information about the cause of the failure.</span></span>

<span data-ttu-id="6117e-217">O exemplo a seguir inicia um trabalho sem as credenciais necessárias.</span><span class="sxs-lookup"><span data-stu-id="6117e-217">The following example starts a job without the required credentials.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="6117e-218">Inspecione a propriedade **Reason** para localizar o erro que causou a falha do trabalho.</span><span class="sxs-lookup"><span data-stu-id="6117e-218">Inspect the **Reason** property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="6117e-219">Nesse caso, o trabalho falhou porque o computador remoto exigia credenciais explícitas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="6117e-219">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="6117e-220">A propriedade **Reason** contém a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="6117e-220">The **Reason** property contains the following message:</span></span>

> <span data-ttu-id="6117e-221">Falha ao conectar-se ao servidor remoto com a seguinte mensagem de erro: "acesso negado".</span><span class="sxs-lookup"><span data-stu-id="6117e-221">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="6117e-222">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6117e-222">See also</span></span>

- [<span data-ttu-id="6117e-223">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="6117e-223">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="6117e-224">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="6117e-224">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="6117e-225">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="6117e-225">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="6117e-226">about_Remote</span><span class="sxs-lookup"><span data-stu-id="6117e-226">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="6117e-227">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="6117e-227">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="6117e-228">Start-Job</span><span class="sxs-lookup"><span data-stu-id="6117e-228">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="6117e-229">Get-Job</span><span class="sxs-lookup"><span data-stu-id="6117e-229">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="6117e-230">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="6117e-230">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="6117e-231">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="6117e-231">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="6117e-232">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="6117e-232">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="6117e-233">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="6117e-233">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="6117e-234">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="6117e-234">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
