---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193689"
---
# <span data-ttu-id="3c0b6-103">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-103">Disable-JobTrigger</span></span>

## <span data-ttu-id="3c0b6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3c0b6-104">SYNOPSIS</span></span>
<span data-ttu-id="3c0b6-105">Desabilita os disparadores de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-105">Disables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="3c0b6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3c0b6-106">SYNTAX</span></span>

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3c0b6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3c0b6-107">DESCRIPTION</span></span>
<span data-ttu-id="3c0b6-108">O cmdlet **Disable-JobTrigger** desabilita temporariamente os gatilhos dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-108">The **Disable-JobTrigger** cmdlet temporarily disables the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="3c0b6-109">A desabilitação preserva todas as propriedades de gatilho de trabalho, mas impede que o gatilho de trabalho inicie o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-109">Disabling preserves all job trigger properties, but it prevents the job trigger from starting the scheduled job.</span></span>

<span data-ttu-id="3c0b6-110">Para usar esse cmdlet, use o cmdlet Get-JobTrigger para obter os gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-110">To use this cmdlet, use the Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="3c0b6-111">Em seguida, redirecione os gatilhos de trabalho para **Disable-JobTrigger** ou utilize seu parâmetro *InputObject* .</span><span class="sxs-lookup"><span data-stu-id="3c0b6-111">Then pipe the job triggers to **Disable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="3c0b6-112">Para desabilitar um gatilho de trabalho, o cmdlet **Disable-JobTrigger** define a propriedade Enabled do gatilho de trabalho para $false.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-112">To disable a job trigger, the **Disable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $False.</span></span>
<span data-ttu-id="3c0b6-113">Para reabilitar o gatilho de trabalho, use o cmdlet Enable-JobTrigger, que define a propriedade **Enabled** do gatilho de trabalho para $true.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-113">To re-enable the job trigger, use the Enable-JobTrigger cmdlet, which sets the **Enabled** property of the job trigger to $True.</span></span>
<span data-ttu-id="3c0b6-114">Desabilitar um gatilho de trabalho não desabilita o trabalho agendado, como é feito pelo cmdlet Disable-ScheduledJob, mas se você desabilitar todos os gatilhos de trabalho, o efeito será o mesmo que desabilitar o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-114">Disabling a job trigger does not disable the scheduled job, such as is done by the Disable-ScheduledJob cmdlet, but if you disable all job triggers, the effect is the same as disabling the scheduled job.</span></span>

<span data-ttu-id="3c0b6-115">Se você desabilitar um trabalho agendado ou desabilitar todos os gatilhos de trabalho de um trabalho agendado, ainda poderá iniciar o trabalho usando o cmdlet Start-Job ou usar o trabalho agendado desabilitado como um modelo.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-115">If you disable a scheduled job or disable all job triggers of a scheduled job, you can still start the job by using the Start-Job cmdlet or use the disabled scheduled job as a template.</span></span>

<span data-ttu-id="3c0b6-116">**Disable-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="3c0b6-117">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="3c0b6-118">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="3c0b6-119">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="3c0b6-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3c0b6-120">EXAMPLES</span></span>

### <span data-ttu-id="3c0b6-121">Exemplo 1: desabilitar um gatilho de trabalho</span><span class="sxs-lookup"><span data-stu-id="3c0b6-121">Example 1: Disable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

<span data-ttu-id="3c0b6-122">Este comando desabilita o primeiro gatilho (ID = 1) de trabalho agendado de arquivos de backup no computador local.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-122">This command disables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="3c0b6-123">O comando usa o cmdlet Get-JobTrigger para obter o gatilho do trabalho.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-123">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="3c0b6-124">Um operador de pipeline envia o gatilho de trabalho para o cmdlet **Disable-JobTrigger** , que o desabilita.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-124">A pipeline operator sends the job trigger to the **Disable-JobTrigger** cmdlet, which disables it.</span></span>

### <span data-ttu-id="3c0b6-125">Exemplo 2: desabilitar todos os gatilhos de trabalho</span><span class="sxs-lookup"><span data-stu-id="3c0b6-125">Example 2: Disable all job triggers</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="3c0b6-126">Esses comandos desabilitam todos os gatilhos de trabalho nos dois trabalhos agendados e exibem os resultados.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-126">These commands disable all job triggers on two scheduled jobs and display the results.</span></span>

### <span data-ttu-id="3c0b6-127">Exemplo 3: desabilitar o gatilho de trabalho de um trabalho agendado em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="3c0b6-127">Example 3: Disable job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

<span data-ttu-id="3c0b6-128">Este comando desabilita os gatilhos de trabalho diários no trabalho agendado DeployPackage no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-128">This command disables the daily job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="3c0b6-129">O comando usa o cmdlet Invoke-Command para executar os comandos no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-129">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="3c0b6-130">O comando remoto usa o cmdlet Get-JobTrigger para obter os disparadores de trabalho do trabalho agendado DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-130">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="3c0b6-131">Um operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que retorna apenas gatilhos de trabalho diários.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-131">A pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only daily job triggers.</span></span>
<span data-ttu-id="3c0b6-132">Um operador de pipeline envia os gatilhos de trabalho diários para o cmdlet **Disable-JobTrigger** , que os desabilita.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-132">A pipeline operator sends the daily job triggers to the **Disable-JobTrigger** cmdlet, which disables them.</span></span>

## <span data-ttu-id="3c0b6-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3c0b6-133">PARAMETERS</span></span>

### <span data-ttu-id="3c0b6-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3c0b6-134">-InputObject</span></span>
<span data-ttu-id="3c0b6-135">Especifica o gatilho de trabalho a ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-135">Specifies the job trigger to be disabled.</span></span>
<span data-ttu-id="3c0b6-136">Insira uma variável que contenha objetos  **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-136">Enter a variable that contains  **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="3c0b6-137">Também é possível canalizar um objeto **ScheduledJobTrigger** para **Disable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="3c0b6-137">You can also pipe a **ScheduledJobTrigger** object to **Disable-JobTrigger** .</span></span>

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

### <span data-ttu-id="3c0b6-138">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3c0b6-138">-PassThru</span></span>
<span data-ttu-id="3c0b6-139">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-139">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="3c0b6-140">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-140">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3c0b6-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3c0b6-141">-Confirm</span></span>
<span data-ttu-id="3c0b6-142">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-142">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c0b6-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3c0b6-143">-WhatIf</span></span>
<span data-ttu-id="3c0b6-144">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3c0b6-145">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-145">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3c0b6-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3c0b6-146">CommonParameters</span></span>
<span data-ttu-id="3c0b6-147">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3c0b6-148">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3c0b6-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3c0b6-149">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3c0b6-149">INPUTS</span></span>

### <span data-ttu-id="3c0b6-150">Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-150">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="3c0b6-151">É possível redirecionar gatilhos de trabalho para **Disable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="3c0b6-151">You can pipe job triggers to **Disable-JobTrigger** .</span></span>

## <span data-ttu-id="3c0b6-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3c0b6-152">OUTPUTS</span></span>

### <span data-ttu-id="3c0b6-153">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3c0b6-153">None</span></span>
<span data-ttu-id="3c0b6-154">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3c0b6-155">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3c0b6-155">NOTES</span></span>

* <span data-ttu-id="3c0b6-156">**Disable-JobTrigger** não gerará erros ou avisos se você desabilitar um gatilho de trabalho que já esteja desabilitado.</span><span class="sxs-lookup"><span data-stu-id="3c0b6-156">**Disable-JobTrigger** does not generate errors or warnings if you disable a job trigger that is already disabled.</span></span>

## <span data-ttu-id="3c0b6-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3c0b6-157">RELATED LINKS</span></span>

[<span data-ttu-id="3c0b6-158">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-158">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="3c0b6-159">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-159">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="3c0b6-160">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3c0b6-160">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="3c0b6-161">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-161">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="3c0b6-162">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3c0b6-162">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="3c0b6-163">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-163">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="3c0b6-164">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3c0b6-164">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="3c0b6-165">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="3c0b6-165">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="3c0b6-166">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-166">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="3c0b6-167">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="3c0b6-167">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="3c0b6-168">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3c0b6-168">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="3c0b6-169">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-169">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="3c0b6-170">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="3c0b6-170">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="3c0b6-171">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3c0b6-171">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="3c0b6-172">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="3c0b6-172">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="3c0b6-173">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3c0b6-173">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
