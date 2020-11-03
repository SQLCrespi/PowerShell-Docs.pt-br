---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193672"
---
# <span data-ttu-id="65d32-103">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-103">New-JobTrigger</span></span>

## <span data-ttu-id="65d32-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="65d32-104">SYNOPSIS</span></span>
<span data-ttu-id="65d32-105">Cria um disparador de trabalho para um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="65d32-105">Creates a job trigger for a scheduled job.</span></span>

## <span data-ttu-id="65d32-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65d32-106">SYNTAX</span></span>

### <span data-ttu-id="65d32-107">Uma vez (padrão)</span><span class="sxs-lookup"><span data-stu-id="65d32-107">Once (Default)</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### <span data-ttu-id="65d32-108">Diário</span><span class="sxs-lookup"><span data-stu-id="65d32-108">Daily</span></span>

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### <span data-ttu-id="65d32-109">Semanal</span><span class="sxs-lookup"><span data-stu-id="65d32-109">Weekly</span></span>

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### <span data-ttu-id="65d32-110">AtStartup</span><span class="sxs-lookup"><span data-stu-id="65d32-110">AtStartup</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### <span data-ttu-id="65d32-111">AtLogon</span><span class="sxs-lookup"><span data-stu-id="65d32-111">AtLogon</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## <span data-ttu-id="65d32-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65d32-112">DESCRIPTION</span></span>
<span data-ttu-id="65d32-113">O cmdlet **New-JobTrigger** cria um gatilho de trabalho que inicia um trabalho agendado em um agendamento de uso único ou recorrente ou quando ocorre um evento.</span><span class="sxs-lookup"><span data-stu-id="65d32-113">The **New-JobTrigger** cmdlet creates a job trigger that starts a scheduled job on a one-time or recurring schedule, or when an event occurs.</span></span>

<span data-ttu-id="65d32-114">Você pode usar o objeto **ScheduledJobTrigger** que retorna **New-JobTrigger** para definir um gatilho de trabalho para um trabalho agendado novo ou existente.</span><span class="sxs-lookup"><span data-stu-id="65d32-114">You can use the **ScheduledJobTrigger** object that **New-JobTrigger** returns to set a job trigger for a new or existing scheduled job.</span></span>
<span data-ttu-id="65d32-115">Você também pode criar um gatilho de trabalho usando o cmdlet Get-JobTrigger para obter o gatilho de trabalho de um trabalho agendado existente ou usando um valor de tabela de hash para representar um gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="65d32-115">You can also create a job trigger by using the Get-JobTrigger cmdlet to get the job trigger of an existing scheduled job, or by using a hash table value to represent a job trigger.</span></span>

<span data-ttu-id="65d32-116">Ao criar um gatilho de trabalho, examine os valores padrão das opções especificadas pelo cmdlet New-ScheduledJobOption.</span><span class="sxs-lookup"><span data-stu-id="65d32-116">When creating a job trigger, review the default values of the options specified by the New-ScheduledJobOption cmdlet.</span></span>
<span data-ttu-id="65d32-117">Essas opções, que têm os mesmos valores válido e padrão das opções correspondentes no **Task Scheduler** , afetam o agendamento e o intervalo dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="65d32-117">These options, which have the same valid and default values as the corresponding options in **Task Scheduler** , affect the scheduling and timing of scheduled jobs.</span></span>

<span data-ttu-id="65d32-118">**New-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65d32-118">**New-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="65d32-119">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="65d32-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="65d32-120">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="65d32-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="65d32-121">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="65d32-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="65d32-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="65d32-122">EXAMPLES</span></span>

### <span data-ttu-id="65d32-123">Exemplo 1: uma vez agenda</span><span class="sxs-lookup"><span data-stu-id="65d32-123">Example 1: Once Schedule</span></span>

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

<span data-ttu-id="65d32-124">Este comando usa o cmdlet **New-JobTrigger** para criar um gatilho de trabalho que inicia um trabalho agendado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="65d32-124">This command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a scheduled job only one time.</span></span>
<span data-ttu-id="65d32-125">O valor do parâmetro *At* é uma cadeia de caracteres que o Windows PowerShell converte em um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="65d32-125">The value of the *At* parameter is a string that Windows PowerShell converts into a **DateTime** object.</span></span>
<span data-ttu-id="65d32-126">O valor de parâmetro *At* inclui uma data explícita, não apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="65d32-126">The *At* parameter value includes an explicit date, not just a time.</span></span>
<span data-ttu-id="65d32-127">Se a data foi omitida, o gatilho seria criado com a data atual e hora de 3h, que é provável que represente uma hora no passado.</span><span class="sxs-lookup"><span data-stu-id="65d32-127">If the date were omitted, the trigger would be created with the current date and 3:00 AM time, which is likely to represent a time in the past.</span></span>

### <span data-ttu-id="65d32-128">Exemplo 2: agendamento diário</span><span class="sxs-lookup"><span data-stu-id="65d32-128">Example 2: Daily Schedule</span></span>

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

<span data-ttu-id="65d32-129">Este comando cria um gatilho de trabalho que inicia um trabalho agendado a cada três dias às 4h15.</span><span class="sxs-lookup"><span data-stu-id="65d32-129">This command creates a job trigger that starts a scheduled job every 3 days at 4:15 a.m.</span></span>

<span data-ttu-id="65d32-130">Como o valor do parâmetro *At* não inclui uma data, a data atual será usada como valor de data do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="65d32-130">Because the value of the *At* parameter does not include a date, the current date is used as the date value in the **DateTime** object.</span></span>
<span data-ttu-id="65d32-131">Se a data e a hora estiverem no passado, a tarefa agendada é iniciada na próxima ocorrência, que é 3 dias depois do valor de parâmetro *At* .</span><span class="sxs-lookup"><span data-stu-id="65d32-131">If the date and time is in the past, the scheduled job is started at the next occurrence, which is 3 days later from the *At* parameter value.</span></span>

### <span data-ttu-id="65d32-132">Exemplo 3: agendamento semanal</span><span class="sxs-lookup"><span data-stu-id="65d32-132">Example 3: Weekly Schedule</span></span>

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

<span data-ttu-id="65d32-133">Este comando cria um gatilho de trabalho que inicia um trabalho agendado a cada 4 semanas na segunda-feira, quarta-feira e sexta-feira às 23 horas (11:00 PM).</span><span class="sxs-lookup"><span data-stu-id="65d32-133">This command creates a job trigger that starts a scheduled job every 4 weeks on Monday, Wednesday, and Friday at 2300 hours (11:00 PM).</span></span>

<span data-ttu-id="65d32-134">Você também pode inserir o valor do parâmetro *DaysOfWeek* em inteiros, como `-DaysOfWeek 1, 5` .</span><span class="sxs-lookup"><span data-stu-id="65d32-134">You can also enter the *DaysOfWeek* parameter value in integers, such as `-DaysOfWeek 1, 5`.</span></span>

### <span data-ttu-id="65d32-135">Exemplo 4: agendamento de logon</span><span class="sxs-lookup"><span data-stu-id="65d32-135">Example 4: Logon Schedule</span></span>

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

<span data-ttu-id="65d32-136">Este comando cria um gatilho de trabalho que inicia um trabalho agendado, sempre que o administrador do domínio faz logon no computador.</span><span class="sxs-lookup"><span data-stu-id="65d32-136">This command creates a job trigger that starts a scheduled job whenever the domain administrator logs onto the computer.</span></span>

### <span data-ttu-id="65d32-137">Exemplo 5: usando um atraso aleatório</span><span class="sxs-lookup"><span data-stu-id="65d32-137">Example 5: Using a Random Delay</span></span>

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

<span data-ttu-id="65d32-138">Este comando cria um gatilho de trabalho que inicia um trabalho agendado diariamente à 1h da manhã.</span><span class="sxs-lookup"><span data-stu-id="65d32-138">This command creates a job trigger that starts a scheduled job every day at 1:00 in the morning.</span></span>
<span data-ttu-id="65d32-139">O comando usa o parâmetro *RandomDelay* para definir o atraso máximo para 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="65d32-139">The command uses the *RandomDelay* parameter to set the maximum delay to 20 minutes.</span></span>
<span data-ttu-id="65d32-140">Como resultado, o trabalho é executado diariamente entre 1h e 1h20, com o intervalo variando pseudo aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="65d32-140">As a result, the job runs every day between 1:00 AM and 1:20 AM, with the interval varying pseudo-randomly.</span></span>

<span data-ttu-id="65d32-141">Você pode usar um atraso aleatório para amostragem, balanceamento de carga e outras tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="65d32-141">You can use a random delay for sampling, load balancing, and other administrative tasks.</span></span>
<span data-ttu-id="65d32-142">Ao definir o valor de atraso, examine os valores efetivo e padrão do cmdlet New-ScheduledJobOption e coordene o atraso com as configurações de opção.</span><span class="sxs-lookup"><span data-stu-id="65d32-142">When setting the delay value, review the effective and default values of the New-ScheduledJobOption cmdlet and coordinate the delay with the option settings.</span></span>

### <span data-ttu-id="65d32-143">Exemplo 6: criar um gatilho de trabalho para um novo trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="65d32-143">Example 6: Create a Job Trigger for a New Scheduled Job</span></span>

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

<span data-ttu-id="65d32-144">Esses comandos usam um gatilho de trabalho para criar um novo trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="65d32-144">These commands use a job trigger to create a new scheduled job.</span></span>

### <span data-ttu-id="65d32-145">Exemplo 7: adicionar um gatilho de trabalho a um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="65d32-145">Example 7: Add a Job Trigger to a Scheduled Job</span></span>

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

<span data-ttu-id="65d32-146">Este exemplo mostra como adicionar um gatilho de trabalho a um trabalho agendado existente.</span><span class="sxs-lookup"><span data-stu-id="65d32-146">This example shows how to add a job trigger to an existing scheduled job.</span></span>
<span data-ttu-id="65d32-147">Você pode adicionar vários gatilhos de trabalho a qualquer trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="65d32-147">You can add multiple job triggers to any scheduled job.</span></span>

<span data-ttu-id="65d32-148">O comando usa o cmdlet Add-JobTrigger para adicionar o gatilho de trabalho ao trabalho agendado SynchronizeApps.</span><span class="sxs-lookup"><span data-stu-id="65d32-148">The command uses the Add-JobTrigger cmdlet to add the job trigger to the SynchronizeApps scheduled job.</span></span>
<span data-ttu-id="65d32-149">O valor do parâmetro *Trigger* é um comando **New-JobTrigger** que executa o trabalho todos os dias às 3h10.</span><span class="sxs-lookup"><span data-stu-id="65d32-149">The value of the *Trigger* parameter is a **New-JobTrigger** command that runs the job every day at 3:10 AM.</span></span>

<span data-ttu-id="65d32-150">Quando o comando é concluído, o SynchronizeApps é um trabalho agendado que é executado nos horários especificados pelo gatilho do trabalho.</span><span class="sxs-lookup"><span data-stu-id="65d32-150">When the command completes, SynchronizeApps is a scheduled job that runs at the times specified by the job trigger.</span></span>

### <span data-ttu-id="65d32-151">Exemplo 8: criar um gatilho de trabalho repetido</span><span class="sxs-lookup"><span data-stu-id="65d32-151">Example 8: Create a repeating job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

<span data-ttu-id="65d32-152">Este comando cria um gatilho de trabalho que executa um trabalho a cada 60 minutos por 48 horas, começando em 12 de setembro de 2013 às 1:00.</span><span class="sxs-lookup"><span data-stu-id="65d32-152">This command creates a job trigger that runs a job every 60 minutes for 48 hours beginning on September 12, 2013 at 1:00 AM.</span></span>

### <span data-ttu-id="65d32-153">Exemplo 9: parar um gatilho de trabalho repetido</span><span class="sxs-lookup"><span data-stu-id="65d32-153">Example 9: Stop a repeating job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

<span data-ttu-id="65d32-154">Esse comando interrompe forçosamente o trabalho SecurityCheck, que é disparado para ser executado a cada 60 minutos até que seu gatilho de trabalho expire.</span><span class="sxs-lookup"><span data-stu-id="65d32-154">This command forcibly stops the SecurityCheck job, which is triggered to run every 60 minutes until its job trigger expires.</span></span>

<span data-ttu-id="65d32-155">Para impedir que o trabalho seja repetido, o comando usa o Get-JobTrigger para obter o gatilho de trabalho do trabalho SecurityCheck e o cmdlet Set-JobTrigger para alterar o intervalo de repetição e a duração da repetição do gatilho de trabalho para zero (0).</span><span class="sxs-lookup"><span data-stu-id="65d32-155">To prevent the job from repeating, the command uses the Get-JobTrigger to get the job trigger of the SecurityCheck job and the Set-JobTrigger cmdlet to change the repetition interval and repetition duration of the job trigger to zero (0).</span></span>

### <span data-ttu-id="65d32-156">Exemplo 10: criar um gatilho de trabalho por hora</span><span class="sxs-lookup"><span data-stu-id="65d32-156">Example 10: Create an hourly job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

<span data-ttu-id="65d32-157">O comando a seguir cria um gatilho de trabalho que executa um trabalho agendado a cada 12 horas, por um período indefinido de tempo.</span><span class="sxs-lookup"><span data-stu-id="65d32-157">The following command creates a job trigger that runs a scheduled job once every 12 hours for an indefinite period of time.</span></span>
<span data-ttu-id="65d32-158">A agenda começa amanhã (21/9/2012) à meia-noite (0:00 AM).</span><span class="sxs-lookup"><span data-stu-id="65d32-158">The schedule begins tomorrow (9/21/2012) at midnight (0:00 AM).</span></span>

## <span data-ttu-id="65d32-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65d32-159">PARAMETERS</span></span>

### <span data-ttu-id="65d32-160">-Em</span><span class="sxs-lookup"><span data-stu-id="65d32-160">-At</span></span>
<span data-ttu-id="65d32-161">Inicia o trabalho em determinada data e hora.</span><span class="sxs-lookup"><span data-stu-id="65d32-161">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="65d32-162">Insira um objeto **DateTime** , como um que o cmdlet Get-Date retorna, ou uma cadeia de caracteres que pode ser convertida em uma data e hora, como "19 de abril de 2012 15:00", "12/31" ou "3am".</span><span class="sxs-lookup"><span data-stu-id="65d32-162">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a date and time, such as "April 19, 2012 15:00", "12/31", or "3am".</span></span>
<span data-ttu-id="65d32-163">Se você não especificar um elemento de data, como o ano, a data no gatilho tem o elemento correspondente a partir da data atual.</span><span class="sxs-lookup"><span data-stu-id="65d32-163">If you don't specify an element of the date, such as the year, the date in the trigger has the corresponding element from the current date.</span></span>

<span data-ttu-id="65d32-164">Ao usar o parâmetro *Once* , defina o valor do parâmetro *At* para uma data e hora futura.</span><span class="sxs-lookup"><span data-stu-id="65d32-164">When using the *Once* parameter, set the value of the *At* parameter to a future date and time.</span></span>
<span data-ttu-id="65d32-165">Como a data padrão em um objeto **DateTime** é a data atual, se você especificar uma hora antes da hora atual sem uma data explícita, o gatilho do trabalho será criado para uma hora no passado.</span><span class="sxs-lookup"><span data-stu-id="65d32-165">Because the default date in a **DateTime** object is the current date, if you specify a time before the current time without an explicit date, the job trigger is created for a time in the past.</span></span>

<span data-ttu-id="65d32-166">Os objetos **DateTime** e as cadeias de caracteres que são convertidos em objetos **DateTime** são automaticamente ajustados para serem compatíveis com os formatos de data e hora selecionados para o computador local em região e idioma no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="65d32-166">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-167">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="65d32-167">-AtLogOn</span></span>
<span data-ttu-id="65d32-168">Inicia o trabalho agendado quando os usuários especificados fazem logon no computador.</span><span class="sxs-lookup"><span data-stu-id="65d32-168">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="65d32-169">Para especificar um usuário, use o parâmetro *User* .</span><span class="sxs-lookup"><span data-stu-id="65d32-169">To specify a user, use the *User* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-170">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="65d32-170">-AtStartup</span></span>
<span data-ttu-id="65d32-171">Inicia o trabalho agendado quando o Windows inicia.</span><span class="sxs-lookup"><span data-stu-id="65d32-171">Starts the scheduled job when Windows starts.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-172">-Diário</span><span class="sxs-lookup"><span data-stu-id="65d32-172">-Daily</span></span>
<span data-ttu-id="65d32-173">Especifica uma agenda recorrente de trabalho diário.</span><span class="sxs-lookup"><span data-stu-id="65d32-173">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="65d32-174">Use os outros parâmetros no conjunto de parâmetros *diário* para especificar os detalhes da agenda.</span><span class="sxs-lookup"><span data-stu-id="65d32-174">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-175">-DaysInterval</span><span class="sxs-lookup"><span data-stu-id="65d32-175">-DaysInterval</span></span>
<span data-ttu-id="65d32-176">Especifica o número de dias entre ocorrências em uma agenda diária.</span><span class="sxs-lookup"><span data-stu-id="65d32-176">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="65d32-177">Por exemplo, um valor de 3 inicia o trabalho agendado nos dias 1, 4, 7 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="65d32-177">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="65d32-178">O valor padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="65d32-178">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-179">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="65d32-179">-DaysOfWeek</span></span>
<span data-ttu-id="65d32-180">Especifica os dias da semana em que um trabalho agendado semanalmente é executado.</span><span class="sxs-lookup"><span data-stu-id="65d32-180">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="65d32-181">Insira os nomes dos dias, como "segunda-feira" ou números inteiros de 0 a 6, onde 0 representa o domingo.</span><span class="sxs-lookup"><span data-stu-id="65d32-181">Enter day names, such as "Monday" or integers 0-6, where 0 represents Sunday.</span></span>
<span data-ttu-id="65d32-182">Este parâmetro é necessário no conjunto de parâmetros Semanal.</span><span class="sxs-lookup"><span data-stu-id="65d32-182">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="65d32-183">Nomes de dias são convertidos em seus valores inteiros no gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="65d32-183">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="65d32-184">Quando você coloca os nomes de dias entre aspas em um comando, coloque o nome de cada dia em aspas separadas, como "Segunda-feira", "Terça-feira".</span><span class="sxs-lookup"><span data-stu-id="65d32-184">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="65d32-185">Se você colocar vários nomes de dias em um par de aspas simples, os valores inteiros correspondentes são somados.</span><span class="sxs-lookup"><span data-stu-id="65d32-185">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="65d32-186">Por exemplo, "Segunda-feira, Terça-feira" (1, 2) resulta em um valor de "Quarta-feira" (3).</span><span class="sxs-lookup"><span data-stu-id="65d32-186">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-187">-Uma vez</span><span class="sxs-lookup"><span data-stu-id="65d32-187">-Once</span></span>
<span data-ttu-id="65d32-188">Especifica uma agenda personalizada de repetição ou não recorrente (única).</span><span class="sxs-lookup"><span data-stu-id="65d32-188">Specifies a non-recurring (one time) or custom repeating schedule.</span></span>
<span data-ttu-id="65d32-189">Para criar uma agenda de repetição, use o parâmetro *Once* com os parâmetros *RepetitionDuration* e *RepetitionInterval* .</span><span class="sxs-lookup"><span data-stu-id="65d32-189">To create a repeating schedule, use the *Once* parameter with the *RepetitionDuration* and *RepetitionInterval* parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-190">-RandomDelay</span><span class="sxs-lookup"><span data-stu-id="65d32-190">-RandomDelay</span></span>
<span data-ttu-id="65d32-191">Permite um atraso aleatório que começa na hora de início agendada e define o valor de tempo de espera máximo.</span><span class="sxs-lookup"><span data-stu-id="65d32-191">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="65d32-192">O tempo de atraso é definido pseudoaleatoriamente para cada início e varia de nenhum atraso até a hora especificada pelo valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="65d32-192">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="65d32-193">O valor padrão, zero (00:00:00), desabilita o atraso aleatório.</span><span class="sxs-lookup"><span data-stu-id="65d32-193">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="65d32-194">Insira um objeto TimeSpan, como um retornado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format, que é automaticamente convertido em um objeto **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="65d32-194">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a **TimeSpan** object.</span></span>

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

### <span data-ttu-id="65d32-195">-RepeatIndefinitely</span><span class="sxs-lookup"><span data-stu-id="65d32-195">-RepeatIndefinitely</span></span>
<span data-ttu-id="65d32-196">Esse parâmetro, disponível a partir do Windows PowerShell 4.0, elimina a necessidade de especificar um valor **TimeSpan.MaxValue** para o parâmetro *RepetitionDuration* para executar um trabalho agendado repetidamente, por um período indefinido.</span><span class="sxs-lookup"><span data-stu-id="65d32-196">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-197">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="65d32-197">-RepetitionDuration</span></span>
<span data-ttu-id="65d32-198">Repete o trabalho até o tempo especificado expirar.</span><span class="sxs-lookup"><span data-stu-id="65d32-198">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="65d32-199">A frequência de repetição é determinada pelo valor do parâmetro *RepetitionInterval* .</span><span class="sxs-lookup"><span data-stu-id="65d32-199">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="65d32-200">Por exemplo, se o valor de **RepetitionInterval** for 5 minutos e o valor de **RepetitionDuration** for de 2 horas, o trabalho será acionado a cada cinco minutos por duas horas.</span><span class="sxs-lookup"><span data-stu-id="65d32-200">For example, if the value of **RepetitionInterval** is 5 minutes and the value of **RepetitionDuration** is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="65d32-201">Insira um objeto TimeSpan, como um que o cmdlet New-TimeSpan retorna ou uma cadeia de caracteres que pode ser convertida em um objeto TimeSpan, como "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="65d32-201">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="65d32-202">Para executar um trabalho indefinidamente, adicione o parâmetro *RepeatIndefinitely* em vez disso.</span><span class="sxs-lookup"><span data-stu-id="65d32-202">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="65d32-203">Para interromper um trabalho antes que a duração da repetição do gatilho de trabalho expire, use o cmdlet Set-JobTrigger para definir o valor de *RepetitionDuration* como zero (0).</span><span class="sxs-lookup"><span data-stu-id="65d32-203">To stop a job before the job trigger repetition duration expires, use the Set-JobTrigger cmdlet to set the *RepetitionDuration* value to zero (0).</span></span>

<span data-ttu-id="65d32-204">Esse parâmetro é válido somente quando os parâmetros *Once* , *At* e *RepetitionInterval* são utilizados no comando.</span><span class="sxs-lookup"><span data-stu-id="65d32-204">This parameter is valid only when the *Once* , *At* and *RepetitionInterval* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-205">-RepetitionInterval</span><span class="sxs-lookup"><span data-stu-id="65d32-205">-RepetitionInterval</span></span>
<span data-ttu-id="65d32-206">Repete o trabalho no tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="65d32-206">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="65d32-207">Por exemplo, se o valor desse parâmetro é de 2 horas, o trabalho será acionado a cada duas horas.</span><span class="sxs-lookup"><span data-stu-id="65d32-207">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="65d32-208">O valor padrão, 0, não repete o trabalho.</span><span class="sxs-lookup"><span data-stu-id="65d32-208">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="65d32-209">Insira um objeto TimeSpan, como um que o cmdlet New-TimeSpan retorna ou uma cadeia de caracteres que pode ser convertida em um objeto TimeSpan, como "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="65d32-209">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="65d32-210">Esse parâmetro é válido somente quando os parâmetros *Once* , *At* e *RepetitionDuration* são utilizados no comando.</span><span class="sxs-lookup"><span data-stu-id="65d32-210">This parameter is valid only when the *Once* , *At* , and *RepetitionDuration* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-211">-User</span><span class="sxs-lookup"><span data-stu-id="65d32-211">-User</span></span>
<span data-ttu-id="65d32-212">Especifica os usuários que disparam um *AtLogon* no início de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="65d32-212">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="65d32-213">Insira o nome de um usuário no \<UserName\> ou \<Domain\Username\> formate ou insira um asterisco ( \* ) para representar todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="65d32-213">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="65d32-214">O valor padrão é todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="65d32-214">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-215">-Semanal</span><span class="sxs-lookup"><span data-stu-id="65d32-215">-Weekly</span></span>
<span data-ttu-id="65d32-216">Especifica uma agenda recorrente de trabalho semanal.</span><span class="sxs-lookup"><span data-stu-id="65d32-216">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="65d32-217">Use os outros parâmetros no conjunto de parâmetros Semanal para especificar os detalhes da agenda.</span><span class="sxs-lookup"><span data-stu-id="65d32-217">Use the other parameters in the Weekly parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-218">-WeeksInterval</span><span class="sxs-lookup"><span data-stu-id="65d32-218">-WeeksInterval</span></span>
<span data-ttu-id="65d32-219">Especifica o número de semanas entre ocorrências em uma agenda semanal.</span><span class="sxs-lookup"><span data-stu-id="65d32-219">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="65d32-220">Por exemplo, um valor de 3 inicia o trabalho agendado nas semanas 1, 4, 7 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="65d32-220">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="65d32-221">O valor padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="65d32-221">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Weekly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65d32-222">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65d32-222">CommonParameters</span></span>
<span data-ttu-id="65d32-223">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="65d32-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65d32-224">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="65d32-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65d32-225">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="65d32-225">INPUTS</span></span>

### <span data-ttu-id="65d32-226">Nenhum</span><span class="sxs-lookup"><span data-stu-id="65d32-226">None</span></span>
<span data-ttu-id="65d32-227">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="65d32-227">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="65d32-228">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="65d32-228">OUTPUTS</span></span>

### <span data-ttu-id="65d32-229">Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-229">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="65d32-230">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="65d32-230">NOTES</span></span>

* <span data-ttu-id="65d32-231">Gatilhos de trabalho não são salvos em disco.</span><span class="sxs-lookup"><span data-stu-id="65d32-231">Job triggers are not saved to disk.</span></span> <span data-ttu-id="65d32-232">No entanto, os trabalhos agendados são salvos em disco e você pode usar o Get-JobTrigger para obter o gatilho de trabalho de qualquer trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="65d32-232">However, scheduled jobs are saved to disk, and you can use the Get-JobTrigger to get the job trigger of any scheduled job.</span></span>
* <span data-ttu-id="65d32-233">**New-JobTrigger** não impede a criação de um gatilho de trabalho que não executará um trabalho agendado, como um gatilho de tempo único para uma data no passado.</span><span class="sxs-lookup"><span data-stu-id="65d32-233">**New-JobTrigger** does not prevent you from creating a job trigger that will not run a scheduled job, such as one-time trigger for a date in the past.</span></span>
* <span data-ttu-id="65d32-234">O cmdlet Register-ScheduledJob aceita um objeto ScheduledJobTrigger, como um retornado pelos cmdlets **New-JobTrigger** ou Get-JobTrigger, ou uma tabela de hash com valores de gatilho.</span><span class="sxs-lookup"><span data-stu-id="65d32-234">The Register-ScheduledJob cmdlet accepts a ScheduledJobTrigger object, such as one returned by the **New-JobTrigger** or Get-JobTrigger cmdlets, or a hash table with trigger values.</span></span>

  <span data-ttu-id="65d32-235">Para enviar uma tabela de hash, use as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="65d32-235">To submit a hash table, use the following keys.</span></span>

  <span data-ttu-id="65d32-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (ou qualquer cadeia de hora válida); `DaysOfWeek="Monday", "Wednesday"` (ou qualquer combinação de nomes de dias); `Interval=2` (ou qualquer intervalo de frequência válido); `RandomDelay="30minutes"` (ou qualquer cadeia de caracteres TimeSpan válida); `User="Domain1\User01` (ou qualquer usuário válido; usado somente com o valor de frequência *AtLogon* )}</span><span class="sxs-lookup"><span data-stu-id="65d32-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01` (or any valid user; used only with the *AtLogon* frequency value) }</span></span>

## <span data-ttu-id="65d32-237">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="65d32-237">RELATED LINKS</span></span>

[<span data-ttu-id="65d32-238">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-238">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="65d32-239">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-239">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="65d32-240">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="65d32-240">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="65d32-241">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-241">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="65d32-242">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="65d32-242">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="65d32-243">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-243">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="65d32-244">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="65d32-244">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="65d32-245">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="65d32-245">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="65d32-246">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-246">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="65d32-247">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="65d32-247">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="65d32-248">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="65d32-248">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="65d32-249">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-249">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="65d32-250">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="65d32-250">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="65d32-251">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="65d32-251">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="65d32-252">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="65d32-252">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="65d32-253">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="65d32-253">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
