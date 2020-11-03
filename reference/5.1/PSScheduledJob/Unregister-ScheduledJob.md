---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193659"
---
# <span data-ttu-id="cda12-103">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-103">Unregister-ScheduledJob</span></span>

## <span data-ttu-id="cda12-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="cda12-104">SYNOPSIS</span></span>
<span data-ttu-id="cda12-105">Exclui os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="cda12-105">Deletes scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="cda12-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cda12-106">SYNTAX</span></span>

### <span data-ttu-id="cda12-107">Definição (padrão)</span><span class="sxs-lookup"><span data-stu-id="cda12-107">Definition (Default)</span></span>

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="cda12-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="cda12-108">DefinitionId</span></span>

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cda12-109">Definitionname</span><span class="sxs-lookup"><span data-stu-id="cda12-109">DefinitionName</span></span>

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cda12-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cda12-110">DESCRIPTION</span></span>
<span data-ttu-id="cda12-111">O cmdlet **Unregister-ScheduledJob** exclui os trabalhos agendados do computador local.</span><span class="sxs-lookup"><span data-stu-id="cda12-111">The **Unregister-ScheduledJob** cmdlet deletes scheduled jobs from the local computer.</span></span>

<span data-ttu-id="cda12-112">Quando ele exclui ou cancela o registro de um trabalho agendado, **o cancelamento do registro-ScheduledJob** exclui o diretório do trabalho agendado (no diretório $home \appdata\local\microsoft\windows\powershell\scheduledjobs), que contém o arquivo XML que define o trabalho agendado, o histórico de execução do trabalho e todos os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="cda12-112">When it deletes or unregisters a scheduled job, **Unregister-ScheduledJob** deletes the directory for the scheduled job (in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory), which contains the XML file that defines the scheduled job, the job execution history, and all job results.</span></span>
<span data-ttu-id="cda12-113">Essa ação também exclui o trabalho do Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="cda12-113">This action also deletes the job from Task Scheduler.</span></span>

<span data-ttu-id="cda12-114">**Unregister-ScheduledJob** exclui somente os trabalhos agendados que são criados usando o cmdlet Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="cda12-114">**Unregister-ScheduledJob** deletes only the scheduled jobs that are created by using the Register-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="cda12-115">Ele não exclui os trabalhos agendados que são criados no Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="cda12-115">It does not delete scheduled jobs that are created in Task Scheduler.</span></span>

<span data-ttu-id="cda12-116">Você pode usar os parâmetros de **Unregister-ScheduledJob** para excluir trabalhos agendados por ID ou nome ou trabalhos agendados de pipe de Get-ScheduledJob para **cancelar o registro-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="cda12-116">You can use the parameters of **Unregister-ScheduledJob** to delete scheduled jobs by ID or name, or pipe scheduled jobs from Get-ScheduledJob to **Unregister-ScheduledJob** .</span></span>

<span data-ttu-id="cda12-117">**Unregister-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cda12-117">**Unregister-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="cda12-118">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="cda12-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="cda12-119">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="cda12-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="cda12-120">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="cda12-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="cda12-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="cda12-121">EXAMPLES</span></span>

### <span data-ttu-id="cda12-122">Exemplo 1: excluir um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="cda12-122">Example 1: Delete a scheduled job</span></span>

```
PS C:\> Unregister-ScheduledJob TestJob
```

<span data-ttu-id="cda12-123">Esse comando exclui o trabalho agendado TestJob no computador local.</span><span class="sxs-lookup"><span data-stu-id="cda12-123">This command deletes the TestJob scheduled job on the local computer.</span></span>

### <span data-ttu-id="cda12-124">Exemplo 2: excluir todos os trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="cda12-124">Example 2: Delete all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

<span data-ttu-id="cda12-125">Este exemplo mostra dois comandos diferentes que excluem todos os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="cda12-125">This example shows two different commands that delete all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="cda12-126">O primeiro comando usa o cmdlet Get-ScheduledJob para obter todos os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="cda12-126">The first command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="cda12-127">Um operador de pipeline (|) envia os trabalhos agendados para **Unregister-ScheduleJob** , que os exclui.</span><span class="sxs-lookup"><span data-stu-id="cda12-127">A pipeline operator (|) sends the scheduled jobs to **Unregister-ScheduleJob** , which deletes them.</span></span>

<span data-ttu-id="cda12-128">O segundo comando usa o parâmetro *Name* do **Unregister-ScheduledJob** com um valor de todos (\*) para excluir todos os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="cda12-128">The second command uses the *Name* parameter of **Unregister-ScheduledJob** with a value of all (\*) to delete all scheduled jobs.</span></span>

<span data-ttu-id="cda12-129">Os dois comandos utilizam o parâmetro *Force* , que exclui um trabalho agendado, mesmo que uma instância do trabalho esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="cda12-129">Both commands use the *Force* parameter, which deletes a scheduled job even if an instance of the job is running.</span></span>

### <span data-ttu-id="cda12-130">Exemplo 3: excluir um trabalho agendado em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="cda12-130">Example 3: Delete a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

<span data-ttu-id="cda12-131">Esse comando exclui os trabalhos agendados com nomes que começam com Test no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="cda12-131">This command deletes scheduled jobs with names that begin with Test on the Server01 remote computer.</span></span>
<span data-ttu-id="cda12-132">O comando usa o cmdlet Invoke-Command para executar o comando **Unregister-ScheduledJob** no computador Server02.</span><span class="sxs-lookup"><span data-stu-id="cda12-132">The command uses the Invoke-Command cmdlet to run the **Unregister-ScheduledJob** command on the Server02 computer.</span></span>

## <span data-ttu-id="cda12-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cda12-133">PARAMETERS</span></span>

### <span data-ttu-id="cda12-134">-Force</span><span class="sxs-lookup"><span data-stu-id="cda12-134">-Force</span></span>
<span data-ttu-id="cda12-135">Excluir o trabalho agendado, mesmo que uma instância do trabalho esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="cda12-135">Deletes the scheduled job even if an instance of the job is running.</span></span>
<span data-ttu-id="cda12-136">Por padrão, o **Unregister-ScheduledJob** não interrompe os trabalhos em execução.</span><span class="sxs-lookup"><span data-stu-id="cda12-136">By default, **Unregister-ScheduledJob** does not interrupt running jobs.</span></span>

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

### <span data-ttu-id="cda12-137">-Id</span><span class="sxs-lookup"><span data-stu-id="cda12-137">-Id</span></span>
<span data-ttu-id="cda12-138">Excluir os trabalhos agendados com os números de identificação especificado (ID).</span><span class="sxs-lookup"><span data-stu-id="cda12-138">Deletes the scheduled jobs with the specified identification numbers (ID).</span></span>
<span data-ttu-id="cda12-139">Insira as IDs dos trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="cda12-139">Enter the IDs of scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cda12-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cda12-140">-InputObject</span></span>
<span data-ttu-id="cda12-141">Especifica um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="cda12-141">Specifies a scheduled job.</span></span>
<span data-ttu-id="cda12-142">Insira uma variável que contenha objetos **ScheduledJob** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJob** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="cda12-142">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="cda12-143">Você também pode canalizar os objetos **ScheduledJob** para **cancelar o registro-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="cda12-143">You can also pipe **ScheduledJob** objects to **Unregister-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cda12-144">-Name</span><span class="sxs-lookup"><span data-stu-id="cda12-144">-Name</span></span>
<span data-ttu-id="cda12-145">Excluir os trabalhos agendados com os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="cda12-145">Deletes the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="cda12-146">Digite os nomes de um ou mais trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="cda12-146">Enter the names of one or more scheduled jobs on the computer.</span></span>
<span data-ttu-id="cda12-147">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="cda12-147">Wildcards are supported.</span></span>

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

### <span data-ttu-id="cda12-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cda12-148">-Confirm</span></span>
<span data-ttu-id="cda12-149">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cda12-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cda12-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cda12-150">-WhatIf</span></span>
<span data-ttu-id="cda12-151">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="cda12-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cda12-152">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="cda12-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cda12-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cda12-153">CommonParameters</span></span>
<span data-ttu-id="cda12-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cda12-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cda12-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cda12-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cda12-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="cda12-156">INPUTS</span></span>

### <span data-ttu-id="cda12-157">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="cda12-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="cda12-158">É possível redirecionar os trabalhos agendados para Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-158">You can pipe scheduled jobs to Unregister-ScheduledJob</span></span>

## <span data-ttu-id="cda12-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="cda12-159">OUTPUTS</span></span>

### <span data-ttu-id="cda12-160">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cda12-160">None</span></span>
<span data-ttu-id="cda12-161">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="cda12-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cda12-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="cda12-162">NOTES</span></span>

## <span data-ttu-id="cda12-163">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="cda12-163">RELATED LINKS</span></span>

[<span data-ttu-id="cda12-164">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cda12-164">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="cda12-165">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cda12-165">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="cda12-166">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-166">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="cda12-167">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cda12-167">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="cda12-168">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-168">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="cda12-169">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cda12-169">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="cda12-170">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-170">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="cda12-171">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cda12-171">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="cda12-172">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cda12-172">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="cda12-173">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cda12-173">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="cda12-174">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-174">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="cda12-175">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cda12-175">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="cda12-176">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cda12-176">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="cda12-177">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-177">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="cda12-178">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cda12-178">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="cda12-179">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cda12-179">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
