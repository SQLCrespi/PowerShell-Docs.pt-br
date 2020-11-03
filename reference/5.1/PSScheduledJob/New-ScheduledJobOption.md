---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193671"
---
# <span data-ttu-id="0f2ab-103">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f2ab-103">New-ScheduledJobOption</span></span>

## <span data-ttu-id="0f2ab-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0f2ab-104">SYNOPSIS</span></span>
<span data-ttu-id="0f2ab-105">Cria um objeto que contém as opções avançadas para um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-105">Creates an object that contains advanced options for a scheduled job.</span></span>

## <span data-ttu-id="0f2ab-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f2ab-106">SYNTAX</span></span>

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="0f2ab-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f2ab-107">DESCRIPTION</span></span>
<span data-ttu-id="0f2ab-108">O cmdlet **New-ScheduledJobOption** cria um objeto que contém as opções avançadas para um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-108">The **New-ScheduledJobOption** cmdlet creates an object that contains advanced options for a scheduled job.</span></span>

<span data-ttu-id="0f2ab-109">Você pode usar o objeto **ScheduledJobOptions** que retorna **New-ScheduledJobOption** para definir opções de trabalho para um trabalho agendado novo ou existente.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-109">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set job options for a new or existing scheduled job.</span></span>
<span data-ttu-id="0f2ab-110">Como alternativa, você pode definir as opções de trabalho usando o cmdlet Get-ScheduledJobOption para obter as opções de trabalho de um trabalho agendado existente ou usando um valor de tabela de hash para representar as opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-110">Alternatively, you can set job options by using the Get-ScheduledJobOption cmdlet to get the job options of an existing scheduled job or by using a hash table value to represent the job options.</span></span>

<span data-ttu-id="0f2ab-111">Sem parâmetros, **New-ScheduledJobOption** gera um objeto que contém os valores padrão para todas as opções.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-111">Without parameters, **New-ScheduledJobOption** generates an object that contains the default values for all of the options.</span></span>
<span data-ttu-id="0f2ab-112">Como todas as propriedades, exceto a propriedade JobDefinition, podem ser editadas, é possível usar o objeto resultante como um modelo e criar objetos de opção padrão para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-112">Because all of the properties except for the JobDefinition property can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="0f2ab-113">Ao criar trabalhos agendados e definir opções de trabalho agendado, examine os valores padrões de todas as opções de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-113">When creating scheduled jobs and setting scheduled job options, review the default values of all scheduled job options.</span></span>
<span data-ttu-id="0f2ab-114">Executar somente quando todas as condições definidas para a execução de trabalhos agendados forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-114">Scheduled jobs run only when all conditions set for their execution are satisfied.</span></span>

<span data-ttu-id="0f2ab-115">**New-ScheduledJobOption** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-115">**New-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="0f2ab-116">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-116">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="0f2ab-117">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-117">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="0f2ab-118">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0f2ab-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0f2ab-119">EXAMPLES</span></span>

### <span data-ttu-id="0f2ab-120">Exemplo 1: criar um objeto de opção de trabalho agendado com valores padrão</span><span class="sxs-lookup"><span data-stu-id="0f2ab-120">Example 1: Create a scheduled job option object with default values</span></span>

```
PS C:\> New-ScheduledJobOption
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
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="0f2ab-121">Este comando cria um objeto de opção de trabalho agendado que tem todos os valores padrões.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-121">This command creates a scheduled job option object that has all of the default values.</span></span>

### <span data-ttu-id="0f2ab-122">Exemplo 2: criar um objeto de opção de trabalho agendado com valores personalizados</span><span class="sxs-lookup"><span data-stu-id="0f2ab-122">Example 2: Create a scheduled job option object with custom values</span></span>

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
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
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="0f2ab-123">O comando a seguir cria um objeto de trabalho agendado que requer a rede e executa o trabalho agendado, mesmo que o computador não esteja conectado à corrente alternada.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-123">The following command creates a scheduled job object that requires the network and runs the scheduled job even if the computer is not connected to AC power.</span></span>

<span data-ttu-id="0f2ab-124">A saída mostra que o parâmetro *RequireNetwork* alterou o valor da propriedade RunWithoutNetwork para $false e o parâmetro *StartIfOnBattery* alterou o valor da propriedade StartIfOnBatteries para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-124">The output shows that the *RequireNetwork* parameter changed the value of the RunWithoutNetwork property to $False and the *StartIfOnBattery* parameter changed the value of the StartIfOnBatteries property to $True.</span></span>

### <span data-ttu-id="0f2ab-125">Exemplo 3: definir opções para um novo trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="0f2ab-125">Example 3: Set options for a new scheduled job</span></span>

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : True
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="0f2ab-126">Este exemplo mostra como usar o objeto **ScheduledJobOptions** que retorna **New-ScheduledJobOption** para definir as opções para um novo trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-126">This example shows how to use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set the options for a new scheduled job.</span></span>

### <span data-ttu-id="0f2ab-127">Exemplo 4: classificar as propriedades de um objeto de opção de trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="0f2ab-127">Example 4: Sort the properties of a scheduled job option object</span></span>

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

<span data-ttu-id="0f2ab-128">Este exemplo mostra como classificar as propriedades de um objeto **ScheduledJobOptions** em ordem alfabética para facilitar a leitura.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-128">This example shows how to sort the properties of a **ScheduledJobOptions** object in alphabetical order for easy reading.</span></span>

<span data-ttu-id="0f2ab-129">O primeiro comando usa o cmdlet **New-ScheduledJobOption** para criar um objeto **ScheduledJobOptions** .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-129">The first command uses the **New-ScheduledJobOption** cmdlet to create a **ScheduledJobOptions** object.</span></span>
<span data-ttu-id="0f2ab-130">O comando usa o parâmetro *WakeToRun* e salva o objeto resultante na variável $Options.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-130">The command uses the *WakeToRun* parameter and saves the resulting object in the $Options variable.</span></span>

<span data-ttu-id="0f2ab-131">Para obter as propriedades de $Options como objetos, o segundo comando usa a propriedade **PSObject** de todos os objetos do Windows PowerShell e sua propriedade Properties.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-131">To get the properties of $Options as objects, the second command uses the **PSObject** property of all Windows PowerShell objects and its Properties property.</span></span>
<span data-ttu-id="0f2ab-132">Em seguida, o comando canaliza os objetos de propriedade para o cmdlet Sort-Object, que classifica as propriedades em ordem alfabética por nome e, em seguida, para o cmdlet Format-Table, que exibe os nomes e valores das propriedades em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-132">The command then pipes the property objects to the Sort-Object cmdlet, which sorts the properties in alphabetical order by name, and then to the Format-Table cmdlet, which displays the names and values of the properties in a table.</span></span>

<span data-ttu-id="0f2ab-133">Esse formato torna muito mais fácil localizar a propriedade WakeToRun do objeto **ScheduledJobOptions** no $Options e verificar se seu valor foi alterado de $False para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-133">This format makes it much easier to find the WakeToRun property of the **ScheduledJobOptions** object in $Options and to verify that its value was changed from $False to $True.</span></span>

## <span data-ttu-id="0f2ab-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f2ab-134">PARAMETERS</span></span>

### <span data-ttu-id="0f2ab-135">-ContinueIfGoingOnBattery</span><span class="sxs-lookup"><span data-stu-id="0f2ab-135">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="0f2ab-136">Não interrompa a tarefa se o computador alternar para a energia da bateria (desconectado da corrente alternada) enquanto o trabalho estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-136">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="0f2ab-137">Por padrão, os trabalhos agendados param quando o computador é desconectado da corrente alternada.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-137">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="0f2ab-138">O parâmetro *ContinueIfGoingOnBattery* define o valor da propriedade StopIfGoingOnBatteries de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-138">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="0f2ab-139">-DoNotAllowDemandStart</span><span class="sxs-lookup"><span data-stu-id="0f2ab-139">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="0f2ab-140">Inicie o trabalho somente quando ele é acionado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-140">Start the job only when it is triggered.</span></span>
<span data-ttu-id="0f2ab-141">Os usuários não podem iniciar o trabalho manualmente, como usando a execução de recursos no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-141">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="0f2ab-142">Este parâmetro afeta somente o Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-142">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="0f2ab-143">Ele não impede que os usuários usem o cmdlet Start-Job para iniciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-143">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="0f2ab-144">O parâmetro *DoNotAllowDemandStart* define o valor da propriedade DoNotAllowDemandStart de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-144">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="0f2ab-145">-HideInTaskScheduler</span><span class="sxs-lookup"><span data-stu-id="0f2ab-145">-HideInTaskScheduler</span></span>
<span data-ttu-id="0f2ab-146">Não exiba o trabalho no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-146">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="0f2ab-147">Esse valor afeta somente o computador no qual o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-147">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="0f2ab-148">Por padrão, as tarefas agendadas são exibidas no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-148">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="0f2ab-149">Mesmo que uma tarefa esteja oculta, os usuários podem exibir a tarefa selecionando a opção Mostrar tarefas ocultas modo de exibição no Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-149">Even if a task is hidden, users can display the task by selecting the Show hidden tasks view option in Task Scheduler.</span></span>

<span data-ttu-id="0f2ab-150">O parâmetro *HideInTaskScheduler* define o valor da propriedade ShowInTaskScheduler de trabalhos agendados para $false.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-150">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="0f2ab-151">-IdleDuration</span><span class="sxs-lookup"><span data-stu-id="0f2ab-151">-IdleDuration</span></span>
<span data-ttu-id="0f2ab-152">Especifica quanto tempo o computador deve permanecer ocioso antes de iniciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-152">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="0f2ab-153">O valor padrão é 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-153">The default value is 10 minutes.</span></span>
<span data-ttu-id="0f2ab-154">Se o computador não estiver ocioso durante o tempo especificado antes do valor de *IdleTimeout* expirar, o trabalho agendado não será executado até que a próxima execução agendada, se houver.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-154">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="0f2ab-155">Insira um objeto **TimeSpan** , como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-155">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format  that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="0f2ab-156">Para habilitar esse valor, use o parâmetro *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-156">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="0f2ab-157">Por padrão, a propriedade StartIfNotIdle dos trabalhos agendados é definida como $True e o Windows PowerShell ignora os valores *IdleDuration* e *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-157">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="0f2ab-158">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="0f2ab-158">-IdleTimeout</span></span>
<span data-ttu-id="0f2ab-159">Especifica quanto tempo a tarefa aguarda o computador ficar ocioso.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-159">Specifies how long the scheduled job waits for the computer to be idle.</span></span>
<span data-ttu-id="0f2ab-160">Se esse tempo limite expirar antes que o computador permaneça ocioso durante um período de tempo especificado pelo parâmetro *IdleDuration* , o trabalho não será executado até a próxima execução agendada, se houver alguma.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-160">If this timeout expires before the computer remains idle for the time period that is specified by the *IdleDuration* parameter, the job does not run until the next scheduled time, if any.</span></span>
<span data-ttu-id="0f2ab-161">O valor padrão é uma hora.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-161">The default value is one hour.</span></span>

<span data-ttu-id="0f2ab-162">Insira um objeto **TimeSpan** , como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-162">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="0f2ab-163">Para habilitar esse valor, use o parâmetro *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-163">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="0f2ab-164">Por padrão, a propriedade StartIfNotIdle dos trabalhos agendados é definida como $True e o Windows PowerShell ignora os valores *IdleDuration* e *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-164">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="0f2ab-165">-MultipleInstancePolicy</span><span class="sxs-lookup"><span data-stu-id="0f2ab-165">-MultipleInstancePolicy</span></span>
<span data-ttu-id="0f2ab-166">Determina como o sistema responde a uma solicitação para iniciar uma instância de um trabalho agendado, enquanto outra instância de trabalho está em execução.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-166">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="0f2ab-167">O valor padrão é IgnoreNew.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-167">The default value is IgnoreNew.</span></span>
<span data-ttu-id="0f2ab-168">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="0f2ab-168">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0f2ab-169">IgnoreNew.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-169">IgnoreNew.</span></span>
<span data-ttu-id="0f2ab-170">A nova instância de trabalho será ignorada.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-170">The new job instance is ignored.</span></span>
- <span data-ttu-id="0f2ab-171">Paralelo.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-171">Parallel.</span></span>
<span data-ttu-id="0f2ab-172">A nova instância de trabalho será iniciada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-172">The new job instance starts immediately.</span></span>
- <span data-ttu-id="0f2ab-173">Fila.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-173">Queue.</span></span>
<span data-ttu-id="0f2ab-174">A nova instância de trabalho começa assim que a instância atual for concluída.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-174">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="0f2ab-175">StopExisting.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-175">StopExisting.</span></span>
<span data-ttu-id="0f2ab-176">A instância atual do trabalho é interrompida e a nova instância é iniciada.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-176">The current instance of the job stops and the new instance starts.</span></span>

<span data-ttu-id="0f2ab-177">Para executar o trabalho, todas as condições da agenda de trabalho devem ser atendidas.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-177">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="0f2ab-178">Por exemplo, se as condições definidas pelos parâmetros *RequireNetwork* , *IdleDuration* e *IdleTimeout* não forem satisfeitas, a instância de trabalho não será iniciada, independentemente do valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-178">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

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

### <span data-ttu-id="0f2ab-179">-RequireNetwork</span><span class="sxs-lookup"><span data-stu-id="0f2ab-179">-RequireNetwork</span></span>
<span data-ttu-id="0f2ab-180">Executa a tarefa agendada somente quando conexões de rede estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-180">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="0f2ab-181">Se você especificar esse parâmetro e a rede não estiver disponível na hora de início agendada, o trabalho não será executado até a próxima hora de início agendada, se houver alguma.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-181">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="0f2ab-182">O parâmetro *RequireNetwork* define o valor da propriedade RunWithoutNetwork de trabalhos agendados para $false.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-182">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="0f2ab-183">-RestartOnIdleResume</span><span class="sxs-lookup"><span data-stu-id="0f2ab-183">-RestartOnIdleResume</span></span>
<span data-ttu-id="0f2ab-184">Reinicia um trabalho agendado quando o computador ficar ocioso.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-184">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="0f2ab-185">Esse parâmetro funciona com o parâmetro *StopIfGoingOffIdle* , que suspende um trabalho agendado em execução se o computador se torna ativo (deixe o estado ocioso).</span><span class="sxs-lookup"><span data-stu-id="0f2ab-185">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="0f2ab-186">O parâmetro *RestartOnIdleResume* define o valor da propriedade RestartOnIdleResume de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-186">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="0f2ab-187">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="0f2ab-187">-RunElevated</span></span>
<span data-ttu-id="0f2ab-188">Executa o trabalho agendado com as permissões de um membro do grupo Administradores no computador no qual o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-188">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="0f2ab-189">Para permitir que um trabalho agendado seja executado com permissões de administrador, use o parâmetro *Credential* de Register-ScheduledJob para fornecer credenciais explícitas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-189">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="0f2ab-190">O parâmetro *RunElevated* define o valor da propriedade RunElevated de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-190">The *RunElevated* parameter sets the value of the RunElevated property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="0f2ab-191">-StartIfIdle</span><span class="sxs-lookup"><span data-stu-id="0f2ab-191">-StartIfIdle</span></span>
<span data-ttu-id="0f2ab-192">Inicia o trabalho agendado, se o computador estiver ocioso durante o tempo especificado pelo parâmetro *IdleDuration* antes da hora especificada pelo parâmetro *IdleTimeout* expirar.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-192">Starts the scheduled job if the computer has been idle for the time specified by the *IdleDuration* parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="0f2ab-193">Por padrão, os parâmetros *IdleDuration* e *IdleTimeout* serão ignorados e o trabalho será iniciado na hora de início agendada, mesmo se o computador estiver ocupado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-193">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="0f2ab-194">Se você especificar esse parâmetro e o computador estiver ocupado (não ocioso) na hora de início agendada, o trabalho não será executado até a próxima hora de início agendada se houver.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-194">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="0f2ab-195">O parâmetro *StartIfIdle* define o valor da propriedade StartIfNotIdle de trabalhos agendados para $false.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-195">The *StartIfIdle* parameter sets the value of the StartIfNotIdle property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="0f2ab-196">-StartIfOnBattery</span><span class="sxs-lookup"><span data-stu-id="0f2ab-196">-StartIfOnBattery</span></span>
<span data-ttu-id="0f2ab-197">Inicia o trabalho agendado, mesmo se o computador estiver usando baterias na hora de início agendada.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-197">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="0f2ab-198">O valor padrão é $False.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-198">The default value is $False.</span></span>

<span data-ttu-id="0f2ab-199">O parâmetro *StartIfOnBattery* define o valor da propriedade StartIfOnBatteries de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-199">The *StartIfOnBattery* parameter sets the value of the StartIfOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="0f2ab-200">-StopIfGoingOffIdle</span><span class="sxs-lookup"><span data-stu-id="0f2ab-200">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="0f2ab-201">Suspende um trabalho agendado em execução se o computador se torna ativo (não ocioso) enquanto o trabalho está em execução.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-201">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="0f2ab-202">Por padrão, um trabalho agendado é suspenso quando o computador se torna ativo e retomado quando o computador tornar-se ocioso novamente.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-202">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="0f2ab-203">Para alterar esse comportamento padrão, utilize o parâmetro *RestartOnIdleResume* .</span><span class="sxs-lookup"><span data-stu-id="0f2ab-203">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="0f2ab-204">O parâmetro *StopIfGoingOffIdle* define o valor da propriedade StopIfGoingOffIdle de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-204">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="0f2ab-205">-WakeToRun</span><span class="sxs-lookup"><span data-stu-id="0f2ab-205">-WakeToRun</span></span>
<span data-ttu-id="0f2ab-206">Desperta o computador de um estado de suspensão ou de hibernação na hora de início agendada para que possa executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-206">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="0f2ab-207">Por padrão, se o computador está em um estado de suspensão ou de hibernação na hora de início agendada, o trabalho não será executado.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-207">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="0f2ab-208">O parâmetro *WakeToRun* define o valor da propriedade WakeToRun de trabalhos agendados para $true.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-208">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="0f2ab-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f2ab-209">CommonParameters</span></span>
<span data-ttu-id="0f2ab-210">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f2ab-211">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0f2ab-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f2ab-212">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0f2ab-212">INPUTS</span></span>

### <span data-ttu-id="0f2ab-213">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0f2ab-213">None</span></span>
<span data-ttu-id="0f2ab-214">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0f2ab-215">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0f2ab-215">OUTPUTS</span></span>

### <span data-ttu-id="0f2ab-216">Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="0f2ab-216">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="0f2ab-217">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0f2ab-217">NOTES</span></span>

* <span data-ttu-id="0f2ab-218">Você pode usar o objeto **ScheduledJobOptions** que **New-ScheduledJobOption** cria como o valor do parâmetro *ScheduledJobOption* do cmdlet Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-218">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** creates as the value of the *ScheduledJobOption* parameter of the Register-ScheduledJob cmdlet.</span></span> <span data-ttu-id="0f2ab-219">No entanto, o parâmetro *ScheduledJobOption* também pode pegar um valor de tabela de hash que especifica as propriedades do objeto **ScheduledJobOptions** e seus valores, como:</span><span class="sxs-lookup"><span data-stu-id="0f2ab-219">However, the *ScheduledJobOption* parameter can also take a hash table value that specifies the properties of the **ScheduledJobOptions** object and their values, such as:</span></span>

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

## <span data-ttu-id="0f2ab-220">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0f2ab-220">RELATED LINKS</span></span>

[<span data-ttu-id="0f2ab-221">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f2ab-221">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="0f2ab-222">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f2ab-222">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="0f2ab-223">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f2ab-223">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="0f2ab-224">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f2ab-224">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="0f2ab-225">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f2ab-225">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="0f2ab-226">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f2ab-226">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="0f2ab-227">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f2ab-227">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="0f2ab-228">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f2ab-228">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="0f2ab-229">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f2ab-229">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="0f2ab-230">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f2ab-230">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="0f2ab-231">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f2ab-231">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="0f2ab-232">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f2ab-232">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="0f2ab-233">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0f2ab-233">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="0f2ab-234">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f2ab-234">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="0f2ab-235">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0f2ab-235">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="0f2ab-236">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0f2ab-236">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
