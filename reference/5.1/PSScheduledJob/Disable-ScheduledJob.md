---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193685"
---
# <span data-ttu-id="fd55c-103">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fd55c-103">Disable-ScheduledJob</span></span>

## <span data-ttu-id="fd55c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fd55c-104">SYNOPSIS</span></span>
<span data-ttu-id="fd55c-105">Desabilita um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-105">Disables a scheduled job.</span></span>

## <span data-ttu-id="fd55c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd55c-106">SYNTAX</span></span>

### <span data-ttu-id="fd55c-107">Definição (padrão)</span><span class="sxs-lookup"><span data-stu-id="fd55c-107">Definition (Default)</span></span>

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fd55c-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="fd55c-108">DefinitionId</span></span>

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fd55c-109">Definitionname</span><span class="sxs-lookup"><span data-stu-id="fd55c-109">DefinitionName</span></span>

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fd55c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd55c-110">DESCRIPTION</span></span>
<span data-ttu-id="fd55c-111">O cmdlet **Disable-ScheduledJob** desabilita temporariamente trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="fd55c-111">The **Disable-ScheduledJob** cmdlet temporarily disables scheduled jobs.</span></span>
<span data-ttu-id="fd55c-112">Desabilitar preserva todas as propriedades do trabalho e não desabilita os disparadores do trabalho, mas impede que os trabalhos agendados iniciem automaticamente quando disparados.</span><span class="sxs-lookup"><span data-stu-id="fd55c-112">Disabling preserves all job properties and does not disable the job triggers, but it prevents the scheduled jobs from starting automatically when triggered.</span></span>
<span data-ttu-id="fd55c-113">Você pode iniciar um trabalho agendado desabilitado usando o cmdlet Start-Job ou usar um trabalho agendado desabilitado como um modelo.</span><span class="sxs-lookup"><span data-stu-id="fd55c-113">You can start a disabled scheduled job by using the Start-Job cmdlet or use a disabled scheduled job as a template.</span></span>

<span data-ttu-id="fd55c-114">Para desabilitar um trabalho agendado, o cmdlet **Disable-ScheduledJob** define a propriedade **Enabled** do trabalho agendado como Falso ($false).</span><span class="sxs-lookup"><span data-stu-id="fd55c-114">To disable a scheduled job, the **Disable-ScheduledJob** cmdlet sets the **Enabled** property of the scheduled job to False ($false).</span></span>
<span data-ttu-id="fd55c-115">Para reabilitar o trabalho agendado, use o cmdlet Enable-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="fd55c-115">To re-enable the scheduled job, use the Enable-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="fd55c-116">**Disable-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd55c-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="fd55c-117">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="fd55c-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="fd55c-118">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="fd55c-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="fd55c-119">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fd55c-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="fd55c-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fd55c-120">EXAMPLES</span></span>

### <span data-ttu-id="fd55c-121">Exemplo 1: desabilitar um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="fd55c-121">Example 1: Disable a scheduled job</span></span>

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

<span data-ttu-id="fd55c-122">Este comando desabilita o trabalho agendado com ID 2 presente no computador local.</span><span class="sxs-lookup"><span data-stu-id="fd55c-122">This command disables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="fd55c-123">A saída mostra o efeito do comando.</span><span class="sxs-lookup"><span data-stu-id="fd55c-123">The output shows the effect of the command.</span></span>

### <span data-ttu-id="fd55c-124">Exemplo 2: desabilitar todos os trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="fd55c-124">Example 2: Disable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

<span data-ttu-id="fd55c-125">Este comando desabilita todos os trabalhos agendados existentes no computador local.</span><span class="sxs-lookup"><span data-stu-id="fd55c-125">This command disables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="fd55c-126">Ele usa o cmdlet Get-ScheduledJob para obter todo o trabalho agendado e o cmdlet **Disable-ScheduledJob** para desabilitá-los.</span><span class="sxs-lookup"><span data-stu-id="fd55c-126">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Disable-ScheduledJob** cmdlet to disable them.</span></span>

<span data-ttu-id="fd55c-127">Você pode reabilitar o trabalho agendado usando o cmdlet Enable-ScheduledJob e executar um trabalho agendado desabilitado usando o cmdlet Start-Job.</span><span class="sxs-lookup"><span data-stu-id="fd55c-127">You can re-enable scheduled job by using the Enable-ScheduledJob cmdlet and run a disabled scheduled job by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="fd55c-128">**Disable-ScheduledJob** não gera avisos ou erros se você desabilitar um trabalho agendado que já está desabilitado, para que você possa desabilitar todos os trabalhos agendados sem condições.</span><span class="sxs-lookup"><span data-stu-id="fd55c-128">**Disable-ScheduledJob** does not generate warnings or errors if you disable a scheduled job that is already disabled, so you can disable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="fd55c-129">Exemplo 3: desabilitar os trabalhos agendados selecionados</span><span class="sxs-lookup"><span data-stu-id="fd55c-129">Example 3: Disable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

<span data-ttu-id="fd55c-130">Este comando desabilita trabalhos agendados que não incluem uma credencial.</span><span class="sxs-lookup"><span data-stu-id="fd55c-130">This command disables scheduled job do not include a credential.</span></span>
<span data-ttu-id="fd55c-131">Trabalhos sem credenciais são executados com a permissão do usuário que os criou.</span><span class="sxs-lookup"><span data-stu-id="fd55c-131">Jobs without credentials run with the permission of the user who created them.</span></span>

<span data-ttu-id="fd55c-132">O comando usa o cmdlet Get-ScheduledJob para obter todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="fd55c-132">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="fd55c-133">Um operador de pipeline envia os trabalhos agendados para o cmdlet Where-Object, que seleciona trabalhos agendados que não têm credenciais.</span><span class="sxs-lookup"><span data-stu-id="fd55c-133">A pipeline operator sends the scheduled jobs to the Where-Object cmdlet, which selects scheduled jobs that do not have credentials.</span></span>
<span data-ttu-id="fd55c-134">O comando usa o operador não (!) e referências à propriedade Credential do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-134">The command uses the not (!) operator and references the Credential property of the scheduled job.</span></span>
<span data-ttu-id="fd55c-135">Outro operador de pipeline envia os trabalhos agendados selecionados para o cmdlet **Disable-ScheduledJob** , que os desabilita.</span><span class="sxs-lookup"><span data-stu-id="fd55c-135">Another pipeline operator sends the selected scheduled jobs to the **Disable-ScheduledJob** cmdlet, which disables them.</span></span>

### <span data-ttu-id="fd55c-136">Exemplo 4: desabilitar trabalhos agendados em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="fd55c-136">Example 4: Disable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

<span data-ttu-id="fd55c-137">Este comando desabilita o trabalho agendado TestJob em dois computadores remotos, Srv01 e Srv10.</span><span class="sxs-lookup"><span data-stu-id="fd55c-137">This command disables the TestJob scheduled job on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="fd55c-138">O comando usa o cmdlet Invoke-Command para executar um comando **Disable-ScheduledJob** nos computadores Srv01 e Srv10.</span><span class="sxs-lookup"><span data-stu-id="fd55c-138">The command uses the Invoke-Command cmdlet to run a **Disable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="fd55c-139">O comando usa o parâmetro *Name* do **Disable-ScheduledJob** para selecionar o trabalho agendado do TestJob em cada computador.</span><span class="sxs-lookup"><span data-stu-id="fd55c-139">The command uses the *Name* parameter of **Disable-ScheduledJob** to select the TestJob scheduled job on each computer.</span></span>

### <span data-ttu-id="fd55c-140">Exemplo 5: desabilitar um trabalho agendado por sua ID global</span><span class="sxs-lookup"><span data-stu-id="fd55c-140">Example 5: Disable a scheduled job by its global ID</span></span>

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

<span data-ttu-id="fd55c-141">Este exemplo mostra como desabilitar um trabalho agendado usando seu identificador global.</span><span class="sxs-lookup"><span data-stu-id="fd55c-141">This examples shows how to disable a scheduled job by using its global identifier.</span></span>
<span data-ttu-id="fd55c-142">O valor da propriedade GlobalID de um trabalho agendado é um identificador exclusivo (GUID).</span><span class="sxs-lookup"><span data-stu-id="fd55c-142">The value of the GlobalID property of a scheduled job is a unique identifier (GUID).</span></span>
<span data-ttu-id="fd55c-143">Use o valor GlobalID quando a precisão é necessária, como quando você está desativando trabalhos agendados em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="fd55c-143">Use the GlobalID value when precision is required, such as when you are disabling scheduled jobs on multiple computers.</span></span>

## <span data-ttu-id="fd55c-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd55c-144">PARAMETERS</span></span>

### <span data-ttu-id="fd55c-145">-Id</span><span class="sxs-lookup"><span data-stu-id="fd55c-145">-Id</span></span>
<span data-ttu-id="fd55c-146">Desabilita o trabalho agendado com o número de identificação (ID) especificado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-146">Disables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="fd55c-147">Insira a ID de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-147">Enter the ID of a scheduled job.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd55c-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fd55c-148">-InputObject</span></span>
<span data-ttu-id="fd55c-149">Especifica o trabalho agendado a ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-149">Specifies the scheduled job to be disabled.</span></span>
<span data-ttu-id="fd55c-150">Insira uma variável que contenha objetos  **ScheduledJobDefinition** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobDefinition** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="fd55c-150">Enter a variable that contains  **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="fd55c-151">Também é possível canalizar um objeto **ScheduledJobDefinition** para **Disable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="fd55c-151">You can also pipe a **ScheduledJobDefinition** object to **Disable-ScheduledJob** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fd55c-152">-Name</span><span class="sxs-lookup"><span data-stu-id="fd55c-152">-Name</span></span>
<span data-ttu-id="fd55c-153">Desabilita os trabalhos agendados com os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="fd55c-153">Disables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="fd55c-154">Insira o nome de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-154">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="fd55c-155">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="fd55c-155">Wildcards are supported.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd55c-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fd55c-156">-PassThru</span></span>
<span data-ttu-id="fd55c-157">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="fd55c-157">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="fd55c-158">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="fd55c-158">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fd55c-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd55c-159">-Confirm</span></span>
<span data-ttu-id="fd55c-160">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd55c-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd55c-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd55c-161">-WhatIf</span></span>
<span data-ttu-id="fd55c-162">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fd55c-163">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fd55c-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd55c-164">CommonParameters</span></span>
<span data-ttu-id="fd55c-165">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd55c-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd55c-166">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd55c-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd55c-167">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fd55c-167">INPUTS</span></span>

### <span data-ttu-id="fd55c-168">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="fd55c-168">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="fd55c-169">Você pode direcionar um trabalho agendado para **Disable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="fd55c-169">You can pipe a scheduled job to **Disable-ScheduledJob** .</span></span>

## <span data-ttu-id="fd55c-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fd55c-170">OUTPUTS</span></span>

### <span data-ttu-id="fd55c-171">Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="fd55c-171">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="fd55c-172">Se você usar o parâmetro **Passthru** , **Disable-ScheduledJob** retorna o trabalho agendado que foi desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-172">If you use the **Passthru** parameter, **Disable-ScheduledJob** returns the scheduled job that was disabled.</span></span>
<span data-ttu-id="fd55c-173">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="fd55c-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fd55c-174">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fd55c-174">NOTES</span></span>

* <span data-ttu-id="fd55c-175">**Disable-ScheduledJob** não gerará avisos ou erros se você usá-lo para desabilitar um trabalho agendado que já está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fd55c-175">**Disable-ScheduledJob** does not generate warnings or errors if you use it to disable a scheduled job that is already disabled.</span></span>

## <span data-ttu-id="fd55c-176">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fd55c-176">RELATED LINKS</span></span>

[<span data-ttu-id="fd55c-177">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fd55c-177">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="fd55c-178">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fd55c-178">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="fd55c-179">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fd55c-179">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="fd55c-180">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fd55c-180">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="fd55c-181">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fd55c-181">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="fd55c-182">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fd55c-182">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="fd55c-183">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fd55c-183">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="fd55c-184">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fd55c-184">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="fd55c-185">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fd55c-185">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="fd55c-186">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fd55c-186">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="fd55c-187">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fd55c-187">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="fd55c-188">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fd55c-188">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="fd55c-189">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fd55c-189">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="fd55c-190">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fd55c-190">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="fd55c-191">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fd55c-191">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="fd55c-192">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fd55c-192">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
