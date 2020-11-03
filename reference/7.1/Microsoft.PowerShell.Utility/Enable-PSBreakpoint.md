---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 547739d6482e86bc558245bc5c5f04eddcfe9614
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194278"
---
# <span data-ttu-id="fd497-103">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fd497-103">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="fd497-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fd497-104">SYNOPSIS</span></span>
<span data-ttu-id="fd497-105">Habilita os pontos de interrupção no console atual.</span><span class="sxs-lookup"><span data-stu-id="fd497-105">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="fd497-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd497-106">SYNTAX</span></span>

### <span data-ttu-id="fd497-107">ID (padrão)</span><span class="sxs-lookup"><span data-stu-id="fd497-107">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fd497-108">Ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="fd497-108">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="fd497-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd497-109">DESCRIPTION</span></span>

<span data-ttu-id="fd497-110">O `Enable-PSBreakpoint` cmdlet habilita novamente os pontos de interrupção desabilitados.</span><span class="sxs-lookup"><span data-stu-id="fd497-110">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="fd497-111">Você pode usá-lo para habilitar todos os pontos de interrupção ou pontos de interrupção específicos fornecendo objetos ou IDs de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd497-111">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="fd497-112">Um ponto de interrupção é um Point em um script em que a execução é interrompida temporariamente para que você possa examinar o estado do script.</span><span class="sxs-lookup"><span data-stu-id="fd497-112">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="fd497-113">Os pontos de interrupção recém-criados são habilitados automaticamente, mas podem ser desabilitados usando `Disable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="fd497-113">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="fd497-114">Tecnicamente, esse cmdlet altera o valor da propriedade **Enabled** de um objeto de ponto de interrupção para **true** .</span><span class="sxs-lookup"><span data-stu-id="fd497-114">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True** .</span></span>

<span data-ttu-id="fd497-115">`Enable-PSBreakpoint` é um dos vários cmdlets projetados para depurar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd497-115">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="fd497-116">Para obter mais informações sobre o depurador do PowerShell, consulte [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="fd497-116">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="fd497-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fd497-117">EXAMPLES</span></span>

### <span data-ttu-id="fd497-118">Exemplo 1: habilitar todos os pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="fd497-118">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="fd497-119">Este exemplo habilita todos os pontos de interrupção na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd497-119">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="fd497-120">Usando aliases, este exemplo pode ser abreviado como `gbp | ebp` .</span><span class="sxs-lookup"><span data-stu-id="fd497-120">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="fd497-121">Exemplo 2: habilitar pontos de interrupção por ID</span><span class="sxs-lookup"><span data-stu-id="fd497-121">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="fd497-122">Este exemplo habilita vários pontos de interrupção usando suas IDs de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd497-122">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="fd497-123">Exemplo 3: habilitar um ponto de interrupção desabilitado</span><span class="sxs-lookup"><span data-stu-id="fd497-123">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="fd497-124">Este exemplo habilita novamente um ponto de interrupção que foi desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fd497-124">This example re-enables a breakpoint that has been disabled.</span></span>

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="fd497-125">`Set-PSBreakpoint` Cria um ponto de interrupção na variável de **nome** no `Sample.ps1` script que salva o objeto de ponto de interrupção na `$B` variável.</span><span class="sxs-lookup"><span data-stu-id="fd497-125">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="fd497-126">O parâmetro **PassThru** exibe o valor da propriedade **Enabled** do ponto de interrupção é **false** .</span><span class="sxs-lookup"><span data-stu-id="fd497-126">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False** .</span></span>

<span data-ttu-id="fd497-127">`Enable-PSBreakpoint` habilita novamente o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd497-127">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="fd497-128">Novamente, usando o parâmetro **PassThru** , vemos que o valor da propriedade **Enabled** é **true** .</span><span class="sxs-lookup"><span data-stu-id="fd497-128">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True** .</span></span>

### <span data-ttu-id="fd497-129">Exemplo 4: habilitar pontos de interrupção usando uma variável</span><span class="sxs-lookup"><span data-stu-id="fd497-129">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="fd497-130">Este exemplo habilita um conjunto de pontos de interrupção usando os objetos de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd497-130">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="fd497-131">`Get-PSBreakpoint` Obtém os pontos de interrupção e salva-os na `$B` variável.</span><span class="sxs-lookup"><span data-stu-id="fd497-131">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="fd497-132">Usando o parâmetro **Breakpoint** , `Enable-PSBreakpoint` habilita os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd497-132">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="fd497-133">Este exemplo é equivalente a executar `Enable-PSBreakpoint -Id 3, 5` .</span><span class="sxs-lookup"><span data-stu-id="fd497-133">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="fd497-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd497-134">PARAMETERS</span></span>

### <span data-ttu-id="fd497-135">-Ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="fd497-135">-Breakpoint</span></span>

<span data-ttu-id="fd497-136">Especifica os pontos de interrupção para habilitar.</span><span class="sxs-lookup"><span data-stu-id="fd497-136">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="fd497-137">Forneça uma variável que contém pontos de interrupção ou um comando que obtém objetos de ponto de interrupção, como `Get-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="fd497-137">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="fd497-138">Também é possível canalizar objetos de ponto de interrupção para `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="fd497-138">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fd497-139">-Id</span><span class="sxs-lookup"><span data-stu-id="fd497-139">-Id</span></span>

<span data-ttu-id="fd497-140">Especifica os números de **ID** dos pontos de interrupção a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="fd497-140">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="fd497-141">O valor padrão é todos os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fd497-141">The default value is all breakpoints.</span></span>
<span data-ttu-id="fd497-142">Forneça a **ID** por número ou em uma variável.</span><span class="sxs-lookup"><span data-stu-id="fd497-142">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="fd497-143">Não é possível canalizar números de **ID** para `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="fd497-143">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="fd497-144">Para localizar a **ID** de um ponto de interrupção, use o `Get-PSBreakpoint` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd497-144">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd497-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fd497-145">-PassThru</span></span>

<span data-ttu-id="fd497-146">Retorna um objeto que representa o ponto de interrupção que está sendo habilitado.</span><span class="sxs-lookup"><span data-stu-id="fd497-146">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="fd497-147">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="fd497-147">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="fd497-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd497-148">-Confirm</span></span>

<span data-ttu-id="fd497-149">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd497-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd497-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd497-150">-WhatIf</span></span>

<span data-ttu-id="fd497-151">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="fd497-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fd497-152">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="fd497-152">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="fd497-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd497-153">CommonParameters</span></span>

<span data-ttu-id="fd497-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fd497-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd497-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fd497-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd497-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fd497-156">INPUTS</span></span>

### <span data-ttu-id="fd497-157">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="fd497-157">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="fd497-158">É possível canalizar um objeto de ponto de interrupção para `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="fd497-158">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="fd497-159">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fd497-159">OUTPUTS</span></span>

### <span data-ttu-id="fd497-160">Nenhum ou System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="fd497-160">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="fd497-161">Quando você usa o parâmetro **PassThru** , `Enable-PSBreakpoint` retorna um objeto de ponto de interrupção que representa o ponto de interrupção que foi habilitado.</span><span class="sxs-lookup"><span data-stu-id="fd497-161">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="fd497-162">Caso contrário, esse cmdlet não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="fd497-162">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="fd497-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fd497-163">NOTES</span></span>

- <span data-ttu-id="fd497-164">O `Enable-PSBreakpoint` cmdlet não gerará um erro se você tentar habilitar um ponto de interrupção que já está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fd497-164">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="fd497-165">Dessa forma, você pode habilitar todos os pontos de interrupção sem erro, mesmo quando apenas alguns estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="fd497-165">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="fd497-166">Os pontos de interrupção são habilitados quando você os cria usando o `Set-PSBreakpoint` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd497-166">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="fd497-167">Você não precisa habilitar pontos de interrupção recém-criados.</span><span class="sxs-lookup"><span data-stu-id="fd497-167">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="fd497-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fd497-168">RELATED LINKS</span></span>

[<span data-ttu-id="fd497-169">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fd497-169">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="fd497-170">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fd497-170">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="fd497-171">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="fd497-171">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="fd497-172">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fd497-172">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="fd497-173">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fd497-173">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

