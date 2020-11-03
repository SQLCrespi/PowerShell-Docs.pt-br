---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a0b5d7e86f9d63b487bc093feb18ecc7a4496999
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194567"
---
# <span data-ttu-id="32421-103">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="32421-103">Set-PSDebug</span></span>

## <span data-ttu-id="32421-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="32421-104">SYNOPSIS</span></span>
<span data-ttu-id="32421-105">Ativa/desativa os recursos de depuração de script, define o nível de rastreamento e ativa/desativa o modo estrito.</span><span class="sxs-lookup"><span data-stu-id="32421-105">Turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span>

## <span data-ttu-id="32421-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32421-106">SYNTAX</span></span>

### <span data-ttu-id="32421-107">em</span><span class="sxs-lookup"><span data-stu-id="32421-107">on</span></span>

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### <span data-ttu-id="32421-108">Desligar</span><span class="sxs-lookup"><span data-stu-id="32421-108">off</span></span>

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## <span data-ttu-id="32421-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32421-109">DESCRIPTION</span></span>

<span data-ttu-id="32421-110">O `Set-PSDebug` cmdlet ativa e desativa os recursos de depuração de script, define o nível de rastreamento e alterna o modo estrito.</span><span class="sxs-lookup"><span data-stu-id="32421-110">The `Set-PSDebug` cmdlet turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span> <span data-ttu-id="32421-111">Por padrão, os recursos de depuração do PowerShell estão desativados.</span><span class="sxs-lookup"><span data-stu-id="32421-111">By default, the PowerShell debug features are off.</span></span>

<span data-ttu-id="32421-112">Quando o parâmetro **trace** tem um valor de `1` , cada linha de script é rastreada à medida que é executada.</span><span class="sxs-lookup"><span data-stu-id="32421-112">When the **Trace** parameter has a value of `1`, each line of script is traced as it runs.</span></span> <span data-ttu-id="32421-113">Quando o parâmetro tem um valor de `2` , atribuições de variáveis, chamadas de função e chamadas de script também são rastreadas.</span><span class="sxs-lookup"><span data-stu-id="32421-113">When the parameter has a value of `2`, variable assignments, function calls, and script calls are also traced.</span></span> <span data-ttu-id="32421-114">Se o parâmetro **Step** for especificado, você será solicitado antes que cada linha do script seja executada.</span><span class="sxs-lookup"><span data-stu-id="32421-114">If the **Step** parameter is specified, you're prompted before each line of the script runs.</span></span>

## <span data-ttu-id="32421-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="32421-115">EXAMPLES</span></span>

### <span data-ttu-id="32421-116">Exemplo 1: definir o nível de rastreamento</span><span class="sxs-lookup"><span data-stu-id="32421-116">Example 1: Set the trace level</span></span>

<span data-ttu-id="32421-117">Este exemplo define o nível de rastreamento como `2` e, em seguida, executa um script que exibe os números 1, 2 e</span><span class="sxs-lookup"><span data-stu-id="32421-117">This example sets the trace level to `2`, and then runs a script that displays the numbers 1, 2, and</span></span>
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### <span data-ttu-id="32421-118">Exemplo 2: ativar a depuração</span><span class="sxs-lookup"><span data-stu-id="32421-118">Example 2: Turn on stepping</span></span>

<span data-ttu-id="32421-119">Este exemplo ativa a depuração e, em seguida, executa um script que exibe os números 1, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="32421-119">This example turns on stepping, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### <span data-ttu-id="32421-120">Exemplo 3: usar o modo estrito</span><span class="sxs-lookup"><span data-stu-id="32421-120">Example 3: Use strict mode</span></span>

<span data-ttu-id="32421-121">Este exemplo coloca o PowerShell no modo estrito e tenta acessar uma variável que não tem um valor atribuído.</span><span class="sxs-lookup"><span data-stu-id="32421-121">This example puts PowerShell in strict mode and attempts to access a variable that doesn't have an assigned value.</span></span>

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### <span data-ttu-id="32421-122">Exemplo 4: desativar os recursos de depuração</span><span class="sxs-lookup"><span data-stu-id="32421-122">Example 4: Turn off debug features</span></span>

<span data-ttu-id="32421-123">Este exemplo desativa todos os recursos de depuração e, em seguida, executa um script que exibe os números 1, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="32421-123">This example turns off all debugging features, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## <span data-ttu-id="32421-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32421-124">PARAMETERS</span></span>

### <span data-ttu-id="32421-125">-Desativado</span><span class="sxs-lookup"><span data-stu-id="32421-125">-Off</span></span>

<span data-ttu-id="32421-126">Desativa todos os recursos de depuração de scripts.</span><span class="sxs-lookup"><span data-stu-id="32421-126">Turns off all script debugging features.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32421-127">-Etapa</span><span class="sxs-lookup"><span data-stu-id="32421-127">-Step</span></span>

<span data-ttu-id="32421-128">Ativa a execução de script passo a passo.</span><span class="sxs-lookup"><span data-stu-id="32421-128">Turns on script stepping.</span></span> <span data-ttu-id="32421-129">Antes de cada linha ser executada, o PowerShell solicita que você pare, continue ou insira um novo nível de interpretador para inspecionar o estado do script.</span><span class="sxs-lookup"><span data-stu-id="32421-129">Before each line runs, PowerShell prompts you to stop, continue, or enter a new interpreter level to inspect the state of the script.</span></span>

<span data-ttu-id="32421-130">A especificação do parâmetro **Step** define automaticamente um nível de rastreamento de `1` .</span><span class="sxs-lookup"><span data-stu-id="32421-130">Specifying the **Step** parameter automatically sets a trace level of `1`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32421-131">-Estrito</span><span class="sxs-lookup"><span data-stu-id="32421-131">-Strict</span></span>

<span data-ttu-id="32421-132">Especifica que as variáveis devem ser atribuídas a um valor antes de serem referenciadas em um script.</span><span class="sxs-lookup"><span data-stu-id="32421-132">Specifies that variables must be assigned a value before being referenced in a script.</span></span> <span data-ttu-id="32421-133">Se uma variável for referenciada antes de um valor ser atribuído, o PowerShell retornará um erro de exceção.</span><span class="sxs-lookup"><span data-stu-id="32421-133">If a variable is referenced before a value is assigned, PowerShell returns an exception error.</span></span> <span data-ttu-id="32421-134">Isso é equivalente a `Set-StrictMode -Version 1`.</span><span class="sxs-lookup"><span data-stu-id="32421-134">This is equivalent to `Set-StrictMode -Version 1`.</span></span> <span data-ttu-id="32421-135">Para obter mais informações, consulte [Set-StrictMode](Set-StrictMode.md).</span><span class="sxs-lookup"><span data-stu-id="32421-135">For more information, see [Set-StrictMode](Set-StrictMode.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32421-136">-Rastreamento</span><span class="sxs-lookup"><span data-stu-id="32421-136">-Trace</span></span>

<span data-ttu-id="32421-137">Especifica o nível de rastreamento para cada linha em um script.</span><span class="sxs-lookup"><span data-stu-id="32421-137">Specifies the trace level for each line in a script.</span></span> <span data-ttu-id="32421-138">Cada linha é rastreada à medida que é executada.</span><span class="sxs-lookup"><span data-stu-id="32421-138">Each line is traced as it's run.</span></span>

<span data-ttu-id="32421-139">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="32421-139">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="32421-140">0: desativar o rastreamento de script.</span><span class="sxs-lookup"><span data-stu-id="32421-140">0: Turn script tracing off.</span></span>
- <span data-ttu-id="32421-141">1: rastrear linhas de script conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="32421-141">1: Trace script lines as they run.</span></span>
- <span data-ttu-id="32421-142">2: rastrear linhas de script, atribuições de variáveis, chamadas de função e scripts.</span><span class="sxs-lookup"><span data-stu-id="32421-142">2: Trace script lines, variable assignments, function calls, and scripts.</span></span>

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32421-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32421-143">CommonParameters</span></span>

<span data-ttu-id="32421-144">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="32421-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32421-145">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="32421-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32421-146">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="32421-146">INPUTS</span></span>

### <span data-ttu-id="32421-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="32421-147">None</span></span>

<span data-ttu-id="32421-148">Não é possível pipeline de entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="32421-148">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="32421-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="32421-149">OUTPUTS</span></span>

### <span data-ttu-id="32421-150">Nenhum</span><span class="sxs-lookup"><span data-stu-id="32421-150">None</span></span>

<span data-ttu-id="32421-151">Esse cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="32421-151">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="32421-152">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="32421-152">NOTES</span></span>

## <span data-ttu-id="32421-153">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="32421-153">RELATED LINKS</span></span>

[<span data-ttu-id="32421-154">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="32421-154">about_Debuggers</span></span>](./About/about_Debuggers.md)

[<span data-ttu-id="32421-155">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="32421-155">Debug-Process</span></span>](../Microsoft.PowerShell.Management/Debug-Process.md)

[<span data-ttu-id="32421-156">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="32421-156">Set-PSBreakpoint</span></span>](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[<span data-ttu-id="32421-157">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="32421-157">Set-StrictMode</span></span>](Set-StrictMode.md)

[<span data-ttu-id="32421-158">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="32421-158">Write-Debug</span></span>](../Microsoft.PowerShell.Utility/Write-Debug.md)

