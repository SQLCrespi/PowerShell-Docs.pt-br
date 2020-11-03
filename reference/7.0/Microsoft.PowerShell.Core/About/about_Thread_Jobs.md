---
description: Fornece informações sobre os trabalhos baseados em thread do PowerShell. Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 973d0ddf18b63cd7462817cf68f7c5d7466f4724
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "93196495"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="75e48-105">Sobre os trabalhos de thread</span><span class="sxs-lookup"><span data-stu-id="75e48-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="75e48-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="75e48-106">Short description</span></span>

<span data-ttu-id="75e48-107">Fornece informações sobre os trabalhos baseados em thread do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75e48-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="75e48-108">Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="75e48-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="75e48-109">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="75e48-109">Long description</span></span>

<span data-ttu-id="75e48-110">Este artigo explica como executar trabalhos de thread no PowerShell em um computador local.</span><span class="sxs-lookup"><span data-stu-id="75e48-110">This article explains how to run thread jobs in PowerShell on a local computer.</span></span>
<span data-ttu-id="75e48-111">Para obter informações sobre como executar trabalhos em segundo plano em um computador local, consulte [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="75e48-111">For information about running background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span>

<span data-ttu-id="75e48-112">Inicie um trabalho de thread usando o `Start-ThreadJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75e48-112">Start a thread job by using the `Start-ThreadJob` cmdlet.</span></span> <span data-ttu-id="75e48-113">Esse cmdlet está disponível no módulo **ThreadJob** que acompanha o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75e48-113">This cmdlet is available in the **ThreadJob** module that ships with PowerShell.</span></span>
<span data-ttu-id="75e48-114">`Start-ThreadJob` Retorna um único objeto de trabalho que encapsula o comando ou script em execução e pode ser usado com todos os cmdlets de manipulação de trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75e48-114">`Start-ThreadJob` returns a single job object that encapsulates the running command or script, and can be used with all PowerShell job manipulating cmdlets.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="75e48-115">Os cmdlets de trabalho</span><span class="sxs-lookup"><span data-stu-id="75e48-115">The job cmdlets</span></span>

|<span data-ttu-id="75e48-116">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="75e48-116">Cmdlet</span></span>           |<span data-ttu-id="75e48-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="75e48-117">Description</span></span>                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|<span data-ttu-id="75e48-118">Inicia um trabalho de thread em um computador local.</span><span class="sxs-lookup"><span data-stu-id="75e48-118">Starts a thread job on a local computer.</span></span>               |
|`Get-Job`        |<span data-ttu-id="75e48-119">Obtém os trabalhos que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="75e48-119">Gets the jobs that were started in the current session.</span></span>|
|`Receive-Job`    |<span data-ttu-id="75e48-120">Obtém os resultados dos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="75e48-120">Gets the results of jobs.</span></span>                              |
|`Stop-Job`       |<span data-ttu-id="75e48-121">Interrompe um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="75e48-121">Stops a running job.</span></span>                                   |
|`Wait-Job`       |<span data-ttu-id="75e48-122">Suprime o prompt de comando até que um ou todos os trabalhos sejam</span><span class="sxs-lookup"><span data-stu-id="75e48-122">Suppresses the command prompt until one or all jobs are</span></span>|
|                 |<span data-ttu-id="75e48-123">concluí.</span><span class="sxs-lookup"><span data-stu-id="75e48-123">complete.</span></span>                                              |
|`Remove-Job`     |<span data-ttu-id="75e48-124">Exclui um trabalho.</span><span class="sxs-lookup"><span data-stu-id="75e48-124">Deletes a job.</span></span>                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a><span data-ttu-id="75e48-125">Como iniciar um trabalho de thread no computador local</span><span class="sxs-lookup"><span data-stu-id="75e48-125">How to start a thread job on the local computer</span></span>

<span data-ttu-id="75e48-126">Para iniciar um trabalho de thread no computador local, use o `Start-ThreadJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75e48-126">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet.</span></span>

<span data-ttu-id="75e48-127">Para gravar um `Start-ThreadJob` comando, coloque o comando ou o script que o trabalho executa entre chaves ( `{ }` ).</span><span class="sxs-lookup"><span data-stu-id="75e48-127">To write a `Start-ThreadJob` command, enclose the command or script the job runs in curly braces (`{ }`).</span></span>

<span data-ttu-id="75e48-128">O comando a seguir inicia um trabalho de thread que executa um `Get-Process` comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="75e48-128">The following command starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="75e48-129">O `Start-ThreadJob` comando retorna um `ThreadJob` objeto que representa o trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="75e48-129">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="75e48-130">O objeto de trabalho contém informações úteis sobre o trabalho, incluindo seu status de execução atual.</span><span class="sxs-lookup"><span data-stu-id="75e48-130">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="75e48-131">Ele coleta os resultados do trabalho à medida que os resultados são gerados.</span><span class="sxs-lookup"><span data-stu-id="75e48-131">It collects the results of the job as the results are being generated.</span></span>

<span data-ttu-id="75e48-132">Para gravar um `ForEach-Object -Parallel` comando, redirecione os dados para o comando e coloque o comando ou o script que o trabalho executa entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="75e48-132">To write a `ForEach-Object -Parallel` command, pipe data to the command and enclose the command or script the job runs in curly braces(`{}`).</span></span> <span data-ttu-id="75e48-133">Use a `-AsJob` opção de parâmetro para que um objeto de trabalho seja retornado.</span><span class="sxs-lookup"><span data-stu-id="75e48-133">Use the `-AsJob` parameter switch so that a job object is returned.</span></span>

<span data-ttu-id="75e48-134">O comando a seguir inicia um trabalho que contém trabalhos filho para cada valor de entrada canalizado para o comando.</span><span class="sxs-lookup"><span data-stu-id="75e48-134">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="75e48-135">Cada trabalho filho executa o `Write-Output` comando com um valor de entrada canalizado como o argumento.</span><span class="sxs-lookup"><span data-stu-id="75e48-135">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="75e48-136">O `ForEach-Object -Parallel` comando retorna um `PSTaskJob` objeto que contém trabalhos filho para cada valor de entrada canalizado.</span><span class="sxs-lookup"><span data-stu-id="75e48-136">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="75e48-137">O objeto de trabalho contém informações úteis sobre o status de execução de trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="75e48-137">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="75e48-138">Ele coleta os resultados dos trabalhos filho à medida que os resultados são gerados.</span><span class="sxs-lookup"><span data-stu-id="75e48-138">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="75e48-139">Como aguardar a conclusão de um trabalho e recuperar os resultados do trabalho</span><span class="sxs-lookup"><span data-stu-id="75e48-139">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="75e48-140">Você pode usar os cmdlets de trabalho do PowerShell, como `Wait-Job` e `Receive-Job` para aguardar a conclusão de um trabalho e, em seguida, retornar todos os resultados gerados pelo trabalho.</span><span class="sxs-lookup"><span data-stu-id="75e48-140">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="75e48-141">O comando a seguir inicia um trabalho de thread que executa um `Get-Process` comando, aguarda até que o comando seja concluído e, finalmente, retorna todos os resultados de dados gerados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="75e48-141">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="75e48-142">O comando a seguir inicia um trabalho que executa um `Write-Output` comando para cada entrada canalizada, aguarda que todos os trabalhos filho sejam concluídos e, finalmente, retorna todos os resultados de dados gerados pelos trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="75e48-142">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="75e48-143">O `Receive-Job` cmdlet retorna os resultados dos trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="75e48-143">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="75e48-144">Como cada trabalho filho é executado em paralelo, a ordem dos resultados gerados não é garantida.</span><span class="sxs-lookup"><span data-stu-id="75e48-144">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="powershell-concurrency-and-jobs"></a><span data-ttu-id="75e48-145">Simultaneidade e trabalhos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="75e48-145">PowerShell concurrency and jobs</span></span>

<span data-ttu-id="75e48-146">O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="75e48-146">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="75e48-147">Há três soluções baseadas em trabalhos fornecidas pelo PowerShell para dar suporte à simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="75e48-147">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="75e48-148">Trabalho</span><span class="sxs-lookup"><span data-stu-id="75e48-148">Job</span></span>            |<span data-ttu-id="75e48-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="75e48-149">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="75e48-150">O comando e o script são executados em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="75e48-150">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="75e48-151">O comando e o script são executados em um processo separado no local</span><span class="sxs-lookup"><span data-stu-id="75e48-151">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="75e48-152">Tradução.</span><span class="sxs-lookup"><span data-stu-id="75e48-152">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="75e48-153">O comando e o script são executados em um thread separado dentro do mesmo</span><span class="sxs-lookup"><span data-stu-id="75e48-153">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="75e48-154">processo no computador local.</span><span class="sxs-lookup"><span data-stu-id="75e48-154">process on the local machine.</span></span>                                |

<span data-ttu-id="75e48-155">Cada tipo de trabalho tem benefícios e desvantagens.</span><span class="sxs-lookup"><span data-stu-id="75e48-155">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="75e48-156">Executar o script remotamente em um computador separado ou em um processo separado tem grande isolamento.</span><span class="sxs-lookup"><span data-stu-id="75e48-156">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="75e48-157">Quaisquer erros não afetarão outros trabalhos em execução ou o cliente que iniciou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="75e48-157">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="75e48-158">Mas a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto.</span><span class="sxs-lookup"><span data-stu-id="75e48-158">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="75e48-159">Todos os objetos passados para e da sessão remota devem ser serializados e, em seguida, desserializados conforme passam entre o cliente e a sessão de destino.</span><span class="sxs-lookup"><span data-stu-id="75e48-159">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="75e48-160">A operação de serialização pode usar muitos recursos de computação e memória para grandes objetos de dados complexos.</span><span class="sxs-lookup"><span data-stu-id="75e48-160">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

## <a name="powershell-thread-based-jobs"></a><span data-ttu-id="75e48-161">Trabalhos baseados em thread do PowerShell</span><span class="sxs-lookup"><span data-stu-id="75e48-161">PowerShell thread based jobs</span></span>

<span data-ttu-id="75e48-162">Os trabalhos baseados em thread não são tão robustos quanto os trabalhos remotos e em segundo plano, pois eles são executados no mesmo processo em threads diferentes.</span><span class="sxs-lookup"><span data-stu-id="75e48-162">Thread based jobs are not as robust as Remote and Background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="75e48-163">Se um trabalho tiver um erro crítico que falha no processo, todos os outros trabalhos no processo também falharão.</span><span class="sxs-lookup"><span data-stu-id="75e48-163">If one job has a critical error that crashes the process, then all other jobs in the process will also fail.</span></span>

<span data-ttu-id="75e48-164">No entanto, os trabalhos baseados em thread têm muito menos sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="75e48-164">However, thread-based jobs have much less overhead.</span></span> <span data-ttu-id="75e48-165">Eles não precisam usar a camada ou a serialização de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="75e48-165">They don't need to use the remoting layer or serialization.</span></span> <span data-ttu-id="75e48-166">O resultado é que os trabalhos baseados em thread tendem a ser executados muito mais rapidamente e usam muito menos recursos do que os outros tipos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="75e48-166">The result is that thread-based jobs tend to run much faster and use far less resources than the other job types.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="75e48-167">Desempenho do trabalho de thread</span><span class="sxs-lookup"><span data-stu-id="75e48-167">Thread job performance</span></span>

<span data-ttu-id="75e48-168">Os trabalhos de thread são mais rápidos e mais leves do que outros tipos de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="75e48-168">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="75e48-169">Mas ainda têm sobrecarga que pode ser grande quando comparada ao trabalho que o trabalho está fazendo.</span><span class="sxs-lookup"><span data-stu-id="75e48-169">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="75e48-170">O PowerShell executa comandos e script em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="75e48-170">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="75e48-171">Somente um comando ou script pode ser executado por vez em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="75e48-171">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="75e48-172">Assim, ao executar vários trabalhos, cada trabalho é executado em uma sessão separada.</span><span class="sxs-lookup"><span data-stu-id="75e48-172">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="75e48-173">Cada sessão contribui para a sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="75e48-173">Each session contributes to the overhead.</span></span>

<span data-ttu-id="75e48-174">Os trabalhos de thread fornecem o melhor desempenho quando o trabalho executado é maior do que a sobrecarga da sessão usada para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="75e48-174">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="75e48-175">Há dois casos para atender a esses critérios.</span><span class="sxs-lookup"><span data-stu-id="75e48-175">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="75e48-176">O trabalho é de computação intensiva – executar um script em vários trabalhos de thread pode tirar proveito de vários núcleos de processador e ser concluído com mais rapidez.</span><span class="sxs-lookup"><span data-stu-id="75e48-176">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="75e48-177">O trabalho consiste em uma espera significativa – um script que passa tempo aguardando os resultados de e/s ou de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="75e48-177">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="75e48-178">A execução em paralelo geralmente é concluída mais rapidamente do que se executado em sequência.</span><span class="sxs-lookup"><span data-stu-id="75e48-178">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

<span data-ttu-id="75e48-179">O primeiro exemplo acima mostra um loop foreach que cria trabalhos de thread de 1000 para fazer uma simples gravação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="75e48-179">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="75e48-180">Devido à sobrecarga do trabalho, levará mais de 33 segundos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="75e48-180">Due to job overhead, it takes over 33 seconds to complete.</span></span>

<span data-ttu-id="75e48-181">O segundo exemplo executa o `ForEach` cmdlet para realizar as mesmas operações de 1000 e cada gravação de cadeia de caracteres é executada sequencialmente sem qualquer sobrecarga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="75e48-181">The second example runs the `ForEach` cmdlet to do the same 1000 operations and each string write is executed sequentially without any job overhead.</span></span> <span data-ttu-id="75e48-182">Ele é concluído em um mero 25 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="75e48-182">It completes in a mere 25 milliseconds.</span></span>

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

<span data-ttu-id="75e48-183">No exemplo acima, até 5000 entradas são coletadas para 10 logs de sistema separados.</span><span class="sxs-lookup"><span data-stu-id="75e48-183">In the above example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="75e48-184">Como o script envolve a leitura de um número de logs, faz sentido fazer as operações em paralelo.</span><span class="sxs-lookup"><span data-stu-id="75e48-184">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span> <span data-ttu-id="75e48-185">E o trabalho é concluído com duas vezes mais rápido quando o script é executado em sequência.</span><span class="sxs-lookup"><span data-stu-id="75e48-185">And the job completes over twice as fast as when the script is run sequentially.</span></span>

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="75e48-186">Trabalhos de thread e variáveis</span><span class="sxs-lookup"><span data-stu-id="75e48-186">Thread jobs and variables</span></span>

<span data-ttu-id="75e48-187">As variáveis são passadas para trabalhos de thread de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="75e48-187">Variables are passed into thread jobs in various ways.</span></span>

<span data-ttu-id="75e48-188">`Start-ThreadJob` pode aceitar variáveis que são canalizadas para o cmdlet, transmitidas para o bloco de script por meio da `$using` palavra-chave, ou transmitidas por meio do parâmetro **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="75e48-188">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job

`ForEach-Object -Parallel` accepts piped in variables, and variables passed
directly to the script block via the `$using` keyword.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="75e48-189">Como os trabalhos de thread são executados no mesmo processo, qualquer tipo de referência de variável passado para o trabalho deve ser tratado com cuidado.</span><span class="sxs-lookup"><span data-stu-id="75e48-189">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="75e48-190">Se não for um objeto de thread seguro, ele nunca deve ser atribuído, e o método e as propriedades nunca devem ser invocados nele.</span><span class="sxs-lookup"><span data-stu-id="75e48-190">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

<span data-ttu-id="75e48-191">O exemplo acima passa um objeto dotNet seguro de thread `ConcurrentDictionary` para todos os trabalhos filho para coletar objetos de processo nomeados exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="75e48-191">The above example passes a thread safe dotNet `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="75e48-192">Como se trata de um objeto de thread seguro, ele pode ser usado com segurança enquanto os trabalhos são executados simultaneamente no processo.</span><span class="sxs-lookup"><span data-stu-id="75e48-192">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

## <a name="see-also"></a><span data-ttu-id="75e48-193">Confira também</span><span class="sxs-lookup"><span data-stu-id="75e48-193">See also</span></span>

- [<span data-ttu-id="75e48-194">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="75e48-194">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="75e48-195">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="75e48-195">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="75e48-196">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="75e48-196">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="75e48-197">about_Remote</span><span class="sxs-lookup"><span data-stu-id="75e48-197">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="75e48-198">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="75e48-198">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="75e48-199">Start-Job</span><span class="sxs-lookup"><span data-stu-id="75e48-199">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="75e48-200">Get-Job</span><span class="sxs-lookup"><span data-stu-id="75e48-200">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="75e48-201">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="75e48-201">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="75e48-202">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="75e48-202">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="75e48-203">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="75e48-203">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="75e48-204">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="75e48-204">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
