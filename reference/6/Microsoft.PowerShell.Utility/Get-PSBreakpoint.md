---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: c130feac876ff812a854d52961ba3141ba341af0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194479"
---
# <span data-ttu-id="6a9b1-103">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6a9b1-103">Get-PSBreakpoint</span></span>

## <span data-ttu-id="6a9b1-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6a9b1-104">SYNOPSIS</span></span>
<span data-ttu-id="6a9b1-105">Obtém os pontos de interrupção definidos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-105">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="6a9b1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a9b1-106">SYNTAX</span></span>

### <span data-ttu-id="6a9b1-107">Script (padrão)</span><span class="sxs-lookup"><span data-stu-id="6a9b1-107">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6a9b1-108">Variável</span><span class="sxs-lookup"><span data-stu-id="6a9b1-108">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="6a9b1-109">Comando</span><span class="sxs-lookup"><span data-stu-id="6a9b1-109">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="6a9b1-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a9b1-110">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="6a9b1-111">ID</span><span class="sxs-lookup"><span data-stu-id="6a9b1-111">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="6a9b1-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6a9b1-112">DESCRIPTION</span></span>

<span data-ttu-id="6a9b1-113">O cmdlet **Get-PSBreakpoint** Obtém os pontos de interrupção definidos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-113">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="6a9b1-114">Você pode usar os parâmetros do cmdlet para obter pontos de interrupção específicos.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-114">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="6a9b1-115">Um ponto de interrupção é um ponto em um comando ou script onde a execução é interrompida temporariamente para que você possa examinar as instruções.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-115">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="6a9b1-116">O **Get-PSBreakpoint** é um dos vários cmdlets projetados para depurar scripts e comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-116">**Get-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts and commands.</span></span> <span data-ttu-id="6a9b1-117">Para obter mais informações sobre o depurador do PowerShell, consulte about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-117">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="6a9b1-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6a9b1-118">EXAMPLES</span></span>

### <span data-ttu-id="6a9b1-119">Exemplo 1: obter todos os pontos de interrupção para todos os scripts e funções</span><span class="sxs-lookup"><span data-stu-id="6a9b1-119">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="6a9b1-120">Este comando obtém todos os pontos de interrupção definidos em todos os scripts e funções presentes na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-120">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="6a9b1-121">Exemplo 2: obter pontos de interrupção por ID</span><span class="sxs-lookup"><span data-stu-id="6a9b1-121">Example 2: Get breakpoints by ID</span></span>

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

<span data-ttu-id="6a9b1-122">Esse comando obtém o ponto de interrupção com o identificador 2.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-122">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="6a9b1-123">Exemplo 3: direcionar uma ID para Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6a9b1-123">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="6a9b1-124">Esses comandos mostram como obter um ponto de interrupção ao canalizar uma ID de ponto de interrupção para **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="6a9b1-124">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint** .</span></span>

<span data-ttu-id="6a9b1-125">O primeiro comando usa o cmdlet Set-PSBreakpoint para criar um ponto de interrupção na função Increment, no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-125">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="6a9b1-126">Ele salva o objeto de ponto de interrupção na variável $B.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-126">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="6a9b1-127">O segundo comando usa o operador ponto (.) para obter a propriedade ID do objeto Breakpoint na variável $B.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-127">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="6a9b1-128">Ele usa um operador de pipeline (|) para enviar a ID para o cmdlet **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="6a9b1-128">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="6a9b1-129">Como resultado, **Get-PSBreakpoint** Obtém o ponto de interrupção com a ID especificada.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-129">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="6a9b1-130">Exemplo 4: obter pontos de interrupção em arquivos de script especificados</span><span class="sxs-lookup"><span data-stu-id="6a9b1-130">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="6a9b1-131">Este comando obtém todos os pontos de interrupção contidos nos arquivos Sample.ps1 e SupportScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-131">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="6a9b1-132">Esse comando não obtém outros pontos de interrupção que podem ser definidos em outros scripts ou em funções na sessão.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-132">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="6a9b1-133">Exemplo 5: obter pontos de interrupção nos cmdlets especificados</span><span class="sxs-lookup"><span data-stu-id="6a9b1-133">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="6a9b1-134">Este comando obtém todos os pontos de interrupção de comando que estão definidos em comandos de Read-Host ou Write-Host contidos no arquivo Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-134">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="6a9b1-135">Exemplo 6: obter pontos de interrupção de comando em um arquivo especificado</span><span class="sxs-lookup"><span data-stu-id="6a9b1-135">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="6a9b1-136">Este comando obtém todos os pontos de interrupção do comando contidos no arquivo Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-136">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="6a9b1-137">Exemplo 7: obter pontos de interrupção por variável</span><span class="sxs-lookup"><span data-stu-id="6a9b1-137">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="6a9b1-138">Esse comando obtém os pontos de interrupção que são definidos no $Index e $Swap variáveis na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-138">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="6a9b1-139">Exemplo 8: obter todos os pontos de interrupção de linha e variável em um arquivo</span><span class="sxs-lookup"><span data-stu-id="6a9b1-139">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="6a9b1-140">Este comando obtém todos os pontos de interrupção variáveis e de linha contidos no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-140">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="6a9b1-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a9b1-141">PARAMETERS</span></span>

### <span data-ttu-id="6a9b1-142">-Command</span><span class="sxs-lookup"><span data-stu-id="6a9b1-142">-Command</span></span>

<span data-ttu-id="6a9b1-143">Especifica uma matriz de pontos de interrupção de comando que são definidos nos nomes de comando especificados.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-143">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="6a9b1-144">Insira os nomes de comando, como, por exemplo, o nome de um cmdlet ou função.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-144">Enter the command names, such as the name of a cmdlet or function.</span></span>

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

### <span data-ttu-id="6a9b1-145">-Id</span><span class="sxs-lookup"><span data-stu-id="6a9b1-145">-Id</span></span>

<span data-ttu-id="6a9b1-146">Especifica as IDs de ponto de interrupção que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-146">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="6a9b1-147">Digite os identificadores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-147">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="6a9b1-148">Você também pode canalizar IDs de ponto de interrupção para **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="6a9b1-148">You can also pipe breakpoint IDs to **Get-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="6a9b1-149">-Script</span><span class="sxs-lookup"><span data-stu-id="6a9b1-149">-Script</span></span>

<span data-ttu-id="6a9b1-150">Especifica uma matriz de scripts que contém os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-150">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="6a9b1-151">Insira o caminho (opcional) e os nomes de um ou mais arquivos de script.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-151">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="6a9b1-152">Se você omitir o caminho, o local padrão a considerar é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-152">If you omit the path, the default location is the current directory.</span></span>

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

### <span data-ttu-id="6a9b1-153">-Type</span><span class="sxs-lookup"><span data-stu-id="6a9b1-153">-Type</span></span>

<span data-ttu-id="6a9b1-154">Especifica uma matriz de tipos de ponto de interrupção que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-154">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="6a9b1-155">Insira um ou mais tipos.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-155">Enter one or more types.</span></span>
<span data-ttu-id="6a9b1-156">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="6a9b1-156">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6a9b1-157">Linha</span><span class="sxs-lookup"><span data-stu-id="6a9b1-157">Line</span></span>
- <span data-ttu-id="6a9b1-158">Comando</span><span class="sxs-lookup"><span data-stu-id="6a9b1-158">Command</span></span>
- <span data-ttu-id="6a9b1-159">Variável</span><span class="sxs-lookup"><span data-stu-id="6a9b1-159">Variable</span></span>

<span data-ttu-id="6a9b1-160">Você também pode canalizar tipos de ponto de interrupção para **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="6a9b1-160">You can also pipe breakpoint types to **Get-PSBreakPoint** .</span></span>

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

### <span data-ttu-id="6a9b1-161">-Variable</span><span class="sxs-lookup"><span data-stu-id="6a9b1-161">-Variable</span></span>

<span data-ttu-id="6a9b1-162">Especifica uma matriz de pontos de interrupção de variável que são definidos nos nomes de variável especificados.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-162">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="6a9b1-163">Digite os nomes de variáveis sem cifrões.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-163">Enter the variable names without dollar signs.</span></span>

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

### <span data-ttu-id="6a9b1-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6a9b1-164">CommonParameters</span></span>

<span data-ttu-id="6a9b1-165">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a9b1-166">Para obter mais informações, confira about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6a9b1-166">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a9b1-167">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6a9b1-167">INPUTS</span></span>

### <span data-ttu-id="6a9b1-168">System. Int32, Microsoft. PowerShell. Commands. Breakpointtype</span><span class="sxs-lookup"><span data-stu-id="6a9b1-168">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="6a9b1-169">Você pode canalizar IDs de ponto de interrupção e tipos de ponto de quebra para **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="6a9b1-169">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint** .</span></span>

## <span data-ttu-id="6a9b1-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6a9b1-170">OUTPUTS</span></span>

### <span data-ttu-id="6a9b1-171">System. Management. Automation. Breakpoint</span><span class="sxs-lookup"><span data-stu-id="6a9b1-171">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="6a9b1-172">**Get-PSBreakpoint** retorna objetos que representam os pontos de interrupção na sessão.</span><span class="sxs-lookup"><span data-stu-id="6a9b1-172">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="6a9b1-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6a9b1-173">NOTES</span></span>

* <span data-ttu-id="6a9b1-174">Você pode usar **Get-PSBreakpoint** ou seu alias, "GBP".</span><span class="sxs-lookup"><span data-stu-id="6a9b1-174">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="6a9b1-175">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6a9b1-175">RELATED LINKS</span></span>

[<span data-ttu-id="6a9b1-176">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6a9b1-176">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="6a9b1-177">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6a9b1-177">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="6a9b1-178">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="6a9b1-178">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="6a9b1-179">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6a9b1-179">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="6a9b1-180">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6a9b1-180">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
