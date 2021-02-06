---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 28cda7a2fa4435092b647e43a250222a852114b0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603350"
---
# <span data-ttu-id="4672d-102">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4672d-102">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="4672d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4672d-103">SYNOPSIS</span></span>
<span data-ttu-id="4672d-104">Habilita os pontos de interrupção no console atual.</span><span class="sxs-lookup"><span data-stu-id="4672d-104">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="4672d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4672d-105">SYNTAX</span></span>

### <span data-ttu-id="4672d-106">ID (padrão)</span><span class="sxs-lookup"><span data-stu-id="4672d-106">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4672d-107">Ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="4672d-107">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="4672d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4672d-108">DESCRIPTION</span></span>

<span data-ttu-id="4672d-109">O `Enable-PSBreakpoint` cmdlet habilita novamente os pontos de interrupção desabilitados.</span><span class="sxs-lookup"><span data-stu-id="4672d-109">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="4672d-110">Você pode usá-lo para habilitar todos os pontos de interrupção ou pontos de interrupção específicos fornecendo objetos ou IDs de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4672d-110">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="4672d-111">Um ponto de interrupção é um Point em um script em que a execução é interrompida temporariamente para que você possa examinar o estado do script.</span><span class="sxs-lookup"><span data-stu-id="4672d-111">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="4672d-112">Os pontos de interrupção recém-criados são habilitados automaticamente, mas podem ser desabilitados usando `Disable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="4672d-112">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="4672d-113">Tecnicamente, esse cmdlet altera o valor da propriedade **Enabled** de um objeto de ponto de interrupção para **true**.</span><span class="sxs-lookup"><span data-stu-id="4672d-113">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True**.</span></span>

<span data-ttu-id="4672d-114">`Enable-PSBreakpoint` é um dos vários cmdlets projetados para depurar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4672d-114">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="4672d-115">Para obter mais informações sobre o depurador do PowerShell, consulte [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="4672d-115">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="4672d-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4672d-116">EXAMPLES</span></span>

### <span data-ttu-id="4672d-117">Exemplo 1: habilitar todos os pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="4672d-117">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="4672d-118">Este exemplo habilita todos os pontos de interrupção na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="4672d-118">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="4672d-119">Usando aliases, este exemplo pode ser abreviado como `gbp | ebp` .</span><span class="sxs-lookup"><span data-stu-id="4672d-119">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="4672d-120">Exemplo 2: habilitar pontos de interrupção por ID</span><span class="sxs-lookup"><span data-stu-id="4672d-120">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="4672d-121">Este exemplo habilita vários pontos de interrupção usando suas IDs de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4672d-121">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="4672d-122">Exemplo 3: habilitar um ponto de interrupção desabilitado</span><span class="sxs-lookup"><span data-stu-id="4672d-122">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="4672d-123">Este exemplo habilita novamente um ponto de interrupção que foi desabilitado.</span><span class="sxs-lookup"><span data-stu-id="4672d-123">This example re-enables a breakpoint that has been disabled.</span></span>

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

<span data-ttu-id="4672d-124">`Set-PSBreakpoint` Cria um ponto de interrupção na variável de **nome** no `Sample.ps1` script que salva o objeto de ponto de interrupção na `$B` variável.</span><span class="sxs-lookup"><span data-stu-id="4672d-124">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="4672d-125">O parâmetro **PassThru** exibe o valor da propriedade **Enabled** do ponto de interrupção é **false**.</span><span class="sxs-lookup"><span data-stu-id="4672d-125">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False**.</span></span>

<span data-ttu-id="4672d-126">`Enable-PSBreakpoint` habilita novamente o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4672d-126">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="4672d-127">Novamente, usando o parâmetro **PassThru** , vemos que o valor da propriedade **Enabled** é **true**.</span><span class="sxs-lookup"><span data-stu-id="4672d-127">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True**.</span></span>

### <span data-ttu-id="4672d-128">Exemplo 4: habilitar pontos de interrupção usando uma variável</span><span class="sxs-lookup"><span data-stu-id="4672d-128">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="4672d-129">Este exemplo habilita um conjunto de pontos de interrupção usando os objetos de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4672d-129">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="4672d-130">`Get-PSBreakpoint` Obtém os pontos de interrupção e salva-os na `$B` variável.</span><span class="sxs-lookup"><span data-stu-id="4672d-130">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="4672d-131">Usando o parâmetro **Breakpoint** , `Enable-PSBreakpoint` habilita os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4672d-131">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="4672d-132">Este exemplo é equivalente a executar `Enable-PSBreakpoint -Id 3, 5` .</span><span class="sxs-lookup"><span data-stu-id="4672d-132">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="4672d-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4672d-133">PARAMETERS</span></span>

### <span data-ttu-id="4672d-134">-Ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="4672d-134">-Breakpoint</span></span>

<span data-ttu-id="4672d-135">Especifica os pontos de interrupção para habilitar.</span><span class="sxs-lookup"><span data-stu-id="4672d-135">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="4672d-136">Forneça uma variável que contém pontos de interrupção ou um comando que obtém objetos de ponto de interrupção, como `Get-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="4672d-136">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="4672d-137">Também é possível canalizar objetos de ponto de interrupção para `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="4672d-137">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

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

### <span data-ttu-id="4672d-138">-Id</span><span class="sxs-lookup"><span data-stu-id="4672d-138">-Id</span></span>

<span data-ttu-id="4672d-139">Especifica os números de **ID** dos pontos de interrupção a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="4672d-139">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="4672d-140">O valor padrão é todos os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4672d-140">The default value is all breakpoints.</span></span>
<span data-ttu-id="4672d-141">Forneça a **ID** por número ou em uma variável.</span><span class="sxs-lookup"><span data-stu-id="4672d-141">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="4672d-142">Não é possível canalizar números de **ID** para `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="4672d-142">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="4672d-143">Para localizar a **ID** de um ponto de interrupção, use o `Get-PSBreakpoint` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4672d-143">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

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

### <span data-ttu-id="4672d-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4672d-144">-PassThru</span></span>

<span data-ttu-id="4672d-145">Retorna um objeto que representa o ponto de interrupção que está sendo habilitado.</span><span class="sxs-lookup"><span data-stu-id="4672d-145">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="4672d-146">Por padrão, esse cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="4672d-146">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="4672d-147">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4672d-147">-Confirm</span></span>

<span data-ttu-id="4672d-148">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4672d-148">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4672d-149">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4672d-149">-WhatIf</span></span>

<span data-ttu-id="4672d-150">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="4672d-150">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="4672d-151">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="4672d-151">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="4672d-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4672d-152">CommonParameters</span></span>

<span data-ttu-id="4672d-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4672d-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4672d-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4672d-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4672d-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4672d-155">INPUTS</span></span>

### <span data-ttu-id="4672d-156">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="4672d-156">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="4672d-157">É possível canalizar um objeto de ponto de interrupção para `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="4672d-157">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="4672d-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4672d-158">OUTPUTS</span></span>

### <span data-ttu-id="4672d-159">Nenhum ou System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="4672d-159">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="4672d-160">Quando você usa o parâmetro **PassThru** , `Enable-PSBreakpoint` retorna um objeto de ponto de interrupção que representa o ponto de interrupção que foi habilitado.</span><span class="sxs-lookup"><span data-stu-id="4672d-160">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="4672d-161">Caso contrário, esse cmdlet não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="4672d-161">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="4672d-162">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4672d-162">NOTES</span></span>

- <span data-ttu-id="4672d-163">O `Enable-PSBreakpoint` cmdlet não gerará um erro se você tentar habilitar um ponto de interrupção que já está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4672d-163">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="4672d-164">Dessa forma, você pode habilitar todos os pontos de interrupção sem erro, mesmo quando apenas alguns estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="4672d-164">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="4672d-165">Os pontos de interrupção são habilitados quando você os cria usando o `Set-PSBreakpoint` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4672d-165">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="4672d-166">Você não precisa habilitar pontos de interrupção recém-criados.</span><span class="sxs-lookup"><span data-stu-id="4672d-166">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="4672d-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4672d-167">RELATED LINKS</span></span>

[<span data-ttu-id="4672d-168">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4672d-168">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="4672d-169">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4672d-169">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="4672d-170">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="4672d-170">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="4672d-171">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4672d-171">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="4672d-172">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4672d-172">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

