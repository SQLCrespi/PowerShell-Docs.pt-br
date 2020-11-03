---
description: Descreve como executar trabalhos em segundo plano em computadores remotos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: fb2270ea5c0acdcf2c506e687787d22c73e2cb2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196056"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="9a265-104">Sobre trabalhos remotos</span><span class="sxs-lookup"><span data-stu-id="9a265-104">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="9a265-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9a265-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9a265-106">Descreve como executar trabalhos em segundo plano em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="9a265-106">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="9a265-107">DESCRIÇÃO DETALHADA</span><span class="sxs-lookup"><span data-stu-id="9a265-107">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="9a265-108">Um trabalho em segundo plano é um comando que é executado de forma assíncrona sem interagir com a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9a265-108">A background job is a command that runs asynchronously without interacting with the current session.</span></span> <span data-ttu-id="9a265-109">O prompt de comando retorna imediatamente e você pode continuar a usar a sessão enquanto o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="9a265-109">The command prompt returns immediately, and you can continue to use the session while the job runs.</span></span>

<span data-ttu-id="9a265-110">Por padrão, os trabalhos em segundo plano são executados no computador local.</span><span class="sxs-lookup"><span data-stu-id="9a265-110">By default, background jobs run on the local computer.</span></span> <span data-ttu-id="9a265-111">No entanto, você pode usar vários procedimentos diferentes para executar trabalhos em segundo plano em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="9a265-111">However, you can use several different procedures to run background jobs on remote computers.</span></span>

<span data-ttu-id="9a265-112">Este tópico explica como executar um trabalho em segundo plano em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-112">This topic explains how to run a background job on a remote computer.</span></span> <span data-ttu-id="9a265-113">Para obter informações sobre como executar trabalhos em segundo plano em um computador local, consulte [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="9a265-113">For information about how to run background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span> <span data-ttu-id="9a265-114">Para obter mais informações sobre trabalhos em segundo plano, consulte [about_Job_Details](about_Job_Details.md).</span><span class="sxs-lookup"><span data-stu-id="9a265-114">For more information about background jobs, see [about_Job_Details](about_Job_Details.md).</span></span>

## <a name="remote-background-jobs"></a><span data-ttu-id="9a265-115">TRABALHOS EM SEGUNDO PLANO REMOTOS</span><span class="sxs-lookup"><span data-stu-id="9a265-115">REMOTE BACKGROUND JOBS</span></span>

<span data-ttu-id="9a265-116">Você pode executar trabalhos em segundo plano em computadores remotos usando três métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="9a265-116">You can run background jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="9a265-117">Inicie uma sessão interativa com um computador remoto e inicie um trabalho na sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="9a265-117">Start an interactive session with a remote computer, and start a job in the interactive session.</span></span> <span data-ttu-id="9a265-118">Os procedimentos são os mesmos que executar um trabalho local, embora todas as ações sejam executadas no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-118">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="9a265-119">Execute um trabalho em segundo plano em um computador remoto que retorna seus resultados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="9a265-119">Run a background job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="9a265-120">Use esse método quando desejar coletar os resultados de trabalhos em segundo plano e mantê-los em um local central no computador local.</span><span class="sxs-lookup"><span data-stu-id="9a265-120">Use this method when you want to collect the results of background jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="9a265-121">Execute um trabalho em segundo plano em um computador remoto que mantém seus resultados no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-121">Run a background job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="9a265-122">Use esse método quando os dados do trabalho forem mantidos com mais segurança no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="9a265-122">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-background-job-in-an-interactive-session"></a><span data-ttu-id="9a265-123">INICIAR UM TRABALHO EM SEGUNDO PLANO EM UMA SESSÃO INTERATIVA</span><span class="sxs-lookup"><span data-stu-id="9a265-123">START A BACKGROUND JOB IN AN INTERACTIVE SESSION</span></span>

<span data-ttu-id="9a265-124">Você pode iniciar uma sessão interativa com um computador remoto e iniciar um trabalho em segundo plano durante a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="9a265-124">You can start an interactive session with a remote computer and then start a background job during the interactive session.</span></span> <span data-ttu-id="9a265-125">Para obter mais informações sobre sessões interativas, consulte about_Remote e consulte Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="9a265-125">For more information about interactive sessions, see about_Remote, and see Enter-PSSession.</span></span>

<span data-ttu-id="9a265-126">O procedimento para iniciar um trabalho em segundo plano em uma sessão interativa é quase idêntico ao procedimento para iniciar um trabalho em segundo plano no computador local.</span><span class="sxs-lookup"><span data-stu-id="9a265-126">The procedure for starting a background job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="9a265-127">No entanto, todas as operações ocorrem no computador remoto, não no computador local.</span><span class="sxs-lookup"><span data-stu-id="9a265-127">However, all of the operations occur on the remote computer, not the local computer.</span></span>

#### <a name="step-1-enter-pssession"></a><span data-ttu-id="9a265-128">ETAPA 1: ENTER-PSSESSION</span><span class="sxs-lookup"><span data-stu-id="9a265-128">STEP 1: ENTER-PSSESSION</span></span>

<span data-ttu-id="9a265-129">Use o cmdlet Enter-PSSession para iniciar uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-129">Use the Enter-PSSession cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="9a265-130">Você pode usar o parâmetro ComputerName de Enter-PSSession para estabelecer uma conexão temporária para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="9a265-130">You can use the ComputerName parameter of Enter-PSSession to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="9a265-131">Ou, você pode usar o parâmetro Session para executar a sessão interativa em uma sessão do PowerShell (PSSession).</span><span class="sxs-lookup"><span data-stu-id="9a265-131">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

<span data-ttu-id="9a265-132">O comando a seguir inicia uma sessão interativa no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-132">The following command starts an interactive session on the Server01 computer.</span></span>

```powershell
C:\PS> Enter-PSSession -computername Server01
```

<span data-ttu-id="9a265-133">O prompt de comando é alterado para mostrar que agora você está conectado ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-133">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

```
Server01\C:>
```

#### <a name="step-2-start-job"></a><span data-ttu-id="9a265-134">ETAPA 2: INICIAR-TRABALHO</span><span class="sxs-lookup"><span data-stu-id="9a265-134">STEP 2: START-JOB</span></span>

<span data-ttu-id="9a265-135">Para iniciar um trabalho em segundo plano na sessão, use o cmdlet Start-Job.</span><span class="sxs-lookup"><span data-stu-id="9a265-135">To start a background job in the session, use the Start-Job cmdlet.</span></span>

<span data-ttu-id="9a265-136">O comando a seguir executa um trabalho em segundo plano que obtém os eventos no log de eventos do Windows PowerShell no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-136">The following command runs a background job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="9a265-137">O cmdlet Start-Job retorna um objeto que representa o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-137">The Start-Job cmdlet returns an object that represents the job.</span></span>

<span data-ttu-id="9a265-138">Esse comando salva o objeto de trabalho na \$ variável de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-138">This command saves the job object in the \$job variable.</span></span>

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

<span data-ttu-id="9a265-139">Enquanto o trabalho é executado, você pode usar a sessão interativa para executar outros comandos, incluindo outros trabalhos em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9a265-139">While the job runs, you can use the interactive session to run other commands, including other background jobs.</span></span> <span data-ttu-id="9a265-140">No entanto, você deve manter a sessão interativa aberta até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="9a265-140">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="9a265-141">Se você encerrar a sessão, o trabalho será interrompido e os resultados serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="9a265-141">If you end the session, the job is interrupted, and the results are lost.</span></span>

#### <a name="step-3-get-job"></a><span data-ttu-id="9a265-142">ETAPA 3: GET-JOB</span><span class="sxs-lookup"><span data-stu-id="9a265-142">STEP 3: GET-JOB</span></span>

<span data-ttu-id="9a265-143">Para descobrir se o trabalho foi concluído, exiba o valor da variável de \$ trabalho ou use o cmdlet Get-Job para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-143">To find out if the job is complete, display the value of the \$job variable, or use the Get-Job cmdlet to get the job.</span></span> <span data-ttu-id="9a265-144">O comando a seguir usa o cmdlet Get-Job para exibir o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-144">The following command uses the Get-Job cmdlet to display the job.</span></span>

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

<span data-ttu-id="9a265-145">A saída Get-Job mostra que o trabalho está em execução no computador "localhost" porque o trabalho foi iniciado no e está em execução no mesmo computador (neste caso, Server01).</span><span class="sxs-lookup"><span data-stu-id="9a265-145">The Get-Job output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

#### <a name="step-4-receive-job"></a><span data-ttu-id="9a265-146">ETAPA 4: RECEBER-TRABALHO</span><span class="sxs-lookup"><span data-stu-id="9a265-146">STEP 4: RECEIVE-JOB</span></span>

<span data-ttu-id="9a265-147">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="9a265-147">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="9a265-148">Você pode exibir os resultados na sessão interativa ou salvá-los em um arquivo no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-148">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="9a265-149">O comando a seguir obtém os resultados do trabalho na variável $job.</span><span class="sxs-lookup"><span data-stu-id="9a265-149">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="9a265-150">O comando usa o operador de redirecionamento (>) para salvar os resultados do trabalho no arquivo de PsLog.txt no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-150">The command uses the redirection operator (>) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a><span data-ttu-id="9a265-151">ETAPA 5: SAIR-PSSESSION</span><span class="sxs-lookup"><span data-stu-id="9a265-151">STEP 5: EXIT-PSSESSION</span></span>

<span data-ttu-id="9a265-152">Para encerrar a sessão interativa, use o cmdlet Exit-PSSession.</span><span class="sxs-lookup"><span data-stu-id="9a265-152">To end the interactive session, use the Exit-PSSession cmdlet.</span></span> <span data-ttu-id="9a265-153">O prompt de comando é alterado para mostrar que você está de volta na sessão original no computador local.</span><span class="sxs-lookup"><span data-stu-id="9a265-153">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a><span data-ttu-id="9a265-154">ETAPA 6: INVOKE-COMMAND: GET-CONTENT</span><span class="sxs-lookup"><span data-stu-id="9a265-154">STEP 6: INVOKE-COMMAND: GET-CONTENT</span></span>

<span data-ttu-id="9a265-155">Para exibir o conteúdo do arquivo de PsLog.txt no computador Server01 a qualquer momento, inicie outra sessão interativa ou execute um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-155">To view the contents of the PsLog.txt file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="9a265-156">Esse tipo de comando é melhor executado em uma PSSession (uma conexão persistente), caso você queira usar vários comandos para investigar e gerenciar os dados no arquivo de PsLog.txt.</span><span class="sxs-lookup"><span data-stu-id="9a265-156">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the PsLog.txt file.</span></span> <span data-ttu-id="9a265-157">Para obter mais informações sobre PSSessions, consulte about_PSSessions.</span><span class="sxs-lookup"><span data-stu-id="9a265-157">For more information about PSSessions, see about_PSSessions.</span></span>

<span data-ttu-id="9a265-158">Os comandos a seguir usam o cmdlet New-PSSession para criar uma PSSession que está conectada ao computador Server01 e usam o cmdlet Invoke-Command para executar um comando Get-Content na PSSession para exibir o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="9a265-158">The following commands use the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer, and they use the Invoke-Command cmdlet to run a Get-Content command in the PSSession to view the contents of the file.</span></span>

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="9a265-159">INICIAR um trabalho remoto que retorna os resultados para o computador LOCAL \( AsJob\)</span><span class="sxs-lookup"><span data-stu-id="9a265-159">START A REMOTE JOB THAT RETURNS THE RESULTS TO THE LOCAL COMPUTER \(ASJOB\)</span></span>

<span data-ttu-id="9a265-160">Para iniciar um trabalho em segundo plano em um computador remoto que retorna os resultados do comando para o computador local, use o parâmetro AsJob de um cmdlet, como o cmdlet Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="9a265-160">To start a background job on a remote computer that returns the command results to the local computer, use the AsJob parameter of a cmdlet such as the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="9a265-161">Quando você usa o parâmetro AsJob, o objeto de trabalho é realmente criado no computador local, mesmo que o trabalho seja executado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-161">When you use the AsJob parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="9a265-162">Quando o trabalho é concluído, os resultados são retornados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="9a265-162">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="9a265-163">Você pode usar os cmdlets que contêm o substantivo do trabalho (os cmdlets de trabalho) para gerenciar qualquer trabalho criado por qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9a265-163">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="9a265-164">Muitos dos cmdlets que têm parâmetros AsJob não usam a comunicação remota do PowerShell, para que você possa usá-los mesmo em computadores que não estão configurados para comunicação remota e que não atendem aos requisitos de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="9a265-164">Many of the cmdlets that have AsJob parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

#### <a name="step-1-invoke-command--asjob"></a><span data-ttu-id="9a265-165">ETAPA 1: INVOKE-COMMAND-ASJOB</span><span class="sxs-lookup"><span data-stu-id="9a265-165">STEP 1: INVOKE-COMMAND -ASJOB</span></span>

<span data-ttu-id="9a265-166">O comando a seguir usa o parâmetro AsJob de Invoke-Command para iniciar um trabalho em segundo plano no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-166">The following command uses the AsJob parameter of Invoke-Command to start a background job on the Server01 computer.</span></span> <span data-ttu-id="9a265-167">O trabalho executa um comando Get-Eventlog que obtém os eventos no log do sistema.</span><span class="sxs-lookup"><span data-stu-id="9a265-167">The job runs a Get-Eventlog command that gets the events in the System log.</span></span> <span data-ttu-id="9a265-168">Você pode usar o parâmetro JobName para atribuir um nome de exibição ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-168">You can use the JobName parameter to assign a display name to the job.</span></span>

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

<span data-ttu-id="9a265-169">Os resultados do comando se assemelham à saída de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9a265-169">The results of the command resemble the following sample output.</span></span>

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

<span data-ttu-id="9a265-170">Quando o parâmetro AsJob é usado, Invoke-Command retorna o mesmo tipo de objeto de trabalho que Start-Job retorna.</span><span class="sxs-lookup"><span data-stu-id="9a265-170">When the AsJob parameter is used, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="9a265-171">Você pode salvar o objeto de trabalho em uma variável ou pode usar um comando Get-Job para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-171">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="9a265-172">Observe que o valor da propriedade Location mostra que o trabalho foi executado no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-172">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

#### <a name="step-2-get-job"></a><span data-ttu-id="9a265-173">ETAPA 2: GET-JOB</span><span class="sxs-lookup"><span data-stu-id="9a265-173">STEP 2: GET-JOB</span></span>

<span data-ttu-id="9a265-174">Para gerenciar um trabalho iniciado usando o parâmetro AsJob do cmdlet Invoke-Command, use os cmdlets de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-174">To manage a job started by using the AsJob parameter of the Invoke-Command cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="9a265-175">Como o objeto de trabalho que representa o trabalho remoto está no computador local, não é necessário executar comandos remotos para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-175">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

<span data-ttu-id="9a265-176">Para determinar se o trabalho está concluído, use um comando Get-Job.</span><span class="sxs-lookup"><span data-stu-id="9a265-176">To determine whether the job is complete, use a Get-Job command.</span></span> <span data-ttu-id="9a265-177">O comando a seguir obtém todos os trabalhos que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9a265-177">The following command gets all of the jobs that were started in the current session.</span></span>

```powershell
get-job
```

<span data-ttu-id="9a265-178">Como o trabalho remoto foi iniciado na sessão atual, um comando Get-Job local Obtém o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-178">Because the remote job was started in the current session, a local Get-Job command gets the job.</span></span> <span data-ttu-id="9a265-179">A propriedade State do objeto Job mostra que o comando foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="9a265-179">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a><span data-ttu-id="9a265-180">ETAPA 3: RECEBER-TRABALHO</span><span class="sxs-lookup"><span data-stu-id="9a265-180">STEP 3: RECEIVE-JOB</span></span>

<span data-ttu-id="9a265-181">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="9a265-181">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="9a265-182">Como os resultados do trabalho são retornados automaticamente para o computador em que o objeto de trabalho reside, você pode obter os resultados com um comando de Receive-Job local.</span><span class="sxs-lookup"><span data-stu-id="9a265-182">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local Receive-Job command.</span></span>

<span data-ttu-id="9a265-183">O comando a seguir usa o cmdlet Receive-Job para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-183">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="9a265-184">Ele usa a ID de sessão para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-184">It uses the session ID to identify the job.</span></span> <span data-ttu-id="9a265-185">Esse comando salva os resultados do trabalho na variável $results.</span><span class="sxs-lookup"><span data-stu-id="9a265-185">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="9a265-186">Você também pode redirecionar os resultados para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9a265-186">You can also redirect the results to a file.</span></span>

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="9a265-187">INICIAR UM TRABALHO REMOTO QUE MANTÉM OS RESULTADOS NO COMPUTADOR REMOTO</span><span class="sxs-lookup"><span data-stu-id="9a265-187">START A REMOTE JOB THAT KEEPS THE RESULTS ON THE REMOTE COMPUTER</span></span>

<span data-ttu-id="9a265-188">Para iniciar um trabalho em segundo plano em um computador remoto que mantém os resultados do comando no computador remoto, use o cmdlet Invoke-Command para executar um comando Start-Job em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-188">To start a background job on a remote computer that keeps the command results on the remote computer, use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span> <span data-ttu-id="9a265-189">Você pode usar esse método para executar trabalhos em segundo plano em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="9a265-189">You can use this method to run background jobs on multiple computers.</span></span>

<span data-ttu-id="9a265-190">Quando você executa um comando Start-Job remotamente, o objeto de trabalho é criado no computador remoto e os resultados do trabalho são mantidos no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-190">When you run a Start-Job command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="9a265-191">Da perspectiva do trabalho, todas as operações são locais.</span><span class="sxs-lookup"><span data-stu-id="9a265-191">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="9a265-192">Você está apenas executando comandos remotamente para gerenciar um trabalho local no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-192">You are just running commands remotely to manage a local job on the remote computer.</span></span>

#### <a name="step-1-invoke-command-start-job"></a><span data-ttu-id="9a265-193">ETAPA 1: INVOKE-COMANDO START-JOB</span><span class="sxs-lookup"><span data-stu-id="9a265-193">STEP 1: INVOKE-COMMAND START-JOB</span></span>

<span data-ttu-id="9a265-194">Use o cmdlet Invoke-Command para executar um comando Start-Job em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-194">Use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span>

<span data-ttu-id="9a265-195">Esse comando requer uma PSSession (uma conexão persistente).</span><span class="sxs-lookup"><span data-stu-id="9a265-195">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="9a265-196">Se você usar o parâmetro ComputerName de Invoke-Command para estabelecer uma conexão temporária, o comando Invoke-Command será considerado como concluído quando o objeto de trabalho for retornado.</span><span class="sxs-lookup"><span data-stu-id="9a265-196">If you use the ComputerName parameter of Invoke-Command to establish a temporary connection, the Invoke-Command command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="9a265-197">Como resultado, a conexão temporária é fechada e o trabalho é cancelado.</span><span class="sxs-lookup"><span data-stu-id="9a265-197">As a result, the temporary connection is closed, and the job is canceled.</span></span>

<span data-ttu-id="9a265-198">O comando a seguir usa o cmdlet New-PSSession para criar uma PSSession que está conectada ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-198">The following command uses the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="9a265-199">O comando salva a PSSession na \$ variável s.</span><span class="sxs-lookup"><span data-stu-id="9a265-199">The command saves the PSSession in the \$s variable.</span></span>

```powershell
$s = new-pssession -computername Server01
```

<span data-ttu-id="9a265-200">O comando a seguir usa o cmdlet Invoke-Command para executar um comando Start-Job na PSSession.</span><span class="sxs-lookup"><span data-stu-id="9a265-200">The next command uses the Invoke-Command cmdlet to run a Start-Job command in the PSSession.</span></span> <span data-ttu-id="9a265-201">O comando Start-Job e o comando Get-Eventlog são colocados entre chaves.</span><span class="sxs-lookup"><span data-stu-id="9a265-201">The Start-Job command and the Get-Eventlog command are enclosed in braces.</span></span>

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

<span data-ttu-id="9a265-202">Os resultados se assemelham à saída de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9a265-202">The results resemble the following sample output.</span></span>

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

<span data-ttu-id="9a265-203">Quando você executa um comando Start-Job remotamente, Invoke-Command retorna o mesmo tipo de objeto de trabalho que Start-Job retorna.</span><span class="sxs-lookup"><span data-stu-id="9a265-203">When you run a Start-Job command remotely, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="9a265-204">Você pode salvar o objeto de trabalho em uma variável ou pode usar um comando Get-Job para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-204">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="9a265-205">Observe que o valor da propriedade Location mostra que o trabalho foi executado no computador local, conhecido como "LocalHost", embora o trabalho tenha sido executado no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-205">Note that the value of the Location property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="9a265-206">Como o objeto de trabalho é criado no computador Server01 e o trabalho é executado no mesmo computador, é considerado um trabalho em segundo plano local.</span><span class="sxs-lookup"><span data-stu-id="9a265-206">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

#### <a name="step-2-invoke-command-get-job"></a><span data-ttu-id="9a265-207">ETAPA 2: INVOKE-COMMAND GET-JOB</span><span class="sxs-lookup"><span data-stu-id="9a265-207">STEP 2: INVOKE-COMMAND GET-JOB</span></span>

<span data-ttu-id="9a265-208">Para gerenciar um trabalho de segundo plano remoto, use os cmdlets de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-208">To manage a remote background job, use the Job cmdlets.</span></span> <span data-ttu-id="9a265-209">Como o objeto de trabalho está no computador remoto, você precisa executar comandos remotos para obter, parar, aguardar ou recuperar os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-209">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

<span data-ttu-id="9a265-210">Para ver se o trabalho está concluído, use um comando Invoke-Command para executar um comando Get-Job na PSSession que está conectada ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-210">To see if the job is complete, use an Invoke-Command command to run a Get-Job command in the PSSession that is connected to the Server01 computer.</span></span>

```powershell
invoke-command -session $s -scriptblock {get-job}
```

<span data-ttu-id="9a265-211">O comando retorna um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-211">The command returns a job object.</span></span> <span data-ttu-id="9a265-212">A propriedade State do objeto Job mostra que o comando foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="9a265-212">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a><span data-ttu-id="9a265-213">ETAPA 3: INVOKE-COMANDO RECEIVE-JOB</span><span class="sxs-lookup"><span data-stu-id="9a265-213">STEP 3: INVOKE-COMMAND RECEIVE-JOB</span></span>

<span data-ttu-id="9a265-214">Para obter os resultados do trabalho, use o cmdlet Invoke-Command para executar um comando Receive-Job na PSSession que está conectada ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-214">To get the results of the job, use the Invoke-Command cmdlet to run a Receive-Job command in the PSSession that is connected to the Server01 computer.</span></span>

<span data-ttu-id="9a265-215">O comando a seguir usa o cmdlet Receive-Job para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-215">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="9a265-216">Ele usa a ID de sessão para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a265-216">It uses the session ID to identify the job.</span></span> <span data-ttu-id="9a265-217">Esse comando salva os resultados do trabalho na \$ variável Results.</span><span class="sxs-lookup"><span data-stu-id="9a265-217">This command saves the job results in the \$results variable.</span></span> <span data-ttu-id="9a265-218">Ele usa o parâmetro Keep de Receive-Job para manter o resultado no cache do trabalho no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-218">It uses the Keep parameter of Receive-Job to keep the result in the job cache on the remote computer.</span></span>

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

<span data-ttu-id="9a265-219">Você também pode redirecionar os resultados para um arquivo no computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="9a265-219">You can also redirect the results to a file on the local or remote computer.</span></span>
<span data-ttu-id="9a265-220">O comando a seguir usa um operador de redirecionamento para salvar os resultados em um arquivo no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="9a265-220">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a><span data-ttu-id="9a265-221">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9a265-221">SEE ALSO</span></span>

[<span data-ttu-id="9a265-222">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="9a265-222">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="9a265-223">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="9a265-223">about_Job_Details</span></span>](about_Job_Details.md)

[<span data-ttu-id="9a265-224">about_Remote</span><span class="sxs-lookup"><span data-stu-id="9a265-224">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="9a265-225">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="9a265-225">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="9a265-226">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="9a265-226">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="9a265-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="9a265-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)

[<span data-ttu-id="9a265-228">Get-Job</span><span class="sxs-lookup"><span data-stu-id="9a265-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)

[<span data-ttu-id="9a265-229">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="9a265-229">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)

[<span data-ttu-id="9a265-230">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="9a265-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)

[<span data-ttu-id="9a265-231">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="9a265-231">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)

[<span data-ttu-id="9a265-232">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="9a265-232">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="9a265-233">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="9a265-233">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="9a265-234">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="9a265-234">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

