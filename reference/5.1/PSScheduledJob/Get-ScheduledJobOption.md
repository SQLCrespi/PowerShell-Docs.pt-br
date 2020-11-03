---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193673"
---
# <span data-ttu-id="c7049-103">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c7049-103">Get-ScheduledJobOption</span></span>

## <span data-ttu-id="c7049-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c7049-104">SYNOPSIS</span></span>
<span data-ttu-id="c7049-105">Obtém as opções de trabalho de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="c7049-105">Gets the job options of scheduled jobs.</span></span>

## <span data-ttu-id="c7049-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7049-106">SYNTAX</span></span>

### <span data-ttu-id="c7049-107">JobDefinition (padrão)</span><span class="sxs-lookup"><span data-stu-id="c7049-107">JobDefinition (Default)</span></span>

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="c7049-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="c7049-108">JobDefinitionId</span></span>

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="c7049-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="c7049-109">JobDefinitionName</span></span>

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="c7049-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c7049-110">DESCRIPTION</span></span>
<span data-ttu-id="c7049-111">O cmdlet **Get-ScheduledJobOption** Obtém as opções de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="c7049-111">The **Get-ScheduledJobOption** cmdlet gets the job options of scheduled jobs.</span></span>
<span data-ttu-id="c7049-112">Você pode usar este comando para examinar as opções de trabalho ou para direcionar as opções de trabalho para outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c7049-112">You can use this command to examine the job options or to pipe the job options to other cmdlets.</span></span>

<span data-ttu-id="c7049-113">As opções de trabalho não são salvas em disco de modo independente; elas são parte de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="c7049-113">Job options are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="c7049-114">Para obter as opções de trabalho de um trabalho agendado, especifique esse trabalho.</span><span class="sxs-lookup"><span data-stu-id="c7049-114">To get the job options of a scheduled job, specify the scheduled job.</span></span>

<span data-ttu-id="c7049-115">Use os parâmetros do cmdlet **Get-ScheduledJobOption** para identificar o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="c7049-115">Use the parameters of the **Get-ScheduledJobOption** cmdlet to identify the scheduled job.</span></span>
<span data-ttu-id="c7049-116">Você pode identificar os trabalhos agendados por seus nomes ou números de identificação ou inserindo ou canalizando objetos **ScheduledJob** , como os que são retornados pelo cmdlet Get-ScheduledJob, para **Get-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="c7049-116">You can identify scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-ScheduledJobOption** .</span></span>

<span data-ttu-id="c7049-117">**Get-ScheduledJobOption** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7049-117">**Get-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="c7049-118">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="c7049-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="c7049-119">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="c7049-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="c7049-120">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c7049-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c7049-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c7049-121">EXAMPLES</span></span>

### <span data-ttu-id="c7049-122">Exemplo 1: obter opções de trabalho</span><span class="sxs-lookup"><span data-stu-id="c7049-122">Example 1: Get job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
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

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="c7049-123">Esse comando obtém as opções de trabalho dos trabalhos agendados que têm BackUp em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="c7049-123">This command gets the job options of scheduled jobs that have BackUp in their names.</span></span>
<span data-ttu-id="c7049-124">Os resultados mostram o objeto de opções de trabalho retornado pelo **Get-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="c7049-124">The results show the job options object that **Get-ScheduledJobOption** returned.</span></span>

### <span data-ttu-id="c7049-125">Exemplo 2: obter todas as opções de trabalho</span><span class="sxs-lookup"><span data-stu-id="c7049-125">Example 2: Get all job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

<span data-ttu-id="c7049-126">Este comando obtém as opções de trabalho de todos os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="c7049-126">This command gets the job options of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="c7049-127">Ele usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="c7049-127">It uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="c7049-128">Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet **Get-ScheduledJobOption** , que obtém as opções de trabalho de cada trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="c7049-128">A pipeline operator (|) sends the scheduled jobs to the **Get-ScheduledJobOption** cmdlet, which gets the job options of each scheduled job.</span></span>

### <span data-ttu-id="c7049-129">Exemplo 3: obter opções de trabalho selecionadas</span><span class="sxs-lookup"><span data-stu-id="c7049-129">Example 3: Get selected job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

<span data-ttu-id="c7049-130">Este exemplo mostra como localizar um objeto de opções de trabalho com valores específicos.</span><span class="sxs-lookup"><span data-stu-id="c7049-130">This example shows how to find job options object with particular values.</span></span>

<span data-ttu-id="c7049-131">O primeiro comando obtém as opções de trabalho nas quais a propriedade RunElevated tem um valor de $True e a propriedade RunWithoutNetwork tem um valor de $False.</span><span class="sxs-lookup"><span data-stu-id="c7049-131">The first command gets job options in which the RunElevated property has a value of $True and the RunWithoutNetwork property has a value of $False.</span></span>
<span data-ttu-id="c7049-132">A saída mostra o objeto **JobOptions** que foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="c7049-132">The output shows the **JobOptions** object that was selected.</span></span>

### <span data-ttu-id="c7049-133">Exemplo 4: usar as opções de trabalho para criar um novo trabalho</span><span class="sxs-lookup"><span data-stu-id="c7049-133">Example 4: Use job options to create a new job</span></span>

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

<span data-ttu-id="c7049-134">Este exemplo mostra como usar as opções de trabalho que Get-ScheduledJobOption obtém em um novo trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="c7049-134">This example shows how to use the job options that Get-ScheduledJobOption gets in a new scheduled job.</span></span>

<span data-ttu-id="c7049-135">O primeiro comando usa **Get-ScheduledJobOption** para obter as opções de trabalhos do trabalho agendado BackupTestLogs.</span><span class="sxs-lookup"><span data-stu-id="c7049-135">The first command uses **Get-ScheduledJobOption** to get the jobs options of the BackupTestLogs scheduled job.</span></span>
<span data-ttu-id="c7049-136">O comando salva as opções na variável $Opts.</span><span class="sxs-lookup"><span data-stu-id="c7049-136">The command saves the options in the $Opts variable.</span></span>

<span data-ttu-id="c7049-137">O segundo comando usa Register-ScheduledJob cmdlet para criar um novo trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="c7049-137">The second command uses Register-ScheduledJob cmdlet to create a new scheduled job.</span></span>
<span data-ttu-id="c7049-138">O valor do parâmetro *ScheduledJobOption* é o objeto de opções na variável $Opts.</span><span class="sxs-lookup"><span data-stu-id="c7049-138">The value of the *ScheduledJobOption* parameter is the options object in the $Opts variable.</span></span>

### <span data-ttu-id="c7049-139">Exemplo 5: obter opções de trabalho de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="c7049-139">Example 5: Get job options from a remote computer</span></span>

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

<span data-ttu-id="c7049-140">Esse comando usa o cmdlet Invoke-Command para obter as opções de trabalho agendado do trabalho datademon no computador Srv01.</span><span class="sxs-lookup"><span data-stu-id="c7049-140">This command uses the Invoke-Command cmdlet to get the scheduled job options of the DataDemon job on the Srv01 computer.</span></span>
<span data-ttu-id="c7049-141">O comando salva as opções na variável $O.</span><span class="sxs-lookup"><span data-stu-id="c7049-141">The command saves the options in the $O variable.</span></span>

## <span data-ttu-id="c7049-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c7049-142">PARAMETERS</span></span>

### <span data-ttu-id="c7049-143">-Id</span><span class="sxs-lookup"><span data-stu-id="c7049-143">-Id</span></span>
<span data-ttu-id="c7049-144">Especifica o número de identificação de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="c7049-144">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="c7049-145">O **Get-ScheduledJobOption** obtém as opções de trabalho do trabalho agendado especificado.</span><span class="sxs-lookup"><span data-stu-id="c7049-145">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>

<span data-ttu-id="c7049-146">Para obter os números de identificação dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="c7049-146">To get the identification numbers of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="c7049-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c7049-147">-InputObject</span></span>
<span data-ttu-id="c7049-148">Especifica um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="c7049-148">Specifies a scheduled job.</span></span>
<span data-ttu-id="c7049-149">Insira uma variável que contenha um objeto **ScheduledJob** ou digite um comando ou uma expressão que obtenha um objeto **ScheduledJob** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="c7049-149">Enter a variable that contains a **ScheduledJob** object or type a command or expression that gets a **ScheduledJob** object, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="c7049-150">Você também pode redirecionar um objeto **ScheduledJob** para **Get-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="c7049-150">You can also pipe a **ScheduledJob** object to **Get-ScheduledJobOption** .</span></span>

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

### <span data-ttu-id="c7049-151">-Name</span><span class="sxs-lookup"><span data-stu-id="c7049-151">-Name</span></span>
<span data-ttu-id="c7049-152">Especifica os nomes dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="c7049-152">Specifies the names of scheduled jobs.</span></span>
<span data-ttu-id="c7049-153">O **Get-ScheduledJobOption** obtém as opções de trabalho do trabalho agendado especificado.</span><span class="sxs-lookup"><span data-stu-id="c7049-153">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>
<span data-ttu-id="c7049-154">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="c7049-154">Wildcards are supported.</span></span>

<span data-ttu-id="c7049-155">Para obter os nomes dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="c7049-155">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7049-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c7049-156">CommonParameters</span></span>
<span data-ttu-id="c7049-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c7049-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7049-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c7049-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7049-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c7049-159">INPUTS</span></span>

### <span data-ttu-id="c7049-160">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="c7049-160">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="c7049-161">É possível canalizar um trabalho agendado de Get-ScheduledJob para **Get-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="c7049-161">You can pipe a scheduled job from Get-ScheduledJob to **Get-ScheduledJobOption** .</span></span>

## <span data-ttu-id="c7049-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c7049-162">OUTPUTS</span></span>

### <span data-ttu-id="c7049-163">Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions</span><span class="sxs-lookup"><span data-stu-id="c7049-163">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="c7049-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c7049-164">NOTES</span></span>

## <span data-ttu-id="c7049-165">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c7049-165">RELATED LINKS</span></span>

[<span data-ttu-id="c7049-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c7049-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="c7049-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c7049-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="c7049-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c7049-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="c7049-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c7049-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="c7049-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c7049-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="c7049-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c7049-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="c7049-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c7049-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="c7049-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c7049-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="c7049-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c7049-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="c7049-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c7049-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="c7049-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c7049-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="c7049-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c7049-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="c7049-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c7049-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="c7049-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c7049-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="c7049-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c7049-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="c7049-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c7049-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
