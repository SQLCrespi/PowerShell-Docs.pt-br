---
description: Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: b28eb480e3f994696738d6053ea7e2622a743ce5
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "93196479"
---
# <a name="about-jobs"></a><span data-ttu-id="ed2cb-104">Sobre trabalhos</span><span class="sxs-lookup"><span data-stu-id="ed2cb-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="ed2cb-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="ed2cb-105">Short description</span></span>
<span data-ttu-id="ed2cb-106">Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="ed2cb-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="ed2cb-107">Long description</span></span>

<span data-ttu-id="ed2cb-108">O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-108">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="ed2cb-109">Há três soluções baseadas em trabalhos fornecidas pelo PowerShell para dar suporte à simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-109">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="ed2cb-110">Trabalho</span><span class="sxs-lookup"><span data-stu-id="ed2cb-110">Job</span></span>            |<span data-ttu-id="ed2cb-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="ed2cb-111">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="ed2cb-112">O comando e o script são executados em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-112">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="ed2cb-113">O comando e o script são executados em um processo separado no local</span><span class="sxs-lookup"><span data-stu-id="ed2cb-113">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="ed2cb-114">Tradução.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-114">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="ed2cb-115">O comando e o script são executados em um thread separado dentro do mesmo</span><span class="sxs-lookup"><span data-stu-id="ed2cb-115">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="ed2cb-116">processo no computador local.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-116">process on the local machine.</span></span>                                |

<span data-ttu-id="ed2cb-117">Cada tipo de trabalho tem benefícios e desvantagens.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-117">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="ed2cb-118">Executar o script remotamente em um computador separado ou em um processo separado tem grande isolamento.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-118">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="ed2cb-119">Quaisquer erros não afetarão outros trabalhos em execução ou o cliente que iniciou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-119">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="ed2cb-120">Mas a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-120">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="ed2cb-121">Todos os objetos passados para e da sessão remota devem ser serializados e, em seguida, desserializados conforme passam entre o cliente e a sessão de destino.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-121">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="ed2cb-122">A operação de serialização pode usar muitos recursos de computação e memória para grandes objetos de dados complexos.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-122">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

<span data-ttu-id="ed2cb-123">Este tópico explica como executar trabalhos em segundo plano no PowerShell em um computador local.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-123">This topic explains how to run background jobs in PowerShell on a local computer.</span></span> <span data-ttu-id="ed2cb-124">Para obter informações sobre como executar trabalhos em segundo plano em computadores remotos, consulte [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ed2cb-124">For information about running background jobs on remote computers, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span> <span data-ttu-id="ed2cb-125">Para obter mais informações sobre os trabalhos de thread, consulte [about_Thread_Jobs](about_Thread_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ed2cb-125">For more information about thread jobs, see [about_Thread_Jobs](about_Thread_Jobs.md).</span></span>

<span data-ttu-id="ed2cb-126">Quando você inicia um trabalho em segundo plano, o prompt de comando retorna imediatamente, mesmo se o trabalho levar um tempo estendido para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-126">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="ed2cb-127">É possível continuar a trabalhar na sessão sem interrupção enquanto o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-127">You can continue to work in the session without interruption while the job runs.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="ed2cb-128">Os cmdlets de trabalho</span><span class="sxs-lookup"><span data-stu-id="ed2cb-128">The job cmdlets</span></span>

|<span data-ttu-id="ed2cb-129">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ed2cb-129">Cmdlet</span></span>          |<span data-ttu-id="ed2cb-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="ed2cb-130">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="ed2cb-131">Inicia um trabalho em segundo plano em um computador local.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-131">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="ed2cb-132">Obtém os trabalhos em segundo plano que foram iniciados no</span><span class="sxs-lookup"><span data-stu-id="ed2cb-132">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="ed2cb-133">sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-133">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="ed2cb-134">Obtém os resultados de trabalhos em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-134">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="ed2cb-135">Interrompe um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-135">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="ed2cb-136">Suprime o prompt de comando até que um ou todos os trabalhos sejam</span><span class="sxs-lookup"><span data-stu-id="ed2cb-136">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="ed2cb-137">concluí.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-137">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="ed2cb-138">Exclui um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-138">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="ed2cb-139">O parâmetro **AsJob** cria um trabalho em segundo plano em um</span><span class="sxs-lookup"><span data-stu-id="ed2cb-139">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="ed2cb-140">computador remoto.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-140">remote computer.</span></span> <span data-ttu-id="ed2cb-141">Você pode usar `Invoke-Command` para executar</span><span class="sxs-lookup"><span data-stu-id="ed2cb-141">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="ed2cb-142">qualquer comando de trabalho remotamente, incluindo `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-142">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="ed2cb-143">Como iniciar um trabalho no computador local</span><span class="sxs-lookup"><span data-stu-id="ed2cb-143">How to start a job on the local computer</span></span>

<span data-ttu-id="ed2cb-144">Para iniciar um trabalho em segundo plano no computador local, use o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-144">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="ed2cb-145">Para gravar um `Start-Job` comando, coloque o comando que o trabalho executa entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="ed2cb-145">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="ed2cb-146">Use o parâmetro **scriptblock** para especificar o comando.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-146">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="ed2cb-147">O comando a seguir inicia um trabalho em segundo plano que executa um `Get-Process` comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-147">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="ed2cb-148">O `Start-Job` comando retorna um objeto que representa o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-148">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="ed2cb-149">O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados deste.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-149">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="ed2cb-150">Salve o objeto de trabalho em uma variável e, em seguida, use-o com os outros cmdlets de trabalho para gerenciar o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-150">Save the job object in a variable, and then use it with the other Job cmdlets to manage the background job.</span></span> <span data-ttu-id="ed2cb-151">O comando a seguir inicia um objeto de trabalho e salva o objeto de trabalho resultante na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-151">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="ed2cb-152">A partir do PowerShell 6,0, você pode usar um amersand ( `&` ) no final de um pipeline para iniciar um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-152">Beginning in PowerShell 6.0, you can use an amersand (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="ed2cb-153">O comando a seguir é funcionalmente equivalente ao comando acima.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-153">The following command is functionally equivalent to the command above.</span></span>

```powershell
$job = Get-Process &
```

<span data-ttu-id="ed2cb-154">O e comercial ( `&` ) é chamado de operador de segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-154">The ampersand (`&`) is called the background operator.</span></span> <span data-ttu-id="ed2cb-155">Para obter mais informações, consulte [background Operator](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="ed2cb-155">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="ed2cb-156">Você também pode usar o `Get-Job` cmdlet para obter objetos que representam os trabalhos iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-156">You can also use the `Get-Job` cmdlet to get objects that represent the jobs started in the current session.</span></span> <span data-ttu-id="ed2cb-157">`Get-Job` Retorna o mesmo objeto de trabalho que `Start-Job` retorna.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-157">`Get-Job` returns the same job object that `Start-Job` returns.</span></span>

## <a name="getting-job-objects"></a><span data-ttu-id="ed2cb-158">Obtendo objetos de trabalho</span><span class="sxs-lookup"><span data-stu-id="ed2cb-158">Getting job objects</span></span>

<span data-ttu-id="ed2cb-159">Para obter o objeto que representa os trabalhos em segundo plano que foram iniciados na sessão atual, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-159">To get object that represent the background jobs that were started in the current session, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="ed2cb-160">Sem parâmetros, `Get-Job` retorna todos os trabalhos que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-160">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

<span data-ttu-id="ed2cb-161">Por exemplo, o comando a seguir obtém os trabalhos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-161">For example, the following command gets the jobs in the current session.</span></span>

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

<span data-ttu-id="ed2cb-162">Você também pode salvar o objeto de trabalho em uma variável e usá-lo para representar o trabalho em um comando posterior.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-162">You can also save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="ed2cb-163">O comando a seguir obtém o trabalho com a ID 1 e salva-o na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-163">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

<span data-ttu-id="ed2cb-164">O objeto de trabalho contém o estado do trabalho, que indica se o trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-164">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="ed2cb-165">Um trabalho concluído tem um estado de **concluído** ou **com falha** .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-165">A finished job has a state of **Complete** or **Failed** .</span></span> <span data-ttu-id="ed2cb-166">Um trabalho também pode ser **bloqueado** ou **em execução** .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-166">A job might also be **blocked** or **running** .</span></span>

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="ed2cb-167">Obtendo os resultados de um trabalho</span><span class="sxs-lookup"><span data-stu-id="ed2cb-167">Getting the results of a job</span></span>

<span data-ttu-id="ed2cb-168">Quando você executa um trabalho em segundo plano, os resultados não aparecem imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-168">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="ed2cb-169">Em vez disso, o `Start-Job` cmdlet retorna um objeto de trabalho que representa o trabalho, mas ele não contém os resultados.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-169">Instead, the `Start-Job` cmdlet returns a job object that represents the job, but it does not contain the results.</span></span> <span data-ttu-id="ed2cb-170">Para obter os resultados de um trabalho em segundo plano, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-170">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="ed2cb-171">O comando a seguir usa o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-171">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="ed2cb-172">Ele usa um objeto de trabalho salvo na `$job` variável para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-172">It uses a job object saved in the `$job` variable to identify the job.</span></span>

```powershell
Receive-Job -Job $job
```

<span data-ttu-id="ed2cb-173">O `Receive-Job` cmdlet retorna os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-173">The `Receive-Job` cmdlet returns the results of the job.</span></span>

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

<span data-ttu-id="ed2cb-174">Você também pode salvar os resultados de um trabalho em uma variável.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-174">You can also save the results of a job in a variable.</span></span> <span data-ttu-id="ed2cb-175">O comando a seguir salva os resultados do trabalho na `$job` variável para a `$results` variável.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-175">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

<span data-ttu-id="ed2cb-176">E você pode salvar os resultados do trabalho em um arquivo usando o operador de redirecionamento ( `>` ) ou o `Out-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-176">And, you can save the results of the job in a file by using the redirection operator (`>`) or the `Out-File` cmdlet.</span></span> <span data-ttu-id="ed2cb-177">O comando a seguir usa o operador de redirecionamento para salvar os resultados do trabalho na `$job` variável no `Results.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-177">The following command uses the redirection operator to save the results of the job in the `$job` variable in the `Results.txt` file.</span></span>

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="ed2cb-178">Obtendo e mantendo resultados parciais do trabalho</span><span class="sxs-lookup"><span data-stu-id="ed2cb-178">Getting and keeping partial job results</span></span>

<span data-ttu-id="ed2cb-179">O `Receive-Job` cmdlet obtém os resultados de um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-179">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="ed2cb-180">Se o trabalho estiver concluído, `Receive-Job` Obtém todos os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-180">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="ed2cb-181">Se o trabalho ainda estiver em execução, `Receive-Job` o obterá os resultados gerados até o momento.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-181">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="ed2cb-182">Você pode executar `Receive-Job` comandos novamente para obter os resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-182">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="ed2cb-183">Quando o `Receive-Job` retorna resultados, por padrão, ele exclui os resultados do cache onde os resultados do trabalho são armazenados.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-183">When `Receive-Job` returns results, by default, it deletes those results from the cache where job results are stored.</span></span> <span data-ttu-id="ed2cb-184">Se você executar outro `Receive-Job` comando, obterá apenas os resultados que ainda não foram recebidos.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-184">If you run another `Receive-Job` command, you get only the results that are not yet received.</span></span>

<span data-ttu-id="ed2cb-185">Os comandos a seguir mostram os resultados da `Receive-Job` execução de comandos antes que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-185">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

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

<span data-ttu-id="ed2cb-186">Para evitar `Receive-Job` a exclusão dos resultados do trabalho que ele retornou, use o parâmetro **Keep** .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-186">To prevent `Receive-Job` from deleting the job results that it has returned, use the **Keep** parameter.</span></span> <span data-ttu-id="ed2cb-187">Como resultado, `Receive-Job` retorna todos os resultados que foram gerados até esse momento.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-187">As a result, `Receive-Job` returns all of the results that have been generated until that time.</span></span>

<span data-ttu-id="ed2cb-188">Os comandos a seguir mostram o efeito de usar o parâmetro **Keep** em um trabalho que ainda não está concluído.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-188">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

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

## <a name="waiting-for-the-results"></a><span data-ttu-id="ed2cb-189">Aguardando os resultados</span><span class="sxs-lookup"><span data-stu-id="ed2cb-189">Waiting for the results</span></span>

<span data-ttu-id="ed2cb-190">Se você executar um comando que leva muito tempo para ser concluído, poderá usar as propriedades do objeto de trabalho para determinar quando o trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-190">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="ed2cb-191">O comando a seguir usa o `Get-Job` objeto para obter todos os trabalhos em segundo plano na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-191">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="ed2cb-192">Os resultados aparecem em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-192">The results appear in a table.</span></span> <span data-ttu-id="ed2cb-193">O status do trabalho é exibido na coluna **estado** .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-193">The status of the job appears in the **State** column.</span></span>

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="ed2cb-194">Nesse caso, a propriedade State revela que o trabalho 2 ainda está em execução.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-194">In this case, the State property reveals that Job 2 is still running.</span></span> <span data-ttu-id="ed2cb-195">Se você usar o `Receive-Job` cmdlet para obter os resultados do trabalho agora, os resultados ficarão incompletos.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-195">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="ed2cb-196">Você pode usar o `Receive-Job` cmdlet repetidamente para obter todos os resultados.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-196">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="ed2cb-197">Por padrão, cada vez que você o usa, obtém apenas os resultados que ainda não foram recebidos, mas você pode usar o parâmetro **Keep** do `Receive-Job` cmdlet para manter os resultados, mesmo que eles já tenham sido recebidos.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-197">By default, each time you use it, you get only the results that were not already received, but you can use the **Keep** parameter of the `Receive-Job` cmdlet to retain the results, even though they were already received.</span></span>

<span data-ttu-id="ed2cb-198">Você pode gravar os resultados parciais em um arquivo e, em seguida, acrescentar os resultados mais recentes à medida que eles chegam, ou você pode aguardar e verificar o estado do trabalho mais tarde.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-198">You can write the partial results to a file and then append newer results as they arrive or you can wait and check the state of the job later.</span></span>

<span data-ttu-id="ed2cb-199">Você pode usar o parâmetro **Wait** do `Receive-Job` cmdlet, que não retorna o prompt de comando até que o trabalho seja concluído e que todos os resultados estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-199">You can use the **Wait** parameter of the `Receive-Job` cmdlet, which does not return the command prompt until the job is complete and all results are available.</span></span>

<span data-ttu-id="ed2cb-200">Você também pode usar o `Wait-Job` cmdlet para aguardar qualquer ou todos os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-200">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="ed2cb-201">`Wait-Job` permite que você aguarde um trabalho específico, para todos os trabalhos ou para que qualquer um dos trabalhos seja concluído.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-201">`Wait-Job` lets you wait for a particular job, for all jobs, or for any of the jobs to be completed.</span></span>

<span data-ttu-id="ed2cb-202">O comando a seguir usa o `Wait-Job` cmdlet para aguardar um trabalho com **ID**</span><span class="sxs-lookup"><span data-stu-id="ed2cb-202">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="ed2cb-203">Como resultado, o prompt do PowerShell é suprimido até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-203">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="ed2cb-204">Você também pode aguardar um período de tempo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-204">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="ed2cb-205">Esse comando usa o parâmetro **Timeout** para limitar a espera de 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-205">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="ed2cb-206">Quando o tempo expira, o prompt de comando retorna, mas o trabalho continua a ser executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-206">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="ed2cb-207">Interrompendo um trabalho</span><span class="sxs-lookup"><span data-stu-id="ed2cb-207">Stopping a job</span></span>

<span data-ttu-id="ed2cb-208">Para interromper um trabalho em segundo plano, use o `Stop-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-208">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="ed2cb-209">O comando a seguir inicia um trabalho para obter todas as entradas no log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-209">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="ed2cb-210">Ele salva o objeto de trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-210">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="ed2cb-211">O comando a seguir interrompe o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-211">The following command stops the job.</span></span> <span data-ttu-id="ed2cb-212">Ele usa um operador de pipeline ( `|` ) para enviar o trabalho na `$job` variável para `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-212">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="ed2cb-213">Excluindo um trabalho</span><span class="sxs-lookup"><span data-stu-id="ed2cb-213">Deleting a job</span></span>

<span data-ttu-id="ed2cb-214">Para excluir um trabalho em segundo plano, use o `Remove-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-214">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="ed2cb-215">O comando a seguir exclui o trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-215">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="ed2cb-216">Investigando um trabalho com falha</span><span class="sxs-lookup"><span data-stu-id="ed2cb-216">Investigating a failed job</span></span>

<span data-ttu-id="ed2cb-217">Para descobrir por que um trabalho falhou, use a propriedade **Reason** do objeto Job.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-217">To find out why a job failed, use the **Reason** property of the job object.</span></span>

<span data-ttu-id="ed2cb-218">O comando a seguir inicia um trabalho sem as credenciais necessárias.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-218">The following command starts a job without the required credentials.</span></span> <span data-ttu-id="ed2cb-219">Ele salva o objeto de trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-219">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="ed2cb-220">O comando a seguir usa a propriedade Reason para localizar o erro que causou a falha do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-220">The following command uses the Reason property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="ed2cb-221">Nesse caso, o trabalho falhou porque o computador remoto exigia credenciais explícitas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-221">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="ed2cb-222">O valor da propriedade **Reason** é:</span><span class="sxs-lookup"><span data-stu-id="ed2cb-222">The value of the **Reason** property is:</span></span>

<span data-ttu-id="ed2cb-223">Falha ao conectar-se ao servidor remoto com a seguinte mensagem de erro: "acesso negado".</span><span class="sxs-lookup"><span data-stu-id="ed2cb-223">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="ed2cb-224">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed2cb-224">See also</span></span>

- [<span data-ttu-id="ed2cb-225">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="ed2cb-225">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="ed2cb-226">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="ed2cb-226">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="ed2cb-227">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="ed2cb-227">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="ed2cb-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="ed2cb-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="ed2cb-229">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="ed2cb-229">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="ed2cb-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="ed2cb-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="ed2cb-231">Get-Job</span><span class="sxs-lookup"><span data-stu-id="ed2cb-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="ed2cb-232">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="ed2cb-232">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="ed2cb-233">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="ed2cb-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="ed2cb-234">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="ed2cb-234">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="ed2cb-235">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="ed2cb-235">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="ed2cb-236">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ed2cb-236">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
