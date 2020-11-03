---
description: Fornece detalhes sobre trabalhos em segundo plano em computadores locais e remotos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_job_details?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Job_Details
ms.openlocfilehash: 0d85cd242c8e79281fa8be153b0e140660f16c1a
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "93196493"
---
# <a name="about-job-details"></a><span data-ttu-id="70184-104">Sobre os detalhes do trabalho</span><span class="sxs-lookup"><span data-stu-id="70184-104">About Job Details</span></span>

## <a name="short-description"></a><span data-ttu-id="70184-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="70184-105">Short description</span></span>
<span data-ttu-id="70184-106">Fornece detalhes sobre trabalhos em segundo plano em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="70184-106">Provides details about background jobs on local and remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="70184-107">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="70184-107">Detailed description</span></span>

<span data-ttu-id="70184-108">Este tópico explica o conceito de um trabalho em segundo plano e fornece informações técnicas sobre como trabalhos em segundo plano funcionam no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70184-108">This topic explains the concept of a background job and provides technical information about how background jobs work in PowerShell.</span></span>

<span data-ttu-id="70184-109">Este tópico é um suplemento para os tópicos [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md)e [about_Remote_Jobs](about_Remote_Jobs.md) .</span><span class="sxs-lookup"><span data-stu-id="70184-109">This topic is a supplement to the [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md), and [about_Remote_Jobs](about_Remote_Jobs.md) topics.</span></span>

### <a name="about-background-jobs"></a><span data-ttu-id="70184-110">Sobre trabalhos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="70184-110">About background jobs</span></span>

<span data-ttu-id="70184-111">Um trabalho em segundo plano executa um comando ou expressão de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="70184-111">A background job runs a command or expression asynchronously.</span></span> <span data-ttu-id="70184-112">Ele pode executar um cmdlet, uma função, um script ou qualquer outra tarefa baseada em comando.</span><span class="sxs-lookup"><span data-stu-id="70184-112">It might run a cmdlet, a function, a script, or any other command-based task.</span></span> <span data-ttu-id="70184-113">Ele foi projetado para executar comandos que usam um longo período de tempo, mas você pode usá-lo para executar qualquer comando em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="70184-113">It is designed to run commands that take an extended period of time, but you can use it to run any command in the background.</span></span>

<span data-ttu-id="70184-114">Quando um comando síncrono é executado, o prompt de comando do PowerShell é suprimido até que o comando seja concluído.</span><span class="sxs-lookup"><span data-stu-id="70184-114">When a synchronous command runs, the PowerShell command prompt is suppressed until the command is complete.</span></span> <span data-ttu-id="70184-115">Mas um trabalho em segundo plano não suprime o prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70184-115">But a background job does not suppress the PowerShell prompt.</span></span> <span data-ttu-id="70184-116">Um comando para iniciar um trabalho em segundo plano retorna um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-116">A command to start a background job returns a job object.</span></span>
<span data-ttu-id="70184-117">O prompt retorna imediatamente para que você possa trabalhar em outras tarefas enquanto o trabalho em segundo plano é executado.</span><span class="sxs-lookup"><span data-stu-id="70184-117">The prompt returns immediately so you can work on other tasks while the background job runs.</span></span>

<span data-ttu-id="70184-118">No entanto, ao iniciar um trabalho em segundo plano, você não obtém os resultados imediatamente, mesmo que o trabalho seja executado muito rapidamente.</span><span class="sxs-lookup"><span data-stu-id="70184-118">However, when you start a background job, you do not get the results immediately even if the job runs very quickly.</span></span> <span data-ttu-id="70184-119">O objeto de trabalho retornado contém informações úteis sobre o trabalho, mas não contém os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-119">The job object that is returned contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="70184-120">Você deve executar um comando separado para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-120">You must run a separate command to get the job results.</span></span> <span data-ttu-id="70184-121">Você também pode executar comandos para interromper o trabalho, aguardar a conclusão do trabalho e excluir o trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-121">You can also run commands to stop the job, to wait for the job to be completed, and to delete the job.</span></span>

<span data-ttu-id="70184-122">Para tornar o tempo de um trabalho em segundo plano independente de outros comandos, cada trabalho em segundo plano é executado em sua própria sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70184-122">To make the timing of a background job independent of other commands, each background job runs in its own PowerShell session.</span></span> <span data-ttu-id="70184-123">No entanto, essa pode ser uma conexão temporária que é criada somente para executar o trabalho e, em seguida, destruída, ou pode ser uma **PSSession** persistente que você pode usar para executar vários trabalhos ou comandos relacionados.</span><span class="sxs-lookup"><span data-stu-id="70184-123">However, this can be a temporary connection that is created only to run the job and is then destroyed, or it can be a persistent **PSSession** that you can use to run several related jobs or commands.</span></span>

### <a name="using-the-job-cmdlets"></a><span data-ttu-id="70184-124">Usando os cmdlets de trabalho</span><span class="sxs-lookup"><span data-stu-id="70184-124">Using the job cmdlets</span></span>

<span data-ttu-id="70184-125">Use um `Start-Job` comando para iniciar um trabalho em segundo plano em um computador local.</span><span class="sxs-lookup"><span data-stu-id="70184-125">Use a `Start-Job` command to start a background job on a local computer.</span></span>
<span data-ttu-id="70184-126">`Start-Job` Retorna um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-126">`Start-Job` returns a job object.</span></span> <span data-ttu-id="70184-127">Você também pode obter objetos que representam os trabalhos que foram iniciados no computador local usando o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-127">You can also get objects representing the jobs that were started on the local computer using the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="70184-128">Para obter os resultados do trabalho, use um `Receive-Job` comando.</span><span class="sxs-lookup"><span data-stu-id="70184-128">To get the job results, use a `Receive-Job` command.</span></span> <span data-ttu-id="70184-129">Se o trabalho não estiver concluído, o `Receive-Job` retornará resultados parciais.</span><span class="sxs-lookup"><span data-stu-id="70184-129">If the job is not complete, `Receive-Job` returns partial results.</span></span> <span data-ttu-id="70184-130">Você também pode usar o `Wait-Job` cmdlet para suprimir o prompt de comando até que um ou todos os trabalhos iniciados na sessão sejam concluídos.</span><span class="sxs-lookup"><span data-stu-id="70184-130">You can also use the `Wait-Job` cmdlet to suppress the command prompt until one or all of the jobs that were started in the session are complete.</span></span>

<span data-ttu-id="70184-131">Para interromper um trabalho em segundo plano, use o `Stop-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-131">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="70184-132">Para excluir um trabalho, use o `Remove-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-132">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="70184-133">Para obter mais informações sobre como os cmdlets funcionam, consulte o tópico da ajuda para cada cmdlet e consulte [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="70184-133">For more information about how the cmdlets work, see the Help topic for each cmdlet, and see [about_Jobs](about_Jobs.md).</span></span>

### <a name="starting-background-jobs-on-remote-computers"></a><span data-ttu-id="70184-134">Iniciando trabalhos em segundo plano em computadores remotos</span><span class="sxs-lookup"><span data-stu-id="70184-134">Starting background jobs on remote computers</span></span>

<span data-ttu-id="70184-135">Você pode criar e gerenciar trabalhos em segundo plano em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="70184-135">You can create and manage background jobs on a local or remote computer.</span></span> <span data-ttu-id="70184-136">Para executar um trabalho em segundo plano remotamente, use o parâmetro **AsJob** de um cmdlet `Invoke-Command` , como, ou use o `Invoke-Command` cmdlet para executar um `Start-Job` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="70184-136">To run a background job remotely, use the **AsJob** parameter of a cmdlet such as `Invoke-Command`, or use the `Invoke-Command` cmdlet to run a `Start-Job` command remotely.</span></span> <span data-ttu-id="70184-137">Você também pode iniciar um trabalho em segundo plano em uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="70184-137">You can also start a background job in an interactive session.</span></span>

<span data-ttu-id="70184-138">Para obter mais informações sobre trabalhos em segundo plano remotos, consulte [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="70184-138">For more information about remote background jobs, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>

### <a name="child-jobs"></a><span data-ttu-id="70184-139">Trabalhos filho</span><span class="sxs-lookup"><span data-stu-id="70184-139">Child jobs</span></span>

<span data-ttu-id="70184-140">Cada trabalho em segundo plano consiste em um trabalho pai e um ou mais trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="70184-140">Each background job consists of a parent job and one or more child jobs.</span></span> <span data-ttu-id="70184-141">Em trabalhos iniciados usando `Start-Job` o ou o parâmetro **AsJob** de `Invoke-Command` , o trabalho pai é um executivo.</span><span class="sxs-lookup"><span data-stu-id="70184-141">In jobs started using `Start-Job` or the **AsJob** parameter of `Invoke-Command`, the parent job is an executive.</span></span> <span data-ttu-id="70184-142">Ele não executa nenhum comando nem retorna nenhum resultado.</span><span class="sxs-lookup"><span data-stu-id="70184-142">It does not run any commands or return any results.</span></span> <span data-ttu-id="70184-143">Os comandos são realmente executados pelos trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="70184-143">The commands are actually run by the child jobs.</span></span> <span data-ttu-id="70184-144">Os trabalhos iniciados usando outros cmdlets podem funcionar de maneira diferente.</span><span class="sxs-lookup"><span data-stu-id="70184-144">Jobs started using other cmdlets might work differently.</span></span>

<span data-ttu-id="70184-145">Os trabalhos filho são armazenados na propriedade **ChildJobs** do objeto de trabalho pai.</span><span class="sxs-lookup"><span data-stu-id="70184-145">The child jobs are stored in the **ChildJobs** property of the parent job object.</span></span> <span data-ttu-id="70184-146">A propriedade **ChildJobs** pode conter um ou vários objetos de trabalho filho.</span><span class="sxs-lookup"><span data-stu-id="70184-146">The **ChildJobs** property can contain one or many child job objects.</span></span>
<span data-ttu-id="70184-147">Os objetos de trabalho filho têm um **nome** , **ID** e **InstanceId** que diferem do trabalho pai para que você possa gerenciar os trabalhos pai e filho individualmente ou como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="70184-147">The child job objects have a **Name** , **ID** , and **InstanceId** that differ from the parent job so that you can manage the parent and child jobs individually or as a unit.</span></span>

<span data-ttu-id="70184-148">Para obter os trabalhos pai e filho de um trabalho, use o parâmetro **IncludeChildJobs** do `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-148">To get the parent and child jobs of a job, use the **IncludeChildJobs** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="70184-149">O parâmetro **IncludeChildJob** foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70184-149">The **IncludeChildJob** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -IncludeChildJob

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="70184-150">Para obter o trabalho pai e apenas os trabalhos filho com um valor de **estado** específico, use o parâmetro **ChildJobState** do `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-150">To get the parent job and only the child jobs with a particular **State** value, use the **ChildJobState** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="70184-151">O parâmetro **ChildJobState** foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70184-151">The **ChildJobState** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -ChildJobState Failed

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="70184-152">Para obter os trabalhos filho de um trabalho em todas as versões do PowerShell, use a propriedade **ChildJob** do trabalho pai.</span><span class="sxs-lookup"><span data-stu-id="70184-152">To get the child jobs of a job on all versions of PowerShell, use the **ChildJob** property of the parent job.</span></span>

```powershell
PS> (Get-Job Job1).ChildJobs

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="70184-153">Você também pode usar um `Get-Job` comando no trabalho filho, conforme mostrado no seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="70184-153">You can also use a `Get-Job` command on the child job, as shown in the following command:</span></span>

```powershell
PS> Get-Job Job3

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="70184-154">A configuração do trabalho filho depende do comando que você usa para iniciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-154">The configuration of the child job depends on the command that you use to start the job.</span></span>

- <span data-ttu-id="70184-155">Quando você usa `Start-Job` o para iniciar um trabalho em um computador local, o trabalho consiste em um trabalho pai executivo e um trabalho filho que executa o comando.</span><span class="sxs-lookup"><span data-stu-id="70184-155">When you use `Start-Job` to start a job on a local computer, the job consists of an executive parent job and a child job that runs the command.</span></span>

- <span data-ttu-id="70184-156">Quando você usa o parâmetro **AsJob** do `Invoke-Command` para iniciar um trabalho em um ou mais computadores, o trabalho consiste em um trabalho pai executivo e um trabalho filho para cada trabalho executado em cada computador.</span><span class="sxs-lookup"><span data-stu-id="70184-156">When you use the **AsJob** parameter of `Invoke-Command` to start a job on one or more computers, the job consists of an executive parent job and a child job for each job run on each computer.</span></span>

- <span data-ttu-id="70184-157">Quando você usa o `Invoke-Command` para executar um `Start-Job` comando em um ou mais computadores remotos, o resultado é o mesmo que um comando local executado em cada computador remoto.</span><span class="sxs-lookup"><span data-stu-id="70184-157">When you use `Invoke-Command` to run a `Start-Job` command on one or more remote computers, the result is the same as a local command run on each remote computer.</span></span> <span data-ttu-id="70184-158">O comando retorna um objeto de trabalho para cada computador.</span><span class="sxs-lookup"><span data-stu-id="70184-158">The command returns a job object for each computer.</span></span> <span data-ttu-id="70184-159">O objeto de trabalho consiste em um trabalho pai executivo e um trabalho filho que executa o comando.</span><span class="sxs-lookup"><span data-stu-id="70184-159">The job object consists of an executive parent job and one child job that runs the command.</span></span>

<span data-ttu-id="70184-160">O trabalho pai representa todos os trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="70184-160">The parent job represents all of the child jobs.</span></span> <span data-ttu-id="70184-161">Ao gerenciar um trabalho pai, você também gerencia os trabalhos filho associados.</span><span class="sxs-lookup"><span data-stu-id="70184-161">When you manage a parent job, you also manage the associated child jobs.</span></span> <span data-ttu-id="70184-162">Por exemplo, se você parar um trabalho pai, todos os trabalhos filho serão interrompidos.</span><span class="sxs-lookup"><span data-stu-id="70184-162">For example, if you stop a parent job, all child jobs are stopped.</span></span> <span data-ttu-id="70184-163">Se você obtiver os resultados de um trabalho pai, obterá os resultados de todos os trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="70184-163">If you get the results of a parent job, you get the results of all child jobs.</span></span>

<span data-ttu-id="70184-164">No entanto, você também pode gerenciar trabalhos filhos individualmente.</span><span class="sxs-lookup"><span data-stu-id="70184-164">However, you can also manage child jobs individually.</span></span> <span data-ttu-id="70184-165">Isso é mais útil quando você deseja investigar um problema com um trabalho ou obter os resultados de apenas um dos vários trabalhos filho iniciado usando o parâmetro **AsJob** de `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="70184-165">This is most useful when you want to investigate a problem with a job or get the results of only one of a number of child jobs started using the **AsJob** parameter of `Invoke-Command`.</span></span>

<span data-ttu-id="70184-166">O comando a seguir usa o parâmetro **AsJob** do `Invoke-Command` para iniciar trabalhos em segundo plano no computador local e em dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="70184-166">The following command uses the **AsJob** parameter of `Invoke-Command` to start background jobs on the local computer and two remote computers.</span></span> <span data-ttu-id="70184-167">O comando salva o trabalho na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="70184-167">The command saves the job in the `$j` variable.</span></span>

```powershell
PS> $j = Invoke-Command -ComputerName localhost, Server01, Server02 `
-Command {Get-Date} -AsJob
```

<span data-ttu-id="70184-168">Quando você exibe as propriedades Name e **ChildJob** do trabalho no `$j` , ele mostra que o comando retornou um objeto de trabalho com três trabalhos filho, um para cada computador.</span><span class="sxs-lookup"><span data-stu-id="70184-168">When you display the Name and **ChildJob** properties of the job in `$j`, it shows that the command returned a job object with three child jobs, one for each computer.</span></span>

```powershell
PS> $j | Format-List Name, ChildJobs

Name      : Job3
ChildJobs : {Job4, Job5, Job6}
```

<span data-ttu-id="70184-169">Quando você exibe o trabalho pai, ele mostra que o trabalho falhou.</span><span class="sxs-lookup"><span data-stu-id="70184-169">When you display the parent job, it shows that the job failed.</span></span>

```powershell
PS> $j

Id Name   PSJobTypeName State      HasMoreData   Location
-- ----   ------------- -----      -----------   --------
3  Job3   RemotingJob   Failed     False         localhost,Server...
```

<span data-ttu-id="70184-170">Mas quando você executa um `Get-Job` comando que obtém os trabalhos filho, a saída mostra que apenas um trabalho filho falhou.</span><span class="sxs-lookup"><span data-stu-id="70184-170">But when you run a `Get-Job` command that gets the child jobs, the output shows that only one child job failed.</span></span>

```powershell
PS> Get-Job -IncludeChildJobs

Id  Name   PSJobTypeName State      HasMoreData   Location    Command
--  ----   ------------- -----      -----------   --------    -------
3   Job3   RemotingJob   Failed     False         localhost,Server...
4   Job4                 Completed  True          localhost   Get-Date
5   Job5                 Failed     False         Server01    Get-Date
6   Job6                 Completed  True          Server02    Get-Date
```

<span data-ttu-id="70184-171">Para obter os resultados de todos os trabalhos filho, use o `Receive-Job` cmdlet para obter os resultados do trabalho pai.</span><span class="sxs-lookup"><span data-stu-id="70184-171">To get the results of all child jobs, use the `Receive-Job` cmdlet to get the results of the parent job.</span></span> <span data-ttu-id="70184-172">Mas você também pode obter os resultados de um trabalho filho específico, conforme mostrado no comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="70184-172">But you can also get the results of a particular child job, as shown in the following command.</span></span>

```powershell
PS> Receive-Job -Name Job6 -Keep | Format-Table ComputerName,
>> DateTime -AutoSize
ComputerName DateTime
------------ --------
Server02     Thursday, March 13, 2008 4:16:03 PM
```

<span data-ttu-id="70184-173">O recurso de trabalhos filho de trabalhos em segundo plano do PowerShell oferece mais controle sobre os trabalhos que você executa.</span><span class="sxs-lookup"><span data-stu-id="70184-173">The child jobs feature of PowerShell background jobs gives you more control over the jobs that you run.</span></span>

### <a name="job-types"></a><span data-ttu-id="70184-174">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="70184-174">Job types</span></span>

<span data-ttu-id="70184-175">O PowerShell dá suporte a diferentes tipos de trabalhos para tarefas diferentes.</span><span class="sxs-lookup"><span data-stu-id="70184-175">PowerShell supports different types of jobs for different tasks.</span></span> <span data-ttu-id="70184-176">A partir do Windows PowerShell 3,0, os desenvolvedores podem escrever "adaptadores de origem do trabalho" que adicionam novos tipos de trabalho ao PowerShell e incluem os adaptadores de origem do trabalho em módulos.</span><span class="sxs-lookup"><span data-stu-id="70184-176">Beginning in Windows PowerShell 3.0, developers can write "job source adapters" that add new job types to PowerShell and include the job source adapters in modules.</span></span>
<span data-ttu-id="70184-177">Ao importar o módulo, você pode usar o novo tipo de trabalho em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="70184-177">When you import the module, you can use the new job type in your session.</span></span>

<span data-ttu-id="70184-178">Por exemplo, o módulo PSScheduledJob adiciona trabalhos agendados e o módulo PSWorkflow adiciona trabalhos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-178">For example, the PSScheduledJob module adds scheduled jobs and the PSWorkflow module adds workflow jobs.</span></span>

<span data-ttu-id="70184-179">Os tipos de trabalhos personalizados podem diferir significativamente dos trabalhos em segundo plano padrão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70184-179">Custom jobs types might differ significantly from standard PowerShell background jobs.</span></span> <span data-ttu-id="70184-180">Por exemplo, os trabalhos agendados são salvos em disco; Eles não existem somente em uma sessão específica.</span><span class="sxs-lookup"><span data-stu-id="70184-180">For example, scheduled jobs are saved on disk; they do not exist only in a particular session.</span></span> <span data-ttu-id="70184-181">Os trabalhos de fluxo de trabalho podem ser suspensos e retomados.</span><span class="sxs-lookup"><span data-stu-id="70184-181">Workflow jobs can be suspended and resumed.</span></span>

<span data-ttu-id="70184-182">Os cmdlets que você usa para gerenciar trabalhos personalizados dependem do tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-182">The cmdlets that you use to manage custom jobs depend on the job type.</span></span> <span data-ttu-id="70184-183">Para alguns, você usa os cmdlets de trabalho padrão, como `Get-Job` e `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="70184-183">For some, you use the standard job cmdlets, such as `Get-Job` and `Start-Job`.</span></span> <span data-ttu-id="70184-184">Outras são fornecidas com cmdlets especializados que gerenciam apenas um determinado tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-184">Others come with specialized cmdlets that manage only a particular type of job.</span></span> <span data-ttu-id="70184-185">Para obter informações detalhadas sobre tipos de trabalho personalizados, consulte os tópicos da ajuda sobre o tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-185">For detailed information about custom job types, see the help topics about the job type.</span></span>

<span data-ttu-id="70184-186">Para localizar o tipo de trabalho de um trabalho, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-186">To find the job type of a job, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="70184-187">`Get-Job` retorna objetos de trabalho diferentes para diferentes tipos de trabalhos.</span><span class="sxs-lookup"><span data-stu-id="70184-187">`Get-Job` returns different job objects for different types of jobs.</span></span> <span data-ttu-id="70184-188">O valor da propriedade **PSJobTypeName** dos objetos de trabalho que `Get-Job` retornam indica o tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-188">The value of the **PSJobTypeName** property of the job objects that `Get-Job` returns indicates the job type.</span></span>

<span data-ttu-id="70184-189">A tabela a seguir lista os tipos de trabalho que vêm com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70184-189">The following table lists the job types that come with PowerShell.</span></span>

|    <span data-ttu-id="70184-190">Tipo de Trabalho</span><span class="sxs-lookup"><span data-stu-id="70184-190">Job Type</span></span>    |                       <span data-ttu-id="70184-191">Descrição</span><span class="sxs-lookup"><span data-stu-id="70184-191">Description</span></span>                        |
| -------------- | -------------------------------------------------------- |
| <span data-ttu-id="70184-192">BackgroundJob</span><span class="sxs-lookup"><span data-stu-id="70184-192">BackgroundJob</span></span>  | <span data-ttu-id="70184-193">Iniciado usando o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-193">Started using the `Start-Job` cmdlet.</span></span>                    |
| <span data-ttu-id="70184-194">RemoteJob</span><span class="sxs-lookup"><span data-stu-id="70184-194">RemoteJob</span></span>      | <span data-ttu-id="70184-195">Iniciado usando o parâmetro **AsJob** do</span><span class="sxs-lookup"><span data-stu-id="70184-195">Started using the **AsJob** parameter of the</span></span>             |
|                | <span data-ttu-id="70184-196">cmdlet `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="70184-196">`Invoke-Command` cmdlet.</span></span>                                 |
| <span data-ttu-id="70184-197">PSWorkflowJob</span><span class="sxs-lookup"><span data-stu-id="70184-197">PSWorkflowJob</span></span>  | <span data-ttu-id="70184-198">Iniciado usando o parâmetro **AsJob** de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-198">Started using the **AsJob** parameter of a workflow.</span></span>     |
| <span data-ttu-id="70184-199">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="70184-199">PSScheduledJob</span></span> | <span data-ttu-id="70184-200">Uma instância de um trabalho agendado iniciado por um gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-200">An instance of a scheduled job started by a job trigger.</span></span> |
| <span data-ttu-id="70184-201">CIMJob</span><span class="sxs-lookup"><span data-stu-id="70184-201">CIMJob</span></span>         | <span data-ttu-id="70184-202">Iniciado usando o parâmetro **AsJob** de um cmdlet a partir de um</span><span class="sxs-lookup"><span data-stu-id="70184-202">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="70184-203">Módulo CDXML.</span><span class="sxs-lookup"><span data-stu-id="70184-203">CDXML module.</span></span>                                            |
| <span data-ttu-id="70184-204">WMIJob</span><span class="sxs-lookup"><span data-stu-id="70184-204">WMIJob</span></span>         | <span data-ttu-id="70184-205">Iniciado usando o parâmetro **AsJob** de um cmdlet a partir de um</span><span class="sxs-lookup"><span data-stu-id="70184-205">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="70184-206">Módulo WMI.</span><span class="sxs-lookup"><span data-stu-id="70184-206">WMI module.</span></span>                                              |
| <span data-ttu-id="70184-207">PSEventJob</span><span class="sxs-lookup"><span data-stu-id="70184-207">PSEventJob</span></span>     | <span data-ttu-id="70184-208">Criado usando `Register-ObjectEvent` e especificando um</span><span class="sxs-lookup"><span data-stu-id="70184-208">Created using`Register-ObjectEvent` and specifying an</span></span>    |
|                | <span data-ttu-id="70184-209">ação com o parâmetro **Action** .</span><span class="sxs-lookup"><span data-stu-id="70184-209">action with the **Action** parameter.</span></span>                    |

<span data-ttu-id="70184-210">Observação: antes de usar o `Get-Job` cmdlet para obter trabalhos de um tipo específico, verifique se o módulo que adiciona o tipo de trabalho é importado para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="70184-210">NOTE: Before using the `Get-Job` cmdlet to get jobs of a particular type, verify that the module that adds the job type is imported into the current session.</span></span>
<span data-ttu-id="70184-211">Caso contrário, `Get-Job` o não obterá trabalhos desse tipo.</span><span class="sxs-lookup"><span data-stu-id="70184-211">Otherwise, `Get-Job` does not get jobs of that type.</span></span>

## <a name="examples"></a><span data-ttu-id="70184-212">Exemplos</span><span class="sxs-lookup"><span data-stu-id="70184-212">Examples</span></span>

<span data-ttu-id="70184-213">Os comandos a seguir criam um trabalho em segundo plano local, um trabalho de segundo plano remoto, um trabalho de fluxo e um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="70184-213">The following commands create a local background job, a remote background job, a workflow job, and a scheduled job.</span></span> <span data-ttu-id="70184-214">Em seguida, ele usa o `Get-Job` cmdlet para obter os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="70184-214">Then, it uses the `Get-Job` cmdlet to get the jobs.</span></span> <span data-ttu-id="70184-215">`Get-Job` Não Obtém o trabalho agendado, mas obtém todas as instâncias iniciadas do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="70184-215">`Get-Job` does not get the scheduled job, but it gets any started instances of the scheduled job.</span></span>

<span data-ttu-id="70184-216">Inicie um trabalho em segundo plano no computador local.</span><span class="sxs-lookup"><span data-stu-id="70184-216">Start a background job on the local computer.</span></span>

```powershell
PS> Start-Job -Name LocalData {Get-Process}

Id Name        PSJobTypeName   State   HasMoreData   Location   Command
-- ----        -------------   -----   -----------   --------   -------
2  LocalData   BackgroundJob   Running        True   localhost  Get-Process
```

<span data-ttu-id="70184-217">Iniciar um trabalho em segundo plano executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="70184-217">Start a background job that runs on a remote computer.</span></span>

```powershell
PS> Invoke-Command -ComputerName Server01 {Get-Process} `
-AsJob -JobName RemoteData

Id  Name        PSJobTypeName  State   HasMoreData   Location   Command
--  ----        -------------  -----   -----------   --------   -------
2   RemoteData  RemoteJob      Running        True   Server01   Get-Process
```

<span data-ttu-id="70184-218">Crie um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="70184-218">Create a scheduled job</span></span>

```powershell
PS>  Register-ScheduledJob -Name ScheduledJob -ScriptBlock `
 {Get-Process} -Trigger (New-JobTrigger -Once -At "3 PM")

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

<span data-ttu-id="70184-219">Crie um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="70184-219">Create a workflow.</span></span>

```powershell
PS> workflow Test-Workflow {Get-Process}
```

<span data-ttu-id="70184-220">Execute o fluxo de trabalho como uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="70184-220">Run the workflow as a job.</span></span>

```powershell

PS> Test-Workflow -AsJob -JobName TestWFJob

Id  Name       PSJobTypeName   State   HasMoreData   Location   Command
--  ----       -------------   -----   -----------   --------   -------
2   TestWFJob  PSWorkflowJob   NotStarted     True   localhost  Get-Process
```

<span data-ttu-id="70184-221">Obter os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="70184-221">Get the jobs.</span></span> <span data-ttu-id="70184-222">O `Get-Job` comando não obtém trabalhos agendados, mas obtém instâncias do trabalho agendado que são iniciados.</span><span class="sxs-lookup"><span data-stu-id="70184-222">The `Get-Job` command does not get scheduled jobs, but it gets instances of the scheduled job that are started.</span></span>

```powershell
PS> Get-Job

Id  Name         PSJobTypeName  State     HasMoreData  Location  Command
--  ----         -------------  -----     -----------  --------  -------
2   LocalData    BackgroundJob  Completed True         localhost Get-Process
4   RemoteData   RemoteJob      Completed True         Server01  Get-Process
6   TestWFJob    PSWorkflowJob  Completed True         localhost WorkflowJob
8   ScheduledJob PSScheduledJob Completed True         localhost Get-Process
```

<span data-ttu-id="70184-223">Para obter trabalhos agendados, use o `Get-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70184-223">To get scheduled jobs, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
PS> Get-ScheduledJob

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

## <a name="see-also"></a><span data-ttu-id="70184-224">Confira também</span><span class="sxs-lookup"><span data-stu-id="70184-224">See also</span></span>

- [<span data-ttu-id="70184-225">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="70184-225">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="70184-226">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="70184-226">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="70184-227">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="70184-227">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="70184-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="70184-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="70184-229">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="70184-229">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="70184-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="70184-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="70184-231">Get-Job</span><span class="sxs-lookup"><span data-stu-id="70184-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="70184-232">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="70184-232">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="70184-233">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="70184-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="70184-234">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="70184-234">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="70184-235">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="70184-235">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="70184-236">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="70184-236">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="70184-237">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="70184-237">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
