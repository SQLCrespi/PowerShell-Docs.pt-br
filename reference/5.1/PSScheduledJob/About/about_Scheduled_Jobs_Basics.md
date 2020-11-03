---
description: Explica como criar e gerenciar trabalhos agendados.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195816"
---
# <a name="about-scheduled-jobs-basics"></a><span data-ttu-id="ee1bc-104">Sobre noções básicas de trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="ee1bc-104">About Scheduled Jobs Basics</span></span>

## <a name="short-description"></a><span data-ttu-id="ee1bc-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="ee1bc-105">Short description</span></span>

<span data-ttu-id="ee1bc-106">Explica como criar e gerenciar trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-106">Explains how to create and manage scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="ee1bc-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="ee1bc-107">Long description</span></span>

<span data-ttu-id="ee1bc-108">Este documento mostra como executar tarefas básicas de criação e gerenciamento de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-108">This document shows how to perform basic tasks of creating and managing scheduled jobs.</span></span> <span data-ttu-id="ee1bc-109">Para obter informações sobre tarefas mais avançadas, consulte [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-109">For information about more advanced tasks, see [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span></span>

<span data-ttu-id="ee1bc-110">Para obter mais informações sobre os cmdlets contidos no módulo **PSScheduledJob** , consulte [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="how-to-create-a-scheduled-job"></a><span data-ttu-id="ee1bc-111">Como criar um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="ee1bc-111">How to create a scheduled job</span></span>

<span data-ttu-id="ee1bc-112">Para criar um trabalho agendado, use o `Register-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-112">To create a scheduled job, use the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="ee1bc-113">O cmdlet requer um nome e os comandos ou o script que o trabalho executa.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-113">The cmdlet requires a name and the commands or script that the job runs.</span></span> <span data-ttu-id="ee1bc-114">Você pode executar o trabalho imediatamente adicionando o parâmetro **RunNow** ou criar um gatilho de trabalho e definir opções de trabalho ao criar o trabalho ou editar um trabalho existente.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-114">You can either run the job immediately by adding the **RunNow** parameter, or create a job trigger and set job options when you create the job, or edit an existing job.</span></span>

<span data-ttu-id="ee1bc-115">Para criar um trabalho que executa um script, use o parâmetro **FilePath** para especificar o caminho para o arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-115">To create a job that runs a script, use the **FilePath** parameter to specify the path to the script file.</span></span> <span data-ttu-id="ee1bc-116">Para criar um trabalho que executa comandos, use o parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-116">To create a job that runs commands, use the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="ee1bc-117">O `Register-ScheduledJob` cmdlet cria o **ProcessJob** , que executa um `Get-Process` comando.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-117">The `Register-ScheduledJob` cmdlet creates the **ProcessJob** , which runs a `Get-Process` command.</span></span> <span data-ttu-id="ee1bc-118">Este trabalho agendado tem as opções de trabalho padrão e nenhum gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-118">This scheduled job has the default job options and no job trigger.</span></span>

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a><span data-ttu-id="ee1bc-119">Como criar um gatilho de trabalho</span><span class="sxs-lookup"><span data-stu-id="ee1bc-119">How to create a job trigger</span></span>

<span data-ttu-id="ee1bc-120">Os gatilhos de trabalho iniciam automaticamente um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-120">Job triggers start a scheduled job automatically.</span></span> <span data-ttu-id="ee1bc-121">Um gatilho de trabalho pode ser agendamento único ou recorrente ou um evento, como quando um usuário faz logon ou o Windows é iniciado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-121">A job trigger can be one-time or recurring schedule or an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="ee1bc-122">Cada trabalho pode ter zero, um ou vários gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-122">Each job can have zero, one, or multiple job triggers.</span></span>

<span data-ttu-id="ee1bc-123">Para criar um gatilho de trabalho, use o `New-JobTrigger` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-123">To create a job trigger, use the `New-JobTrigger` cmdlet.</span></span> <span data-ttu-id="ee1bc-124">O comando a seguir cria um gatilho de trabalho que inicia um trabalho todas as segundas e quintas-feiras às 5:00.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-124">The following command creates a job trigger that starts a job every Monday and Thursday at 5:00 AM.</span></span>
<span data-ttu-id="ee1bc-125">O comando salva o gatilho de trabalho na `$T` variável.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-125">The command saves the job trigger in the `$T` variable.</span></span>

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

<span data-ttu-id="ee1bc-126">Disparadores de trabalho são opcionais.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-126">Job triggers are optional.</span></span> <span data-ttu-id="ee1bc-127">Você pode iniciar um trabalho agendado a qualquer momento adicionando o parâmetro **RunNow** ao `Register-ScheduledJob` comando ou usando os `Start-Job` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-127">You can start a scheduled job at any time by adding the **RunNow** parameter to your `Register-ScheduledJob` command, or by using the `Start-Job` cmdlets.</span></span>

## <a name="how-to-add-a-job-trigger"></a><span data-ttu-id="ee1bc-128">Como adicionar um gatilho de trabalho</span><span class="sxs-lookup"><span data-stu-id="ee1bc-128">How to add a job trigger</span></span>

<span data-ttu-id="ee1bc-129">Quando você adiciona um gatilho de trabalho a um trabalho agendado, o gatilho de trabalho é adicionado ao arquivo XML de trabalho agendado para o trabalho agendado e torna-se parte do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-129">When you add a job trigger to a scheduled job, the job trigger is added to the scheduled job XML file for the scheduled job and becomes part of the scheduled job.</span></span>

<span data-ttu-id="ee1bc-130">Você pode adicionar um gatilho de trabalho a um trabalho agendado ao criar o trabalho agendado ou editar um trabalho existente.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-130">You can add a job trigger to a scheduled job when you create the scheduled job, or edit an existing job.</span></span> <span data-ttu-id="ee1bc-131">Você pode alterar o gatilho de trabalho de um trabalho agendado a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-131">You can change the job trigger of a scheduled job at any time.</span></span>

<span data-ttu-id="ee1bc-132">O PowerShell usa alguns dos mesmos gatilhos de trabalho que Agendador de Tarefas usa.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-132">PowerShell uses some of the same job triggers that Task Scheduler uses.</span></span> <span data-ttu-id="ee1bc-133">Para obter informações detalhadas sobre gatilhos de trabalho, consulte o tópico de ajuda para o cmdlet [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-133">For detailed information about job triggers, see the help topic for the [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) cmdlet.</span></span>

<span data-ttu-id="ee1bc-134">O exemplo a seguir usa nivelamento para criar `$JobParms` que são valores de parâmetro que são passados para o `Register-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-134">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="ee1bc-135">Para obter mais informações, consulte [about_Splatting. MD](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-135">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="ee1bc-136">O `Register-ScheduledJob` usa `@JobParms` para criar um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-136">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="ee1bc-137">Ele usa o parâmetro **Trigger** para especificar o gatilho do trabalho na `$T` variável.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-137">It uses the **Trigger** parameter to specify the job trigger in the `$T` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="ee1bc-138">Você também pode adicionar um gatilho de trabalho a um trabalho agendado existente a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-138">You can also add a job trigger to an existing scheduled job at any time.</span></span> <span data-ttu-id="ee1bc-139">O `Add-JobTrigger` cmdlet adiciona o gatilho de trabalho na `$T` variável ao trabalho agendado **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-139">The `Add-JobTrigger` cmdlet adds the job trigger in the `$T` variable to the **ProcessJob** scheduled job.</span></span>

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

<span data-ttu-id="ee1bc-140">Como resultado, o gatilho de trabalho inicia o **ProcessJob** automaticamente todas as segundas e quintas-feiras às 5:00.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-140">As a result, the job trigger starts the **ProcessJob** automatically every Monday and Thursday at 5:00 AM.</span></span>

## <a name="how-to-get-a-job-trigger"></a><span data-ttu-id="ee1bc-141">Como obter um gatilho de trabalho</span><span class="sxs-lookup"><span data-stu-id="ee1bc-141">How to get a job trigger</span></span>

<span data-ttu-id="ee1bc-142">Para obter o gatilho de trabalho de um trabalho agendado, use o `Get-JobTrigger` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-142">To get the job trigger of a scheduled job, use the `Get-JobTrigger` cmdlet.</span></span> <span data-ttu-id="ee1bc-143">Use os parâmetros **Name** , **ID** e **InputObject** para especificar o trabalho agendado, não o gatilho do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-143">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job trigger.</span></span>

<span data-ttu-id="ee1bc-144">`Get-JobTrigger` Obtém o gatilho de trabalho do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-144">`Get-JobTrigger` gets the job trigger of the **ProcessJob** .</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a><span data-ttu-id="ee1bc-145">Como criar opções de trabalho</span><span class="sxs-lookup"><span data-stu-id="ee1bc-145">How to create job options</span></span>

<span data-ttu-id="ee1bc-146">As opções de trabalho estabelecem condições para iniciar e executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-146">Job options establish conditions for starting and running the job.</span></span> <span data-ttu-id="ee1bc-147">Cada trabalho tem as opções de trabalho padrão, a menos que você as altere.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-147">Every job has the default job options unless you change them.</span></span> <span data-ttu-id="ee1bc-148">Como as opções de trabalho podem impedir que um trabalho seja executado no horário agendado, é importante entender as opções de trabalho e usá-las com cuidado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-148">Because job options can prevent a job from running at the scheduled time, it is important to understand the job options and use them carefully.</span></span>

<span data-ttu-id="ee1bc-149">O PowerShell usa as mesmas opções de trabalho que o Agendador de Tarefas usa.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-149">PowerShell uses the same job options that Task Scheduler uses.</span></span> <span data-ttu-id="ee1bc-150">Para obter informações detalhadas sobre as opções de trabalho, consulte o tópico da ajuda para [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-150">For detailed information about the job options, see the help topic for [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

<span data-ttu-id="ee1bc-151">As opções de trabalho são armazenadas no arquivo XML de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-151">Job options are stored in the scheduled job XML file.</span></span> <span data-ttu-id="ee1bc-152">Você pode definir opções de trabalho ao criar um trabalho agendado ou alterá-los a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-152">You can set job options when you create a scheduled job or change them at any time.</span></span>

<span data-ttu-id="ee1bc-153">O `New-ScheduledJobOption` cmdlet cria uma opção de trabalho agendado na qual a opção de trabalho agendado **WakeToRun** é definida como true.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-153">The `New-ScheduledJobOption` cmdlet creates a scheduled job option in which the **WakeToRun** scheduled job option is set to True.</span></span> <span data-ttu-id="ee1bc-154">A opção **WakeToRun** executa o trabalho agendado mesmo que o computador esteja no estado de suspensão ou hibernação na hora de início agendada.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-154">The **WakeToRun** option runs the scheduled job even if the computer is in the Sleep or Hibernate state at the scheduled start time.</span></span> <span data-ttu-id="ee1bc-155">O comando salva as opções de trabalho na `$O` variável.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-155">The command saves the job options in the `$O` variable.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a><span data-ttu-id="ee1bc-156">Como obter opções de trabalho</span><span class="sxs-lookup"><span data-stu-id="ee1bc-156">How to get job options</span></span>

<span data-ttu-id="ee1bc-157">Para obter as opções de trabalho de um trabalho agendado, use o `Get-ScheduledJobOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-157">To get the job options of a scheduled job, use the `Get-ScheduledJobOption` cmdlet.</span></span> <span data-ttu-id="ee1bc-158">Use os parâmetros **Name** , **ID** e **InputObject** para especificar o trabalho agendado, não as opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-158">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job options.</span></span>

<span data-ttu-id="ee1bc-159">`Get-ScheduledJobOption` Obtém as opções de trabalho do **ProcessJob** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-159">`Get-ScheduledJobOption` gets the job options of the **ProcessJob** .</span></span>

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
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

## <a name="how-to-change-job-options"></a><span data-ttu-id="ee1bc-160">Como alterar as opções de trabalho</span><span class="sxs-lookup"><span data-stu-id="ee1bc-160">How to change job options</span></span>

<span data-ttu-id="ee1bc-161">Você pode alterar as opções de trabalho de um trabalho agendado ao criar um trabalho agendado ou editar um trabalho existente.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-161">You can change the job options of a scheduled job when you create a scheduled job or edit an existing job.</span></span>

<span data-ttu-id="ee1bc-162">Os splatted `$JobParms` são passados para o `Add-JobTrigger` cmdlet para criar o trabalho de processo.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-162">The splatted `$JobParms` are passed to the `Add-JobTrigger` cmdlet to create the process job.</span></span> <span data-ttu-id="ee1bc-163">Ele usa o parâmetro **ScheduledJobOption** para especificar as opções de trabalho na `$O` variável.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-163">It uses the **ScheduledJobOption** parameter to specify the job options in the `$O` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

<span data-ttu-id="ee1bc-164">Você também pode alterar as opções de trabalho para um trabalho agendado existente a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-164">You can also change the job options to an existing scheduled job at any time.</span></span>
<span data-ttu-id="ee1bc-165">O comando a seguir usa o `Set-ScheduledJobOption` cmdlet para alterar o valor da opção **WakeToRun** de **ProcessJob** scheduledJob para **true** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-165">The following command uses the `Set-ScheduledJobOption` cmdlet to change the value of the **WakeToRun** option of the **ProcessJob** scheduledJob to **True** .</span></span>

<span data-ttu-id="ee1bc-166">Os `Set` cmdlets no módulo **PSScheduledJob** , como o `Set-ScheduledJobOption` cmdlet, não têm parâmetros **Name** ou **ID** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-166">The `Set` cmdlets in the **PSScheduledJob** module, such as the `Set-ScheduledJobOption` cmdlet, don't have **Name** or **ID** parameters.</span></span> <span data-ttu-id="ee1bc-167">Você pode usar o parâmetro **InputObject** para especificar as opções de trabalho agendado ou canalizar um trabalho agendado de um `Get-ScheduledJobOption` cmdlet para `Set-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-167">You can use the **InputObject** parameter to specify the scheduled job options or pipe a scheduled job from `Get-ScheduledJobOption` cmdlet to `Set-ScheduledJobOption`.</span></span>

<span data-ttu-id="ee1bc-168">Este exemplo usa o `Get-ScheduledJob` cmdlet para obter o ProcessJob.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-168">This example uses the `Get-ScheduledJob` cmdlet to get the ProcessJob.</span></span> <span data-ttu-id="ee1bc-169">Ele usa o `Get-ScheduledJobOption` cmdlet para obter as opções de trabalho no **ProcessJob** e o `Set-ScheduledJobOption` cmdlet para alterar a opção de trabalho **WakeToRun** no ProcessJob para true.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-169">It uses the `Get-ScheduledJobOption` cmdlet to get the job options in the **ProcessJob** and the `Set-ScheduledJobOption` cmdlet to change the **WakeToRun** job option in the ProcessJob to True.</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a><span data-ttu-id="ee1bc-170">Como obter instâncias de trabalho agendadas</span><span class="sxs-lookup"><span data-stu-id="ee1bc-170">How to get scheduled job instances</span></span>

<span data-ttu-id="ee1bc-171">Quando um trabalho agendado é iniciado, o PowerShell cria uma instância de trabalho semelhante a um trabalho em segundo plano padrão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-171">When a scheduled job is started, PowerShell creates a job instance that is similar to a standard PowerShell background job.</span></span> <span data-ttu-id="ee1bc-172">Você pode usar os cmdlets de trabalho, como `Get-Job` `Stop-Job` e `Receive-Job` para gerenciar as instâncias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-172">You can use the job cmdlets, such as `Get-Job`, `Stop-Job` and `Receive-Job` to manage the job instances.</span></span>

> [!NOTE]
> <span data-ttu-id="ee1bc-173">Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-173">To use the job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="ee1bc-174">Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-174">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="ee1bc-175">Para obter todas as instâncias de trabalhos agendados do PowerShell e todos os trabalhos padrão ativos, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-175">To get all instances of PowerShell scheduled jobs, and all active standard jobs, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="ee1bc-176">O `Import-Module` cmdlet importa o módulo **PSScheduledJob** e `Get-Job` Obtém os trabalhos no computador local.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-176">The `Import-Module` cmdlet imports the **PSScheduledJob** module and `Get-Job` gets the jobs on the local computer.</span></span>

```powershell
Import-Module PSScheduledJob
Get-Job
```

<span data-ttu-id="ee1bc-177">`Get-Job` Obtém as instâncias de **ProcessJob** no computador local.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-177">`Get-Job` gets instances of **ProcessJob** on the local computer.</span></span>

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

<span data-ttu-id="ee1bc-178">A exibição padrão não mostra a hora de início, que normalmente distingue instâncias do mesmo trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-178">The default display does not show the start time, which typically distinguishes instances of the same scheduled job.</span></span>

<span data-ttu-id="ee1bc-179">O `Get-Job` cmdlet envia objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-179">The `Get-Job` cmdlet sends objects down the pipeline.</span></span> <span data-ttu-id="ee1bc-180">O `Format-Table` cmdlet exibe as propriedades **Name** , **ID** e **BeginTime** do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-180">The `Format-Table` cmdlet displays the **Name** , **ID** , and **BeginTime** properties of the scheduled job.</span></span>

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
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

## <a name="get-scheduled-job-results"></a><span data-ttu-id="ee1bc-181">Obter resultados do trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="ee1bc-181">Get scheduled job results</span></span>

<span data-ttu-id="ee1bc-182">Para obter os resultados de uma instância de um trabalho agendado, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-182">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ee1bc-183">Para usar os cmdlets de trabalho em instâncias de trabalhos agendados, o módulo **PSScheduledJob** deve ser importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-183">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="ee1bc-184">Para importar o módulo **PSScheduledJob** , digite `Import-Module PSScheduledJob` ou use qualquer cmdlet de trabalho agendado, como `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-184">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="ee1bc-185">Este exemplo obtém os resultados da instância mais recente do trabalho agendado **ProcessJob** (ID = 51).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-185">This examples gets the results of the newest instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

<span data-ttu-id="ee1bc-186">Os resultados de trabalhos agendados são salvos em disco, portanto, o parâmetro **Keep** de `Receive-Job` não é necessário.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-186">The results of scheduled jobs are saved on disk, so the **Keep** parameter of `Receive-Job` is not required.</span></span> <span data-ttu-id="ee1bc-187">No entanto, sem o parâmetro **Keep** , você pode obter os resultados de um trabalho agendado apenas uma vez em cada sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-187">However, without the **Keep** parameter, you can get the results of a scheduled job only once in each PowerShell session.</span></span> <span data-ttu-id="ee1bc-188">Para iniciar uma nova sessão do PowerShell, digite `PowerShell` ou abra uma nova janela do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-188">To start a new PowerShell session, type `PowerShell` or open a new PowerShell window.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee1bc-189">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee1bc-189">See also</span></span>

[<span data-ttu-id="ee1bc-190">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="ee1bc-190">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="ee1bc-191">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="ee1bc-191">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="ee1bc-192">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="ee1bc-192">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="ee1bc-193">about_Splatting. MD</span><span class="sxs-lookup"><span data-stu-id="ee1bc-193">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="ee1bc-194">Cmdlets do módulo [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="ee1bc-194">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="ee1bc-195">Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="ee1bc-195">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
