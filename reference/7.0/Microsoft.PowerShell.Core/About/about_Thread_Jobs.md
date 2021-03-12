---
description: Fornece informações sobre os trabalhos baseados em thread do PowerShell. Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.
Locale: en-US
ms.date: 11/11/2020
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 67f3fc585a8c2d1c3ca98c7336a7e367ed6c66c7
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193969"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="6b198-104">Sobre os trabalhos de thread</span><span class="sxs-lookup"><span data-stu-id="6b198-104">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="6b198-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="6b198-105">Short description</span></span>

<span data-ttu-id="6b198-106">Fornece informações sobre os trabalhos baseados em thread do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b198-106">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="6b198-107">Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6b198-107">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="6b198-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="6b198-108">Long description</span></span>

<span data-ttu-id="6b198-109">O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="6b198-109">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="6b198-110">Há três tipos de trabalhos fornecidos pelo PowerShell para dar suporte à simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="6b198-110">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="6b198-111">`RemoteJob` -Comandos e scripts executados em uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="6b198-111">`RemoteJob` - Commands and scripts run in a remote session.</span></span> <span data-ttu-id="6b198-112">Para obter informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6b198-112">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="6b198-113">`BackgroundJob` -Comandos e scripts são executados em um processo separado no computador local.</span><span class="sxs-lookup"><span data-stu-id="6b198-113">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="6b198-114">Para obter mais informações, consulte [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6b198-114">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="6b198-115">`PSTaskJob` ou `ThreadJob` -comandos e scripts são executados em um thread separado dentro do mesmo processo no computador local.</span><span class="sxs-lookup"><span data-stu-id="6b198-115">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span>

<span data-ttu-id="6b198-116">Os trabalhos baseados em thread não são tão robustos quanto os trabalhos remotos e em segundo plano, pois eles são executados no mesmo processo em threads diferentes.</span><span class="sxs-lookup"><span data-stu-id="6b198-116">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="6b198-117">Se um trabalho tiver um erro crítico que falha no processo, todos os outros trabalhos no processo serão encerrados.</span><span class="sxs-lookup"><span data-stu-id="6b198-117">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="6b198-118">No entanto, os trabalhos baseados em thread exigem menos sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6b198-118">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="6b198-119">Eles não usam a camada ou serialização de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="6b198-119">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="6b198-120">Os objetos de resultado são retornados como referências a objetos dinâmicos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6b198-120">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="6b198-121">Sem essa sobrecarga, os trabalhos baseados em threads são executados mais rapidamente e usam menos recursos do que os outros tipos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b198-121">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b198-122">A sessão pai que criou o trabalho também monitora o status do trabalho e coleta dados do pipeline.</span><span class="sxs-lookup"><span data-stu-id="6b198-122">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="6b198-123">O processo filho do trabalho é encerrado pelo processo pai quando o trabalho atinge um estado concluído.</span><span class="sxs-lookup"><span data-stu-id="6b198-123">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="6b198-124">Se a sessão pai for encerrada, todos os trabalhos filho em execução serão encerrados junto com seus processos filho.</span><span class="sxs-lookup"><span data-stu-id="6b198-124">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="6b198-125">Há duas maneiras de solucionar essa situação:</span><span class="sxs-lookup"><span data-stu-id="6b198-125">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="6b198-126">Use `Invoke-Command` para criar trabalhos que são executados em sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="6b198-126">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="6b198-127">Para obter mais informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6b198-127">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="6b198-128">Use `Start-Process` para criar um novo processo em vez de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b198-128">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="6b198-129">Para obter mais informações, consulte [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="6b198-129">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="how-to-start-and-manage-thread-based-jobs"></a><span data-ttu-id="6b198-130">Como iniciar e gerenciar trabalhos baseados em thread</span><span class="sxs-lookup"><span data-stu-id="6b198-130">How to start and manage thread-based jobs</span></span>

<span data-ttu-id="6b198-131">Há duas maneiras de iniciar trabalhos baseados em thread:</span><span class="sxs-lookup"><span data-stu-id="6b198-131">There are two ways to start thread-based jobs:</span></span>

- <span data-ttu-id="6b198-132">`Start-ThreadJob`-do módulo **ThreadJob**</span><span class="sxs-lookup"><span data-stu-id="6b198-132">`Start-ThreadJob` - from the **ThreadJob** module</span></span>
- <span data-ttu-id="6b198-133">`ForEach-Object -Parallel -AsJob` -o recurso paralelo foi adicionado no PowerShell 7,0</span><span class="sxs-lookup"><span data-stu-id="6b198-133">`ForEach-Object -Parallel -AsJob` - the parallel feature was added in PowerShell 7.0</span></span>

<span data-ttu-id="6b198-134">Use os mesmos cmdlets de **trabalho** descritos em [about_Jobs](about_Jobs.md) para gerenciar trabalhos baseados em thread.</span><span class="sxs-lookup"><span data-stu-id="6b198-134">Use the same **Job** cmdlets described in [about_Jobs](about_Jobs.md) to manage thread-based jobs.</span></span>

### <a name="using-start-threadjob"></a><span data-ttu-id="6b198-135">Usando `Start-ThreadJob`</span><span class="sxs-lookup"><span data-stu-id="6b198-135">Using `Start-ThreadJob`</span></span>

<span data-ttu-id="6b198-136">O módulo **ThreadJob** foi enviado pela primeira vez com o PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6b198-136">The **ThreadJob** module first shipped with PowerShell 6.</span></span> <span data-ttu-id="6b198-137">Ele também pode ser instalado do Galeria do PowerShell para o Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="6b198-137">It can also be installed from the PowerShell Gallery for Windows PowerShell 5.1.</span></span>

<span data-ttu-id="6b198-138">Para iniciar um trabalho de thread no computador local, use o `Start-ThreadJob` cmdlet com um comando ou script entre chaves ( `{ }` ).</span><span class="sxs-lookup"><span data-stu-id="6b198-138">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet with a command or script enclosed in curly braces (`{ }`).</span></span>

<span data-ttu-id="6b198-139">O exemplo a seguir inicia um trabalho de thread que executa um `Get-Process` comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="6b198-139">The following example starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="6b198-140">O `Start-ThreadJob` comando retorna um `ThreadJob` objeto que representa o trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="6b198-140">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="6b198-141">O objeto de trabalho contém informações úteis sobre o trabalho, incluindo seu status de execução atual.</span><span class="sxs-lookup"><span data-stu-id="6b198-141">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="6b198-142">Ele coleta os resultados do trabalho à medida que os resultados são gerados.</span><span class="sxs-lookup"><span data-stu-id="6b198-142">It collects the results of the job as the results are being generated.</span></span>

### <a name="using-foreach-object--parallel--asjob"></a><span data-ttu-id="6b198-143">Usando `ForEach-Object -Parallel -AsJob`</span><span class="sxs-lookup"><span data-stu-id="6b198-143">Using `ForEach-Object -Parallel -AsJob`</span></span>

<span data-ttu-id="6b198-144">O PowerShell 7,0 adicionou um novo parâmetro definido para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6b198-144">PowerShell 7.0 added a new parameter set to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="6b198-145">Os novos parâmetros permitem executar blocos de script em threads paralelos como trabalhos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b198-145">The new parameters allow you to run script blocks in parallel threads as PowerShell jobs.</span></span>

<span data-ttu-id="6b198-146">Você pode canalizar dados para o `ForEach-Object -Parallel` .</span><span class="sxs-lookup"><span data-stu-id="6b198-146">You can pipe data to `ForEach-Object -Parallel`.</span></span> <span data-ttu-id="6b198-147">Os dados são passados para o bloco de script que é executado em paralelo.</span><span class="sxs-lookup"><span data-stu-id="6b198-147">The data is passed to the script block that is run in parallel.</span></span> <span data-ttu-id="6b198-148">O `-AsJob` parâmetro cria objetos de trabalhos para cada um dos threads paralelos.</span><span class="sxs-lookup"><span data-stu-id="6b198-148">The `-AsJob` parameter creates jobs objects for each of the parallel threads.</span></span>

<span data-ttu-id="6b198-149">O comando a seguir inicia um trabalho que contém trabalhos filho para cada valor de entrada canalizado para o comando.</span><span class="sxs-lookup"><span data-stu-id="6b198-149">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="6b198-150">Cada trabalho filho executa o `Write-Output` comando com um valor de entrada canalizado como o argumento.</span><span class="sxs-lookup"><span data-stu-id="6b198-150">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="6b198-151">O `ForEach-Object -Parallel` comando retorna um `PSTaskJob` objeto que contém trabalhos filho para cada valor de entrada canalizado.</span><span class="sxs-lookup"><span data-stu-id="6b198-151">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="6b198-152">O objeto de trabalho contém informações úteis sobre o status de execução de trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="6b198-152">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="6b198-153">Ele coleta os resultados dos trabalhos filho à medida que os resultados são gerados.</span><span class="sxs-lookup"><span data-stu-id="6b198-153">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="6b198-154">Como aguardar a conclusão de um trabalho e recuperar os resultados do trabalho</span><span class="sxs-lookup"><span data-stu-id="6b198-154">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="6b198-155">Você pode usar os cmdlets de trabalho do PowerShell, como `Wait-Job` e `Receive-Job` para aguardar a conclusão de um trabalho e, em seguida, retornar todos os resultados gerados pelo trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b198-155">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="6b198-156">O comando a seguir inicia um trabalho de thread que executa um `Get-Process` comando, aguarda até que o comando seja concluído e, finalmente, retorna todos os resultados de dados gerados pelo comando.</span><span class="sxs-lookup"><span data-stu-id="6b198-156">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="6b198-157">O comando a seguir inicia um trabalho que executa um `Write-Output` comando para cada entrada canalizada, aguarda que todos os trabalhos filho sejam concluídos e, finalmente, retorna todos os resultados de dados gerados pelos trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="6b198-157">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="6b198-158">O `Receive-Job` cmdlet retorna os resultados dos trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="6b198-158">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="6b198-159">Como cada trabalho filho é executado em paralelo, a ordem dos resultados gerados não é garantida.</span><span class="sxs-lookup"><span data-stu-id="6b198-159">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="6b198-160">Desempenho do trabalho de thread</span><span class="sxs-lookup"><span data-stu-id="6b198-160">Thread job performance</span></span>

<span data-ttu-id="6b198-161">Os trabalhos de thread são mais rápidos e mais leves do que outros tipos de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="6b198-161">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="6b198-162">Mas ainda têm sobrecarga que pode ser grande quando comparada ao trabalho que o trabalho está fazendo.</span><span class="sxs-lookup"><span data-stu-id="6b198-162">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="6b198-163">O PowerShell executa comandos e script em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6b198-163">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="6b198-164">Somente um comando ou script pode ser executado por vez em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6b198-164">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="6b198-165">Assim, ao executar vários trabalhos, cada trabalho é executado em uma sessão separada.</span><span class="sxs-lookup"><span data-stu-id="6b198-165">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="6b198-166">Cada sessão contribui para a sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6b198-166">Each session contributes to the overhead.</span></span>

<span data-ttu-id="6b198-167">Os trabalhos de thread fornecem o melhor desempenho quando o trabalho executado é maior do que a sobrecarga da sessão usada para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b198-167">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="6b198-168">Há dois casos para atender a esses critérios.</span><span class="sxs-lookup"><span data-stu-id="6b198-168">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="6b198-169">O trabalho é de computação intensiva – executar um script em vários trabalhos de thread pode tirar proveito de vários núcleos de processador e ser concluído com mais rapidez.</span><span class="sxs-lookup"><span data-stu-id="6b198-169">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="6b198-170">O trabalho consiste em uma espera significativa – um script que passa tempo aguardando os resultados de e/s ou de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="6b198-170">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="6b198-171">A execução em paralelo geralmente é concluída mais rapidamente do que se executado em sequência.</span><span class="sxs-lookup"><span data-stu-id="6b198-171">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
36860.8226

(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
7.1975
```

<span data-ttu-id="6b198-172">O primeiro exemplo acima mostra um loop foreach que cria trabalhos de thread de 1000 para fazer uma simples gravação de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6b198-172">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="6b198-173">Devido à sobrecarga do trabalho, levará mais de 36 segundos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="6b198-173">Due to job overhead, it takes over 36 seconds to complete.</span></span>

<span data-ttu-id="6b198-174">O segundo exemplo executa o `ForEach` cmdlet para realizar as mesmas operações de 1000.</span><span class="sxs-lookup"><span data-stu-id="6b198-174">The second example runs the `ForEach` cmdlet to do the same 1000 operations.</span></span>
<span data-ttu-id="6b198-175">Desta vez, `ForEach-Object` é executado em sequência, em um único thread, sem nenhuma sobrecarga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b198-175">This time, `ForEach-Object` runs sequentially, on a single thread, without any job overhead.</span></span> <span data-ttu-id="6b198-176">Ele é concluído em um mero 7 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="6b198-176">It completes in a mere 7 milliseconds.</span></span>

<span data-ttu-id="6b198-177">No exemplo a seguir, até 5000 entradas são coletadas para 10 logs de sistema separados.</span><span class="sxs-lookup"><span data-stu-id="6b198-177">In the following example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="6b198-178">Como o script envolve a leitura de um número de logs, faz sentido fazer as operações em paralelo.</span><span class="sxs-lookup"><span data-stu-id="6b198-178">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span>

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

<span data-ttu-id="6b198-179">O script é concluído na metade do tempo em que os trabalhos são executados em paralelo.</span><span class="sxs-lookup"><span data-stu-id="6b198-179">The script completes in half the time when the jobs are run in parallel.</span></span>

```powershell
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

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="6b198-180">Trabalhos de thread e variáveis</span><span class="sxs-lookup"><span data-stu-id="6b198-180">Thread jobs and variables</span></span>

<span data-ttu-id="6b198-181">Há várias maneiras de passar valores para os trabalhos baseados em thread.</span><span class="sxs-lookup"><span data-stu-id="6b198-181">There are multiple ways to pass values into the thread-based jobs.</span></span>

<span data-ttu-id="6b198-182">`Start-ThreadJob` pode aceitar variáveis que são canalizadas para o cmdlet, transmitidas para o bloco de script por meio da `$using` palavra-chave, ou transmitidas por meio do parâmetro **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="6b198-182">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

<span data-ttu-id="6b198-183">`ForEach-Object -Parallel` aceita o piped em variáveis e variáveis passadas diretamente para o bloco de script por meio da `$using` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="6b198-183">`ForEach-Object -Parallel` accepts piped in variables, and variables passed directly to the script block via the `$using` keyword.</span></span>

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="6b198-184">Como os trabalhos de thread são executados no mesmo processo, qualquer tipo de referência de variável passado para o trabalho deve ser tratado com cuidado.</span><span class="sxs-lookup"><span data-stu-id="6b198-184">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="6b198-185">Se não for um objeto de thread seguro, ele nunca deve ser atribuído, e o método e as propriedades nunca devem ser invocados nele.</span><span class="sxs-lookup"><span data-stu-id="6b198-185">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

<span data-ttu-id="6b198-186">O exemplo a seguir passa um objeto .NET thread-safe `ConcurrentDictionary` para todos os trabalhos filho para coletar objetos de processo nomeados exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="6b198-186">The following example passes a thread-safe .NET `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="6b198-187">Como se trata de um objeto de thread seguro, ele pode ser usado com segurança enquanto os trabalhos são executados simultaneamente no processo.</span><span class="sxs-lookup"><span data-stu-id="6b198-187">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6b198-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="6b198-188">See also</span></span>

- [<span data-ttu-id="6b198-189">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="6b198-189">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="6b198-190">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="6b198-190">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="6b198-191">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="6b198-191">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="6b198-192">about_Remote</span><span class="sxs-lookup"><span data-stu-id="6b198-192">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="6b198-193">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="6b198-193">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="6b198-194">Start-Job</span><span class="sxs-lookup"><span data-stu-id="6b198-194">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="6b198-195">Get-Job</span><span class="sxs-lookup"><span data-stu-id="6b198-195">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="6b198-196">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="6b198-196">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="6b198-197">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="6b198-197">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="6b198-198">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="6b198-198">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="6b198-199">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="6b198-199">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
