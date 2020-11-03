---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 66ef0cec2bfdb1aa70b97001830811f68c68b911
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194509"
---
# <span data-ttu-id="e62e9-103">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e62e9-103">Disable-PSBreakpoint</span></span>

## <span data-ttu-id="e62e9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e62e9-104">SYNOPSIS</span></span>
<span data-ttu-id="e62e9-105">Desabilita os pontos de interrupção no console atual.</span><span class="sxs-lookup"><span data-stu-id="e62e9-105">Disables the breakpoints in the current console.</span></span>

## <span data-ttu-id="e62e9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e62e9-106">SYNTAX</span></span>

### <span data-ttu-id="e62e9-107">Ponto de interrupção (padrão)</span><span class="sxs-lookup"><span data-stu-id="e62e9-107">Breakpoint (Default)</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e62e9-108">ID</span><span class="sxs-lookup"><span data-stu-id="e62e9-108">Id</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e62e9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e62e9-109">DESCRIPTION</span></span>

<span data-ttu-id="e62e9-110">O cmdlet **Disable-PSBreakpoint** desabilita pontos de interrupção, o que garante que eles não sejam atingidos quando o script for executado.</span><span class="sxs-lookup"><span data-stu-id="e62e9-110">The **Disable-PSBreakpoint** cmdlet disables breakpoints, which assures that they are not hit when the script runs.</span></span>
<span data-ttu-id="e62e9-111">Você pode usá-lo para desabilitar todos os pontos de interrupção ou pode especificar os pontos de interrupção enviando objetos de ponto de interrupção ou IDs de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e62e9-111">You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.</span></span>

<span data-ttu-id="e62e9-112">Tecnicamente, esse cmdlet altera o valor da propriedade Enabled de um objeto de ponto de interrupção para False.</span><span class="sxs-lookup"><span data-stu-id="e62e9-112">Technically, this cmdlet changes the value of the Enabled property of a breakpoint object to False.</span></span>
<span data-ttu-id="e62e9-113">Para reabilitar um ponto de interrupção, use o cmdlet Enable-PSBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="e62e9-113">To re-enable a breakpoint, use the Enable-PSBreakpoint cmdlet.</span></span>
<span data-ttu-id="e62e9-114">Pontos de interrupção estão habilitados por padrão ao criá-los usando o cmdlet Set-PSBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="e62e9-114">Breakpoints are enabled by default when you create them by using the Set-PSBreakpoint cmdlet.</span></span>

<span data-ttu-id="e62e9-115">Um ponto de interrupção é um ponto em um script onde a execução para temporariamente para que você possa examinar as instruções no script.</span><span class="sxs-lookup"><span data-stu-id="e62e9-115">A breakpoint is a point in a script where execution stops temporarily so that you can examine the instructions in the script.</span></span>
<span data-ttu-id="e62e9-116">**Disable-PSBreakpoint** é um dos vários cmdlets projetados para depurar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e62e9-116">**Disable-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="e62e9-117">Para obter mais informações sobre o depurador do PowerShell, consulte about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="e62e9-117">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="e62e9-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e62e9-118">EXAMPLES</span></span>

### <span data-ttu-id="e62e9-119">Exemplo 1: definir um ponto de interrupção e desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="e62e9-119">Example 1: Set a breakpoint and disable it</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

<span data-ttu-id="e62e9-120">Esses comandos desabilitam um ponto de interrupção recém-criado.</span><span class="sxs-lookup"><span data-stu-id="e62e9-120">These commands disable a newly-created breakpoint.</span></span>

<span data-ttu-id="e62e9-121">O primeiro comando usa o cmdlet Set-PSBreakpoint para criar um ponto de interrupção na variável *Name* no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="e62e9-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the *Name* variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="e62e9-122">Em seguida, ele salva o objeto de ponto de interrupção na variável $B.</span><span class="sxs-lookup"><span data-stu-id="e62e9-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="e62e9-123">O segundo comando usa o cmdlet **Disable-PSBreakpoint** para desabilitar o novo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e62e9-123">The second command uses the **Disable-PSBreakpoint** cmdlet to disable the new breakpoint.</span></span>
<span data-ttu-id="e62e9-124">Ele usa um operador de pipeline (|) para enviar o objeto de ponto de interrupção em $B para o cmdlet **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="e62e9-124">It uses a pipeline operator (|) to send the breakpoint object in $B to the **Disable-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="e62e9-125">Como resultado desse comando, o valor da propriedade Enabled do objeto de ponto de interrupção no $B é false.</span><span class="sxs-lookup"><span data-stu-id="e62e9-125">As a result of this command, the value of the Enabled property of the breakpoint object in $B is False.</span></span>

### <span data-ttu-id="e62e9-126">Exemplo 2: desabilitar um ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="e62e9-126">Example 2: Disable a breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Id 0
```

<span data-ttu-id="e62e9-127">Este comando desabilita o ponto de interrupção com a ID do ponto de interrupção 0.</span><span class="sxs-lookup"><span data-stu-id="e62e9-127">This command disables the breakpoint with breakpoint ID 0.</span></span>

### <span data-ttu-id="e62e9-128">Exemplo 3: criar um ponto de interrupção desabilitado</span><span class="sxs-lookup"><span data-stu-id="e62e9-128">Example 3: Create a disabled breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

<span data-ttu-id="e62e9-129">Este comando cria um novo ponto de interrupção que será desabilitado até você habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="e62e9-129">This command creates a new breakpoint that is disabled until you enable it.</span></span>

<span data-ttu-id="e62e9-130">Ele usa o cmdlet **Disable-PSBreakpoint** para desabilitar o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e62e9-130">It uses the **Disable-PSBreakpoint** cmdlet to disable the breakpoint.</span></span>
<span data-ttu-id="e62e9-131">O valor do parâmetro *Breakpoint* é um comando Set-PSBreakpoint que define um novo ponto de interrupção, gera um objeto de ponto de interrupção e salva o objeto na variável $B.</span><span class="sxs-lookup"><span data-stu-id="e62e9-131">The value of the *Breakpoint* parameter is a Set-PSBreakpoint command that sets a new breakpoint, generates a breakpoint object, and saves the object in the $B variable.</span></span>

<span data-ttu-id="e62e9-132">Parâmetros de cmdlet que usam objetos como seus valores podem aceitar uma variável que contém o objeto ou um comando que recebe ou gera o objeto.</span><span class="sxs-lookup"><span data-stu-id="e62e9-132">Cmdlet parameters that take objects as their values can accept a variable that contains the object or a command that gets or generates the object.</span></span>
<span data-ttu-id="e62e9-133">Nesse caso, como **Set-PSBreakpoint** gera um objeto de ponto de interrupção, ele pode ser usado como o valor do parâmetro *Breakpoint* .</span><span class="sxs-lookup"><span data-stu-id="e62e9-133">In this case, because **Set-PSBreakpoint** generates a breakpoint object, it can be used as the value of the *Breakpoint* parameter.</span></span>

<span data-ttu-id="e62e9-134">O segundo comando exibe o objeto de ponto de interrupção no valor da variável $B.</span><span class="sxs-lookup"><span data-stu-id="e62e9-134">The second command displays the breakpoint object in the value of the $B variable.</span></span>

### <span data-ttu-id="e62e9-135">Exemplo 4: desabilitar todos os pontos de interrupção no console atual</span><span class="sxs-lookup"><span data-stu-id="e62e9-135">Example 4: Disable all breakpoints in the current console</span></span>

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

<span data-ttu-id="e62e9-136">Este comando desabilita todos os pontos de interrupção no console atual.</span><span class="sxs-lookup"><span data-stu-id="e62e9-136">This command disables all breakpoints in the current console.</span></span>
<span data-ttu-id="e62e9-137">Você pode abreviar este comando como: "GBP | DBP ".</span><span class="sxs-lookup"><span data-stu-id="e62e9-137">You can abbreviate this command as: "gbp | dbp".</span></span>

## <span data-ttu-id="e62e9-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e62e9-138">PARAMETERS</span></span>

### <span data-ttu-id="e62e9-139">-Ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="e62e9-139">-Breakpoint</span></span>

<span data-ttu-id="e62e9-140">Especifica os pontos de interrupção para desabilitar.</span><span class="sxs-lookup"><span data-stu-id="e62e9-140">Specifies the breakpoints to disable.</span></span>
<span data-ttu-id="e62e9-141">Insira uma variável que contém objetos de ponto de interrupção ou um comando que obtém os objetos de ponto de interrupção, como um comando Get-PSBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="e62e9-141">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a Get-PSBreakpoint command.</span></span>
<span data-ttu-id="e62e9-142">Você também pode canalizar objetos de ponto de interrupção para o cmdlet **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="e62e9-142">You can also pipe breakpoint objects to the **Disable-PSBreakpoint** cmdlet.</span></span>

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

### <span data-ttu-id="e62e9-143">-Id</span><span class="sxs-lookup"><span data-stu-id="e62e9-143">-Id</span></span>

<span data-ttu-id="e62e9-144">Desabilita os pontos de interrupção com as IDs de ponto de interrupção especificados.</span><span class="sxs-lookup"><span data-stu-id="e62e9-144">Disables the breakpoints with the specified breakpoint IDs.</span></span>
<span data-ttu-id="e62e9-145">Insira as IDs ou uma variável que contém as IDs.</span><span class="sxs-lookup"><span data-stu-id="e62e9-145">Enter the IDs or a variable that contains the IDs.</span></span>
<span data-ttu-id="e62e9-146">Não é possível canalizar IDs para **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="e62e9-146">You cannot pipe IDs to **Disable-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="e62e9-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e62e9-147">-PassThru</span></span>

<span data-ttu-id="e62e9-148">Retorna um objeto que representa os pontos de interrupção habilitados.</span><span class="sxs-lookup"><span data-stu-id="e62e9-148">Returns an object representing the enabled breakpoints.</span></span>
<span data-ttu-id="e62e9-149">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="e62e9-149">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e62e9-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e62e9-150">-Confirm</span></span>

<span data-ttu-id="e62e9-151">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e62e9-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e62e9-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e62e9-152">-WhatIf</span></span>

<span data-ttu-id="e62e9-153">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e62e9-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e62e9-154">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e62e9-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e62e9-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e62e9-155">CommonParameters</span></span>

<span data-ttu-id="e62e9-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e62e9-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e62e9-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e62e9-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e62e9-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e62e9-158">INPUTS</span></span>

### <span data-ttu-id="e62e9-159">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="e62e9-159">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="e62e9-160">É possível canalizar um objeto de ponto de interrupção para **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="e62e9-160">You can pipe a breakpoint object to **Disable-PSBreakpoint** .</span></span>

## <span data-ttu-id="e62e9-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e62e9-161">OUTPUTS</span></span>

### <span data-ttu-id="e62e9-162">Nenhum ou System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="e62e9-162">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="e62e9-163">Quando você usa o parâmetro *PassThru* , **Disable-PSBreakpoint** retorna um objeto que representa o ponto de interrupção desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e62e9-163">When you use the *PassThru* parameter, **Disable-PSBreakpoint** returns an object that represents the disabled breakpoint.</span></span>
<span data-ttu-id="e62e9-164">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="e62e9-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e62e9-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e62e9-165">NOTES</span></span>

## <span data-ttu-id="e62e9-166">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e62e9-166">RELATED LINKS</span></span>

[<span data-ttu-id="e62e9-167">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e62e9-167">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="e62e9-168">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e62e9-168">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="e62e9-169">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="e62e9-169">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="e62e9-170">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e62e9-170">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="e62e9-171">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e62e9-171">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
