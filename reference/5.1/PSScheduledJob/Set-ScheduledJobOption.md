---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193660"
---
# <span data-ttu-id="6134a-103">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="6134a-103">Set-ScheduledJobOption</span></span>

## <span data-ttu-id="6134a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6134a-104">SYNOPSIS</span></span>
<span data-ttu-id="6134a-105">Altera as opções de trabalho de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="6134a-105">Changes the job options of a scheduled job.</span></span>

## <span data-ttu-id="6134a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6134a-106">SYNTAX</span></span>

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="6134a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6134a-107">DESCRIPTION</span></span>
<span data-ttu-id="6134a-108">O cmdlet **Set-ScheduledJobOptions** altera as opções de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="6134a-108">The **Set-ScheduledJobOptions** cmdlet changes the job options of scheduled jobs.</span></span>

<span data-ttu-id="6134a-109">Para alterar as opções de um trabalho agendado, comece usando o cmdlet Get-ScheduledJobOption para obter as opções de trabalho de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="6134a-109">To change the options of a scheduled job, begin by using the Get-ScheduledJobOption cmdlet to get the job options of a scheduled job.</span></span>
<span data-ttu-id="6134a-110">Em seguida, canalize as opções para **Set-ScheduledJobOption** ou salve-o em uma variável e use o parâmetro *InputObject* do cmdlet **Set-ScheduledJobOption** para identificar as opções.</span><span class="sxs-lookup"><span data-stu-id="6134a-110">Then, pipe the options to **Set-ScheduledJobOption** or save the options in a variable and use the *InputObject* parameter of **Set-ScheduledJobOption** cmdlet to identify the options.</span></span>
<span data-ttu-id="6134a-111">Use os parâmetros restantes do **Set-ScheduledJobOption** para alterar as opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6134a-111">Use the remaining parameters of **Set-ScheduledJobOption** to change the job options.</span></span>

<span data-ttu-id="6134a-112">Para ativar uma opção de trabalho, use o parâmetro que define essa opção.</span><span class="sxs-lookup"><span data-stu-id="6134a-112">To turn on a job option, use the parameter that sets that option.</span></span>
<span data-ttu-id="6134a-113">Para desativar uma opção, digite o nome do parâmetro, dois-pontos (:) e $False.</span><span class="sxs-lookup"><span data-stu-id="6134a-113">To turn off an option, type the parameter name, a colon (:), and $False.</span></span>
<span data-ttu-id="6134a-114">Por exemplo, para desativar a opção *RunElevated* , digite `-RunElevated:$False` .</span><span class="sxs-lookup"><span data-stu-id="6134a-114">For example, to turn off the *RunElevated* option, type `-RunElevated:$False`.</span></span>

<span data-ttu-id="6134a-115">Cada objeto de opções de trabalho inclui uma propriedade JobDefinition que contém o trabalho agendado, portanto, a associação com o trabalho agendado é mantida quando as opções de trabalho são alteradas.</span><span class="sxs-lookup"><span data-stu-id="6134a-115">Each job options object includes a JobDefinition property that contains the scheduled job, so the association with the scheduled job is retained when the job options are changed.</span></span>

<span data-ttu-id="6134a-116">As opções de trabalho agendadas determinam como o trabalho é executado quando ele é iniciado pelo Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="6134a-116">The scheduled job options determine how the job runs when it is started by Task Scheduler.</span></span>
<span data-ttu-id="6134a-117">Essas opções não se aplicam quando você usa o cmdlet Start-Job para iniciar um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="6134a-117">These options to not apply when you use the Start-Job cmdlet to start a scheduled job.</span></span>

<span data-ttu-id="6134a-118">**Set-ScheduledJobOption** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6134a-118">**Set-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="6134a-119">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="6134a-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="6134a-120">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="6134a-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="6134a-121">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6134a-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="6134a-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6134a-122">EXAMPLES</span></span>

### <span data-ttu-id="6134a-123">Exemplo 1: alterar as opções de trabalho</span><span class="sxs-lookup"><span data-stu-id="6134a-123">Example 1: Change job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
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
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
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
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

<span data-ttu-id="6134a-124">Este exemplo mostra como alterar as opções de uma tarefa agendada no computador local.</span><span class="sxs-lookup"><span data-stu-id="6134a-124">This example shows how to change the options of a scheduled job on the local computer.</span></span>

<span data-ttu-id="6134a-125">O primeiro comando usa o cmdlet Get-ScheduledJobOption para obter as opções de trabalho do trabalho agendado DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="6134a-125">The first command uses the Get-ScheduledJobOption cmdlet to get the job options of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="6134a-126">A saída mostra que as propriedades WakeToRun e RunElevated são definidas como $False.</span><span class="sxs-lookup"><span data-stu-id="6134a-126">The output shows that the WakeToRun and RunElevated properties are set to $False.</span></span>

<span data-ttu-id="6134a-127">Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração da opção.</span><span class="sxs-lookup"><span data-stu-id="6134a-127">This command is not required; it is included only to show the effect of the option change.</span></span>

### <span data-ttu-id="6134a-128">Exemplo 2: alterar uma opção em todos os trabalhos agendados remotamente</span><span class="sxs-lookup"><span data-stu-id="6134a-128">Example 2: Change an option on all remote scheduled jobs</span></span>

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

<span data-ttu-id="6134a-129">Esse comando altera o valor de *IdleTimeout* de uma hora (o valor padrão) para duas horas em todos os trabalhos agendados no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="6134a-129">This command changes the value of the *IdleTimeout* from one hour (the default value) to two hours on all scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="6134a-130">O comando usa o cmdlet Invoke-Command para executar um comando no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="6134a-130">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="6134a-131">O comando remoto começa com um comando Get-ScheduledJob que obtém todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="6134a-131">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="6134a-132">Os trabalhos agendados são canalizados para o cmdlet Get-ScheduledJobOption, que obtém as opções de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="6134a-132">The scheduled jobs are piped to the Get-ScheduledJobOption cmdlet, which gets the job options of the scheduled jobs.</span></span>
<span data-ttu-id="6134a-133">Cada objeto de opções de trabalho contém uma propriedade JobDefinition que contém o trabalho agendado, por isso o objeto de opções permaneça associado ao trabalho agendado, mesmo quando alterado.</span><span class="sxs-lookup"><span data-stu-id="6134a-133">Each job options object contains a JobDefinition property that contains the scheduled job, so the options object remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="6134a-134">Os gatilhos de trabalho são canalizados para o cmdlet **set-ScheduledJobOption** , que altera o valor da opção *IdleTimeout* para duas horas (2:00:00).</span><span class="sxs-lookup"><span data-stu-id="6134a-134">The job triggers are piped to the **Set-ScheduledJobOption** cmdlet, which changes the value of the *IdleTimeout* option to two hours (2:00:00).</span></span>

## <span data-ttu-id="6134a-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6134a-135">PARAMETERS</span></span>

### <span data-ttu-id="6134a-136">-ContinueIfGoingOnBattery</span><span class="sxs-lookup"><span data-stu-id="6134a-136">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="6134a-137">Não interrompa a tarefa se o computador alternar para a energia da bateria (desconectado da corrente alternada) enquanto o trabalho estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="6134a-137">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="6134a-138">Por padrão, os trabalhos agendados param quando o computador é desconectado da corrente alternada.</span><span class="sxs-lookup"><span data-stu-id="6134a-138">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="6134a-139">O parâmetro *ContinueIfGoingOnBattery* define o valor da propriedade StopIfGoingOnBatteries de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="6134a-139">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-140">-DoNotAllowDemandStart</span><span class="sxs-lookup"><span data-stu-id="6134a-140">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="6134a-141">Inicie o trabalho somente quando ele é acionado.</span><span class="sxs-lookup"><span data-stu-id="6134a-141">Start the job only when it is triggered.</span></span>
<span data-ttu-id="6134a-142">Os usuários não podem iniciar o trabalho manualmente, como usando a execução de recursos no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="6134a-142">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="6134a-143">Este parâmetro afeta somente o Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="6134a-143">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="6134a-144">Ele não impede que os usuários usem o cmdlet Start-Job para iniciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6134a-144">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="6134a-145">O parâmetro *DoNotAllowDemandStart* define o valor da propriedade DoNotAllowDemandStart de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="6134a-145">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-146">-HideInTaskScheduler</span><span class="sxs-lookup"><span data-stu-id="6134a-146">-HideInTaskScheduler</span></span>
<span data-ttu-id="6134a-147">Não exiba o trabalho no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="6134a-147">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="6134a-148">Esse valor afeta somente o computador no qual o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="6134a-148">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="6134a-149">Por padrão, as tarefas agendadas são exibidas no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="6134a-149">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="6134a-150">Mesmo que uma tarefa esteja oculta, os usuários podem exibir a tarefa selecionando a opção **Mostrar tarefas ocultas** modo de exibição no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="6134a-150">Even if a task is hidden, users can display the task by selecting the **Show hidden tasks** view option in Task Scheduler.</span></span>

<span data-ttu-id="6134a-151">O parâmetro *HideInTaskScheduler* define o valor da propriedade ShowInTaskScheduler de trabalhos agendados para $false.</span><span class="sxs-lookup"><span data-stu-id="6134a-151">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-152">-IdleDuration</span><span class="sxs-lookup"><span data-stu-id="6134a-152">-IdleDuration</span></span>
<span data-ttu-id="6134a-153">Especifica quanto tempo o computador deve permanecer ocioso antes de iniciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6134a-153">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="6134a-154">O valor padrão é 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="6134a-154">The default value is 10 minutes.</span></span>
<span data-ttu-id="6134a-155">Se o computador não estiver ocioso durante o tempo especificado antes do valor de *IdleTimeout* expirar, o trabalho agendado não será executado até que a próxima execução agendada, se houver.</span><span class="sxs-lookup"><span data-stu-id="6134a-155">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="6134a-156">Insira um objeto TimeSpan, como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="6134a-156">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="6134a-157">Para habilitar esse valor, use o parâmetro *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="6134a-157">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="6134a-158">Por padrão, a propriedade StartIfNotIdle dos trabalhos agendados é definida como $True e o Windows PowerShell ignora os valores *IdleDuration* e *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="6134a-158">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-159">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="6134a-159">-IdleTimeout</span></span>
<span data-ttu-id="6134a-160">Especifica quanto tempo o computador deve permanecer ocioso antes de iniciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6134a-160">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="6134a-161">O valor padrão é 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="6134a-161">The default value is 10 minutes.</span></span>
<span data-ttu-id="6134a-162">Se o computador não estiver ocioso durante o tempo especificado antes do valor de **IdleTimeout** expirar, o trabalho agendado não será executado até que a próxima execução agendada, se houver.</span><span class="sxs-lookup"><span data-stu-id="6134a-162">If the computer is not idle for the specified duration before the value of **IdleTimeout** expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="6134a-163">Insira um objeto TimeSpan, como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="6134a-163">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="6134a-164">Para habilitar esse valor, use o parâmetro *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="6134a-164">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="6134a-165">Por padrão, a propriedade StartIfNotIdle dos trabalhos agendados é definida como $True e o Windows PowerShell ignora os valores *IdleDuration* e *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="6134a-165">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6134a-166">-InputObject</span></span>
<span data-ttu-id="6134a-167">Especifica as opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6134a-167">Specifies the job options.</span></span>
<span data-ttu-id="6134a-168">Insira uma variável que contenha objetos **ScheduledJobOptions** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobOptions** , como um comando Get-ScheduledJobOption.</span><span class="sxs-lookup"><span data-stu-id="6134a-168">Enter a variable that contains **ScheduledJobOptions** objects or type a command or expression that gets **ScheduledJobOptions** objects, such as a Get-ScheduledJobOption command.</span></span>
<span data-ttu-id="6134a-169">Você também pode canalizar um objeto **ScheduledJobOptions** para **set-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="6134a-169">You can also pipe a **ScheduledJobOptions** object to **Set-ScheduledJobOption** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-170">-MultipleInstancePolicy</span><span class="sxs-lookup"><span data-stu-id="6134a-170">-MultipleInstancePolicy</span></span>
<span data-ttu-id="6134a-171">Determina como o sistema responde a uma solicitação para iniciar uma instância de um trabalho agendado, enquanto outra instância de trabalho está em execução.</span><span class="sxs-lookup"><span data-stu-id="6134a-171">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="6134a-172">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="6134a-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6134a-173">IgnoreNew.</span><span class="sxs-lookup"><span data-stu-id="6134a-173">IgnoreNew.</span></span>
<span data-ttu-id="6134a-174">A nova instância de trabalho será ignorada.</span><span class="sxs-lookup"><span data-stu-id="6134a-174">The new job instance is ignored.</span></span>
<span data-ttu-id="6134a-175">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="6134a-175">This is the default value.</span></span>
- <span data-ttu-id="6134a-176">Paralelo.</span><span class="sxs-lookup"><span data-stu-id="6134a-176">Parallel.</span></span>
<span data-ttu-id="6134a-177">A nova instância de trabalho será iniciada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="6134a-177">The new job instance starts immediately.</span></span>
- <span data-ttu-id="6134a-178">Fila.</span><span class="sxs-lookup"><span data-stu-id="6134a-178">Queue.</span></span>
<span data-ttu-id="6134a-179">A nova instância de trabalho começa assim que a instância atual for concluída.</span><span class="sxs-lookup"><span data-stu-id="6134a-179">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="6134a-180">StopExisting.</span><span class="sxs-lookup"><span data-stu-id="6134a-180">StopExisting.</span></span>
<span data-ttu-id="6134a-181">A instância atual do trabalho parado e a nova instância foram iniciadas.</span><span class="sxs-lookup"><span data-stu-id="6134a-181">The current instance of the job stop and the new instance starts.</span></span>

<span data-ttu-id="6134a-182">Para executar o trabalho, todas as condições da agenda de trabalho devem ser atendidas.</span><span class="sxs-lookup"><span data-stu-id="6134a-182">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="6134a-183">Por exemplo, se as condições definidas pelos parâmetros *RequireNetwork* , *IdleDuration* e *IdleTimeout* não forem satisfeitas, a instância de trabalho não será iniciada, independentemente do valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6134a-183">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-184">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6134a-184">-PassThru</span></span>
<span data-ttu-id="6134a-185">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="6134a-185">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="6134a-186">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="6134a-186">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-187">-RequireNetwork</span><span class="sxs-lookup"><span data-stu-id="6134a-187">-RequireNetwork</span></span>
<span data-ttu-id="6134a-188">Executa a tarefa agendada somente quando conexões de rede estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6134a-188">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="6134a-189">Se você especificar esse parâmetro e a rede não estiver disponível na hora de início agendada, o trabalho não será executado até a próxima hora de início agendada, se houver alguma.</span><span class="sxs-lookup"><span data-stu-id="6134a-189">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="6134a-190">O parâmetro *RequireNetwork* define o valor da propriedade RunWithoutNetwork de trabalhos agendados para $false.</span><span class="sxs-lookup"><span data-stu-id="6134a-190">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-191">-RestartOnIdleResume</span><span class="sxs-lookup"><span data-stu-id="6134a-191">-RestartOnIdleResume</span></span>
<span data-ttu-id="6134a-192">Reinicia um trabalho agendado quando o computador ficar ocioso.</span><span class="sxs-lookup"><span data-stu-id="6134a-192">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="6134a-193">Esse parâmetro funciona com o parâmetro *StopIfGoingOffIdle* , que suspende um trabalho agendado em execução se o computador se torna ativo (deixe o estado ocioso).</span><span class="sxs-lookup"><span data-stu-id="6134a-193">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="6134a-194">O parâmetro *RestartOnIdleResume* define o valor da propriedade RestartOnIdleResume de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="6134a-194">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-195">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="6134a-195">-RunElevated</span></span>
<span data-ttu-id="6134a-196">Executa o trabalho agendado com as permissões de um membro do grupo Administradores no computador no qual o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="6134a-196">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="6134a-197">Para permitir que um trabalho agendado seja executado com permissões de administrador, use o parâmetro *Credential* de Register-ScheduledJob para fornecer credenciais explícitas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6134a-197">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="6134a-198">O parâmetro **RunElevated** define o valor da propriedade **RunElevated** de trabalhos agendados como true.</span><span class="sxs-lookup"><span data-stu-id="6134a-198">The **RunElevated** parameter sets the value of the **RunElevated** property of scheduled jobs to True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-199">-StartIfIdle</span><span class="sxs-lookup"><span data-stu-id="6134a-199">-StartIfIdle</span></span>
<span data-ttu-id="6134a-200">Inicia o trabalho agendado, se o computador estiver ocioso durante o tempo especificado pelo parâmetro **IdleDuration** antes da hora especificada pelo parâmetro *IdleTimeout* expirar.</span><span class="sxs-lookup"><span data-stu-id="6134a-200">Starts the scheduled job if the computer has been idle for the time specified by the **IdleDuration** parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="6134a-201">Por padrão, os parâmetros *IdleDuration* e *IdleTimeout* serão ignorados e o trabalho será iniciado na hora de início agendada, mesmo se o computador estiver ocupado.</span><span class="sxs-lookup"><span data-stu-id="6134a-201">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="6134a-202">Se você especificar esse parâmetro e o computador estiver ocupado (não ocioso) na hora de início agendada, o trabalho não será executado até a próxima hora de início agendada se houver.</span><span class="sxs-lookup"><span data-stu-id="6134a-202">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="6134a-203">O parâmetro *StartIfIdle* define o valor da propriedade **StartIfNotIdle** de trabalhos agendados como false.</span><span class="sxs-lookup"><span data-stu-id="6134a-203">The *StartIfIdle* parameter sets the value of the **StartIfNotIdle** property of scheduled jobs to False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-204">-StartIfOnBattery</span><span class="sxs-lookup"><span data-stu-id="6134a-204">-StartIfOnBattery</span></span>
<span data-ttu-id="6134a-205">Inicia o trabalho agendado, mesmo se o computador estiver usando baterias na hora de início agendada.</span><span class="sxs-lookup"><span data-stu-id="6134a-205">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="6134a-206">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="6134a-206">The default value is False.</span></span>

<span data-ttu-id="6134a-207">O parâmetro *StartIfOnBattery* define o valor da propriedade **StartIfOnBatteries** de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="6134a-207">The *StartIfOnBattery* parameter sets the value of the **StartIfOnBatteries** property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-208">-StopIfGoingOffIdle</span><span class="sxs-lookup"><span data-stu-id="6134a-208">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="6134a-209">Suspende um trabalho agendado em execução se o computador se torna ativo (não ocioso) enquanto o trabalho está em execução.</span><span class="sxs-lookup"><span data-stu-id="6134a-209">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="6134a-210">Por padrão, um trabalho agendado é suspenso quando o computador se torna ativo e retomado quando o computador tornar-se ocioso novamente.</span><span class="sxs-lookup"><span data-stu-id="6134a-210">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="6134a-211">Para alterar esse comportamento padrão, utilize o parâmetro *RestartOnIdleResume* .</span><span class="sxs-lookup"><span data-stu-id="6134a-211">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="6134a-212">O parâmetro *StopIfGoingOffIdle* define o valor da propriedade StopIfGoingOffIdle de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="6134a-212">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-213">-WakeToRun</span><span class="sxs-lookup"><span data-stu-id="6134a-213">-WakeToRun</span></span>
<span data-ttu-id="6134a-214">Desperta o computador de um estado de suspensão ou de hibernação na hora de início agendada para que possa executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6134a-214">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="6134a-215">Por padrão, se o computador está em um estado de suspensão ou de hibernação na hora de início agendada, o trabalho não será executado.</span><span class="sxs-lookup"><span data-stu-id="6134a-215">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="6134a-216">O parâmetro *WakeToRun* define o valor da propriedade WakeToRun de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="6134a-216">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6134a-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6134a-217">CommonParameters</span></span>
<span data-ttu-id="6134a-218">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6134a-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6134a-219">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6134a-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6134a-220">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6134a-220">INPUTS</span></span>

### <span data-ttu-id="6134a-221">Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="6134a-221">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="6134a-222">Você pode direcionar um objeto de opções de trabalho agendadas para **Set-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="6134a-222">You can pipe a scheduled job options object to **Set-ScheduledJobOption** .</span></span>

## <span data-ttu-id="6134a-223">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6134a-223">OUTPUTS</span></span>

### <span data-ttu-id="6134a-224">Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="6134a-224">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="6134a-225">Ao usar o parâmetro *Passthru* , o **Set-ScheduledJobOption** retorna as opções de trabalho que foram alteradas.</span><span class="sxs-lookup"><span data-stu-id="6134a-225">When you use the *Passthru* parameter, **Set-ScheduledJobOption** returns the job options that were changed.</span></span>
<span data-ttu-id="6134a-226">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="6134a-226">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6134a-227">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6134a-227">NOTES</span></span>

## <span data-ttu-id="6134a-228">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6134a-228">RELATED LINKS</span></span>

[<span data-ttu-id="6134a-229">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6134a-229">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="6134a-230">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6134a-230">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="6134a-231">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6134a-231">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="6134a-232">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6134a-232">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="6134a-233">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6134a-233">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="6134a-234">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6134a-234">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="6134a-235">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6134a-235">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="6134a-236">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="6134a-236">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="6134a-237">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6134a-237">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="6134a-238">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="6134a-238">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="6134a-239">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6134a-239">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="6134a-240">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6134a-240">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="6134a-241">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="6134a-241">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="6134a-242">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6134a-242">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="6134a-243">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="6134a-243">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="6134a-244">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="6134a-244">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
