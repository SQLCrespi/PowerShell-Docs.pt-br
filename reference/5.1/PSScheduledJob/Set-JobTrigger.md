---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193666"
---
# <span data-ttu-id="4526e-103">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-103">Set-JobTrigger</span></span>

## <span data-ttu-id="4526e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4526e-104">SYNOPSIS</span></span>
<span data-ttu-id="4526e-105">Altera o disparador do trabalho de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="4526e-105">Changes the job trigger of a scheduled job.</span></span>

## <span data-ttu-id="4526e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4526e-106">SYNTAX</span></span>

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="4526e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4526e-107">DESCRIPTION</span></span>
<span data-ttu-id="4526e-108">O cmdlet **Set-JobTrigger** altera as propriedades dos disparadores de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="4526e-108">The **Set-JobTrigger** cmdlet changes the properties of the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="4526e-109">Você pode usá-lo para alterar o tempo ou a frequência em que os trabalhos iniciam ou mudar de um agendamento com base no tempo para agendas que são disparadas por um logon ou na inicialização.</span><span class="sxs-lookup"><span data-stu-id="4526e-109">You can use it to change the time or frequency at which the jobs start or to change from a time-based schedules to schedules that are triggered by a logon or startup.</span></span>

<span data-ttu-id="4526e-110">Um gatilho de trabalho define uma agenda recorrente ou condições para iniciar um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="4526e-110">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="4526e-111">Embora disparadores de trabalho não sejam salvos em disco, você pode alterar os disparos de trabalho dos trabalhos agendados, que são salvos em disco.</span><span class="sxs-lookup"><span data-stu-id="4526e-111">Although job triggers are not saved to disk, you can change the job triggers of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="4526e-112">Para alterar um gatilho de trabalho de um trabalho agendado, comece usando o cmdlet Get-JobTrigger para obter o gatilho de trabalho de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="4526e-112">To change a job trigger of a scheduled job, begin by using the Get-JobTrigger cmdlet to get the job trigger of a scheduled job.</span></span>
<span data-ttu-id="4526e-113">Em seguida, canalize o disparador para **Set-JobTrigger** ou salve-o em uma variável e use o parâmetro *InputObject* do cmdlet **Set-JobTrigger** para identificar o disparador.</span><span class="sxs-lookup"><span data-stu-id="4526e-113">Then, pipe the trigger to **Set-JobTrigger** or save the trigger in a variable and use the *InputObject* parameter of **Set-JobTrigger** cmdlet to identify the trigger.</span></span>
<span data-ttu-id="4526e-114">Use os parâmetros restantes do **Set-JobTrigger** para alterar o disparador de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4526e-114">Use the remaining parameters of **Set-JobTrigger** to change the job trigger.</span></span>

<span data-ttu-id="4526e-115">Quando você altera o tipo de um gatilho de trabalho, como alterar um gatilho de trabalho de um gatilho diário ou semanal para um gatilho *AtLogon* , as propriedades originais do gatilho são excluídas.</span><span class="sxs-lookup"><span data-stu-id="4526e-115">When you change the type of a job trigger, such as changing a job trigger from a daily or weekly trigger to an *AtLogon* trigger, the original trigger properties are deleted.</span></span>
<span data-ttu-id="4526e-116">No entanto, se você alterar os valores do disparador, mas não seu tipo, como alterar os dias em um disparador semanal, somente as propriedades que você especificar serão alteradas.</span><span class="sxs-lookup"><span data-stu-id="4526e-116">However, if you change the values of the trigger, but not its type, such as changing the days in a weekly trigger, only the properties that you specify are changed.</span></span>
<span data-ttu-id="4526e-117">Todas as outras propriedades originais do disparador de trabalho são mantidas.</span><span class="sxs-lookup"><span data-stu-id="4526e-117">All other properties of the original job trigger are retained.</span></span>

<span data-ttu-id="4526e-118">**Set-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4526e-118">**Set-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="4526e-119">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="4526e-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="4526e-120">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*`  ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="4526e-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*`  or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="4526e-121">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="4526e-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="4526e-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4526e-122">EXAMPLES</span></span>

### <span data-ttu-id="4526e-123">Exemplo 1: alterar os dias em um gatilho de trabalho</span><span class="sxs-lookup"><span data-stu-id="4526e-123">Example 1: Change the days in a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

<span data-ttu-id="4526e-124">Este exemplo mostra como alterar os dias em um disparador de trabalho semanal.</span><span class="sxs-lookup"><span data-stu-id="4526e-124">This example shows how to change the days in a weekly job trigger.</span></span>

<span data-ttu-id="4526e-125">O primeiro comando usa o cmdlet Get-JobTrigger para obter o gatilho de trabalho do trabalho agendado DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="4526e-125">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="4526e-126">A saída mostra que o disparador inicia o trabalho à meia-noite nas quartas-feiras e sábados.</span><span class="sxs-lookup"><span data-stu-id="4526e-126">The output shows that the trigger starts the job at midnight on Wednesdays and Saturdays.</span></span>

<span data-ttu-id="4526e-127">Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração do disparador.</span><span class="sxs-lookup"><span data-stu-id="4526e-127">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="4526e-128">Exemplo 2: alterar o tipo de gatilho do trabalho</span><span class="sxs-lookup"><span data-stu-id="4526e-128">Example 2: Change the job trigger type</span></span>

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

<span data-ttu-id="4526e-129">Este exemplo mostra como alterar o tipo de disparador de trabalho que inicia um trabalho.</span><span class="sxs-lookup"><span data-stu-id="4526e-129">This example shows how to change the type of job trigger that starts a job.</span></span>
<span data-ttu-id="4526e-130">Os comandos neste exemplo substituem um disparador de trabalho AtStartup com um disparador semanal.</span><span class="sxs-lookup"><span data-stu-id="4526e-130">The commands in this example replace an AtStartup job trigger with a weekly trigger.</span></span>

<span data-ttu-id="4526e-131">O primeiro comando usa o cmdlet Get-JobTrigger para obter o gatilho de trabalho do trabalho agendado de inventário.</span><span class="sxs-lookup"><span data-stu-id="4526e-131">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the Inventory scheduled job.</span></span>
<span data-ttu-id="4526e-132">A saída mostra que o trabalho tem dois disparadores um gatilho diário e um gatilho *AtStartup* .</span><span class="sxs-lookup"><span data-stu-id="4526e-132">The output shows that the job has two triggers a daily trigger and an *AtStartup* trigger.</span></span>

<span data-ttu-id="4526e-133">Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração do disparador.</span><span class="sxs-lookup"><span data-stu-id="4526e-133">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="4526e-134">Exemplo 3: alterar o usuário em um gatilho de trabalho remoto</span><span class="sxs-lookup"><span data-stu-id="4526e-134">Example 3: Change the user on a remote job trigger</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

<span data-ttu-id="4526e-135">Esse comando altera o usuário em todos os gatilhos de trabalho do *AtLogon* dos trabalhos agendados no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="4526e-135">This command changes the user in all *AtLogon* job triggers of scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="4526e-136">O comando usa o cmdlet Invoke-Command para executar um comando no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="4526e-136">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="4526e-137">O comando remoto começa com um comando Get-ScheduledJob que obtém todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="4526e-137">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="4526e-138">Os trabalhos agendados são canalizados para o cmdlet Get-JobTrigger, que obtém os disparadores de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="4526e-138">The scheduled jobs are piped to the Get-JobTrigger cmdlet, which gets the job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="4526e-139">Cada disparador de trabalho contém uma propriedade JobDefinition que contém o trabalho agendado, por isso o disparador permanece associado ao trabalho agendado, mesmo quando alterado.</span><span class="sxs-lookup"><span data-stu-id="4526e-139">Each job trigger contains a JobDefinition property that contains the scheduled job, so the trigger remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="4526e-140">Os gatilhos de trabalho são canalizados para o cmdlet Where-Object, que obtém gatilhos de trabalho que têm a propriedade User.</span><span class="sxs-lookup"><span data-stu-id="4526e-140">The job triggers are piped to the Where-Object cmdlet, which gets job triggers that have the User property.</span></span>
<span data-ttu-id="4526e-141">Os disparadores de trabalho selecionados serão canalizados para o cmdlet **Set-JobTrigger** , que altera o usuário para Domain01\Admin02.</span><span class="sxs-lookup"><span data-stu-id="4526e-141">The selected job triggers are piped to the **Set-JobTrigger** cmdlet, which changes the user to Domain01\Admin02.</span></span>

### <span data-ttu-id="4526e-142">Exemplo 4: alterar um dos vários gatilhos de trabalho</span><span class="sxs-lookup"><span data-stu-id="4526e-142">Example 4: Change one of many job triggers</span></span>

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="4526e-143">Os comandos neste exemplo alteram o intervalo de repetição do disparador de trabalho *Once* do trabalho agendado SecurityCheck de cada 60 minutos para cada 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="4526e-143">The commands in this example changes the repetition interval of the *Once* job trigger of SecurityCheck scheduled job from every 60 minutes to every 90 minutes.</span></span>
<span data-ttu-id="4526e-144">O trabalho agendado SecurityCheck tem três gatilhos de trabalho, portanto, os comandos usam o parâmetro *triggerid* do cmdlet Get-JobTrigger para identificar o gatilho de trabalho que está sendo alterado.</span><span class="sxs-lookup"><span data-stu-id="4526e-144">The SecurityCheck scheduled job has three job triggers, so the commands use the *TriggerId* parameter of the Get-JobTrigger cmdlet to identify the job trigger that is being changed.</span></span>

<span data-ttu-id="4526e-145">O primeiro comando usa o cmdlet **Get-JobTrigger** para obter todos os disparadores de trabalho do trabalho agendado SecurityCheck.</span><span class="sxs-lookup"><span data-stu-id="4526e-145">The first command uses the **Get-JobTrigger** cmdlet to get all job triggers of the SecurityCheck scheduled job.</span></span>
<span data-ttu-id="4526e-146">O resultado, que exibe as IDs dos disparadores de trabalho, revela que o disparador de trabalho *Once* tem uma ID de 3.</span><span class="sxs-lookup"><span data-stu-id="4526e-146">The output, which displays the IDs of the job triggers, reveals that the *Once* job trigger has an ID of 3.</span></span>

## <span data-ttu-id="4526e-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4526e-147">PARAMETERS</span></span>

### <span data-ttu-id="4526e-148">-Em</span><span class="sxs-lookup"><span data-stu-id="4526e-148">-At</span></span>
<span data-ttu-id="4526e-149">Inicia o trabalho em determinada data e hora.</span><span class="sxs-lookup"><span data-stu-id="4526e-149">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="4526e-150">Insira um objeto **DateTime** , como um que o cmdlet Get-Date retorna, ou uma cadeia de caracteres que pode ser convertida em uma hora, como "19 de abril de 2012 15:00", "12/31/2013 9:00 PM" ou "3am".</span><span class="sxs-lookup"><span data-stu-id="4526e-150">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a time, such as "April 19, 2012 15:00", "12/31/2013 9:00 PM", or "3am".</span></span>

<span data-ttu-id="4526e-151">Se você não especificar um elemento do objeto **DateTime** , como segundos, esse elemento do gatilho do trabalho não será alterado.</span><span class="sxs-lookup"><span data-stu-id="4526e-151">If you don't specify an element of the **DateTime** object, such as seconds, that element of the job trigger is not changed.</span></span>
<span data-ttu-id="4526e-152">Se o gatilho do trabalho original não incluir um objeto **DateTime** e você omitir um elemento, o gatilho do trabalho será criado com o elemento correspondente da data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="4526e-152">If the original job trigger didn't include a **DateTime** object and you omit an element, the job trigger is created with the corresponding element from the current date and time.</span></span>

<span data-ttu-id="4526e-153">Ao usar o parâmetro *Once* , defina o valor do parâmetro *At* para uma determinada data e hora.</span><span class="sxs-lookup"><span data-stu-id="4526e-153">When using the *Once* parameter, set the value of the *At* parameter to a particular date and time.</span></span>
<span data-ttu-id="4526e-154">Como a data padrão em um objeto **DateTime** é a data atual, definir uma hora antes da hora atual sem uma data explícita resultará em um disparador de trabalho para uma hora no passado.</span><span class="sxs-lookup"><span data-stu-id="4526e-154">Because the default date in a **DateTime** object is the current date, setting a time before the current time without an explicit date results in a job trigger for a time in the past.</span></span>

<span data-ttu-id="4526e-155">Os objetos **DateTime** e as cadeias de caracteres que são convertidos em objetos **DateTime** são automaticamente ajustados para serem compatíveis com os formatos de data e hora selecionados para o computador local em região e idioma no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="4526e-155">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4526e-156">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="4526e-156">-AtLogOn</span></span>
<span data-ttu-id="4526e-157">Inicia o trabalho agendado quando os usuários especificados fazem logon no computador.</span><span class="sxs-lookup"><span data-stu-id="4526e-157">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="4526e-158">Para especificar um usuário, use o parâmetro *User* .</span><span class="sxs-lookup"><span data-stu-id="4526e-158">To specify a user, use the *User* parameter.</span></span>

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

### <span data-ttu-id="4526e-159">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="4526e-159">-AtStartup</span></span>
<span data-ttu-id="4526e-160">Inicia o trabalho agendado quando o Windows inicia.</span><span class="sxs-lookup"><span data-stu-id="4526e-160">Starts the scheduled job when Windows starts.</span></span>

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

### <span data-ttu-id="4526e-161">-Diário</span><span class="sxs-lookup"><span data-stu-id="4526e-161">-Daily</span></span>
<span data-ttu-id="4526e-162">Especifica uma agenda recorrente de trabalho diário.</span><span class="sxs-lookup"><span data-stu-id="4526e-162">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="4526e-163">Use os outros parâmetros no conjunto de parâmetros *diário* para especificar os detalhes da agenda.</span><span class="sxs-lookup"><span data-stu-id="4526e-163">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="4526e-164">-DaysInterval</span><span class="sxs-lookup"><span data-stu-id="4526e-164">-DaysInterval</span></span>
<span data-ttu-id="4526e-165">Especifica o número de dias entre ocorrências em uma agenda diária.</span><span class="sxs-lookup"><span data-stu-id="4526e-165">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="4526e-166">Por exemplo, um valor de 3 inicia o trabalho agendado nos dias 1, 4, 7 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4526e-166">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="4526e-167">O valor padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="4526e-167">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4526e-168">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="4526e-168">-DaysOfWeek</span></span>
<span data-ttu-id="4526e-169">Especifica os dias da semana em que um trabalho agendado semanalmente é executado.</span><span class="sxs-lookup"><span data-stu-id="4526e-169">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="4526e-170">Insira nomes de dias, como segunda-feira, quinta-feira, inteiros 0-6, em que 0 representa domingo ou um asterisco ( \* ) para representar todos os dias.</span><span class="sxs-lookup"><span data-stu-id="4526e-170">Enter day names, such as Monday, Thursday, integers 0-6, where 0 represents Sunday, or an asterisk (\*) to represent every day.</span></span>
<span data-ttu-id="4526e-171">Este parâmetro é necessário no conjunto de parâmetros Semanal.</span><span class="sxs-lookup"><span data-stu-id="4526e-171">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="4526e-172">Nomes de dias são convertidos em seus valores inteiros no gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4526e-172">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="4526e-173">Quando você coloca os nomes de dias entre aspas em um comando, coloque o nome de cada dia em aspas separadas, como "Segunda-feira", "Terça-feira".</span><span class="sxs-lookup"><span data-stu-id="4526e-173">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="4526e-174">Se você colocar vários nomes de dias em um par de aspas simples, os valores inteiros correspondentes são somados.</span><span class="sxs-lookup"><span data-stu-id="4526e-174">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="4526e-175">Por exemplo, "Segunda-feira, Terça-feira" (1, 2) resulta em um valor de "Quarta-feira" (3).</span><span class="sxs-lookup"><span data-stu-id="4526e-175">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4526e-176">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4526e-176">-InputObject</span></span>
<span data-ttu-id="4526e-177">Especifica os disparadores de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4526e-177">Specifies the job triggers.</span></span>
<span data-ttu-id="4526e-178">Insira uma variável que contenha objetos **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="4526e-178">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="4526e-179">Você também pode canalizar um objeto **ScheduledJobTrigger** para **set-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="4526e-179">You can also pipe a **ScheduledJobTrigger** object to **Set-JobTrigger** .</span></span>

<span data-ttu-id="4526e-180">Se você especificar vários disparadores de trabalho, o **Set-JobTrigger** realiza as mesmas alterações em todos os disparadores de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4526e-180">If you specify multiple job triggers, **Set-JobTrigger** makes the same changes to all job triggers.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4526e-181">-Uma vez</span><span class="sxs-lookup"><span data-stu-id="4526e-181">-Once</span></span>
<span data-ttu-id="4526e-182">Especifica uma agenda não recorrente (uma vez).</span><span class="sxs-lookup"><span data-stu-id="4526e-182">Specifies a non-recurring (one time) schedule.</span></span>

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

### <span data-ttu-id="4526e-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4526e-183">-PassThru</span></span>
<span data-ttu-id="4526e-184">Retorna os disparadores de trabalho que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="4526e-184">Returns the job triggers that changed.</span></span>
<span data-ttu-id="4526e-185">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="4526e-185">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="4526e-186">-RandomDelay</span><span class="sxs-lookup"><span data-stu-id="4526e-186">-RandomDelay</span></span>
<span data-ttu-id="4526e-187">Permite um atraso aleatório que começa na hora de início agendada e define o valor de tempo de espera máximo.</span><span class="sxs-lookup"><span data-stu-id="4526e-187">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="4526e-188">O tempo de atraso é definido pseudoaleatoriamente para cada início e varia de nenhum atraso até a hora especificada pelo valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4526e-188">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="4526e-189">O valor padrão, zero (00:00:00), desabilita o atraso aleatório.</span><span class="sxs-lookup"><span data-stu-id="4526e-189">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="4526e-190">Insira um objeto TimeSpan, como um retornado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format, que é automaticamente convertido em um objeto TimeSpan.</span><span class="sxs-lookup"><span data-stu-id="4526e-190">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a timespan object.</span></span>

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

### <span data-ttu-id="4526e-191">-RepeatIndefinitely</span><span class="sxs-lookup"><span data-stu-id="4526e-191">-RepeatIndefinitely</span></span>
<span data-ttu-id="4526e-192">Esse parâmetro, disponível a partir do Windows PowerShell 4.0, elimina a necessidade de especificar um valor **TimeSpan.MaxValue** para o parâmetro *RepetitionDuration* para executar um trabalho agendado repetidamente, por um período indefinido.</span><span class="sxs-lookup"><span data-stu-id="4526e-192">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

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

### <span data-ttu-id="4526e-193">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="4526e-193">-RepetitionDuration</span></span>
<span data-ttu-id="4526e-194">Repete o trabalho até o tempo especificado expirar.</span><span class="sxs-lookup"><span data-stu-id="4526e-194">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="4526e-195">A frequência de repetição é determinada pelo valor do parâmetro *RepetitionInterval* .</span><span class="sxs-lookup"><span data-stu-id="4526e-195">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="4526e-196">Por exemplo, se o valor de **RepetitionInterval** for 5 minutos e o valor de *RepetitionDuration* for de 2 horas, o trabalho será acionado a cada cinco minutos por duas horas.</span><span class="sxs-lookup"><span data-stu-id="4526e-196">For example, if the value of **RepetitionInterval** is 5 minutes and the value of *RepetitionDuration* is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="4526e-197">Insira um objeto TimeSpan, como um que o cmdlet New-TimeSpan retorna ou uma cadeia de caracteres que pode ser convertida em um objeto TimeSpan, como "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="4526e-197">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="4526e-198">Para executar um trabalho indefinidamente, adicione o parâmetro *RepeatIndefinitely* em vez disso.</span><span class="sxs-lookup"><span data-stu-id="4526e-198">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="4526e-199">Para interromper um trabalho antes que a duração de repetição do disparador trabalho expire, defina o valor **RepetitionDuration** para zero (0).</span><span class="sxs-lookup"><span data-stu-id="4526e-199">To stop a job before the job trigger repetition duration expires, set the **RepetitionDuration** value to zero (0).</span></span>

<span data-ttu-id="4526e-200">Para alterar a duração de repetição ou o intervalo de repetição de um disparador de trabalho *Once* , o comando deve incluir o parâmetro **RepetitionInterval** e **RepetitionDuration** .</span><span class="sxs-lookup"><span data-stu-id="4526e-200">To change the repetition duration or repetition interval of a *Once* job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="4526e-201">Para alterar a duração da repetição ou intervalos de repetição de outros tipos de disparadores de trabalho, o comando deve incluir os parâmetros *Once* , *At* , *RepetitionInterval* e *RepetitionDuration* .</span><span class="sxs-lookup"><span data-stu-id="4526e-201">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the *Once* , *At* , *RepetitionInterval* and *RepetitionDuration* parameters.</span></span>

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

### <span data-ttu-id="4526e-202">-RepetitionInterval</span><span class="sxs-lookup"><span data-stu-id="4526e-202">-RepetitionInterval</span></span>
<span data-ttu-id="4526e-203">Repete o trabalho no tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="4526e-203">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="4526e-204">Por exemplo, se o valor desse parâmetro é de 2 horas, o trabalho será acionado a cada duas horas.</span><span class="sxs-lookup"><span data-stu-id="4526e-204">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="4526e-205">O valor padrão, 0, não repete o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4526e-205">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="4526e-206">Insira um objeto TimeSpan, como um que o cmdlet New-TimeSpan retorna ou uma cadeia de caracteres que pode ser convertida em um objeto TimeSpan, como "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="4526e-206">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="4526e-207">Para alterar a duração de repetição ou o intervalo de repetição de um disparador de trabalho **Once** , o comando deve incluir o parâmetro **RepetitionInterval** e **RepetitionDuration** .</span><span class="sxs-lookup"><span data-stu-id="4526e-207">To change the repetition duration or repetition interval of a **Once** job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="4526e-208">Para alterar a duração da repetição ou intervalos de repetição de outros tipos de disparadores de trabalho, o comando deve incluir os parâmetros **Once** , **At** , **RepetitionInterval** e **RepetitionDuration** .</span><span class="sxs-lookup"><span data-stu-id="4526e-208">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the **Once** , **At** , **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>

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

### <span data-ttu-id="4526e-209">-User</span><span class="sxs-lookup"><span data-stu-id="4526e-209">-User</span></span>
<span data-ttu-id="4526e-210">Especifica os usuários que disparam um *AtLogon* no início de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="4526e-210">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="4526e-211">Insira o nome de um usuário no \<UserName\> ou \<Domain\Username\> formate ou insira um asterisco ( \* ) para representar todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="4526e-211">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="4526e-212">O valor padrão é todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="4526e-212">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4526e-213">-Semanal</span><span class="sxs-lookup"><span data-stu-id="4526e-213">-Weekly</span></span>
<span data-ttu-id="4526e-214">Especifica uma agenda recorrente de trabalho semanal.</span><span class="sxs-lookup"><span data-stu-id="4526e-214">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="4526e-215">Use os outros parâmetros no parâmetro *semanal* definido para especificar os detalhes da agenda.</span><span class="sxs-lookup"><span data-stu-id="4526e-215">Use the other parameters in the *Weekly* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="4526e-216">-WeeksInterval</span><span class="sxs-lookup"><span data-stu-id="4526e-216">-WeeksInterval</span></span>
<span data-ttu-id="4526e-217">Especifica o número de semanas entre ocorrências em uma agenda semanal.</span><span class="sxs-lookup"><span data-stu-id="4526e-217">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="4526e-218">Por exemplo, um valor de 3 inicia o trabalho agendado nas semanas 1, 4, 7 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4526e-218">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="4526e-219">O valor padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="4526e-219">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4526e-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4526e-220">CommonParameters</span></span>
<span data-ttu-id="4526e-221">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4526e-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4526e-222">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4526e-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4526e-223">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4526e-223">INPUTS</span></span>

### <span data-ttu-id="4526e-224">Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-224">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="4526e-225">É possível canalizar vários gatilhos de trabalho para **set-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="4526e-225">You can pipe multiple job triggers to **Set-JobTrigger** .</span></span>

## <span data-ttu-id="4526e-226">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4526e-226">OUTPUTS</span></span>

### <span data-ttu-id="4526e-227">Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-227">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="4526e-228">Ao usar o parâmetro *Passthru* , o **Set-JobTrigger** retorna os disparadores de trabalho que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="4526e-228">When you use the *Passthru* parameter, **Set-JobTrigger** returns the job triggers that were changed.</span></span>
<span data-ttu-id="4526e-229">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="4526e-229">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4526e-230">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4526e-230">NOTES</span></span>

* <span data-ttu-id="4526e-231">Disparadores de trabalho têm uma propriedade JobDefintion que os associa com o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="4526e-231">Job triggers have a JobDefintion property that associates them with the scheduled job.</span></span> <span data-ttu-id="4526e-232">Quando você altera o disparador de trabalho de um trabalho agendado, o trabalho é alterado.</span><span class="sxs-lookup"><span data-stu-id="4526e-232">When you change the job trigger of a scheduled job, the job is changed.</span></span> <span data-ttu-id="4526e-233">Você não precisa usar um comando Set-ScheduledJob para aplicar o gatilho alterado ao trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="4526e-233">You do not need to use a Set-ScheduledJob command to apply the changed trigger to the scheduled job.</span></span>

## <span data-ttu-id="4526e-234">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4526e-234">RELATED LINKS</span></span>

[<span data-ttu-id="4526e-235">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-235">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="4526e-236">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-236">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="4526e-237">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4526e-237">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="4526e-238">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-238">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="4526e-239">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4526e-239">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="4526e-240">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-240">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="4526e-241">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4526e-241">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="4526e-242">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="4526e-242">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="4526e-243">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-243">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="4526e-244">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="4526e-244">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="4526e-245">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4526e-245">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="4526e-246">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-246">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="4526e-247">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4526e-247">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="4526e-248">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4526e-248">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="4526e-249">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="4526e-249">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="4526e-250">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4526e-250">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
