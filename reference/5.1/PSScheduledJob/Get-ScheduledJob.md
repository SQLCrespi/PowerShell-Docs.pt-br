---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193675"
---
# <span data-ttu-id="098f8-103">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="098f8-103">Get-ScheduledJob</span></span>

## <span data-ttu-id="098f8-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="098f8-104">SYNOPSIS</span></span>
<span data-ttu-id="098f8-105">Obtém os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="098f8-105">Gets scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="098f8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="098f8-106">SYNTAX</span></span>

### <span data-ttu-id="098f8-107">DefinitionId (padrão)</span><span class="sxs-lookup"><span data-stu-id="098f8-107">DefinitionId (Default)</span></span>

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="098f8-108">Definitionname</span><span class="sxs-lookup"><span data-stu-id="098f8-108">DefinitionName</span></span>

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="098f8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="098f8-109">DESCRIPTION</span></span>
<span data-ttu-id="098f8-110">O cmdlet **Get-ScheduledJob** obtém os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="098f8-110">The **Get-ScheduledJob** cmdlet gets scheduled jobs on the local computer.</span></span>
<span data-ttu-id="098f8-111">**Get-ScheduledJob** obtém apenas os trabalhos agendados que são criados pelo usuário atual usando o cmdlet Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="098f8-111">**Get-ScheduledJob** gets only scheduled jobs that are created by the current user using the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="098f8-112">Embora trabalhos que são criados usando o cmdlet **Register-ScheduledJob** apareçam no Agendador de tarefas, o **Get-ScheduledJob** obtém apenas os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="098f8-112">Although jobs that are created by using the **Register-ScheduledJob** cmdlet appear in Task Scheduler, **Get-ScheduledJob** gets only scheduled jobs.</span></span>
<span data-ttu-id="098f8-113">Ele não obtém os trabalhos agendados que são criados no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="098f8-113">It does not get scheduled tasks created in Task Scheduler.</span></span>

<span data-ttu-id="098f8-114">Sem parâmetros, o **Get-ScheduledJob** obtém todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="098f8-114">Without parameters, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="098f8-115">Você pode usar os parâmetros de **Get-ScheduledJob** para obter os trabalhos agendados pelo nome ou ID e examiná-los ou direcioná-los para outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="098f8-115">You can use the parameters of **Get-ScheduledJob** to get scheduled jobs by ID or name and examine them or pipe them to other cmdlets.</span></span>

<span data-ttu-id="098f8-116">**Get-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="098f8-116">**Get-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="098f8-117">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="098f8-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="098f8-118">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="098f8-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="098f8-119">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="098f8-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="098f8-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="098f8-120">EXAMPLES</span></span>

### <span data-ttu-id="098f8-121">Exemplo 1: obter todos os trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="098f8-121">Example 1: Get all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob
```

<span data-ttu-id="098f8-122">Este comando obtém todos os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="098f8-122">This command gets all scheduled jobs on the local computer.</span></span>

### <span data-ttu-id="098f8-123">Exemplo 2: obter trabalhos agendados por nome</span><span class="sxs-lookup"><span data-stu-id="098f8-123">Example 2: Get scheduled jobs by name</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

<span data-ttu-id="098f8-124">Esse comando obtém todos os trabalhos agendados no computador que têm nomes que incluem backup ou arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="098f8-124">This command gets all scheduled jobs on the computer that have names that include Backup or Archive.</span></span>
<span data-ttu-id="098f8-125">Esse formato de comando permite pesquisar trabalhos específicos.</span><span class="sxs-lookup"><span data-stu-id="098f8-125">This command format lets you search for particular jobs.</span></span>

### <span data-ttu-id="098f8-126">Exemplo 3: obter trabalhos agendados em computadores remotos</span><span class="sxs-lookup"><span data-stu-id="098f8-126">Example 3: Get scheduled jobs on remote computers</span></span>

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

<span data-ttu-id="098f8-127">Esse comando obtém todos os trabalhos agendados nos computadores que estão listados no arquivo txt.</span><span class="sxs-lookup"><span data-stu-id="098f8-127">This command gets all scheduled jobs on the computers that are listed in the Servers.txt file.</span></span>
<span data-ttu-id="098f8-128">O comando usa o cmdlet Invoke-Command para executar um comando **Get-ScheduleJob** em cada computador.</span><span class="sxs-lookup"><span data-stu-id="098f8-128">The command uses the Invoke-Command cmdlet to run a **Get-ScheduleJob** command on each computer.</span></span>

### <span data-ttu-id="098f8-129">Exemplo 4: direcionar trabalhos agendados para outros cmdlets</span><span class="sxs-lookup"><span data-stu-id="098f8-129">Example 4: Pipe scheduled jobs to other cmdlets</span></span>

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

<span data-ttu-id="098f8-130">Esse comando obtém os disparadores de trabalho dos trabalhos agendados DailyBackup e WeeklyBackup.</span><span class="sxs-lookup"><span data-stu-id="098f8-130">This command gets the job triggers of the DailyBackup and WeeklyBackup scheduled jobs.</span></span>
<span data-ttu-id="098f8-131">Ele usa o cmdlet **Get-ScheduledJob** para obter os trabalhos agendados e o cmdlet Get-JobTrigger para obter os disparadores de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="098f8-131">It uses the **Get-ScheduledJob** cmdlet to get the scheduled jobs and the Get-JobTrigger cmdlet to get the job triggers of the scheduled jobs.</span></span>

## <span data-ttu-id="098f8-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="098f8-132">PARAMETERS</span></span>

### <span data-ttu-id="098f8-133">-Id</span><span class="sxs-lookup"><span data-stu-id="098f8-133">-Id</span></span>
<span data-ttu-id="098f8-134">Obtém somente os trabalhos agendados com o número de identificação especificado (ID).</span><span class="sxs-lookup"><span data-stu-id="098f8-134">Gets only the scheduled jobs with the specified identification number (ID).</span></span>
<span data-ttu-id="098f8-135">Insira um ou mais IDs dos trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="098f8-135">Enter one or more IDs of scheduled jobs on the computer.</span></span>
<span data-ttu-id="098f8-136">Por padrão, o **Get-ScheduledJob** obtém todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="098f8-136">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="098f8-137">-Name</span><span class="sxs-lookup"><span data-stu-id="098f8-137">-Name</span></span>
<span data-ttu-id="098f8-138">Obtém somente os trabalhos agendados com os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="098f8-138">Gets only the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="098f8-139">Insira um ou mais nomes dos trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="098f8-139">Enter one or more names of scheduled jobs on the computer.</span></span>
<span data-ttu-id="098f8-140">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="098f8-140">Wildcards are supported.</span></span>
<span data-ttu-id="098f8-141">Por padrão, o **Get-ScheduledJob** obtém todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="098f8-141">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="098f8-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="098f8-142">CommonParameters</span></span>
<span data-ttu-id="098f8-143">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="098f8-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="098f8-144">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="098f8-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="098f8-145">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="098f8-145">INPUTS</span></span>

### <span data-ttu-id="098f8-146">Nenhum</span><span class="sxs-lookup"><span data-stu-id="098f8-146">None</span></span>
<span data-ttu-id="098f8-147">Não é possível canalizar a entrada para **Get-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="098f8-147">You cannot pipe input to **Get-ScheduledJob** .</span></span>

## <span data-ttu-id="098f8-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="098f8-148">OUTPUTS</span></span>

### <span data-ttu-id="098f8-149">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="098f8-149">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="098f8-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="098f8-150">NOTES</span></span>

* <span data-ttu-id="098f8-151">Cada trabalho agendado é salvo em um subdiretório do diretório $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs no computador local.</span><span class="sxs-lookup"><span data-stu-id="098f8-151">Each scheduled job is saved in a subdirectory of the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the local computer.</span></span> <span data-ttu-id="098f8-152">O subdiretório é nomeado de acordo com o trabalho agendado e contém o arquivo XML para o trabalho agendado e registros do histórico de execução.</span><span class="sxs-lookup"><span data-stu-id="098f8-152">The subdirectory is named for the scheduled job and contains the XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="098f8-153">Para obter mais informações sobre trabalhos agendados no disco, consulte about_Scheduled_Jobs_Advanced.</span><span class="sxs-lookup"><span data-stu-id="098f8-153">For more information about scheduled jobs on disk, see about_Scheduled_Jobs_Advanced.</span></span>
* <span data-ttu-id="098f8-154">Trabalhos agendados que você cria no Windows PowerShell aparecem no Agendador de tarefas na pasta Library\Microsoft\Windows\PowerShell\ScheduledJobs do Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="098f8-154">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs folder.</span></span> <span data-ttu-id="098f8-155">Você pode usar o Agendador de tarefas para exibir e editar o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="098f8-155">You can use Task Scheduler to view and edit the scheduled job.</span></span>
* <span data-ttu-id="098f8-156">Você pode usar o Agendador de tarefas, a ferramenta de linha de comando SchTasks.exe e os cmdlets do Agendador de tarefas para gerenciar trabalhos agendados criados por você com os cmdlets do Trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="098f8-156">You can use Task Scheduler, the SchTasks.exe command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="098f8-157">No entanto, você não pode usar os cmdlets do Trabalho agendado para gerenciar tarefas que você cria no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="098f8-157">However, you cannot use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

## <span data-ttu-id="098f8-158">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="098f8-158">RELATED LINKS</span></span>

[<span data-ttu-id="098f8-159">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="098f8-159">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="098f8-160">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="098f8-160">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="098f8-161">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="098f8-161">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="098f8-162">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="098f8-162">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="098f8-163">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="098f8-163">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="098f8-164">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="098f8-164">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="098f8-165">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="098f8-165">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="098f8-166">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="098f8-166">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="098f8-167">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="098f8-167">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="098f8-168">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="098f8-168">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="098f8-169">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="098f8-169">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="098f8-170">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="098f8-170">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="098f8-171">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="098f8-171">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="098f8-172">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="098f8-172">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="098f8-173">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="098f8-173">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="098f8-174">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="098f8-174">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
