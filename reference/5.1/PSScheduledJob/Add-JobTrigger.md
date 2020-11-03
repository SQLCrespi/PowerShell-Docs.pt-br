---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193690"
---
# <span data-ttu-id="cfc12-103">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-103">Add-JobTrigger</span></span>

## <span data-ttu-id="cfc12-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="cfc12-104">SYNOPSIS</span></span>
<span data-ttu-id="cfc12-105">Adiciona disparadores de trabalho a trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-105">Adds job triggers to scheduled jobs.</span></span>

## <span data-ttu-id="cfc12-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfc12-106">SYNTAX</span></span>

### <span data-ttu-id="cfc12-107">JobDefinition (padrão)</span><span class="sxs-lookup"><span data-stu-id="cfc12-107">JobDefinition (Default)</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### <span data-ttu-id="cfc12-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="cfc12-108">JobDefinitionId</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="cfc12-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="cfc12-109">JobDefinitionName</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="cfc12-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cfc12-110">DESCRIPTION</span></span>
<span data-ttu-id="cfc12-111">O cmdlet **Add-JobTrigger** adiciona gatilhos de trabalho a trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-111">The **Add-JobTrigger** cmdlet adds job triggers to scheduled jobs.</span></span>
<span data-ttu-id="cfc12-112">Você pode usá-lo para adicionar vários gatilhos a vários trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-112">You can use it to add multiple triggers to multiple scheduled jobs.</span></span>

<span data-ttu-id="cfc12-113">Um gatilho de trabalho inicia um trabalho agendado em um agendamento de uso único ou recorrente ou quando ocorre um evento.</span><span class="sxs-lookup"><span data-stu-id="cfc12-113">A job trigger starts a scheduled job on a one-time or recurring schedule or when an event occurs.</span></span>

<span data-ttu-id="cfc12-114">Use o parâmetro *Trigger* de **Add-JobTrigger** para identificar os gatilhos de trabalho a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-114">Use the *Trigger* parameter of **Add-JobTrigger** to identify the job triggers to add.</span></span>
<span data-ttu-id="cfc12-115">Use os parâmetros *Name* , *ID* ou *InputObject* de **Add-JobTrigger** para identificar o trabalho agendado ao qual os gatilhos são adicionados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-115">Use the *Name* , *ID* , or *InputObject* parameters of **Add-JobTrigger** to identify the scheduled job to which the triggers are added.</span></span>

<span data-ttu-id="cfc12-116">Para criar gatilhos de trabalho para o valor do parâmetro *Trigger* , use o cmdlet New-JobTrigger ou use uma tabela de hash para especificar o gatilho do trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfc12-116">To create job triggers for the value of the *Trigger* parameter, use the New-JobTrigger cmdlet or use a hash table to specify the job trigger.</span></span>

<span data-ttu-id="cfc12-117">**Add-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfc12-117">**Add-JobTrigger** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="cfc12-118">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="cfc12-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="cfc12-119">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="cfc12-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="cfc12-120">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="cfc12-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="cfc12-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="cfc12-121">EXAMPLES</span></span>

### <span data-ttu-id="cfc12-122">Exemplo 1: adicionar um gatilho de trabalho a um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="cfc12-122">Example 1: Add a job trigger to a scheduled job</span></span>

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

<span data-ttu-id="cfc12-123">Estes comandos adicionam o gatilho de trabalho Daily ao trabalho agendado TestJob.</span><span class="sxs-lookup"><span data-stu-id="cfc12-123">These commands add the Daily job trigger to the TestJob scheduled job.</span></span>

<span data-ttu-id="cfc12-124">O primeiro comando usa o cmdlet New-JobTrigger para criar um gatilho de trabalho que inicia um trabalho agendado todos os dias às 3:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="cfc12-124">The first command uses the New-JobTrigger cmdlet to create a job trigger that starts a scheduled job every day at 3:00 a.m.</span></span>
<span data-ttu-id="cfc12-125">O comando salva o gatilho de trabalho na variável $Daily.</span><span class="sxs-lookup"><span data-stu-id="cfc12-125">The command saves the job trigger in the $Daily variable.</span></span>

<span data-ttu-id="cfc12-126">O segundo comando usa o cmdlet **Add-JobTrigger** para adicionar o gatilho de trabalho na variável $Startup ao trabalho agendado TestJob.</span><span class="sxs-lookup"><span data-stu-id="cfc12-126">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in the $Startup variable to the TestJob scheduled job.</span></span>

### <span data-ttu-id="cfc12-127">Exemplo 2: adicionar um gatilho de trabalho a vários trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="cfc12-127">Example 2: Add a job trigger to several scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

<span data-ttu-id="cfc12-128">Este comando adiciona um gatilho de trabalho AtStartup a todos os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="cfc12-128">This command adds an AtStartup job trigger to all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="cfc12-129">Ele usa o Get-ScheduledJob para obter todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="cfc12-129">It uses the Get-ScheduledJob to get all of the scheduled jobs on the computer.</span></span>
<span data-ttu-id="cfc12-130">Ele usa um operador de pipeline (|) para enviar os trabalhos para o cmdlet **Add-JobTrigger** , que adiciona o gatilho de trabalho a cada um dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-130">It uses a pipeline operator (|) to send the jobs to the **Add-JobTrigger** cmdlet, which adds the job trigger to each of the scheduled jobs.</span></span>
<span data-ttu-id="cfc12-131">O valor do parâmetro *Trigger* é um comando New-JobTrigger que cria o gatilho de trabalho AtStartup.</span><span class="sxs-lookup"><span data-stu-id="cfc12-131">The value of the *Trigger* parameter is a New-JobTrigger command that creates the AtStartup job trigger.</span></span>

### <span data-ttu-id="cfc12-132">Exemplo 3: copiar um gatilho de trabalho</span><span class="sxs-lookup"><span data-stu-id="cfc12-132">Example 3: Copy a job trigger</span></span>

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

<span data-ttu-id="cfc12-133">Estes comandos copiam o gatilho de trabalho do trabalho agendado BackupArchives e adicionam-no aos trabalhos agendados TestBackup e BackupLogs.</span><span class="sxs-lookup"><span data-stu-id="cfc12-133">These commands copy the job trigger from the BackupArchives scheduled job and add it to the TestBackup and BackupLogs scheduled jobs.</span></span>

<span data-ttu-id="cfc12-134">O primeiro comando usa o cmdlet Get-JobTrigger para obter o gatilho de trabalho do trabalho agendado trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfc12-134">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the BackupArchives scheduled job.</span></span>
<span data-ttu-id="cfc12-135">O comando salva o gatilho na variável $t.</span><span class="sxs-lookup"><span data-stu-id="cfc12-135">The command saves the trigger in the $t variable.</span></span>

<span data-ttu-id="cfc12-136">O segundo comando usa o cmdlet **Add-JobTrigger** para adicionar o gatilho de trabalho em $t aos trabalhos agendados TestBackup e BackupLogs.</span><span class="sxs-lookup"><span data-stu-id="cfc12-136">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in $t to the TestBackup and BackupLogs scheduled jobs.</span></span>

## <span data-ttu-id="cfc12-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfc12-137">PARAMETERS</span></span>

### <span data-ttu-id="cfc12-138">-Id</span><span class="sxs-lookup"><span data-stu-id="cfc12-138">-Id</span></span>
<span data-ttu-id="cfc12-139">Especifica os números de identificação dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-139">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="cfc12-140">**Add-JobTrigger** adiciona o gatilho de trabalho a trabalhos agendados especificados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-140">**Add-JobTrigger** adds the job trigger to the specified scheduled jobs.</span></span>

<span data-ttu-id="cfc12-141">Para obter o número de identificação de trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="cfc12-141">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfc12-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cfc12-142">-InputObject</span></span>
<span data-ttu-id="cfc12-143">Especifica os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-143">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="cfc12-144">Insira uma variável que contenha objetos **ScheduledJob** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJob** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="cfc12-144">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="cfc12-145">Você também pode canalizar objetos **ScheduledJob** para **Add-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="cfc12-145">You can also pipe **ScheduledJob** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cfc12-146">-Name</span><span class="sxs-lookup"><span data-stu-id="cfc12-146">-Name</span></span>
<span data-ttu-id="cfc12-147">Especifica os nomes dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-147">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="cfc12-148">**Add-JobTrigger** adiciona os gatilhos de trabalho a trabalhos agendados especificados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-148">**Add-JobTrigger** adds the job triggers to the specified scheduled jobs.</span></span>
<span data-ttu-id="cfc12-149">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="cfc12-149">Wildcards are supported.</span></span>

<span data-ttu-id="cfc12-150">Para obter os nomes dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="cfc12-150">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfc12-151">-Gatilho</span><span class="sxs-lookup"><span data-stu-id="cfc12-151">-Trigger</span></span>
<span data-ttu-id="cfc12-152">Especifica os gatilhos de trabalho a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="cfc12-152">Specifies the job triggers to add.</span></span>
<span data-ttu-id="cfc12-153">Insira uma tabela de hash que especifique gatilhos de trabalho ou uma variável que contenha objetos **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="cfc12-153">Enter a hash table that specifies job triggers or a variable that contains **ScheduledJobTrigger** objects, or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="cfc12-154">Você também pode canalizar objetos **ScheduledJobTrigger** para **Add-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="cfc12-154">You can also pipe **ScheduledJobTrigger** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cfc12-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cfc12-155">CommonParameters</span></span>
<span data-ttu-id="cfc12-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cfc12-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfc12-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cfc12-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfc12-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="cfc12-158">INPUTS</span></span>

### <span data-ttu-id="cfc12-159">Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger, Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="cfc12-159">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger, Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="cfc12-160">É possível redirecionar gatilhos de trabalho ou trabalhos agendados para **Add-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="cfc12-160">You can pipe job triggers or scheduled jobs to **Add-JobTrigger** .</span></span>

## <span data-ttu-id="cfc12-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="cfc12-161">OUTPUTS</span></span>

### <span data-ttu-id="cfc12-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cfc12-162">None</span></span>
<span data-ttu-id="cfc12-163">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="cfc12-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="cfc12-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="cfc12-164">NOTES</span></span>

## <span data-ttu-id="cfc12-165">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="cfc12-165">RELATED LINKS</span></span>

[<span data-ttu-id="cfc12-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="cfc12-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="cfc12-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cfc12-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="cfc12-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="cfc12-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cfc12-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="cfc12-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="cfc12-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cfc12-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="cfc12-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cfc12-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="cfc12-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="cfc12-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cfc12-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="cfc12-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cfc12-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="cfc12-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="cfc12-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cfc12-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="cfc12-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cfc12-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="cfc12-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cfc12-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="cfc12-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cfc12-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
