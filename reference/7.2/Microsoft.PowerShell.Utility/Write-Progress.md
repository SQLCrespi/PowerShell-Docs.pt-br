---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 2e2bd5474198745d72ad2b87c3c305695a198f22
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595771"
---
# <span data-ttu-id="8272d-102">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="8272d-102">Write-Progress</span></span>

## <span data-ttu-id="8272d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8272d-103">SYNOPSIS</span></span>
<span data-ttu-id="8272d-104">Exibe uma barra de progresso dentro de uma janela de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8272d-104">Displays a progress bar within a PowerShell command window.</span></span>

## <span data-ttu-id="8272d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8272d-105">SYNTAX</span></span>

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="8272d-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8272d-106">DESCRIPTION</span></span>

<span data-ttu-id="8272d-107">O `Write-Progress` cmdlet exibe uma barra de progresso em uma janela de comando do PowerShell que descreve o status de um comando ou script em execução.</span><span class="sxs-lookup"><span data-stu-id="8272d-107">The `Write-Progress` cmdlet displays a progress bar in a PowerShell command window that depicts the status of a running command or script.</span></span> <span data-ttu-id="8272d-108">Você pode selecionar os indicadores que a barra reflete e o texto que aparece acima e abaixo da barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="8272d-108">You can select the indicators that the bar reflects and the text that appears above and below the progress bar.</span></span>

## <span data-ttu-id="8272d-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8272d-109">EXAMPLES</span></span>

### <span data-ttu-id="8272d-110">Exemplo 1: exibir o progresso de um loop for</span><span class="sxs-lookup"><span data-stu-id="8272d-110">Example 1: Display the progress of a For loop</span></span>

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

<span data-ttu-id="8272d-111">Este comando exibe o progresso de um loop For que realiza a contagem de 1 a 100.</span><span class="sxs-lookup"><span data-stu-id="8272d-111">This command displays the progress of a For loop that counts from 1 to 100.</span></span>

<span data-ttu-id="8272d-112">O `Write-Progress` cmdlet inclui um título de barra de status `Activity` , uma linha de status e a variável `$i` (o contador no loop for), que indica a conclusão relativa da tarefa.</span><span class="sxs-lookup"><span data-stu-id="8272d-112">The `Write-Progress` cmdlet includes a status bar heading `Activity`, a status line, and the variable `$i` (the counter in the For loop), which indicates the relative completeness of the task.</span></span>

### <span data-ttu-id="8272d-113">Exemplo 2: exibir o progresso de loops for aninhados</span><span class="sxs-lookup"><span data-stu-id="8272d-113">Example 2: Display the progress of nested For loops</span></span>

```powershell
for($I = 1; $I -lt 101; $I++ )
{
    Write-Progress -Activity Updating -Status 'Progress->' -PercentComplete $I -CurrentOperation OuterLoop
    for($j = 1; $j -lt 101; $j++ )
    {
        Write-Progress -Id 1 -Activity Updating -Status 'Progress' -PercentComplete $j -CurrentOperation InnerLoop
    }
}
```

```Output
Updating
Progress ->
 [ooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo]
OuterLoop
Updating
Progress
 [oooooooooooooooooo                                                   ]
InnerLoop
```

<span data-ttu-id="8272d-114">Este exemplo exibe o progresso de dois loops aninhados For, cada um dos quais é representado por uma barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="8272d-114">This example displays the progress of two nested For loops, each of which is represented by a progress bar.</span></span>

<span data-ttu-id="8272d-115">O `Write-Progress` comando da segunda barra de progresso inclui o parâmetro **ID** que o distingue da primeira barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="8272d-115">The `Write-Progress` command for the second progress bar includes the **Id** parameter that distinguishes it from the first progress bar.</span></span>

<span data-ttu-id="8272d-116">Sem o parâmetro **ID** , as barras de progresso seriam sobrepostas umas às outras em vez de serem exibidas uma abaixo da outra.</span><span class="sxs-lookup"><span data-stu-id="8272d-116">Without the **Id** parameter, the progress bars would be superimposed on each other instead of being displayed one below the other.</span></span>

### <span data-ttu-id="8272d-117">Exemplo 3: exibir o progresso ao procurar uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8272d-117">Example 3: Display the progress while searching for a string</span></span>

```powershell
# Use Get-EventLog to get the events in the System log and store them in the $Events variable.
$Events = Get-EventLog -LogName system
# Pipe the events to the ForEach-Object cmdlet.
$Events | ForEach-Object -Begin {
    # In the Begin block, use Clear-Host to clear the screen.
    Clear-Host
    # Set the $i counter variable to zero.
    $i = 0
    # Set the $out variable to a empty string.
    $out = ""
} -Process {
    # In the Process script block search the message property of each incoming object for "bios".
    if($_.message -like "*bios*")
    {
        # Append the matching message to the out variable.
        $out=$out + $_.Message
    }
    # Increment the $i counter variable which is used to create the progress bar.
    $i = $i+1
    # Use Write-Progress to output a progress bar.
    # The Activity and Status parameters create the first and second lines of the progress bar heading, respectively.
    Write-Progress -Activity "Searching Events" -Status "Progress:" -PercentComplete ($i/$Events.count*100)
} -End {
    # Display the matching messages using the out variable.
    $out
}
```

<span data-ttu-id="8272d-118">Este comando exibe o progresso de um comando para encontrar a cadeia de caracteres "bios" no log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="8272d-118">This command displays the progress of a command to find the string "bios" in the System event log.</span></span>

<span data-ttu-id="8272d-119">O valor do parâmetro **PercentComplete** é calculado dividindo-se o número de eventos que foram processados `$I` pelo número total de eventos recuperados `$Events.count` e, em seguida, multiplicando esse resultado por 100.</span><span class="sxs-lookup"><span data-stu-id="8272d-119">The **PercentComplete** parameter value is calculated by dividing the number of events that have been processed `$I` by the total number of events retrieved `$Events.count` and then multiplying that result by 100.</span></span>

### <span data-ttu-id="8272d-120">Exemplo 4: exibir o progresso de cada nível de um processo aninhado</span><span class="sxs-lookup"><span data-stu-id="8272d-120">Example 4: Display progress for each level of a nested process</span></span>

```powershell
foreach ( $i in 1..10 ) {
  Write-Progress -Id 0 "Step $i"
  foreach ( $j in 1..10 ) {
    Write-Progress -Id 1 -ParentId 0 "Step $i - Substep $j"
    foreach ( $k in 1..10 ) {
      Write-Progress -Id 2  -ParentId 1 "Step $i - Substep $j - iteration $k"; start-sleep -m 150
    }
  }
}
```

```Output
Step 1
     Processing
    Step 1 - Substep 2
         Processing
        Step 1 - Substep 2 - Iteration 3
             Processing
```

<span data-ttu-id="8272d-121">Neste exemplo, você pode usar o parâmetro **parentID** para ter uma saída recuada para mostrar relações pai/filho no andamento de cada etapa.</span><span class="sxs-lookup"><span data-stu-id="8272d-121">In this example you can use the **ParentId** parameter to have indented output to show parent/child relationships in the progress of each step.</span></span>

## <span data-ttu-id="8272d-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8272d-122">PARAMETERS</span></span>

### <span data-ttu-id="8272d-123">-Atividade</span><span class="sxs-lookup"><span data-stu-id="8272d-123">-Activity</span></span>

<span data-ttu-id="8272d-124">Especifica a primeira linha de texto no título acima da barra de status.</span><span class="sxs-lookup"><span data-stu-id="8272d-124">Specifies the first line of text in the heading above the status bar.</span></span>
<span data-ttu-id="8272d-125">Esse texto descreve a atividade cujo progresso está sendo relatado.</span><span class="sxs-lookup"><span data-stu-id="8272d-125">This text describes the activity whose progress is being reported.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-126">-Concluído</span><span class="sxs-lookup"><span data-stu-id="8272d-126">-Completed</span></span>

<span data-ttu-id="8272d-127">Indica se a barra de progresso está visível.</span><span class="sxs-lookup"><span data-stu-id="8272d-127">Indicates whether the progress bar is visible.</span></span>
<span data-ttu-id="8272d-128">Se esse parâmetro for omitido, `Write-Progress` exibirá informações de progresso.</span><span class="sxs-lookup"><span data-stu-id="8272d-128">If this parameter is omitted, `Write-Progress` displays progress information.</span></span>

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

### <span data-ttu-id="8272d-129">-CurrentOperation</span><span class="sxs-lookup"><span data-stu-id="8272d-129">-CurrentOperation</span></span>

<span data-ttu-id="8272d-130">Especifica a linha de texto abaixo da barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="8272d-130">Specifies the line of text below the progress bar.</span></span>
<span data-ttu-id="8272d-131">Esse texto descreve a operação que está ocorrendo no momento.</span><span class="sxs-lookup"><span data-stu-id="8272d-131">This text describes the operation that is currently taking place.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-132">-Id</span><span class="sxs-lookup"><span data-stu-id="8272d-132">-Id</span></span>

<span data-ttu-id="8272d-133">Especifica um identificador que distingue cada barra de progresso das demais.</span><span class="sxs-lookup"><span data-stu-id="8272d-133">Specifies an ID that distinguishes each progress bar from the others.</span></span> <span data-ttu-id="8272d-134">Use este parâmetro quando você estiver criando mais de uma barra de progresso em um único comando.</span><span class="sxs-lookup"><span data-stu-id="8272d-134">Use this parameter when you are creating more than one progress bar in a single command.</span></span> <span data-ttu-id="8272d-135">Se as barras de progresso não possuem identificadores diferentes, elas são sobrepostas em vez de exibidas em série.</span><span class="sxs-lookup"><span data-stu-id="8272d-135">If the progress bars do not have different IDs, they are superimposed instead of being displayed in a series.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-136">-ParentId</span><span class="sxs-lookup"><span data-stu-id="8272d-136">-ParentId</span></span>

<span data-ttu-id="8272d-137">Especifica a atividade pai da atividade atual.</span><span class="sxs-lookup"><span data-stu-id="8272d-137">Specifies the parent activity of the current activity.</span></span>
<span data-ttu-id="8272d-138">Use o valor -1 se a atividade atual não tem nenhuma atividade pai.</span><span class="sxs-lookup"><span data-stu-id="8272d-138">Use the value -1 if the current activity has no parent activity.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-139">-PercentComplete</span><span class="sxs-lookup"><span data-stu-id="8272d-139">-PercentComplete</span></span>

<span data-ttu-id="8272d-140">Especifica a porcentagem concluída de uma determinada atividade.</span><span class="sxs-lookup"><span data-stu-id="8272d-140">Specifies the percentage of the activity that is completed.</span></span>
<span data-ttu-id="8272d-141">Use o valor -1 se a porcentagem concluída é desconhecida ou não aplicável.</span><span class="sxs-lookup"><span data-stu-id="8272d-141">Use the value -1 if the percentage complete is unknown or not applicable.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-142">-SecondsRemaining</span><span class="sxs-lookup"><span data-stu-id="8272d-142">-SecondsRemaining</span></span>

<span data-ttu-id="8272d-143">Especifica o número previsto de segundos restantes até que a atividade seja concluída.</span><span class="sxs-lookup"><span data-stu-id="8272d-143">Specifies the projected number of seconds remaining until the activity is completed.</span></span>
<span data-ttu-id="8272d-144">Use o valor -1 se o número de segundos restantes é desconhecido ou não aplicável.</span><span class="sxs-lookup"><span data-stu-id="8272d-144">Use the value -1 if the number of seconds remaining is unknown or not applicable.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-145">-SourceID</span><span class="sxs-lookup"><span data-stu-id="8272d-145">-SourceId</span></span>

<span data-ttu-id="8272d-146">Especifica a origem do registro.</span><span class="sxs-lookup"><span data-stu-id="8272d-146">Specifies the source of the record.</span></span> <span data-ttu-id="8272d-147">Você pode usar isso no lugar da **ID** , mas não pode ser usado com outros parâmetros como **parentID**.</span><span class="sxs-lookup"><span data-stu-id="8272d-147">You can use this in place of **Id** but cannot be used with other parameters like **ParentId**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-148">-Status</span><span class="sxs-lookup"><span data-stu-id="8272d-148">-Status</span></span>

<span data-ttu-id="8272d-149">Especifica a segunda linha de texto no título acima da barra de status.</span><span class="sxs-lookup"><span data-stu-id="8272d-149">Specifies the second line of text in the heading above the status bar.</span></span>
<span data-ttu-id="8272d-150">Esse texto descreve o estado atual da atividade.</span><span class="sxs-lookup"><span data-stu-id="8272d-150">This text describes current state of the activity.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8272d-151">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8272d-151">CommonParameters</span></span>

<span data-ttu-id="8272d-152">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8272d-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8272d-153">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8272d-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8272d-154">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8272d-154">INPUTS</span></span>

### <span data-ttu-id="8272d-155">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8272d-155">None</span></span>

<span data-ttu-id="8272d-156">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8272d-156">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8272d-157">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8272d-157">OUTPUTS</span></span>

### <span data-ttu-id="8272d-158">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8272d-158">None</span></span>

<span data-ttu-id="8272d-159">`Write-Progress` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="8272d-159">`Write-Progress` does not generate any output.</span></span>

## <span data-ttu-id="8272d-160">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8272d-160">NOTES</span></span>

<span data-ttu-id="8272d-161">Se a barra de progresso não for exibida, verifique o valor da `$ProgressPreference` variável.</span><span class="sxs-lookup"><span data-stu-id="8272d-161">If the progress bar does not appear, check the value of the `$ProgressPreference` variable.</span></span> <span data-ttu-id="8272d-162">Se o valor está definido como SilentlyContinue, a barra de progresso não é exibida.</span><span class="sxs-lookup"><span data-stu-id="8272d-162">If the value is set to SilentlyContinue, the progress bar is not displayed.</span></span> <span data-ttu-id="8272d-163">Para obter mais informações sobre as preferências do PowerShell, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8272d-163">For more information about PowerShell preferences, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="8272d-164">Os parâmetros do cmdlet correspondem às propriedades da classe **System. Management. Automation. ProgressRecord** .</span><span class="sxs-lookup"><span data-stu-id="8272d-164">The parameters of the cmdlet correspond to the properties of the **System.Management.Automation.ProgressRecord** class.</span></span> <span data-ttu-id="8272d-165">Para obter mais informações, consulte [classe ProgressRecord](/dotnet/api/system.management.automation.progressrecord).</span><span class="sxs-lookup"><span data-stu-id="8272d-165">For more information, see [ProgressRecord Class](/dotnet/api/system.management.automation.progressrecord).</span></span>

## <span data-ttu-id="8272d-166">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8272d-166">RELATED LINKS</span></span>

[<span data-ttu-id="8272d-167">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="8272d-167">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="8272d-168">Write-Error</span><span class="sxs-lookup"><span data-stu-id="8272d-168">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="8272d-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="8272d-169">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="8272d-170">Write-Output</span><span class="sxs-lookup"><span data-stu-id="8272d-170">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="8272d-171">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="8272d-171">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="8272d-172">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="8272d-172">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="8272d-173">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="8272d-173">Write-Warning</span></span>](Write-Warning.md)
