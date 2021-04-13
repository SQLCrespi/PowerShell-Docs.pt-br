---
description: Descreve como executar trabalhos em computadores remotos.
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 4efeb4f4b89e6c44ace0b8b4099efd7d41821f66
ms.sourcegitcommit: f6cc3752463b254f6ba7fc14c1e4532ad33f06bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "107216826"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="adf69-103">Sobre trabalhos remotos</span><span class="sxs-lookup"><span data-stu-id="adf69-103">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="adf69-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="adf69-104">Short Description</span></span>
<span data-ttu-id="adf69-105">Descreve como executar trabalhos em segundo plano em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="adf69-105">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="adf69-106">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="adf69-106">Detailed Description</span></span>

<span data-ttu-id="adf69-107">O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="adf69-107">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="adf69-108">Há três tipos de trabalhos fornecidos pelo PowerShell para dar suporte à simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="adf69-108">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="adf69-109">`RemoteJob` -Comandos e scripts executados em uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="adf69-109">`RemoteJob` - Commands and scripts run in a remote session.</span></span>
- <span data-ttu-id="adf69-110">`BackgroundJob` -Comandos e scripts são executados em um processo separado no computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-110">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="adf69-111">Para obter mais informações, consulte [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="adf69-111">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="adf69-112">`PSTaskJob` ou `ThreadJob` -comandos e scripts são executados em um thread separado dentro do mesmo processo no computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-112">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="adf69-113">Para obter mais informações, consulte [about_Thread_Jobs](about_Thread_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="adf69-113">For more information, see [about_Thread_Jobs](about_Thread_Jobs.md).</span></span>

<span data-ttu-id="adf69-114">Executar scripts remotamente, em um computador separado ou em um processo separado, proporcionar um grande isolamento.</span><span class="sxs-lookup"><span data-stu-id="adf69-114">Running scripts remotely, on a separate machine or in a separate process, provide great isolation.</span></span> <span data-ttu-id="adf69-115">Os erros que ocorrem no trabalho remoto não afetam outros trabalhos em execução ou a sessão pai que iniciou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-115">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="adf69-116">No entanto, a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto.</span><span class="sxs-lookup"><span data-stu-id="adf69-116">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="adf69-117">Todos os objetos são serializados e desserializados à medida que são passados entre a sessão pai e a sessão remota (trabalho).</span><span class="sxs-lookup"><span data-stu-id="adf69-117">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="adf69-118">A serialização de grandes objetos de dados complexos pode consumir grandes quantidades de recursos de computação e memória e transferir grandes quantidades de dados pela rede.</span><span class="sxs-lookup"><span data-stu-id="adf69-118">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adf69-119">A sessão pai que criou o trabalho também monitora o status do trabalho e coleta dados do pipeline.</span><span class="sxs-lookup"><span data-stu-id="adf69-119">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="adf69-120">O processo filho do trabalho é encerrado pelo processo pai quando o trabalho atinge um estado concluído.</span><span class="sxs-lookup"><span data-stu-id="adf69-120">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="adf69-121">Se a sessão pai for encerrada, todos os trabalhos filho em execução serão encerrados junto com seus processos filho.</span><span class="sxs-lookup"><span data-stu-id="adf69-121">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="adf69-122">Há duas maneiras de solucionar essa situação:</span><span class="sxs-lookup"><span data-stu-id="adf69-122">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="adf69-123">Use `Invoke-Command` para criar trabalhos que são executados em sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="adf69-123">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="adf69-124">Consulte a seção [processos desanexados](#how-to-run-as-a-detached-process) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="adf69-124">See the [detached processes](#how-to-run-as-a-detached-process) section of this article.</span></span>
1. <span data-ttu-id="adf69-125">Use `Start-Process` para criar um novo processo em vez de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-125">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="adf69-126">Para obter mais informações, consulte [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="adf69-126">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="remote-jobs"></a><span data-ttu-id="adf69-127">Trabalhos remotos</span><span class="sxs-lookup"><span data-stu-id="adf69-127">Remote Jobs</span></span>

<span data-ttu-id="adf69-128">Você pode executar trabalhos em computadores remotos usando três métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="adf69-128">You can run jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="adf69-129">Iniciar uma sessão interativa em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-129">Start an interactive session on a remote computer.</span></span> <span data-ttu-id="adf69-130">Em seguida, inicie um trabalho na sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="adf69-130">Then start a job in the interactive session.</span></span> <span data-ttu-id="adf69-131">Os procedimentos são os mesmos que executar um trabalho local, embora todas as ações sejam executadas no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-131">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="adf69-132">Execute um trabalho em um computador remoto que retorna seus resultados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-132">Run a job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="adf69-133">Use esse método quando desejar coletar os resultados dos trabalhos e mantê-los em um local central no computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-133">Use this method when you want to collect the results of jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="adf69-134">Execute um trabalho em um computador remoto que mantém seus resultados no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-134">Run a job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="adf69-135">Use esse método quando os dados do trabalho forem mantidos com mais segurança no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="adf69-135">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-job-in-an-interactive-session"></a><span data-ttu-id="adf69-136">Iniciar um trabalho em uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="adf69-136">Start a job in an interactive session</span></span>

<span data-ttu-id="adf69-137">Você pode iniciar uma sessão interativa com um computador remoto e, em seguida, iniciar um trabalho durante a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="adf69-137">You can start an interactive session with a remote computer and then start a job during the interactive session.</span></span> <span data-ttu-id="adf69-138">Para obter mais informações sobre sessões interativas, consulte about_Remote e ver `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="adf69-138">For more information about interactive sessions, see about_Remote, and see `Enter-PSSession`.</span></span>

<span data-ttu-id="adf69-139">O procedimento para iniciar um trabalho em uma sessão interativa é quase idêntico ao procedimento para iniciar um trabalho em segundo plano no computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-139">The procedure for starting a job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="adf69-140">No entanto, todas as operações ocorrem no computador remoto, não no computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-140">However, all of the operations occur on the remote computer, not the local computer.</span></span>

1. <span data-ttu-id="adf69-141">Use o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-141">Use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="adf69-142">Você pode usar o parâmetro ComputerName do `Enter-PSSession` para estabelecer uma conexão temporária para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="adf69-142">You can use the ComputerName parameter of `Enter-PSSession` to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="adf69-143">Ou, você pode usar o parâmetro Session para executar a sessão interativa em uma sessão do PowerShell (PSSession).</span><span class="sxs-lookup"><span data-stu-id="adf69-143">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

   <span data-ttu-id="adf69-144">O comando a seguir inicia uma sessão interativa no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-144">The following command starts an interactive session on the Server01 computer.</span></span>

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   <span data-ttu-id="adf69-145">O prompt de comando é alterado para mostrar que agora você está conectado ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-145">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

   ```
   Server01\C:>
   ```

1. <span data-ttu-id="adf69-146">Para iniciar um trabalho remoto na sessão, use o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="adf69-146">To start a remote job in the session, use the `Start-Job` cmdlet.</span></span> <span data-ttu-id="adf69-147">O comando a seguir executa um trabalho remoto que obtém os eventos no log de eventos do Windows PowerShell no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-147">The following command runs a remote job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="adf69-148">O `Start-Job` cmdlet retorna um objeto que representa o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-148">The `Start-Job` cmdlet returns an object that represents the job.</span></span>

   <span data-ttu-id="adf69-149">Esse comando salva o objeto de trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="adf69-149">This command saves the job object in the `$job` variable.</span></span>

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   <span data-ttu-id="adf69-150">Enquanto o trabalho é executado, você pode usar a sessão interativa para executar outros comandos, incluindo outros trabalhos.</span><span class="sxs-lookup"><span data-stu-id="adf69-150">While the job runs, you can use the interactive session to run other commands, including other jobs.</span></span> <span data-ttu-id="adf69-151">No entanto, você deve manter a sessão interativa aberta até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="adf69-151">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="adf69-152">Se você encerrar a sessão, o trabalho será interrompido e os resultados serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="adf69-152">If you end the session, the job is interrupted, and the results are lost.</span></span>

1. <span data-ttu-id="adf69-153">Para descobrir se o trabalho foi concluído, exiba o valor da `$job` variável ou use o `Get-Job` cmdlet para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-153">To find out if the job is complete, display the value of the `$job` variable, or use the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="adf69-154">O comando a seguir usa o `Get-Job` cmdlet para exibir o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-154">The following command uses the `Get-Job` cmdlet to display the job.</span></span>

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   <span data-ttu-id="adf69-155">A `Get-Job` saída mostra que o trabalho está em execução no computador "localhost" porque o trabalho foi iniciado no e está em execução no mesmo computador (nesse caso, Server01).</span><span class="sxs-lookup"><span data-stu-id="adf69-155">The `Get-Job` output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

1. <span data-ttu-id="adf69-156">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="adf69-156">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="adf69-157">Você pode exibir os resultados na sessão interativa ou salvá-los em um arquivo no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-157">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="adf69-158">O comando a seguir obtém os resultados do trabalho na variável $job.</span><span class="sxs-lookup"><span data-stu-id="adf69-158">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="adf69-159">O comando usa o operador de redirecionamento ( `>` ) para salvar os resultados do trabalho no arquivo de PsLog.txt no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-159">The command uses the redirection operator (`>`) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. <span data-ttu-id="adf69-160">Para encerrar a sessão interativa, use o `Exit-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="adf69-160">To end the interactive session, use the `Exit-PSSession` cmdlet.</span></span> <span data-ttu-id="adf69-161">O prompt de comando é alterado para mostrar que você está de volta na sessão original no computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-161">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. <span data-ttu-id="adf69-162">Para exibir o conteúdo do `PsLog.txt` arquivo no computador Server01 a qualquer momento, inicie outra sessão interativa ou execute um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-162">To view the contents of the `PsLog.txt` file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="adf69-163">Esse tipo de comando é melhor executado em uma PSSession (uma conexão persistente), caso você queira usar vários comandos para investigar e gerenciar os dados no `PsLog.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="adf69-163">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the `PsLog.txt` file.</span></span> <span data-ttu-id="adf69-164">Para obter mais informações sobre PSSessions, consulte [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="adf69-164">For more information about PSSessions, see [about_PSSessions](about_PSSessions.md).</span></span>

   <span data-ttu-id="adf69-165">Os comandos a seguir usam o `New-PSSession` cmdlet para criar uma **PSSession** que está conectada ao computador Server01 e usam o `Invoke-Command` cmdlet para executar um `Get-Content` comando na PSSession para exibir o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="adf69-165">The following commands use the `New-PSSession` cmdlet to create a **PSSession** that is connected to the Server01 computer, and they use the `Invoke-Command` cmdlet to run a `Get-Content` command in the PSSession to view the contents of the file.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="adf69-166">Iniciar um trabalho remoto que retorna os resultados para o computador local (AsJob)</span><span class="sxs-lookup"><span data-stu-id="adf69-166">Start a remote job that returns the results to the local computer (AsJob)</span></span>

<span data-ttu-id="adf69-167">Para iniciar um trabalho em um computador remoto que retorna os resultados do comando para o computador local, use o parâmetro **AsJob** de um cmdlet, como o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="adf69-167">To start a job on a remote computer that returns the command results to the local computer, use the **AsJob** parameter of a cmdlet such as the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="adf69-168">Quando você usa o parâmetro **AsJob** , o objeto de trabalho é realmente criado no computador local, mesmo que o trabalho seja executado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-168">When you use the **AsJob** parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="adf69-169">Quando o trabalho é concluído, os resultados são retornados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-169">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="adf69-170">Você pode usar os cmdlets que contêm o substantivo do trabalho (os cmdlets de trabalho) para gerenciar qualquer trabalho criado por qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="adf69-170">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="adf69-171">Muitos dos cmdlets que têm parâmetros **AsJob** não usam a comunicação remota do PowerShell, para que você possa usá-los mesmo em computadores que não estão configurados para comunicação remota e que não atendem aos requisitos de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="adf69-171">Many of the cmdlets that have **AsJob** parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

1. <span data-ttu-id="adf69-172">O comando a seguir usa o parâmetro **AsJob** do `Invoke-Command` para iniciar um trabalho no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-172">The following command uses the **AsJob** parameter of `Invoke-Command` to start a job on the Server01 computer.</span></span> <span data-ttu-id="adf69-173">O trabalho executa um `Get-Eventlog` comando que obtém os eventos no log do sistema.</span><span class="sxs-lookup"><span data-stu-id="adf69-173">The job runs a `Get-Eventlog` command that gets the events in the System log.</span></span> <span data-ttu-id="adf69-174">Você pode usar o parâmetro JobName para atribuir um nome de exibição ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-174">You can use the JobName parameter to assign a display name to the job.</span></span>

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   <span data-ttu-id="adf69-175">Os resultados do comando se assemelham à saída de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="adf69-175">The results of the command resemble the following sample output.</span></span>

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   <span data-ttu-id="adf69-176">Quando o parâmetro **AsJob** é usado, `Invoke-Command` retorna o mesmo tipo de objeto de trabalho que `Start-Job` retorna.</span><span class="sxs-lookup"><span data-stu-id="adf69-176">When the **AsJob** parameter is used, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="adf69-177">Você pode salvar o objeto de trabalho em uma variável ou pode usar um `Get-Job` comando para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-177">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="adf69-178">Observe que o valor da propriedade Location mostra que o trabalho foi executado no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-178">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

1. <span data-ttu-id="adf69-179">Para gerenciar um trabalho iniciado usando o parâmetro **AsJob** do `Invoke-Command` cmdlet, use os cmdlets de trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-179">To manage a job started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="adf69-180">Como o objeto de trabalho que representa o trabalho remoto está no computador local, não é necessário executar comandos remotos para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-180">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

   <span data-ttu-id="adf69-181">Para determinar se o trabalho está concluído, use um `Get-Job` comando.</span><span class="sxs-lookup"><span data-stu-id="adf69-181">To determine whether the job is complete, use a `Get-Job` command.</span></span> <span data-ttu-id="adf69-182">O comando a seguir obtém todos os trabalhos que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="adf69-182">The following command gets all of the jobs that were started in the current session.</span></span>

   ```powershell
   Get-Job
   ```

   <span data-ttu-id="adf69-183">Como o trabalho remoto foi iniciado na sessão atual, um comando local `Get-Job` Obtém o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-183">Because the remote job was started in the current session, a local `Get-Job` command gets the job.</span></span> <span data-ttu-id="adf69-184">A propriedade State do objeto Job mostra que o comando foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="adf69-184">The State property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. <span data-ttu-id="adf69-185">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="adf69-185">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="adf69-186">Como os resultados do trabalho são retornados automaticamente para o computador em que o objeto de trabalho reside, você pode obter os resultados com um `Receive-Job` comando local.</span><span class="sxs-lookup"><span data-stu-id="adf69-186">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local `Receive-Job` command.</span></span>

   <span data-ttu-id="adf69-187">O comando a seguir usa o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-187">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="adf69-188">Ele usa a ID de sessão para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-188">It uses the session ID to identify the job.</span></span> <span data-ttu-id="adf69-189">Esse comando salva os resultados do trabalho na variável $results.</span><span class="sxs-lookup"><span data-stu-id="adf69-189">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="adf69-190">Você também pode redirecionar os resultados para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="adf69-190">You can also redirect the results to a file.</span></span>

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="adf69-191">Iniciar um trabalho remoto que mantém os resultados no computador remoto</span><span class="sxs-lookup"><span data-stu-id="adf69-191">Start a remote job that keeps the results on the remote computer</span></span>

<span data-ttu-id="adf69-192">Para iniciar um trabalho em um computador remoto que mantém os resultados do comando no computador remoto, use o `Invoke-Command` cmdlet para executar um `Start-Job` comando em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-192">To start a job on a remote computer that keeps the command results on the remote computer, use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span> <span data-ttu-id="adf69-193">Você pode usar esse método para executar trabalhos em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="adf69-193">You can use this method to run jobs on multiple computers.</span></span>

<span data-ttu-id="adf69-194">Quando você executa um `Start-Job` comando remotamente, o objeto de trabalho é criado no computador remoto e os resultados do trabalho são mantidos no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-194">When you run a `Start-Job` command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="adf69-195">Da perspectiva do trabalho, todas as operações são locais.</span><span class="sxs-lookup"><span data-stu-id="adf69-195">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="adf69-196">Você está apenas executando comandos remotamente para gerenciar um trabalho local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-196">You are just running commands remotely to manage a local job on the remote computer.</span></span>

1. <span data-ttu-id="adf69-197">Use o `Invoke-Command` cmdlet para executar um `Start-Job` comando em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-197">Use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span>

   <span data-ttu-id="adf69-198">Esse comando requer uma PSSession (uma conexão persistente).</span><span class="sxs-lookup"><span data-stu-id="adf69-198">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="adf69-199">Se você usar o parâmetro ComputerName de `Invoke-Command` para estabelecer uma conexão temporária, o `Invoke-Command` comando será considerado como concluído quando o objeto de trabalho for retornado.</span><span class="sxs-lookup"><span data-stu-id="adf69-199">If you use the ComputerName parameter of `Invoke-Command` to establish a temporary connection, the `Invoke-Command` command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="adf69-200">Como resultado, a conexão temporária é fechada e o trabalho é cancelado.</span><span class="sxs-lookup"><span data-stu-id="adf69-200">As a result, the temporary connection is closed, and the job is canceled.</span></span>

   <span data-ttu-id="adf69-201">O comando a seguir usa o `New-PSSession` cmdlet para criar uma PSSession que está conectada ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-201">The following command uses the `New-PSSession` cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="adf69-202">O comando salva a PSSession na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="adf69-202">The command saves the PSSession in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   <span data-ttu-id="adf69-203">O comando a seguir usa o `Invoke-Command` cmdlet para executar um `Start-Job` comando na PSSession.</span><span class="sxs-lookup"><span data-stu-id="adf69-203">The next command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the PSSession.</span></span> <span data-ttu-id="adf69-204">O `Start-Job` comando e o `Get-Eventlog` comando são colocados entre chaves.</span><span class="sxs-lookup"><span data-stu-id="adf69-204">The `Start-Job` command and the `Get-Eventlog` command are enclosed in braces.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   <span data-ttu-id="adf69-205">Os resultados se assemelham à saída de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="adf69-205">The results resemble the following sample output.</span></span>

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   <span data-ttu-id="adf69-206">Quando você executa um `Start-Job` comando remotamente, `Invoke-Command` o retorna o mesmo tipo de objeto de trabalho que o `Start-Job` retorna.</span><span class="sxs-lookup"><span data-stu-id="adf69-206">When you run a `Start-Job` command remotely, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="adf69-207">Você pode salvar o objeto de trabalho em uma variável ou pode usar um `Get-Job` comando para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-207">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="adf69-208">Observe que o valor da propriedade **Location** mostra que o trabalho foi executado no computador local, conhecido como "localhost", embora o trabalho tenha sido executado no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-208">Note that the value of the **Location** property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="adf69-209">Como o objeto de trabalho é criado no computador Server01 e o trabalho é executado no mesmo computador, é considerado um trabalho em segundo plano local.</span><span class="sxs-lookup"><span data-stu-id="adf69-209">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

1. <span data-ttu-id="adf69-210">Para gerenciar um trabalho remoto, use os cmdlets de **trabalho** .</span><span class="sxs-lookup"><span data-stu-id="adf69-210">To manage a remote job, use the **Job** cmdlets.</span></span> <span data-ttu-id="adf69-211">Como o objeto de trabalho está no computador remoto, você precisa executar comandos remotos para obter, parar, aguardar ou recuperar os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-211">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

   <span data-ttu-id="adf69-212">Para ver se o trabalho está concluído, use um `Invoke-Command` comando para executar um `Get-Job` comando na PSSession que está conectada ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-212">To see if the job is complete, use an `Invoke-Command` command to run a `Get-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   <span data-ttu-id="adf69-213">O comando retorna um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-213">The command returns a job object.</span></span> <span data-ttu-id="adf69-214">A propriedade **State** do objeto Job mostra que o comando foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="adf69-214">The **State** property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. <span data-ttu-id="adf69-215">Para obter os resultados do trabalho, use o `Invoke-Command` cmdlet para executar um `Receive-Job` comando na PSSession que está conectada ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-215">To get the results of the job, use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   <span data-ttu-id="adf69-216">O comando a seguir usa o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-216">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="adf69-217">Ele usa a ID de sessão para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-217">It uses the session ID to identify the job.</span></span> <span data-ttu-id="adf69-218">Esse comando salva os resultados do trabalho na `$results` variável.</span><span class="sxs-lookup"><span data-stu-id="adf69-218">This command saves the job results in the `$results` variable.</span></span> <span data-ttu-id="adf69-219">Ele usa o parâmetro Keep de `Receive-Job` para manter o resultado no cache do trabalho no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-219">It uses the Keep parameter of `Receive-Job` to keep the result in the job cache on the remote computer.</span></span>

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   <span data-ttu-id="adf69-220">Você também pode redirecionar os resultados para um arquivo no computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="adf69-220">You can also redirect the results to a file on the local or remote computer.</span></span>
   <span data-ttu-id="adf69-221">O comando a seguir usa um operador de redirecionamento para salvar os resultados em um arquivo no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="adf69-221">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a><span data-ttu-id="adf69-222">Como executar como um processo desanexado</span><span class="sxs-lookup"><span data-stu-id="adf69-222">How to run as a detached process</span></span>

<span data-ttu-id="adf69-223">Como mencionado anteriormente, quando a sessão pai é encerrada, todos os trabalhos filho em execução são encerrados junto com seus processos filhos.</span><span class="sxs-lookup"><span data-stu-id="adf69-223">As previously mentioned, when the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span> <span data-ttu-id="adf69-224">Você pode usar a comunicação remota no computador local para executar trabalhos que não estão anexados à sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adf69-224">You can use remoting on the local machine to run jobs that are not attached to the current PowerShell session.</span></span>

<span data-ttu-id="adf69-225">Crie uma nova sessão do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="adf69-225">Create a new PowerShell session on the local machine.</span></span> <span data-ttu-id="adf69-226">O uso `Invoke-Command` para iniciar um trabalho nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="adf69-226">The use `Invoke-Command` to start a job in this session.</span></span> <span data-ttu-id="adf69-227">`Invoke-Command` permite que você desconecte uma sessão remota e encerre a sessão pai.</span><span class="sxs-lookup"><span data-stu-id="adf69-227">`Invoke-Command` allows you to disconnect a remote session and terminate the parent session.</span></span> <span data-ttu-id="adf69-228">Posteriormente, você pode iniciar uma nova sessão do PowerShell e conectar-se à sessão desconectada anteriormente para retomar o monitoramento do trabalho.</span><span class="sxs-lookup"><span data-stu-id="adf69-228">Later, you can start a new PowerShell session and connect to the previously disconnected session to resume monitoring the job.</span></span> <span data-ttu-id="adf69-229">No entanto, todos os dados retornados para a sessão original do PowerShell são perdidos quando essa sessão é encerrada.</span><span class="sxs-lookup"><span data-stu-id="adf69-229">However, any data that was returned to the original PowerShell session is lost when that session is terminated.</span></span> <span data-ttu-id="adf69-230">Somente novos objetos de dados gerados após a desconexão são retornados quando reconectados.</span><span class="sxs-lookup"><span data-stu-id="adf69-230">Only new data objects generated after the disconnect are returned when re-connected.</span></span>

```powershell
# Create remote session on local machine
PS> $session = New-PSSession -cn localhost

# Start remote job
PS> $job = Invoke-Command -Session $session -ScriptBlock { 1..60 | % { sleep 1; "Output $_" } } -AsJob
PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Running       True            localhost     1..60 | % { sleep 1; ...

# Disconnect the job session
PS> Disconnect-PSSession $session

Id Name         Transport ComputerName    ComputerType    State         ConfigurationName     Availability
-- ----         --------- ------------    ------------    -----         -----------------     ------------
1 Runspace1     WSMan     localhost       RemoteMachine   Disconnected  Microsoft.PowerShell          None

PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Disconnected  True            localhost     1..60 | % { sleep 1;

# Reconnect the session to a new job object
PS> $jobNew = Receive-PSSession -Session $session -OutTarget Job
PS> $job | Wait-Job | Receive-Job
Output 9
Output 10
Output 11
...
```

<span data-ttu-id="adf69-231">Para este exemplo, os trabalhos ainda estão anexados a uma sessão pai do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adf69-231">For this example, the jobs are still attached to a parent PowerShell session.</span></span>
<span data-ttu-id="adf69-232">No entanto, a sessão pai não é a sessão do PowerShell original em que `Invoke-Command` foi executada.</span><span class="sxs-lookup"><span data-stu-id="adf69-232">However, the parent session is not the original PowerShell session where `Invoke-Command` was run.</span></span>

## <a name="see-also"></a><span data-ttu-id="adf69-233">Veja também</span><span class="sxs-lookup"><span data-stu-id="adf69-233">See also</span></span>

- [<span data-ttu-id="adf69-234">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="adf69-234">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="adf69-235">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="adf69-235">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="adf69-236">about_Remote</span><span class="sxs-lookup"><span data-stu-id="adf69-236">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="adf69-237">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="adf69-237">about_Remote_Variables</span></span>](about_Remote_Variables.md)
- [<span data-ttu-id="adf69-238">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="adf69-238">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="adf69-239">Start-Job</span><span class="sxs-lookup"><span data-stu-id="adf69-239">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="adf69-240">Get-Job</span><span class="sxs-lookup"><span data-stu-id="adf69-240">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="adf69-241">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="adf69-241">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="adf69-242">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="adf69-242">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="adf69-243">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="adf69-243">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="adf69-244">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="adf69-244">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="adf69-245">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="adf69-245">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="adf69-246">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="adf69-246">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
