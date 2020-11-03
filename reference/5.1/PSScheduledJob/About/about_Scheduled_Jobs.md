---
description: Descreve os trabalhos agendados e explica como usar e gerenciar trabalhos agendados no PowerShell e no Agendador de Tarefas.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195819"
---
# <a name="about-scheduled-jobs"></a><span data-ttu-id="dc846-104">Sobre os trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="dc846-104">About Scheduled Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="dc846-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="dc846-105">Short description</span></span>

<span data-ttu-id="dc846-106">Descreve os trabalhos agendados e explica como usar e gerenciar trabalhos agendados no PowerShell e no Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="dc846-106">Describes scheduled jobs and explains how to use and manage scheduled jobs in PowerShell and in Task Scheduler.</span></span>

## <a name="long-description"></a><span data-ttu-id="dc846-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="dc846-107">Long description</span></span>

<span data-ttu-id="dc846-108">Os trabalhos agendados do PowerShell são um híbrido útil de trabalhos em segundo plano do PowerShell e tarefas de Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="dc846-108">PowerShell scheduled jobs are a useful hybrid of PowerShell background jobs and Task Scheduler tasks.</span></span>

<span data-ttu-id="dc846-109">Como trabalhos em segundo plano do PowerShell, os trabalhos agendados são executados de forma assíncrona em segundo plano</span><span class="sxs-lookup"><span data-stu-id="dc846-109">Like PowerShell background jobs, scheduled jobs run asynchronously in the background.</span></span> <span data-ttu-id="dc846-110">As instâncias de trabalhos agendados que têm execução podem ser gerenciadas usando os cmdlets de trabalho, como `Start-Job` ,, `Get-Job` `Stop-Job` e `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="dc846-110">Instances of scheduled jobs that have run can be managed by using the job cmdlets, such as `Start-Job`, `Get-Job`, `Stop-Job`, and `Receive-Job`.</span></span>

<span data-ttu-id="dc846-111">Assim como Agendador de Tarefas tarefas, os trabalhos agendados são salvos em disco.</span><span class="sxs-lookup"><span data-stu-id="dc846-111">Like Task Scheduler tasks, scheduled jobs are saved to disk.</span></span> <span data-ttu-id="dc846-112">Você pode exibir e gerenciar os trabalhos no Agendador de Tarefas, habilitá-los e desabilitá-los conforme necessário, executá-los ou usá-los como modelos, estabelecer agendamentos de uso único ou recorrente para iniciar os trabalhos ou definir condições sob as quais os trabalhos são iniciados.</span><span class="sxs-lookup"><span data-stu-id="dc846-112">You can view and manage the jobs in Task Scheduler, enable and disable them as needed, run them or use them as templates, establish a one-time or recurring schedules for starting the jobs, or set conditions under which the jobs start.</span></span>

<span data-ttu-id="dc846-113">Além disso, os resultados das instâncias de trabalho agendadas são salvos em disco em um formato facilmente acessível, fornecendo um log de saída de trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="dc846-113">In addition, the results of scheduled job instances are saved to disk in an easily accessible format, providing a running log of job output.</span></span> <span data-ttu-id="dc846-114">Os trabalhos agendados são fornecidos com um conjunto personalizado de cmdlets para gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="dc846-114">Scheduled jobs come with a customized set of cmdlets for managing them.</span></span> <span data-ttu-id="dc846-115">Os cmdlets permitem que você crie, edite, gerencie, desabilite e habilite novamente os trabalhos agendados, gatilhos de trabalho e opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc846-115">The cmdlets let you create, edit, manage, disable, and re-enable scheduled jobs, job triggers and job options.</span></span>

<span data-ttu-id="dc846-116">Esse conjunto abrangente e flexível de ferramentas torna os trabalhos agendados um componente essencial de muitas soluções profissionais de ti do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc846-116">This comprehensive and flexible set of tools make scheduled jobs an essential component of many professional PowerShell IT solutions.</span></span>

<span data-ttu-id="dc846-117">Os cmdlets de trabalho agendados são incluídos no módulo **PSScheduledJob** que é instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc846-117">The scheduled job cmdlets are included in the **PSScheduledJob** module that is installed with PowerShell.</span></span> <span data-ttu-id="dc846-118">Esse módulo foi introduzido no PowerShell 3,0 e funciona no PowerShell 3,0 e em versões posteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc846-118">This module was introduced in PowerShell 3.0 and works in PowerShell 3.0 and later versions of PowerShell.</span></span> <span data-ttu-id="dc846-119">Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="dc846-119">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

<span data-ttu-id="dc846-120">Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="dc846-120">For more information about PowerShell background jobs, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

<span data-ttu-id="dc846-121">Para obter mais informações sobre Agendador de Tarefas, consulte [Agendador de tarefas](/windows/desktop/TaskSchd/task-scheduler-reference).</span><span class="sxs-lookup"><span data-stu-id="dc846-121">For more information about Task Scheduler, see [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-reference).</span></span>

> [!NOTE]
> <span data-ttu-id="dc846-122">Você pode exibir e gerenciar trabalhos agendados do PowerShell no Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="dc846-122">You can view and manage PowerShell scheduled jobs in Task Scheduler.</span></span> <span data-ttu-id="dc846-123">Os cmdlets do PowerShell e trabalhos agendados funcionam apenas em trabalhos agendados que são criados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc846-123">The PowerShell jobs and scheduled job cmdlets work only on scheduled jobs that are created in PowerShell.</span></span>

## <a name="quick-start"></a><span data-ttu-id="dc846-124">Início rápido</span><span class="sxs-lookup"><span data-stu-id="dc846-124">Quick start</span></span>

<span data-ttu-id="dc846-125">Este exemplo cria um trabalho agendado que é iniciado todos os dias às 3:00 e executa o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dc846-125">This example creates a scheduled job that starts every day at 3:00 AM and runs the `Get-Process` cmdlet.</span></span> <span data-ttu-id="dc846-126">O trabalho é iniciado mesmo que o computador esteja sendo executado em baterias.</span><span class="sxs-lookup"><span data-stu-id="dc846-126">The job starts even if the computer is running on batteries.</span></span>

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

<span data-ttu-id="dc846-127">O `Get-ScheduledJob` cmdlet obtém os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="dc846-127">The `Get-ScheduledJob` cmdlet gets the scheduled jobs on the local computer.</span></span>

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

<span data-ttu-id="dc846-128">`Get-JobTrigger` Obtém os gatilhos de trabalho de **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="dc846-128">`Get-JobTrigger` gets the job triggers of **ProcessJob** .</span></span> <span data-ttu-id="dc846-129">Os parâmetros de entrada especificam o trabalho agendado, não o gatilho, porque os gatilhos são salvos em um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="dc846-129">The input parameters specify the scheduled job, not the trigger, because triggers are saved in a scheduled job.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

<span data-ttu-id="dc846-130">Este exemplo usa o parâmetro **ContinueIfGoingOnBattery** do `Set-ScheduledJob` cmdlet para alterar a propriedade **StopIfGoingOnBatteries** de **ProcessJob** para **false** .</span><span class="sxs-lookup"><span data-stu-id="dc846-130">This example uses the **ContinueIfGoingOnBattery** parameter of the `Set-ScheduledJob` cmdlet to change the **StopIfGoingOnBatteries** property of **ProcessJob** to **False** .</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
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

<span data-ttu-id="dc846-131">O `Get-ScheduledJob` cmdlet obtém o trabalho agendado do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="dc846-131">The `Get-ScheduledJob` cmdlet gets the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

<span data-ttu-id="dc846-132">O `Get-Job` cmdlet obtém todas as instâncias do trabalho agendado **ProcessJob** que foram executados até o momento.</span><span class="sxs-lookup"><span data-stu-id="dc846-132">The `Get-Job` cmdlet gets all instances of the **ProcessJob** scheduled job that have run thus far.</span></span> <span data-ttu-id="dc846-133">O `Get-Job` cmdlet obtém trabalhos agendados somente quando o módulo **PSScheduledJob** é importado para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="dc846-133">The `Get-Job` cmdlet gets scheduled jobs only when the **PSScheduledJob** module is imported into the current session.</span></span>

> [!TIP]
> <span data-ttu-id="dc846-134">Observe que você usa os cmdlets de trabalho agendado para gerenciar trabalhos agendados, mas usa os cmdlets de trabalho para gerenciar instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="dc846-134">Notice that you use the scheduled job cmdlets to manage scheduled jobs, but you use the job cmdlets to manage instances of scheduled jobs.</span></span>

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

<span data-ttu-id="dc846-135">O `Receive-Job` cmdlet obtém os resultados da instância mais recente do trabalho agendado **PROCESSJOB** (ID = 51).</span><span class="sxs-lookup"><span data-stu-id="dc846-135">The `Receive-Job` cmdlet gets the results of the most recent instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Receive-Job -ID 51
```

<span data-ttu-id="dc846-136">Embora o `Receive-Job` comando não tenha incluído o parâmetro **Keep** , os resultados do trabalho são salvos no disco até que você os exclua ou o número máximo de resultados seja excedido.</span><span class="sxs-lookup"><span data-stu-id="dc846-136">Even though the `Receive-Job` command did not include the **Keep** parameter, the results of the job are saved on disk until you delete them or the maximum number of results are exceeded.</span></span>

<span data-ttu-id="dc846-137">Os resultados do trabalho não estão mais disponíveis nesta sessão, mas se você iniciar uma nova sessão ou abrir uma nova janela do PowerShell, os resultados do trabalho estarão disponíveis novamente.</span><span class="sxs-lookup"><span data-stu-id="dc846-137">The job results are no longer available in this session, but if you start a new session or open a new PowerShell window, the results of the job are available again.</span></span>

<span data-ttu-id="dc846-138">O comando a seguir usa o parâmetro **definitionname** do `Start-Job` cmdlet para iniciar o trabalho agendado do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="dc846-138">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the **ProcessJob** scheduled job.</span></span>

<span data-ttu-id="dc846-139">Os trabalhos que são iniciados usando o `Start-Job` cmdlet são trabalhos em segundo plano padrão do PowerShell, não instâncias do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="dc846-139">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="dc846-140">Como todos os trabalhos em segundo plano, esses trabalhos são iniciados imediatamente, eles não estão sujeitos a opções de trabalho ou afetados por gatilhos de trabalho, e sua saída não é salva no diretório de saída do diretório de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="dc846-140">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers, and their output is not saved in the output directory of the scheduled job directory.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="dc846-141">O `Unregister-ScheduledJob` cmdlet exclui o trabalho agendado **ProcessJob** e todos os resultados salvos de suas instâncias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc846-141">The `Unregister-ScheduledJob` cmdlet deletes the **ProcessJob** scheduled job and all saved results of its job instances.</span></span>

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a><span data-ttu-id="dc846-142">Conceitos de trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="dc846-142">Scheduled jobs concepts</span></span>

<span data-ttu-id="dc846-143">Um trabalho agendado executa comandos ou um script.</span><span class="sxs-lookup"><span data-stu-id="dc846-143">A scheduled job runs commands or a script.</span></span> <span data-ttu-id="dc846-144">Um trabalho agendado pode incluir gatilhos de trabalho que iniciam as opções de trabalho e trabalho que definem condições para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc846-144">A scheduled job can include job triggers that start the job and job options that set conditions for running the job.</span></span>

<span data-ttu-id="dc846-145">Um gatilho de trabalho inicia automaticamente um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="dc846-145">A job trigger starts a scheduled job automatically.</span></span> <span data-ttu-id="dc846-146">Um gatilho de trabalho pode incluir uma agenda única ou recorrente ou especificar um evento, como quando um usuário faz logon ou o Windows é iniciado.</span><span class="sxs-lookup"><span data-stu-id="dc846-146">A job trigger can include a one-time or recurring schedule or specify an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="dc846-147">Um trabalho agendado pode ter um ou mais gatilhos de trabalho, e você pode criar, adicionar, habilitar, desabilitar e obter gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc846-147">A scheduled job can have one or more job triggers, and you can create, add, enable, disable, and get job triggers.</span></span>

<span data-ttu-id="dc846-148">Disparadores de trabalho são opcionais.</span><span class="sxs-lookup"><span data-stu-id="dc846-148">Job triggers are optional.</span></span> <span data-ttu-id="dc846-149">Você pode iniciar trabalhos agendados imediatamente usando o `Start-Job cmdlet` , ou adicionando o parâmetro **RunNow** ao `Register-ScheduledJob` comando.</span><span class="sxs-lookup"><span data-stu-id="dc846-149">You can start scheduled jobs immediately by using the `Start-Job cmdlet`, or by adding the **RunNow** parameter to your `Register-ScheduledJob` command.</span></span>

<span data-ttu-id="dc846-150">As opções de trabalho definem as condições para executar um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="dc846-150">Job options set the conditions for running a scheduled job.</span></span> <span data-ttu-id="dc846-151">Cada trabalho agendado tem um objeto de opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc846-151">Every scheduled job has one job options object.</span></span> <span data-ttu-id="dc846-152">Você pode criar e editar objetos de opções de trabalho e adicioná-los a um ou mais trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="dc846-152">You can create and edit job options objects and add them to one or more scheduled jobs.</span></span>

<span data-ttu-id="dc846-153">Cada vez que um trabalho agendado é iniciado, uma instância de trabalho é criada.</span><span class="sxs-lookup"><span data-stu-id="dc846-153">Each time a scheduled job starts, a job instance is created.</span></span> <span data-ttu-id="dc846-154">Use os cmdlets de trabalho do PowerShell para exibir e gerenciar a instância de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc846-154">Use the PowerShell job cmdlets to view and manage the job instance.</span></span>

<span data-ttu-id="dc846-155">Os trabalhos agendados são salvos em disco e usam o verbo do cmdlet, `Register` em vez de `New` .</span><span class="sxs-lookup"><span data-stu-id="dc846-155">Scheduled jobs are saved to disk and use the cmdlet verb, `Register`, instead of `New`.</span></span> <span data-ttu-id="dc846-156">Os arquivos XML estão localizados no computador local no diretório `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` .</span><span class="sxs-lookup"><span data-stu-id="dc846-156">The XML files are located on the local computer in the directory `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

<span data-ttu-id="dc846-157">O PowerShell cria um diretório para cada trabalho agendado e salva os comandos do trabalho, os gatilhos de trabalho, as opções de trabalho e os resultados do trabalho no diretório de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="dc846-157">PowerShell creates a directory for each scheduled job and saves the job commands, job triggers, job options and job results in the scheduled job directory.</span></span> <span data-ttu-id="dc846-158">Os gatilhos de trabalho e as opções de trabalho não são salvos em disco de forma independente.</span><span class="sxs-lookup"><span data-stu-id="dc846-158">Job triggers and job options aren't saved to disk independently.</span></span>
<span data-ttu-id="dc846-159">Eles são salvos no XML do trabalho agendado de cada trabalho agendado ao qual estão associados.</span><span class="sxs-lookup"><span data-stu-id="dc846-159">They are saved in the scheduled job XML of each scheduled job with which they are associated.</span></span>

<span data-ttu-id="dc846-160">Os trabalhos agendados, os gatilhos de trabalho e as opções de trabalho aparecem no PowerShell como objetos.</span><span class="sxs-lookup"><span data-stu-id="dc846-160">Scheduled jobs, job triggers, and job options appear in PowerShell as objects.</span></span>
<span data-ttu-id="dc846-161">Os objetos são interligados, o que os torna fácil de descobrir e usar em comandos e scripts.</span><span class="sxs-lookup"><span data-stu-id="dc846-161">The objects are interlinked, which makes them easy to discover and use in commands and scripts.</span></span>

<span data-ttu-id="dc846-162">Os trabalhos agendados aparecem como objetos **ScheduledJobDefinition** .</span><span class="sxs-lookup"><span data-stu-id="dc846-162">Scheduled jobs appear as **ScheduledJobDefinition** objects.</span></span> <span data-ttu-id="dc846-163">O objeto **ScheduledJobDefinition** tem uma propriedade **JobTriggers** que contém os gatilhos de trabalho do trabalho agendado e uma propriedade **Options** que contém as opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc846-163">The **ScheduledJobDefinition** object has a **JobTriggers** property that contains the job triggers of the scheduled job and an **Options** property that contains the job options.</span></span> <span data-ttu-id="dc846-164">Os objetos **ScheduledJobTriggers** e **ScheduledJobOptions** que representam gatilhos de trabalho e opções de trabalho, respectivamente, têm uma propriedade **JobDefinition** que contém o trabalho agendado ao qual estão associados.</span><span class="sxs-lookup"><span data-stu-id="dc846-164">The **ScheduledJobTriggers** and **ScheduledJobOptions** objects that represent job triggers and job options, respectively, each have a **JobDefinition** property that contains the scheduled job with which they are associated.</span></span> <span data-ttu-id="dc846-165">Essa interconexão recursiva facilita a localização dos gatilhos e das opções de um trabalho agendado, bem como a localização, o script e a exibição do trabalho agendado ao qual qualquer opção de trabalho ou gatilho de trabalho está associada.</span><span class="sxs-lookup"><span data-stu-id="dc846-165">This recursive interconnection makes it easy to find the triggers and options of a scheduled job and to find, script, and display the scheduled job to which any job trigger or job option is associated.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc846-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="dc846-166">See also</span></span>

[<span data-ttu-id="dc846-167">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="dc846-167">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="dc846-168">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="dc846-168">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="dc846-169">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="dc846-169">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

<span data-ttu-id="dc846-170">Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="dc846-170">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="dc846-171">Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="dc846-171">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
