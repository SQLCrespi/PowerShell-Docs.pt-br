---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193677"
---
# <span data-ttu-id="0bfcb-103">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-103">Enable-JobTrigger</span></span>

## <span data-ttu-id="0bfcb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0bfcb-104">SYNOPSIS</span></span>
<span data-ttu-id="0bfcb-105">Habilita os disparadores de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-105">Enables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="0bfcb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bfcb-106">SYNTAX</span></span>

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0bfcb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bfcb-107">DESCRIPTION</span></span>
<span data-ttu-id="0bfcb-108">O cmdlet **Enable-JobTrigger** reabilita os gatilhos de trabalho de trabalhos agendados, como aqueles que foram desabilitados usando o cmdlet Disable-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-108">The **Enable-JobTrigger** cmdlet re-enables job triggers of scheduled jobs, such as those that were disabled by using the Disable-JobTrigger cmdlet.</span></span>
<span data-ttu-id="0bfcb-109">Gatilhos de trabalho habilitados e reabilitados podem iniciar trabalhos agendados imediatamente, não é necessário reiniciar o Windows ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-109">Enabled and re-enabled job triggers can start scheduled jobs immediately; there is no need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="0bfcb-110">Para usar esse cmdlet, use o cmdlet Get-JobTrigger para obter os gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-110">To use this cmdlet, use the  Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="0bfcb-111">Em seguida, direcione os gatilhos de trabalho para **Enable-JobTrigger** ou use seu parâmetro *InputObject* .</span><span class="sxs-lookup"><span data-stu-id="0bfcb-111">Then pipe the job triggers to **Enable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="0bfcb-112">Para habilitar um gatilho de trabalho, o cmdlet **Enable-JobTrigger** define a propriedade Enabled do gatilho de trabalho para $true.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-112">To enable a job trigger, the **Enable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $True.</span></span>

<span data-ttu-id="0bfcb-113">**Enable-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-113">**Enable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="0bfcb-114">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-114">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="0bfcb-115">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-115">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="0bfcb-116">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0bfcb-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0bfcb-117">EXAMPLES</span></span>

### <span data-ttu-id="0bfcb-118">Exemplo 1: habilitar um gatilho de trabalho</span><span class="sxs-lookup"><span data-stu-id="0bfcb-118">Example 1: Enable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

<span data-ttu-id="0bfcb-119">Este comando habilita o primeiro gatilho (ID = 1) de trabalho agendado de arquivos de backup no computador local.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-119">This command enables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="0bfcb-120">O comando usa o cmdlet Get-JobTrigger para obter o gatilho do trabalho.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-120">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="0bfcb-121">Um operador de pipeline envia o gatilho de trabalho para o cmdlet **Enable-JobTrigger** , que o habilita.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-121">A pipeline operator sends the job trigger to the **Enable-JobTrigger** cmdlet, which enables it.</span></span>

### <span data-ttu-id="0bfcb-122">Exemplo 2: habilitar todos os gatilhos de trabalho</span><span class="sxs-lookup"><span data-stu-id="0bfcb-122">Example 2: Enable all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

<span data-ttu-id="0bfcb-123">O comando usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-123">The command uses the Get-ScheduledJob cmdlet to get  the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="0bfcb-124">Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet Get-JobTrigger, que obtém todos os gatilhos de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-124">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="0bfcb-125">Outro operador pipeline envia os gatilhos de trabalho para o cmdlet **Enable-JobTrigger** , que os habilita.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-125">Another pipeline operator sends the job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="0bfcb-126">Exemplo 3: habilitar o gatilho de trabalho de um trabalho agendado em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="0bfcb-126">Example 3: Enable the job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

<span data-ttu-id="0bfcb-127">Este comando reabilita os gatilhos de trabalho AtLogon no trabalho agendado DeployPackage no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-127">This command re-enables the AtLogon job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="0bfcb-128">O comando usa o cmdlet Invoke-Command para executar os comandos no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-128">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="0bfcb-129">O comando remoto usa o cmdlet Get-JobTrigger para obter os disparadores de trabalho do trabalho agendado DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-129">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="0bfcb-130">Um operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que retorna somente gatilhos de trabalho AtLogon.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-130">A pipeline operator sends the job triggers to the Where-Object cmdlet which returns only AtLogon job triggers.</span></span>
<span data-ttu-id="0bfcb-131">Um operador de pipeline envia os gatilhos de trabalho AtLogon para o cmdlet **Enable-JobTrigger** , que os habilita.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-131">A pipeline operator sends the AtLogon job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="0bfcb-132">Exemplo 4: Exibir gatilhos de trabalho desabilitados</span><span class="sxs-lookup"><span data-stu-id="0bfcb-132">Example 4: Display disabled job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="0bfcb-133">Este comando exibe todos os gatilhos de trabalho desabilitados de todos os trabalhos agendados em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-133">This command displays all disabled job triggers of all scheduled jobs in a table.</span></span>
<span data-ttu-id="0bfcb-134">Você pode usar um comando como este para descobrir os gatilhos de trabalho que talvez precisem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-134">You can use a command like this one to discover job triggers that might need to be enabled.</span></span>

<span data-ttu-id="0bfcb-135">O comando usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-135">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="0bfcb-136">Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet Get-JobTrigger, que obtém todos os gatilhos de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-136">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="0bfcb-137">Outro operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que retorna somente gatilhos de trabalho que estão desabilitados, ou seja, onde o valor da propriedade Enabled do gatilho de trabalho não é (!) true.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-137">Another pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only job triggers that are disabled, that is, where the value of the Enabled property of the job trigger is not (!) true.</span></span>

<span data-ttu-id="0bfcb-138">Outro operador de pipeline envia os gatilhos de trabalho desabilitados para o cmdlet Format-Table, que exibe as propriedades selecionadas dos gatilhos de trabalho em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-138">Another pipeline operator sends the disabled job triggers to the Format-Table cmdlet, which displays the selected properties of the job triggers in a table.</span></span>
<span data-ttu-id="0bfcb-139">As propriedades incluem uma nova propriedade JobName que exibe o nome do trabalho agendado na propriedade de JobDefinition do gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-139">The properties include a new JobName property that displays the name of the scheduled job in the JobDefinition property of the job trigger.</span></span>

## <span data-ttu-id="0bfcb-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bfcb-140">PARAMETERS</span></span>

### <span data-ttu-id="0bfcb-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0bfcb-141">-InputObject</span></span>
<span data-ttu-id="0bfcb-142">Especifica o gatilho de trabalho a ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-142">Specifies the job trigger to enable.</span></span>
<span data-ttu-id="0bfcb-143">Insira uma variável que contenha objetos **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-143">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="0bfcb-144">Também é possível canalizar um objeto **ScheduledJobTrigger** para **Enable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="0bfcb-144">You can also pipe a **ScheduledJobTrigger** object to **Enable-JobTrigger** .</span></span>

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

### <span data-ttu-id="0bfcb-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0bfcb-145">-PassThru</span></span>
<span data-ttu-id="0bfcb-146">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-146">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="0bfcb-147">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0bfcb-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0bfcb-148">-Confirm</span></span>
<span data-ttu-id="0bfcb-149">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0bfcb-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0bfcb-150">-WhatIf</span></span>
<span data-ttu-id="0bfcb-151">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0bfcb-152">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0bfcb-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bfcb-153">CommonParameters</span></span>
<span data-ttu-id="0bfcb-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bfcb-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0bfcb-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bfcb-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0bfcb-156">INPUTS</span></span>

### <span data-ttu-id="0bfcb-157">Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="0bfcb-158">Você pode canalizar gatilhos de trabalho para **Enable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="0bfcb-158">You can pipe job triggers to **Enable-JobTrigger** .</span></span>

## <span data-ttu-id="0bfcb-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0bfcb-159">OUTPUTS</span></span>

### <span data-ttu-id="0bfcb-160">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0bfcb-160">None</span></span>
<span data-ttu-id="0bfcb-161">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0bfcb-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0bfcb-162">NOTES</span></span>

* <span data-ttu-id="0bfcb-163">**Enable-JobTrigger** não gerará erros ou avisos se você habilitar um gatilho de trabalho que já esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="0bfcb-163">**Enable-JobTrigger** does not generate errors or warnings if you enable a job trigger that is already enabled.</span></span>

## <span data-ttu-id="0bfcb-164">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0bfcb-164">RELATED LINKS</span></span>

[<span data-ttu-id="0bfcb-165">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-165">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="0bfcb-166">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-166">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="0bfcb-167">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0bfcb-167">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="0bfcb-168">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-168">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="0bfcb-169">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0bfcb-169">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="0bfcb-170">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-170">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="0bfcb-171">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0bfcb-171">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="0bfcb-172">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0bfcb-172">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="0bfcb-173">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-173">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="0bfcb-174">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0bfcb-174">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="0bfcb-175">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0bfcb-175">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="0bfcb-176">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-176">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="0bfcb-177">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0bfcb-177">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="0bfcb-178">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0bfcb-178">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="0bfcb-179">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0bfcb-179">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="0bfcb-180">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0bfcb-180">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
