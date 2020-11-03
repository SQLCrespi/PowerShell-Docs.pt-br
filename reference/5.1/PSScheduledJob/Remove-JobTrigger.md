---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193669"
---
# <span data-ttu-id="13754-103">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-103">Remove-JobTrigger</span></span>

## <span data-ttu-id="13754-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="13754-104">SYNOPSIS</span></span>
<span data-ttu-id="13754-105">Excluir gatilhos de trabalho de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-105">Delete job triggers from scheduled jobs.</span></span>

## <span data-ttu-id="13754-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="13754-106">SYNTAX</span></span>

### <span data-ttu-id="13754-107">JobDefinition (padrão)</span><span class="sxs-lookup"><span data-stu-id="13754-107">JobDefinition (Default)</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### <span data-ttu-id="13754-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="13754-108">JobDefinitionId</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="13754-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="13754-109">JobDefinitionName</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="13754-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="13754-110">DESCRIPTION</span></span>
<span data-ttu-id="13754-111">O cmdlet **Remove-JobTrigger** exclui os gatilhos de trabalho dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-111">The **Remove-JobTrigger** cmdlet deletes job triggers from scheduled jobs.</span></span>

<span data-ttu-id="13754-112">Um gatilho de trabalho define uma agenda recorrente ou condições para iniciar um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="13754-112">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="13754-113">Para gerenciar gatilhos de trabalho, use os cmdlets New-JobTrigger, Add-JobTrigger, Set-JobTrigger e Set-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="13754-113">To manage job triggers, use the New-JobTrigger, Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJob cmdlets.</span></span>

<span data-ttu-id="13754-114">Use os parâmetros *Name* , *ID* ou *InputObject* de **Remove-JobTrigger** para identificar os trabalhos agendados dos quais os gatilhos são removidos.</span><span class="sxs-lookup"><span data-stu-id="13754-114">Use the *Name* , *ID* , or *InputObject* parameters of **Remove-JobTrigger** to identify the scheduled jobs from which the triggers are removed.</span></span>
<span data-ttu-id="13754-115">Use o parâmetro *triggerid* para identificar os gatilhos de trabalho a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="13754-115">Use the *TriggerID* parameter to identify the job triggers to delete.</span></span>
<span data-ttu-id="13754-116">Por padrão, o **Remove-JobTrigger** exclui todos os gatilhos de trabalho de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="13754-116">By default, **Remove-JobTrigger** deletes all job triggers of a scheduled job.</span></span>

<span data-ttu-id="13754-117">**Remove-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13754-117">**Remove-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="13754-118">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="13754-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="13754-119">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="13754-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="13754-120">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="13754-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="13754-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="13754-121">EXAMPLES</span></span>

### <span data-ttu-id="13754-122">Exemplo 1: excluir todos os gatilhos de trabalho</span><span class="sxs-lookup"><span data-stu-id="13754-122">Example 1: Delete all job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

<span data-ttu-id="13754-123">Este comando exclui todos os gatilhos de trabalho agendados que têm nomes que começam com teste.</span><span class="sxs-lookup"><span data-stu-id="13754-123">This command deletes all job triggers from scheduled job that have names that begin with Test.</span></span>

### <span data-ttu-id="13754-124">Exemplo 2: excluir gatilhos de trabalho selecionados</span><span class="sxs-lookup"><span data-stu-id="13754-124">Example 2: Delete selected job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

<span data-ttu-id="13754-125">Esse comando exclui somente o terceiro gatilho (ID = 3) do trabalho agendado BackupArchive.</span><span class="sxs-lookup"><span data-stu-id="13754-125">This command deletes only the third trigger (ID = 3) from the BackupArchive scheduled job.</span></span>

### <span data-ttu-id="13754-126">Exemplo 3: excluir gatilhos de trabalho AtStartup de todos os trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="13754-126">Example 3: Delete AtStartup job triggers from all scheduled jobs</span></span>

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

<span data-ttu-id="13754-127">Esta função exclui todos os gatilhos de trabalho AtStartup de todos os trabalhos no computador local.</span><span class="sxs-lookup"><span data-stu-id="13754-127">This function deletes all AtStartup job triggers from all jobs on the local computer.</span></span>
<span data-ttu-id="13754-128">Para usar a função, execute a função em sua sessão e digite `Delete-AtStartup` .</span><span class="sxs-lookup"><span data-stu-id="13754-128">To use the function, run the function in your session and then type `Delete-AtStartup`.</span></span>

<span data-ttu-id="13754-129">A função Delete-AtStartup contém um único comando.</span><span class="sxs-lookup"><span data-stu-id="13754-129">The Delete-AtStartup function contains a single command.</span></span>
<span data-ttu-id="13754-130">O comando usa o cmdlet Get-ScheduledJob para obter os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="13754-130">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="13754-131">Um operador de pipeline (|) envia os trabalhos agendados para o cmdlet Get-JobTrigger, que obtém todos os gatilhos de trabalho de cada um dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-131">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all of the job triggers from each of the scheduled jobs.</span></span>
<span data-ttu-id="13754-132">Um operador de pipeline envia os gatilhos de trabalho para o cmdlet Where-Object, que seleciona os gatilhos de trabalho em que o valor da propriedade Frequency do gatilho do trabalho é igual a AtStartup.</span><span class="sxs-lookup"><span data-stu-id="13754-132">A pipeline operator sends the job triggers to the Where-Object cmdlet, which selects job triggers where the value of the Frequency property of the job trigger equals AtStartup.</span></span>

<span data-ttu-id="13754-133">Os objetos **JobTrigger** têm uma propriedade **JobDefinition** que contém o trabalho agendado que eles disparam.</span><span class="sxs-lookup"><span data-stu-id="13754-133">**JobTrigger** objects have a **JobDefinition** property that contains the scheduled job that they trigger.</span></span>
<span data-ttu-id="13754-134">O restante do comando usa esse recurso valioso.</span><span class="sxs-lookup"><span data-stu-id="13754-134">The remainder of the command uses that valuable feature.</span></span>

<span data-ttu-id="13754-135">Um operador de pipeline envia os gatilhos de trabalho AtStartup para o cmdlet ForEach-Object, que executa um comando **Remove-JobTrigger** em cada gatilho AtStartup.</span><span class="sxs-lookup"><span data-stu-id="13754-135">A pipeline operator sends the AtStartup job triggers to the ForEach-Object cmdlet, which runs a **Remove-JobTrigger** command on each AtStartup trigger.</span></span>
<span data-ttu-id="13754-136">O valor do parâmetro *InputObject\*\*\*Remove-JobTrigger*\* é o trabalho agendado na propriedade JobDefinition do gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="13754-136">The value of the *InputObject* parameter of **Remove-JobTrigger** is the scheduled job in the JobDefinition property of the job trigger.</span></span>
<span data-ttu-id="13754-137">O valor do parâmetro *TriggerID* é o identificador na propriedade ID do gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="13754-137">The value of the *TriggerID* parameter is the identifier in the ID property of the job trigger.</span></span>

### <span data-ttu-id="13754-138">Exemplo 4: excluir um gatilho de trabalho de um trabalho agendado remoto</span><span class="sxs-lookup"><span data-stu-id="13754-138">Example 4: Delete a job trigger from a remote scheduled job</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

<span data-ttu-id="13754-139">Esse comando exclui o primeiro gatilho de trabalho do trabalho Inventory no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="13754-139">This command deletes the first job trigger from the Inventory job on the Server01 computer.</span></span>

<span data-ttu-id="13754-140">O comando usa o cmdlet **Invoke-Command** para executar o cmdlet **Remove-JobTrigger** no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="13754-140">The command uses the **Invoke-Command** cmdlet to run the **Remove-JobTrigger** cmdlet on the Server01 computer.</span></span>
<span data-ttu-id="13754-141">O cmdlet **Remove-JobTrigger** usa o parâmetro *ID* para identificar o trabalho agendado de inventário e o parâmetro *triggerid* para especificar o primeiro gatilho.</span><span class="sxs-lookup"><span data-stu-id="13754-141">The **Remove-JobTrigger** cmdlet uses the *ID* parameter to identify the Inventory scheduled job and the *TriggerID* parameter to specify the first trigger.</span></span>
<span data-ttu-id="13754-142">O parâmetro *ID* é especialmente útil quando vários trabalhos agendados têm nomes iguais ou semelhantes.</span><span class="sxs-lookup"><span data-stu-id="13754-142">The *ID* parameter is especially useful when multiple scheduled jobs have the same or similar names.</span></span>

## <span data-ttu-id="13754-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="13754-143">PARAMETERS</span></span>

### <span data-ttu-id="13754-144">-Id</span><span class="sxs-lookup"><span data-stu-id="13754-144">-Id</span></span>
<span data-ttu-id="13754-145">Especifica os números de identificação dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-145">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="13754-146">O **Remove-JobTrigger** exclui os gatilhos dos trabalhos agendados especificados.</span><span class="sxs-lookup"><span data-stu-id="13754-146">**Remove-JobTrigger** deletes job triggers from the specified scheduled jobs.</span></span>

<span data-ttu-id="13754-147">Para obter o número de identificação de trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="13754-147">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="13754-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="13754-148">-InputObject</span></span>
<span data-ttu-id="13754-149">Especifica os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-149">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="13754-150">Insira uma variável que contenha objetos **ScheduledJob** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJob** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="13754-150">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="13754-151">Você também pode canalizar objetos **ScheduledJob** para **Remove-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="13754-151">You can also pipe **ScheduledJob** objects to **Remove-JobTrigger** .</span></span>

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

### <span data-ttu-id="13754-152">-Name</span><span class="sxs-lookup"><span data-stu-id="13754-152">-Name</span></span>
<span data-ttu-id="13754-153">Especifica os nomes dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-153">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="13754-154">O **Remove-JobTrigger** exclui os gatilhos dos trabalhos agendados especificados.</span><span class="sxs-lookup"><span data-stu-id="13754-154">**Remove-JobTrigger** deletes the job triggers from the specified scheduled jobs.</span></span>
<span data-ttu-id="13754-155">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="13754-155">Wildcards are supported.</span></span>

<span data-ttu-id="13754-156">Para obter os nomes dos trabalhos agendados no computador local ou em um computador remoto, use o cmdlet Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="13754-156">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="13754-157">-Triggerid</span><span class="sxs-lookup"><span data-stu-id="13754-157">-TriggerId</span></span>
<span data-ttu-id="13754-158">Exclui somente os gatilhos de trabalho especificados.</span><span class="sxs-lookup"><span data-stu-id="13754-158">Deletes only the specified job triggers.</span></span>
<span data-ttu-id="13754-159">Por padrão, o **Remove-JobTrigger** exclui todos os gatilhos de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-159">By default, **Remove-JobTrigger** deletes all triggers from the scheduled jobs.</span></span>
<span data-ttu-id="13754-160">Use esse parâmetro quando os trabalhos agendados tiverem vários gatilhos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="13754-160">Use this parameter when the scheduled jobs have multiple job triggers.</span></span>

<span data-ttu-id="13754-161">Insira as IDs de gatilho de um ou mais gatilhos de trabalho de uma tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="13754-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="13754-162">Se você especificar vários trabalhos agendados, **Remove-JobTrigger** excluirá o gatilho de trabalho com a ID especificada de todos os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13754-162">If you specify multiple scheduled jobs, **Remove-JobTrigger** deletes the job trigger with the specified ID from all scheduled jobs.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13754-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="13754-163">CommonParameters</span></span>
<span data-ttu-id="13754-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="13754-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="13754-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="13754-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="13754-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="13754-166">INPUTS</span></span>

### <span data-ttu-id="13754-167">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="13754-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="13754-168">É possível redirecionar os trabalhos agendados para o cmdlet **Remove-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="13754-168">You can pipe scheduled jobs to the **Remove-JobTrigger** cmdlet.</span></span>

## <span data-ttu-id="13754-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="13754-169">OUTPUTS</span></span>

### <span data-ttu-id="13754-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="13754-170">None</span></span>
<span data-ttu-id="13754-171">O cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="13754-171">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="13754-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="13754-172">NOTES</span></span>

## <span data-ttu-id="13754-173">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="13754-173">RELATED LINKS</span></span>

[<span data-ttu-id="13754-174">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-174">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="13754-175">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-175">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="13754-176">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="13754-176">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="13754-177">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-177">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="13754-178">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="13754-178">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="13754-179">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-179">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="13754-180">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="13754-180">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="13754-181">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="13754-181">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="13754-182">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-182">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="13754-183">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="13754-183">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="13754-184">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="13754-184">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="13754-185">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-185">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="13754-186">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="13754-186">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="13754-187">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="13754-187">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="13754-188">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="13754-188">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="13754-189">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="13754-189">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
