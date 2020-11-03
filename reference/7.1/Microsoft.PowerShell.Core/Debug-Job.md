---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 8ff583fbf0ebf453a5194deecbc1eb42a51242d4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194779"
---
# <span data-ttu-id="75842-103">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="75842-103">Debug-Job</span></span>

## <span data-ttu-id="75842-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="75842-104">SYNOPSIS</span></span>
<span data-ttu-id="75842-105">Debugs de um trabalho de plano de fundo, remoto ou do PowerShell em execução.</span><span class="sxs-lookup"><span data-stu-id="75842-105">Debugs a running background, remote, or PowerShell Workflow job.</span></span>

## <span data-ttu-id="75842-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75842-106">SYNTAX</span></span>

### <span data-ttu-id="75842-107">JobParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="75842-107">JobParameterSet (Default)</span></span>

```
Debug-Job [-Job] <Job> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="75842-108">JobNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="75842-108">JobNameParameterSet</span></span>

```
Debug-Job [-Name] <String> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="75842-109">JobIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="75842-109">JobIdParameterSet</span></span>

```
Debug-Job [-Id] <Int32> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="75842-110">JobInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="75842-110">JobInstanceIdParameterSet</span></span>

```
Debug-Job [-InstanceId] <Guid> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="75842-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="75842-111">DESCRIPTION</span></span>
<span data-ttu-id="75842-112">O cmdlet **debug-Job** permite depurar scripts que estão sendo executados em trabalhos.</span><span class="sxs-lookup"><span data-stu-id="75842-112">The **Debug-Job** cmdlet lets you debug scripts that are running within jobs.</span></span>
<span data-ttu-id="75842-113">O cmdlet é projetado para depurar trabalhos de fluxo de trabalho do PowerShell, trabalhos em segundo plano e trabalhos em execução em sessões remotas.</span><span class="sxs-lookup"><span data-stu-id="75842-113">The cmdlet is designed to debug PowerShell Workflow jobs, background jobs, and jobs running in remote sessions.</span></span>
<span data-ttu-id="75842-114">**Debug-Job** aceita um objeto de trabalho em execução, nome, ID ou ID de instância como entrada e inicia uma sessão de depuração no script que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="75842-114">**Debug-Job** accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running.</span></span>
<span data-ttu-id="75842-115">O comando do depurador **Quit** interrompe o trabalho e executa o script.</span><span class="sxs-lookup"><span data-stu-id="75842-115">The debugger **quit** command stops the job and running script.</span></span>
<span data-ttu-id="75842-116">A partir do Windows PowerShell 5,0, o comando **Exit** desanexa o depurador e permite que o trabalho continue a ser executado.</span><span class="sxs-lookup"><span data-stu-id="75842-116">Starting in Windows PowerShell 5.0, the **exit** command detaches the debugger, and allows the job to continue to run.</span></span>

## <span data-ttu-id="75842-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="75842-117">EXAMPLES</span></span>

### <span data-ttu-id="75842-118">Exemplo 1: Depurar um trabalho por ID do trabalho</span><span class="sxs-lookup"><span data-stu-id="75842-118">Example 1: Debug a job by job ID</span></span>

```
PS C:\> Debug-Job -ID 3
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
3      Job3            RemoteJob       Running       True            PowerShellIx         TestWFDemo1.ps1
          Entering debug mode. Use h or ? for help.

          Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

          At C:\TestWFDemo1.ps1:8 char:5
          +     Write-Output -InputObject "Now writing output:"
          +     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
          [DBG:PowerShellIx]: PS C:\> > list

              3:
              4:  workflow SampleWorkflowTest
              5:  {
              6:      param ($MyOutput)
              7:
              8:*     Write-Output -InputObject "Now writing output:"
              9:      Write-Output -Input $MyOutput
             10:
             11:      Write-Output -InputObject "Get PowerShell process:"
             12:      Get-Process -Name powershell
             13:
             14:      Write-Output -InputObject "Workflow function complete."
             15:  }
             16:
             17:  # Call workflow function
             18:  SampleWorkflowTest -MyOutput "Hello"
```

<span data-ttu-id="75842-119">Esse comando quebra um trabalho em execução com uma ID de 3.</span><span class="sxs-lookup"><span data-stu-id="75842-119">This command breaks into a running job with an ID of 3.</span></span>

## <span data-ttu-id="75842-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75842-120">PARAMETERS</span></span>

### <span data-ttu-id="75842-121">-Id</span><span class="sxs-lookup"><span data-stu-id="75842-121">-Id</span></span>
<span data-ttu-id="75842-122">Especifica o número de ID de um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="75842-122">Specifies the ID number of a running job.</span></span>
<span data-ttu-id="75842-123">Para obter o número de ID de um trabalho, execute o cmdlet Get-Job.</span><span class="sxs-lookup"><span data-stu-id="75842-123">To get the ID number of a job, run the Get-Job cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75842-124">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="75842-124">-InstanceId</span></span>
<span data-ttu-id="75842-125">Especifica o GUID de ID de instância de um trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="75842-125">Specifies the instance ID GUID of a running job.</span></span>
<span data-ttu-id="75842-126">Para obter a *InstanceId* de um trabalho, execute o cmdlet **Get-Job** , canalizando os resultados em um cmdlet **Format-** \*, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="75842-126">To get the *InstanceId* of a job, run the **Get-Job** cmdlet, piping the results into a **Format-** \* cmdlet, as shown in the following example:</span></span>

`Get-Job | Format-List -Property Id,Name,InstanceId,State`

```yaml
Type: System.Guid
Parameter Sets: JobInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75842-127">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="75842-127">-Job</span></span>
<span data-ttu-id="75842-128">Especifica um objeto de trabalho em execução.</span><span class="sxs-lookup"><span data-stu-id="75842-128">Specifies a running job object.</span></span>
<span data-ttu-id="75842-129">A maneira mais simples de usar esse parâmetro é salvar os resultados de um comando **Get-Job** que retorna o trabalho em execução que você deseja depurar em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="75842-129">The simplest way to use this parameter is to save the results of a **Get-Job** command that returns the running job that you want to debug in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Management.Automation.Job
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="75842-130">-Name</span><span class="sxs-lookup"><span data-stu-id="75842-130">-Name</span></span>
<span data-ttu-id="75842-131">Especifica um trabalho pelo nome amigável do trabalho.</span><span class="sxs-lookup"><span data-stu-id="75842-131">Specifies a job by the friendly name of the job.</span></span>
<span data-ttu-id="75842-132">Ao iniciar um trabalho, você pode especificar um nome de trabalho adicionando o parâmetro *JobName* , em cmdlets como Invoke-Command e Start-Job.</span><span class="sxs-lookup"><span data-stu-id="75842-132">When you start a job, you can specify a job name by adding the *JobName* parameter, in cmdlets such as Invoke-Command and Start-Job.</span></span>

```yaml
Type: System.String
Parameter Sets: JobNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75842-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="75842-133">-Confirm</span></span>
<span data-ttu-id="75842-134">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75842-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="75842-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="75842-135">-WhatIf</span></span>
<span data-ttu-id="75842-136">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="75842-136">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="75842-137">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="75842-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="75842-138">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="75842-138">-BreakAll</span></span>

<span data-ttu-id="75842-139">{{Descrição de BreakAll de preenchimento}}</span><span class="sxs-lookup"><span data-stu-id="75842-139">{{ Fill BreakAll Description }}</span></span>

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

### <span data-ttu-id="75842-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="75842-140">CommonParameters</span></span>
<span data-ttu-id="75842-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="75842-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75842-142">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="75842-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75842-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="75842-143">INPUTS</span></span>

### <span data-ttu-id="75842-144">System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="75842-144">System.Management.Automation.RemotingJob</span></span>

## <span data-ttu-id="75842-145">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="75842-145">OUTPUTS</span></span>

## <span data-ttu-id="75842-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="75842-146">NOTES</span></span>

## <span data-ttu-id="75842-147">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="75842-147">RELATED LINKS</span></span>

[<span data-ttu-id="75842-148">Get-Job</span><span class="sxs-lookup"><span data-stu-id="75842-148">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="75842-149">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="75842-149">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="75842-150">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="75842-150">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="75842-151">Start-Job</span><span class="sxs-lookup"><span data-stu-id="75842-151">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="75842-152">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="75842-152">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="75842-153">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="75842-153">Wait-Job</span></span>](Wait-Job.md)

