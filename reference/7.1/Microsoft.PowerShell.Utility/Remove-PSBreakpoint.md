---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: a20b9114858a83de2b334340500efcf92e5d258d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194004"
---
# <span data-ttu-id="c9d12-103">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c9d12-103">Remove-PSBreakpoint</span></span>

## <span data-ttu-id="c9d12-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c9d12-104">SYNOPSIS</span></span>
<span data-ttu-id="c9d12-105">Exclui os pontos de interrupção do console atual.</span><span class="sxs-lookup"><span data-stu-id="c9d12-105">Deletes breakpoints from the current console.</span></span>

## <span data-ttu-id="c9d12-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c9d12-106">SYNTAX</span></span>

### <span data-ttu-id="c9d12-107">Ponto de interrupção (padrão)</span><span class="sxs-lookup"><span data-stu-id="c9d12-107">Breakpoint (Default)</span></span>

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c9d12-108">ID</span><span class="sxs-lookup"><span data-stu-id="c9d12-108">Id</span></span>

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c9d12-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c9d12-109">DESCRIPTION</span></span>
<span data-ttu-id="c9d12-110">O cmdlet **Remove-PSBreakpoint** exclui um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c9d12-110">The **Remove-PSBreakpoint** cmdlet deletes a breakpoint.</span></span>
<span data-ttu-id="c9d12-111">Insira um objeto de ponto de interrupção ou uma ID de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c9d12-111">Enter a breakpoint object or a breakpoint ID.</span></span>

<span data-ttu-id="c9d12-112">Quando você remove um ponto de interrupção, o objeto de ponto de interrupção não está mais disponível ou funcional.</span><span class="sxs-lookup"><span data-stu-id="c9d12-112">When you remove a breakpoint, the breakpoint object is no longer available or functional.</span></span>
<span data-ttu-id="c9d12-113">Se você salvou um objeto de ponto de interrupção em uma variável, a referência ainda existe, mas o ponto de interrupção não funciona.</span><span class="sxs-lookup"><span data-stu-id="c9d12-113">If you have saved a breakpoint object in a variable, the reference still exists, but the breakpoint does not function.</span></span>

<span data-ttu-id="c9d12-114">**Remove-PSBreakpoint** é um dos vários cmdlets projetados para depurar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9d12-114">**Remove-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="c9d12-115">Para obter mais informações sobre o depurador do PowerShell, consulte about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="c9d12-115">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="c9d12-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c9d12-116">EXAMPLES</span></span>

### <span data-ttu-id="c9d12-117">Exemplo 1: remover todos os pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="c9d12-117">Example 1: Remove all breakpoints</span></span>

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

<span data-ttu-id="c9d12-118">Esta função exclui todos os pontos de interrupção no console atual.</span><span class="sxs-lookup"><span data-stu-id="c9d12-118">This command deletes all of the breakpoints in the current console.</span></span>

### <span data-ttu-id="c9d12-119">Exemplo 2: remover um ponto de interrupção especificado</span><span class="sxs-lookup"><span data-stu-id="c9d12-119">Example 2: Remove a specified breakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

<span data-ttu-id="c9d12-120">Esse comando exclui um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c9d12-120">This command deletes a breakpoint.</span></span>

<span data-ttu-id="c9d12-121">O primeiro comando usa o cmdlet Set-PSBreakpoint para criar um ponto de interrupção na variável Name no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="c9d12-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Name variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="c9d12-122">Em seguida, ele salva o objeto de ponto de interrupção na variável $B.</span><span class="sxs-lookup"><span data-stu-id="c9d12-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="c9d12-123">O segundo comando usa o cmdlet **Remove-PSBreakpoint** para excluir o novo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c9d12-123">The second command uses the **Remove-PSBreakpoint** cmdlet to delete the new breakpoint.</span></span>
<span data-ttu-id="c9d12-124">Ele usa um operador de pipeline (|) para enviar o objeto de ponto de interrupção na variável $B para o cmdlet **Remove-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="c9d12-124">It uses a pipeline operator (|) to send the breakpoint object in the $B variable to the **Remove-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="c9d12-125">Como resultado desse comando, se você executar o script, ele é executado sem parar até a conclusão.</span><span class="sxs-lookup"><span data-stu-id="c9d12-125">As a result of this command, if you run the script, it runs to completion without stopping.</span></span>
<span data-ttu-id="c9d12-126">Além disso, o cmdlet **Get-PSBreakpoint** não retorna esse ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c9d12-126">Also, the **Get-PSBreakpoint** cmdlet does not return this breakpoint.</span></span>

### <span data-ttu-id="c9d12-127">Exemplo 3: remover um ponto de interrupção por ID</span><span class="sxs-lookup"><span data-stu-id="c9d12-127">Example 3: Remove a breakpoint by ID</span></span>

```
PS C:\> Remove-PSBreakpoint -Id 2
```

<span data-ttu-id="c9d12-128">Este comando exclui o ponto de interrupção com a ID do ponto de interrupção 2.</span><span class="sxs-lookup"><span data-stu-id="c9d12-128">This command deletes the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="c9d12-129">Exemplo 4: usar uma função para remover todos os pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="c9d12-129">Example 4: Use a function to remove all breakpoints</span></span>

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

<span data-ttu-id="c9d12-130">Esta função simples exclui todos os pontos de interrupção no console atual.</span><span class="sxs-lookup"><span data-stu-id="c9d12-130">This simple function deletes all of the breakpoints in the current console.</span></span>
<span data-ttu-id="c9d12-131">Ele usa o cmdlet Get-PSBreakpoint para obter os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c9d12-131">It uses the Get-PSBreakpoint cmdlet to get the breakpoints.</span></span>
<span data-ttu-id="c9d12-132">Em seguida, ele usa um operador de pipeline (|) para enviar os pontos de interrupção para o cmdlet **Remove-PSBreakpoint** , que os exclui.</span><span class="sxs-lookup"><span data-stu-id="c9d12-132">Then, it uses a pipeline operator (|) to send the breakpoints to the **Remove-PSBreakpoint** cmdlet, which deletes them.</span></span>

<span data-ttu-id="c9d12-133">Como resultado, você pode digitar `del-psb` em vez do comando mais longo.</span><span class="sxs-lookup"><span data-stu-id="c9d12-133">As a result, you can type `del-psb` instead of the longer command.</span></span>

<span data-ttu-id="c9d12-134">Para salvar a função, adicione-a ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9d12-134">To save the function, add it to your PowerShell profile.</span></span>

## <span data-ttu-id="c9d12-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c9d12-135">PARAMETERS</span></span>

### <span data-ttu-id="c9d12-136">-Ponto de interrupção</span><span class="sxs-lookup"><span data-stu-id="c9d12-136">-Breakpoint</span></span>
<span data-ttu-id="c9d12-137">Especifica os pontos de interrupção a excluir.</span><span class="sxs-lookup"><span data-stu-id="c9d12-137">Specifies the breakpoints to delete.</span></span>
<span data-ttu-id="c9d12-138">Insira uma variável que contenha objetos de ponto de interrupção ou um comando que obtém objetos de ponto de interrupção, como um comando **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="c9d12-138">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a **Get-PSBreakpoint** command.</span></span>
<span data-ttu-id="c9d12-139">Você também pode canalizar objetos de ponto de interrupção para **Remove-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="c9d12-139">You can also pipe breakpoint objects to **Remove-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="c9d12-140">-Id</span><span class="sxs-lookup"><span data-stu-id="c9d12-140">-Id</span></span>
<span data-ttu-id="c9d12-141">Especifica as IDs de ponto de interrupção para os quais esse cmdlet exclui pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c9d12-141">Specifies breakpoint IDs for which this cmdlet deletes breakpoints.</span></span>

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

### <span data-ttu-id="c9d12-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c9d12-142">-Confirm</span></span>
<span data-ttu-id="c9d12-143">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9d12-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c9d12-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c9d12-144">-WhatIf</span></span>
<span data-ttu-id="c9d12-145">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="c9d12-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c9d12-146">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="c9d12-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c9d12-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c9d12-147">CommonParameters</span></span>
<span data-ttu-id="c9d12-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c9d12-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c9d12-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c9d12-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c9d12-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c9d12-150">INPUTS</span></span>

### <span data-ttu-id="c9d12-151">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="c9d12-151">System.Management.Automation.Breakpoint</span></span>
<span data-ttu-id="c9d12-152">É possível canalizar objetos de ponto de interrupção para **Remove-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="c9d12-152">You can pipe breakpoint objects to **Remove-PSBreakpoint** .</span></span>

## <span data-ttu-id="c9d12-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c9d12-153">OUTPUTS</span></span>

### <span data-ttu-id="c9d12-154">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c9d12-154">None</span></span>
<span data-ttu-id="c9d12-155">O cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="c9d12-155">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c9d12-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c9d12-156">NOTES</span></span>

## <span data-ttu-id="c9d12-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c9d12-157">RELATED LINKS</span></span>

[<span data-ttu-id="c9d12-158">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c9d12-158">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="c9d12-159">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c9d12-159">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="c9d12-160">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c9d12-160">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="c9d12-161">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="c9d12-161">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="c9d12-162">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c9d12-162">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

