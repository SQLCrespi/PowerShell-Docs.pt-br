---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193678"
---
# <span data-ttu-id="d9abb-103">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d9abb-103">Enable-ScheduledJob</span></span>

## <span data-ttu-id="d9abb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d9abb-104">SYNOPSIS</span></span>
<span data-ttu-id="d9abb-105">Habilita um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-105">Enables a scheduled job.</span></span>

## <span data-ttu-id="d9abb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d9abb-106">SYNTAX</span></span>

### <span data-ttu-id="d9abb-107">Definição (padrão)</span><span class="sxs-lookup"><span data-stu-id="d9abb-107">Definition (Default)</span></span>

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="d9abb-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="d9abb-108">DefinitionId</span></span>

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d9abb-109">Definitionname</span><span class="sxs-lookup"><span data-stu-id="d9abb-109">DefinitionName</span></span>

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d9abb-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d9abb-110">DESCRIPTION</span></span>
<span data-ttu-id="d9abb-111">O cmdlet **Enable-ScheduledJob** habilita novamente os trabalhos agendados que estão desabilitados, como aqueles que estão desabilitados usando o cmdlet Disable-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="d9abb-111">The **Enable-ScheduledJob** cmdlet re-enables scheduled jobs that are disabled, such as those that are disabled by using the Disable-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="d9abb-112">Trabalhos habilitados são executados automaticamente quando disparados.</span><span class="sxs-lookup"><span data-stu-id="d9abb-112">Enabled jobs run automatically when triggered.</span></span>

<span data-ttu-id="d9abb-113">Para habilitar um trabalho agendado, o cmdlet **Enable-ScheduledJob** define a propriedade Enabled do trabalho agendado para $true.</span><span class="sxs-lookup"><span data-stu-id="d9abb-113">To enable a scheduled job, the **Enable-ScheduledJob** cmdlet sets the Enabled property of the scheduled job to $True.</span></span>

<span data-ttu-id="d9abb-114">**Enabled-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9abb-114">**Enabled-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="d9abb-115">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="d9abb-115">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="d9abb-116">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="d9abb-116">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="d9abb-117">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d9abb-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d9abb-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d9abb-118">EXAMPLES</span></span>

### <span data-ttu-id="d9abb-119">Exemplo 1: habilitar um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="d9abb-119">Example 1: Enable a scheduled job</span></span>

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

<span data-ttu-id="d9abb-120">Este comando habilita o trabalho agendado com ID 2 no computador local.</span><span class="sxs-lookup"><span data-stu-id="d9abb-120">This command enables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="d9abb-121">A saída mostra o efeito do comando.</span><span class="sxs-lookup"><span data-stu-id="d9abb-121">The output shows the effect of the command.</span></span>

### <span data-ttu-id="d9abb-122">Exemplo 2: habilitar todos os trabalhos agendados</span><span class="sxs-lookup"><span data-stu-id="d9abb-122">Example 2: Enable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

<span data-ttu-id="d9abb-123">Este comando habilita todos os trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="d9abb-123">This command enables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="d9abb-124">Ele usa o cmdlet Get-ScheduledJob para obter todo o trabalho agendado e o cmdlet **Enable-ScheduledJob** para habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="d9abb-124">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Enable-ScheduledJob** cmdlet to enable them.</span></span>

<span data-ttu-id="d9abb-125">O **Enable-ScheduledJob** não gera avisos ou erros se você habilitar um trabalho agendado que já está habilitado, para que você possa habilitar todos os trabalhos agendados sem condições.</span><span class="sxs-lookup"><span data-stu-id="d9abb-125">**Enable-ScheduledJob** does not generate warnings or errors if you enable a scheduled job that is already enabled, so you can enable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="d9abb-126">Exemplo 3: habilitar os trabalhos agendados selecionados</span><span class="sxs-lookup"><span data-stu-id="d9abb-126">Example 3: Enable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

<span data-ttu-id="d9abb-127">Este comando habilita os trabalhos agendados que não exigem uma conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="d9abb-127">This command enables scheduled jobs that do not require a network connection.</span></span>

<span data-ttu-id="d9abb-128">O comando usa o cmdlet Get-ScheduledJob para obter todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="d9abb-128">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="d9abb-129">Um operador de pipeline envia os trabalhos agendados para o cmdlet Get-ScheduledJobOption, que obtém as opções de trabalho de cada trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-129">A pipeline operator sends the scheduled jobs to the Get-ScheduledJobOption cmdlet, which gets the job options of each scheduled job.</span></span>
<span data-ttu-id="d9abb-130">Cada objeto de opções de trabalho tem uma propriedade JobDefinition que contém o trabalho agendado associado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-130">Each job options object has a JobDefinition property that contains the associated scheduled job.</span></span>
<span data-ttu-id="d9abb-131">A propriedade JobDefinition é usada para concluir o comando.</span><span class="sxs-lookup"><span data-stu-id="d9abb-131">The JobDefinition property is used to complete the command.</span></span>

<span data-ttu-id="d9abb-132">O comando usa um operador de pipeline (|) para enviar as opções de trabalho para o cmdlet Where-Object, que seleciona objetos de opção de trabalho agendado nos quais a propriedade **RunWithoutNetwork** tem um valor de True ($true).</span><span class="sxs-lookup"><span data-stu-id="d9abb-132">The command uses a pipeline operator (|) to send the job options to the Where-Object cmdlet, which selects scheduled job option objects in which the **RunWithoutNetwork** property has a value of True ($true).</span></span>
<span data-ttu-id="d9abb-133">Outro operador de pipeline envia os objetos de opções de trabalho agendado selecionados para o cmdlet ForEach-Object, que executa um comando **Enable-ScheduledJob** no trabalho agendado no valor da propriedade JobDefinition de cada objeto de opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d9abb-133">Another pipeline operator sends the selected scheduled job options objects to the ForEach-Object cmdlet which runs an **Enable-ScheduledJob** command on the scheduled job in the value of the JobDefinition property of each job options object.</span></span>

### <span data-ttu-id="d9abb-134">Exemplo 4: habilitar trabalhos agendados em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="d9abb-134">Example 4: Enable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

<span data-ttu-id="d9abb-135">Este comando habilita os trabalhos agendados que possuem "teste" em seus nomes em dois computadores remotos, Srv01 e Srv10.</span><span class="sxs-lookup"><span data-stu-id="d9abb-135">This command enables scheduled jobs that have "test" in their names on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="d9abb-136">O comando usa o cmdlet Invoke-Command para executar um comando **Enable-ScheduledJob** nos computadores Srv01 e Srv10.</span><span class="sxs-lookup"><span data-stu-id="d9abb-136">The command uses the Invoke-Command cmdlet to run an **Enable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="d9abb-137">O comando usa o parâmetro *Name* do **Enable-ScheduledJob** para habilitar o trabalho agendado Inventory em cada computador.</span><span class="sxs-lookup"><span data-stu-id="d9abb-137">The command uses the *Name* parameter of **Enable-ScheduledJob** to enable the Inventory scheduled job on each computer.</span></span>

## <span data-ttu-id="d9abb-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d9abb-138">PARAMETERS</span></span>

### <span data-ttu-id="d9abb-139">-Id</span><span class="sxs-lookup"><span data-stu-id="d9abb-139">-Id</span></span>
<span data-ttu-id="d9abb-140">Habilita o trabalho agendado com o número de identificação (ID) especificado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-140">Enables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="d9abb-141">Insira a ID de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-141">Enter the ID of a scheduled job.</span></span>

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

### <span data-ttu-id="d9abb-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d9abb-142">-InputObject</span></span>
<span data-ttu-id="d9abb-143">Especifica o trabalho agendado a ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-143">Specifies the scheduled job to enable.</span></span>
<span data-ttu-id="d9abb-144">Insira uma variável que contenha objetos **ScheduledJobDefinition** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobDefinition** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="d9abb-144">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="d9abb-145">Também é possível canalizar um objeto **ScheduledJobDefinition** para **Enable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="d9abb-145">You can also pipe a **ScheduledJobDefinition** object to **Enable-ScheduledJob** .</span></span>

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

### <span data-ttu-id="d9abb-146">-Name</span><span class="sxs-lookup"><span data-stu-id="d9abb-146">-Name</span></span>
<span data-ttu-id="d9abb-147">Habilita os trabalhos agendados com os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="d9abb-147">Enables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="d9abb-148">Insira o nome de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-148">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="d9abb-149">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d9abb-149">Wildcards are supported.</span></span>

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

### <span data-ttu-id="d9abb-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d9abb-150">-PassThru</span></span>
<span data-ttu-id="d9abb-151">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="d9abb-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="d9abb-152">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d9abb-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d9abb-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d9abb-153">-Confirm</span></span>
<span data-ttu-id="d9abb-154">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d9abb-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d9abb-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d9abb-155">-WhatIf</span></span>
<span data-ttu-id="d9abb-156">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d9abb-157">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d9abb-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d9abb-158">CommonParameters</span></span>
<span data-ttu-id="d9abb-159">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d9abb-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d9abb-160">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d9abb-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d9abb-161">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d9abb-161">INPUTS</span></span>

### <span data-ttu-id="d9abb-162">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="d9abb-162">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="d9abb-163">É possível canalizar um trabalho agendado para **Enable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="d9abb-163">You can pipe a scheduled job to **Enable-ScheduledJob** .</span></span>

## <span data-ttu-id="d9abb-164">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d9abb-164">OUTPUTS</span></span>

### <span data-ttu-id="d9abb-165">Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="d9abb-165">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="d9abb-166">Se você usar o parâmetro **Passthru** , **Enable-ScheduledJob** retorna o trabalho agendado que foi habilitado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-166">If you use the **Passthru** parameter, **Enable-ScheduledJob** returns the scheduled job that was enabled.</span></span>
<span data-ttu-id="d9abb-167">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="d9abb-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d9abb-168">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d9abb-168">NOTES</span></span>

* <span data-ttu-id="d9abb-169">O **Enable-ScheduledJob** não gera avisos ou erros se você usá-lo para habilitar um trabalho agendado que já está habilitado.</span><span class="sxs-lookup"><span data-stu-id="d9abb-169">**Enable-ScheduledJob** does not generate warnings or errors if you use it to enable a scheduled job that is already enabled.</span></span>

## <span data-ttu-id="d9abb-170">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d9abb-170">RELATED LINKS</span></span>

[<span data-ttu-id="d9abb-171">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d9abb-171">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="d9abb-172">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d9abb-172">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="d9abb-173">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d9abb-173">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="d9abb-174">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d9abb-174">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="d9abb-175">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d9abb-175">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="d9abb-176">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d9abb-176">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="d9abb-177">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d9abb-177">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="d9abb-178">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d9abb-178">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="d9abb-179">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d9abb-179">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="d9abb-180">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d9abb-180">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="d9abb-181">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d9abb-181">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="d9abb-182">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d9abb-182">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="d9abb-183">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="d9abb-183">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="d9abb-184">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d9abb-184">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="d9abb-185">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="d9abb-185">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="d9abb-186">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d9abb-186">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
