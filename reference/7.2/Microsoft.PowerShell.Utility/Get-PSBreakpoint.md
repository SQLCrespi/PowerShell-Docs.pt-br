---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: 78691b806fe68aaa8d9e502d28e6f3967867f95b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598004"
---
# <span data-ttu-id="85d1d-102">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="85d1d-102">Get-PSBreakpoint</span></span>

## <span data-ttu-id="85d1d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="85d1d-103">SYNOPSIS</span></span>
<span data-ttu-id="85d1d-104">Obtém os pontos de interrupção definidos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="85d1d-104">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="85d1d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85d1d-105">SYNTAX</span></span>

### <span data-ttu-id="85d1d-106">Script (padrão)</span><span class="sxs-lookup"><span data-stu-id="85d1d-106">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="85d1d-107">Variável</span><span class="sxs-lookup"><span data-stu-id="85d1d-107">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="85d1d-108">Comando</span><span class="sxs-lookup"><span data-stu-id="85d1d-108">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="85d1d-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="85d1d-109">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="85d1d-110">ID</span><span class="sxs-lookup"><span data-stu-id="85d1d-110">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="85d1d-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="85d1d-111">DESCRIPTION</span></span>

<span data-ttu-id="85d1d-112">O cmdlet **Get-PSBreakpoint** Obtém os pontos de interrupção definidos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="85d1d-112">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="85d1d-113">Você pode usar os parâmetros do cmdlet para obter pontos de interrupção específicos.</span><span class="sxs-lookup"><span data-stu-id="85d1d-113">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="85d1d-114">Um ponto de interrupção é um ponto em um comando ou script onde a execução é interrompida temporariamente para que você possa examinar as instruções.</span><span class="sxs-lookup"><span data-stu-id="85d1d-114">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="85d1d-115">O **Get-PSBreakpoint** é um dos vários cmdlets projetados para depurar scripts e comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85d1d-115">**Get-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts and commands.</span></span> <span data-ttu-id="85d1d-116">Para obter mais informações sobre o depurador do PowerShell, consulte about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="85d1d-116">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="85d1d-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="85d1d-117">EXAMPLES</span></span>

### <span data-ttu-id="85d1d-118">Exemplo 1: obter todos os pontos de interrupção para todos os scripts e funções</span><span class="sxs-lookup"><span data-stu-id="85d1d-118">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="85d1d-119">Este comando obtém todos os pontos de interrupção definidos em todos os scripts e funções presentes na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="85d1d-119">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="85d1d-120">Exemplo 2: obter pontos de interrupção por ID</span><span class="sxs-lookup"><span data-stu-id="85d1d-120">Example 2: Get breakpoints by ID</span></span>

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="85d1d-121">Esse comando obtém o ponto de interrupção com o identificador 2.</span><span class="sxs-lookup"><span data-stu-id="85d1d-121">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="85d1d-122">Exemplo 3: direcionar uma ID para Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="85d1d-122">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="85d1d-123">Esses comandos mostram como obter um ponto de interrupção ao canalizar uma ID de ponto de interrupção para **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="85d1d-123">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint**.</span></span>

<span data-ttu-id="85d1d-124">O primeiro comando usa o cmdlet Set-PSBreakpoint para criar um ponto de interrupção na função Increment, no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="85d1d-124">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="85d1d-125">Ele salva o objeto de ponto de interrupção na variável $B.</span><span class="sxs-lookup"><span data-stu-id="85d1d-125">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="85d1d-126">O segundo comando usa o operador ponto (.) para obter a propriedade ID do objeto Breakpoint na variável $B.</span><span class="sxs-lookup"><span data-stu-id="85d1d-126">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="85d1d-127">Ele usa um operador de pipeline (|) para enviar a ID para o cmdlet **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="85d1d-127">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="85d1d-128">Como resultado, **Get-PSBreakpoint** Obtém o ponto de interrupção com a ID especificada.</span><span class="sxs-lookup"><span data-stu-id="85d1d-128">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="85d1d-129">Exemplo 4: obter pontos de interrupção em arquivos de script especificados</span><span class="sxs-lookup"><span data-stu-id="85d1d-129">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="85d1d-130">Este comando obtém todos os pontos de interrupção contidos nos arquivos Sample.ps1 e SupportScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="85d1d-130">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="85d1d-131">Esse comando não obtém outros pontos de interrupção que podem ser definidos em outros scripts ou em funções na sessão.</span><span class="sxs-lookup"><span data-stu-id="85d1d-131">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="85d1d-132">Exemplo 5: obter pontos de interrupção nos cmdlets especificados</span><span class="sxs-lookup"><span data-stu-id="85d1d-132">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="85d1d-133">Este comando obtém todos os pontos de interrupção de comando que estão definidos em comandos de Read-Host ou Write-Host contidos no arquivo Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="85d1d-133">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="85d1d-134">Exemplo 6: obter pontos de interrupção de comando em um arquivo especificado</span><span class="sxs-lookup"><span data-stu-id="85d1d-134">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="85d1d-135">Este comando obtém todos os pontos de interrupção do comando contidos no arquivo Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="85d1d-135">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="85d1d-136">Exemplo 7: obter pontos de interrupção por variável</span><span class="sxs-lookup"><span data-stu-id="85d1d-136">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="85d1d-137">Esse comando obtém os pontos de interrupção que são definidos no $Index e $Swap variáveis na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="85d1d-137">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="85d1d-138">Exemplo 8: obter todos os pontos de interrupção de linha e variável em um arquivo</span><span class="sxs-lookup"><span data-stu-id="85d1d-138">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="85d1d-139">Este comando obtém todos os pontos de interrupção variáveis e de linha contidos no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="85d1d-139">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="85d1d-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85d1d-140">PARAMETERS</span></span>

### <span data-ttu-id="85d1d-141">-Command</span><span class="sxs-lookup"><span data-stu-id="85d1d-141">-Command</span></span>

<span data-ttu-id="85d1d-142">Especifica uma matriz de pontos de interrupção de comando que são definidos nos nomes de comando especificados.</span><span class="sxs-lookup"><span data-stu-id="85d1d-142">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="85d1d-143">Insira os nomes de comando, como, por exemplo, o nome de um cmdlet ou função.</span><span class="sxs-lookup"><span data-stu-id="85d1d-143">Enter the command names, such as the name of a cmdlet or function.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85d1d-144">-Id</span><span class="sxs-lookup"><span data-stu-id="85d1d-144">-Id</span></span>

<span data-ttu-id="85d1d-145">Especifica as IDs de ponto de interrupção que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="85d1d-145">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="85d1d-146">Digite os identificadores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="85d1d-146">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="85d1d-147">Você também pode canalizar IDs de ponto de interrupção para **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="85d1d-147">You can also pipe breakpoint IDs to **Get-PSBreakpoint**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="85d1d-148">-Script</span><span class="sxs-lookup"><span data-stu-id="85d1d-148">-Script</span></span>

<span data-ttu-id="85d1d-149">Especifica uma matriz de scripts que contém os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="85d1d-149">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="85d1d-150">Insira o caminho (opcional) e os nomes de um ou mais arquivos de script.</span><span class="sxs-lookup"><span data-stu-id="85d1d-150">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="85d1d-151">Se você omitir o caminho, o local padrão a considerar é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="85d1d-151">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="85d1d-152">-Type</span><span class="sxs-lookup"><span data-stu-id="85d1d-152">-Type</span></span>

<span data-ttu-id="85d1d-153">Especifica uma matriz de tipos de ponto de interrupção que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="85d1d-153">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="85d1d-154">Insira um ou mais tipos.</span><span class="sxs-lookup"><span data-stu-id="85d1d-154">Enter one or more types.</span></span>
<span data-ttu-id="85d1d-155">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="85d1d-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85d1d-156">Linha</span><span class="sxs-lookup"><span data-stu-id="85d1d-156">Line</span></span>
- <span data-ttu-id="85d1d-157">Comando</span><span class="sxs-lookup"><span data-stu-id="85d1d-157">Command</span></span>
- <span data-ttu-id="85d1d-158">Variável</span><span class="sxs-lookup"><span data-stu-id="85d1d-158">Variable</span></span>

<span data-ttu-id="85d1d-159">Você também pode canalizar tipos de ponto de interrupção para **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="85d1d-159">You can also pipe breakpoint types to **Get-PSBreakPoint**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="85d1d-160">-Variable</span><span class="sxs-lookup"><span data-stu-id="85d1d-160">-Variable</span></span>

<span data-ttu-id="85d1d-161">Especifica uma matriz de pontos de interrupção de variável que são definidos nos nomes de variável especificados.</span><span class="sxs-lookup"><span data-stu-id="85d1d-161">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="85d1d-162">Digite os nomes de variáveis sem cifrões.</span><span class="sxs-lookup"><span data-stu-id="85d1d-162">Enter the variable names without dollar signs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85d1d-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="85d1d-163">CommonParameters</span></span>

<span data-ttu-id="85d1d-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="85d1d-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85d1d-165">Para obter mais informações, confira about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="85d1d-165">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85d1d-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="85d1d-166">INPUTS</span></span>

### <span data-ttu-id="85d1d-167">System. Int32, Microsoft. PowerShell. Commands. Breakpointtype</span><span class="sxs-lookup"><span data-stu-id="85d1d-167">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="85d1d-168">Você pode canalizar IDs de ponto de interrupção e tipos de ponto de quebra para **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="85d1d-168">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint**.</span></span>

## <span data-ttu-id="85d1d-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="85d1d-169">OUTPUTS</span></span>

### <span data-ttu-id="85d1d-170">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="85d1d-170">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="85d1d-171">**Get-PSBreakpoint** retorna objetos que representam os pontos de interrupção na sessão.</span><span class="sxs-lookup"><span data-stu-id="85d1d-171">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="85d1d-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="85d1d-172">NOTES</span></span>

* <span data-ttu-id="85d1d-173">Você pode usar **Get-PSBreakpoint** ou seu alias, "GBP".</span><span class="sxs-lookup"><span data-stu-id="85d1d-173">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="85d1d-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="85d1d-174">RELATED LINKS</span></span>

[<span data-ttu-id="85d1d-175">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="85d1d-175">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="85d1d-176">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="85d1d-176">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="85d1d-177">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="85d1d-177">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="85d1d-178">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="85d1d-178">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="85d1d-179">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="85d1d-179">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

