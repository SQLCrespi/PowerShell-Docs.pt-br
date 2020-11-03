---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193676"
---
# <span data-ttu-id="f2757-103">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-103">Get-JobTrigger</span></span>

## <span data-ttu-id="f2757-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f2757-104">SYNOPSIS</span></span>
<span data-ttu-id="f2757-105">Habilita os gatilhos de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="f2757-105">Gets the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="f2757-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f2757-106">SYNTAX</span></span>

### <span data-ttu-id="f2757-107">JobDefinition (padrão)</span><span class="sxs-lookup"><span data-stu-id="f2757-107">JobDefinition (Default)</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="f2757-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="f2757-108">JobDefinitionId</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="f2757-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="f2757-109">JobDefinitionName</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="f2757-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f2757-110">DESCRIPTION</span></span>
<span data-ttu-id="f2757-111">O cmdlet **Get-JobTrigger** obtém os gatilhos de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="f2757-111">The **Get-JobTrigger** cmdlet gets the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="f2757-112">Você pode usar este comando para examinar os gatilhos de trabalho ou para direcionar os gatilhos de trabalho para outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f2757-112">You can use this command to examine the job triggers or to pipe the job triggers to other cmdlets.</span></span>

<span data-ttu-id="f2757-113">Um gatilho de trabalho define uma agenda recorrente ou condições para iniciar um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-113">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="f2757-114">Gatilhos de trabalho não são salvas em disco de modo independente; elas fazem parte de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-114">Job triggers are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="f2757-115">Para obter um gatilho de trabalho, especifique o trabalho agendado que o gatilho inicia.</span><span class="sxs-lookup"><span data-stu-id="f2757-115">To get a job trigger, specify the scheduled job that the trigger starts.</span></span>

<span data-ttu-id="f2757-116">Use os parâmetros do cmdlet **Get-JobTrigger** para identificar os trabalhos agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-116">Use the parameters of the **Get-JobTrigger** cmdlet to identify the scheduled jobs.</span></span>
<span data-ttu-id="f2757-117">Você pode identificar os trabalhos agendados por seus nomes ou números de identificação, ou inserindo ou canalizando objetos **ScheduledJob** , como os que são retornados pelo cmdlet Get-ScheduledJob, para **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="f2757-117">You can identify the scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-JobTrigger** .</span></span>

<span data-ttu-id="f2757-118">**Get-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2757-118">**Get-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="f2757-119">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f2757-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="f2757-120">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="f2757-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="f2757-121">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f2757-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f2757-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f2757-122">EXAMPLES</span></span>

### <span data-ttu-id="f2757-123">Exemplo 1: obter um gatilho de trabalho por nome de trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="f2757-123">Example 1: Get a job trigger by scheduled job name</span></span>

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

<span data-ttu-id="f2757-124">O comando usa o parâmetro *Name* de **Get-JobTrigger** para obter os gatilhos de trabalho do trabalho agendado BackupJob.</span><span class="sxs-lookup"><span data-stu-id="f2757-124">The command uses the *Name* parameter of **Get-JobTrigger** to get the job triggers of the BackupJob scheduled job.</span></span>

### <span data-ttu-id="f2757-125">Exemplo 2: obter um gatilho de trabalho por ID</span><span class="sxs-lookup"><span data-stu-id="f2757-125">Example 2: Get a job trigger by ID</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

<span data-ttu-id="f2757-126">O exemplo usa o parâmetro *ID* de **Get-JobTrigger** para obter os gatilhos de trabalho de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-126">The example uses the *ID* parameter of **Get-JobTrigger** to get the job triggers of a scheduled job.</span></span>

### <span data-ttu-id="f2757-127">Exemplo 3: obter gatilhos de trabalho ao canalizar um trabalho</span><span class="sxs-lookup"><span data-stu-id="f2757-127">Example 3: Get job triggers by piping a job</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

<span data-ttu-id="f2757-128">Esse comando obtém os gatilhos de trabalho de todos os trabalhos que têm backup ou arquivamento em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="f2757-128">This command gets the job triggers of all jobs that have Backup or Archive in their names.</span></span>

### <span data-ttu-id="f2757-129">Exemplo 4: obter o gatilho de trabalho de um trabalho em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="f2757-129">Example 4: Get the job trigger of a job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

<span data-ttu-id="f2757-130">Esse comando obtém um dos dois gatilhos trabalhos de um trabalho agendado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f2757-130">This command gets one of the two job triggers of a scheduled job on a remote computer.</span></span>

<span data-ttu-id="f2757-131">O comando usa o cmdlet Invoke-Command para executar um comando no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f2757-131">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>
<span data-ttu-id="f2757-132">Ele usa o cmdlet Get-ScheduledJob para obter o trabalho agendado de backup, que ele canaliza para o cmdlet **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="f2757-132">It uses the Get-ScheduledJob cmdlet to get the Backup scheduled job, which it pipes to the **Get-JobTrigger** cmdlet.</span></span>
<span data-ttu-id="f2757-133">Ele usa o parâmetro *triggerid* para obter apenas o segundo gatilho.</span><span class="sxs-lookup"><span data-stu-id="f2757-133">It uses the *TriggerID* parameter to get only the second trigger.</span></span>

### <span data-ttu-id="f2757-134">Exemplo 5: obter todos os gatilhos de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2757-134">Example 5: Get all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

<span data-ttu-id="f2757-135">Este comando obtém todos os gatilhos de trabalho de todos os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="f2757-135">This command gets all job triggers of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="f2757-136">O comando usa o Get-ScheduledJob para obter os trabalhos agendados no computador local e os canaliza para **Get-JobTrigger** , que obtém o gatilho de trabalho de cada trabalho agendado (se houver).</span><span class="sxs-lookup"><span data-stu-id="f2757-136">The command uses the Get-ScheduledJob to get the scheduled jobs on the local computer and pipes them to **Get-JobTrigger** , which gets the job trigger of each scheduled job (if any).</span></span>

<span data-ttu-id="f2757-137">Para adicionar o nome do trabalho agendado à exibição do gatilho de trabalho, o comando usa o recurso de propriedade calculada do cmdlet Format-Table.</span><span class="sxs-lookup"><span data-stu-id="f2757-137">To add the name of the scheduled job to the job trigger display, the command uses the calculated property feature of the Format-Table cmdlet.</span></span>
<span data-ttu-id="f2757-138">Além das propriedades do gatilho de trabalho que são exibidas por padrão, o comando cria uma nova propriedade ScheduledJob que exibe o nome do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-138">In addition to the job trigger properties that are displayed by default, the command creates a new ScheduledJob property that displays the name of the scheduled job.</span></span>

### <span data-ttu-id="f2757-139">Exemplo 6: obter a propriedade de gatilho de trabalho de um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="f2757-139">Example 6: Get the job trigger property of a scheduled job</span></span>

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

<span data-ttu-id="f2757-140">Os gatilhos de trabalho de uma tarefa agendada são armazenados na propriedade JobTriggers do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2757-140">The job triggers of a scheduled job are stored in the JobTriggers property of the job.</span></span>
<span data-ttu-id="f2757-141">Este exemplo mostra alternativas ao uso do cmdlet **Get-JobTrigger** para obter gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2757-141">This example shows alternatives to using the **Get-JobTrigger** cmdlet to get job triggers.</span></span>
<span data-ttu-id="f2757-142">Os resultados são idênticos a usar o cmdlet **Get-JobTrigger** e as técnicas podem ser usadas intercambiavelmente.</span><span class="sxs-lookup"><span data-stu-id="f2757-142">The results are identical to using the **Get-JobTrigger** cmdlet and the techniques can be used interchangeably.</span></span>

### <span data-ttu-id="f2757-143">Exemplo 7: comparar gatilhos de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2757-143">Example 7: Compare job triggers</span></span>

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

<span data-ttu-id="f2757-144">Este exemplo mostra como comparar os gatilhos de trabalho de dois trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="f2757-144">This example shows how to compare the job triggers of two scheduled jobs.</span></span>

## <span data-ttu-id="f2757-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f2757-145">PARAMETERS</span></span>

### <span data-ttu-id="f2757-146">-Id</span><span class="sxs-lookup"><span data-stu-id="f2757-146">-Id</span></span>
<span data-ttu-id="f2757-147">Especifica o número de identificação de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-147">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="f2757-148">O **Get-JobTrigger** obtém o gatilho de trabalho do trabalho agendado especificado.</span><span class="sxs-lookup"><span data-stu-id="f2757-148">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>

<span data-ttu-id="f2757-149">Para obter o número de identificação de trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f2757-149">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f2757-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f2757-150">-InputObject</span></span>
<span data-ttu-id="f2757-151">Especifica um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-151">Specifies a scheduled job.</span></span>
<span data-ttu-id="f2757-152">Insira uma variável que contenha objetos  **ScheduledJob** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJob** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f2757-152">Enter a variable that contains  **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="f2757-153">Você também pode canalizar objetos **ScheduledJob** para **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="f2757-153">You can also pipe **ScheduledJob** objects to **Get-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f2757-154">-Name</span><span class="sxs-lookup"><span data-stu-id="f2757-154">-Name</span></span>
<span data-ttu-id="f2757-155">Especifique o nome de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f2757-155">Specifies the name of a scheduled job.</span></span>
<span data-ttu-id="f2757-156">O **Get-JobTrigger** obtém o gatilho de trabalho do trabalho agendado especificado.</span><span class="sxs-lookup"><span data-stu-id="f2757-156">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>
<span data-ttu-id="f2757-157">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="f2757-157">Wildcards are supported.</span></span>

<span data-ttu-id="f2757-158">Para obter os nomes dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f2757-158">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f2757-159">-Triggerid</span><span class="sxs-lookup"><span data-stu-id="f2757-159">-TriggerId</span></span>
<span data-ttu-id="f2757-160">Obtém os gatilhos de trabalho especificado.</span><span class="sxs-lookup"><span data-stu-id="f2757-160">Gets the specified job triggers.</span></span>
<span data-ttu-id="f2757-161">Insira as IDs de gatilho de um ou mais gatilhos de trabalho de uma tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="f2757-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="f2757-162">Use esse parâmetro quando o trabalho agendado especificado pelos parâmetros *Name* , *ID* ou *InputObject* tiverem vários gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2757-162">Use this parameter when the scheduled job that is specified by the *Name* , *ID* , or *InputObject* parameters has multiple job triggers.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f2757-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f2757-163">CommonParameters</span></span>
<span data-ttu-id="f2757-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f2757-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f2757-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f2757-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f2757-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f2757-166">INPUTS</span></span>

### <span data-ttu-id="f2757-167">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="f2757-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f2757-168">É possível canalizar um trabalho agendado de Get-ScheduledJob para **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="f2757-168">You can pipe a scheduled job from Get-ScheduledJob to **Get-JobTrigger** .</span></span>

## <span data-ttu-id="f2757-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f2757-169">OUTPUTS</span></span>

### <span data-ttu-id="f2757-170">Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-170">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="f2757-171">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f2757-171">NOTES</span></span>

## <span data-ttu-id="f2757-172">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f2757-172">RELATED LINKS</span></span>

[<span data-ttu-id="f2757-173">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-173">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="f2757-174">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-174">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="f2757-175">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f2757-175">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="f2757-176">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-176">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="f2757-177">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f2757-177">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="f2757-178">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-178">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="f2757-179">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f2757-179">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="f2757-180">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f2757-180">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="f2757-181">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-181">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="f2757-182">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f2757-182">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="f2757-183">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f2757-183">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="f2757-184">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-184">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="f2757-185">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f2757-185">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="f2757-186">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f2757-186">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="f2757-187">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f2757-187">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="f2757-188">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f2757-188">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
