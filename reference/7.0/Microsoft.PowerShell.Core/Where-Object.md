---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 0d9101c751e9ebc0b0c6fe80564bb76524de8bb6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192773"
---
# <span data-ttu-id="0188e-103">Where-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-103">Where-Object</span></span>

## <span data-ttu-id="0188e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0188e-104">SYNOPSIS</span></span>
<span data-ttu-id="0188e-105">Seleciona objetos de uma coleção com base em seus valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="0188e-105">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="0188e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0188e-106">SYNTAX</span></span>

### <span data-ttu-id="0188e-107">Igualset (padrão)</span><span class="sxs-lookup"><span data-stu-id="0188e-107">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-108">ScriptBlockset</span><span class="sxs-lookup"><span data-stu-id="0188e-108">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="0188e-109">Matchset</span><span class="sxs-lookup"><span data-stu-id="0188e-109">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-110">CaseSensitiveEqualSet</span><span class="sxs-lookup"><span data-stu-id="0188e-110">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-111">Não Igualset</span><span class="sxs-lookup"><span data-stu-id="0188e-111">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-112">CaseSensitiveNotEqualSet</span><span class="sxs-lookup"><span data-stu-id="0188e-112">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-113">GreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="0188e-113">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-114">CaseSensitiveGreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="0188e-114">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-115">LessThanSet</span><span class="sxs-lookup"><span data-stu-id="0188e-115">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-116">CaseSensitiveLessThanSet</span><span class="sxs-lookup"><span data-stu-id="0188e-116">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-117">GreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0188e-117">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-118">CaseSensitiveGreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0188e-118">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-119">LessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0188e-119">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-120">CaseSensitiveLessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="0188e-120">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-121">Likeset</span><span class="sxs-lookup"><span data-stu-id="0188e-121">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-122">CaseSensitiveLikeSet</span><span class="sxs-lookup"><span data-stu-id="0188e-122">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-123">Não gosto de</span><span class="sxs-lookup"><span data-stu-id="0188e-123">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-124">CaseSensitiveNotLikeSet</span><span class="sxs-lookup"><span data-stu-id="0188e-124">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-125">CaseSensitiveMatchSet</span><span class="sxs-lookup"><span data-stu-id="0188e-125">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-126">Não Correspondenteset</span><span class="sxs-lookup"><span data-stu-id="0188e-126">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-127">CaseSensitiveNotMatchSet</span><span class="sxs-lookup"><span data-stu-id="0188e-127">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-128">Contémset</span><span class="sxs-lookup"><span data-stu-id="0188e-128">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-129">CaseSensitiveContainsSet</span><span class="sxs-lookup"><span data-stu-id="0188e-129">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-130">Não contém Oset</span><span class="sxs-lookup"><span data-stu-id="0188e-130">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-131">CaseSensitiveNotContainsSet</span><span class="sxs-lookup"><span data-stu-id="0188e-131">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-132">Levo</span><span class="sxs-lookup"><span data-stu-id="0188e-132">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-133">CaseSensitiveInSet</span><span class="sxs-lookup"><span data-stu-id="0188e-133">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-134">Não inserir</span><span class="sxs-lookup"><span data-stu-id="0188e-134">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-135">CaseSensitiveNotInSet</span><span class="sxs-lookup"><span data-stu-id="0188e-135">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-136">IsSet</span><span class="sxs-lookup"><span data-stu-id="0188e-136">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-137">Isnotset</span><span class="sxs-lookup"><span data-stu-id="0188e-137">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="0188e-138">Not</span><span class="sxs-lookup"><span data-stu-id="0188e-138">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="0188e-139">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0188e-139">DESCRIPTION</span></span>

<span data-ttu-id="0188e-140">O `Where-Object` cmdlet seleciona objetos que têm valores de propriedade específicos da coleção de objetos que são passados para ele.</span><span class="sxs-lookup"><span data-stu-id="0188e-140">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="0188e-141">Por exemplo, você pode usar o `Where-Object` cmdlet para selecionar os arquivos que foram criados após uma determinada data, eventos com uma ID específica ou computadores que usam uma versão específica do Windows.</span><span class="sxs-lookup"><span data-stu-id="0188e-141">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="0188e-142">A partir do Windows PowerShell 3,0, há duas maneiras diferentes de construir um `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="0188e-142">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="0188e-143">**Bloco de script** .</span><span class="sxs-lookup"><span data-stu-id="0188e-143">**Script block** .</span></span> <span data-ttu-id="0188e-144">Você pode usar um bloco de script para especificar o nome da propriedade, um operador de comparação e um valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="0188e-144">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="0188e-145">`Where-Object` Retorna todos os objetos para os quais a instrução de bloco de script é verdadeira.</span><span class="sxs-lookup"><span data-stu-id="0188e-145">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="0188e-146">Por exemplo, o comando a seguir obtém os processos na classe de prioridade normal, ou seja, processos em que o valor da propriedade **PriorityClass** é igual a normal.</span><span class="sxs-lookup"><span data-stu-id="0188e-146">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="0188e-147">Todos os operadores de comparação do PowerShell são válidos no formato de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="0188e-147">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="0188e-148">Para obter mais informações sobre operadores de comparação, consulte [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0188e-148">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="0188e-149">**Instrução de comparação** .</span><span class="sxs-lookup"><span data-stu-id="0188e-149">**Comparison statement** .</span></span> <span data-ttu-id="0188e-150">Você também pode escrever uma instrução de comparação, que é muito mais como uma linguagem natural.</span><span class="sxs-lookup"><span data-stu-id="0188e-150">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="0188e-151">Instruções de comparação foram introduzidas no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-151">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="0188e-152">Por exemplo, os comandos a seguir também obtêm processos que têm uma classe de prioridade normal.</span><span class="sxs-lookup"><span data-stu-id="0188e-152">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="0188e-153">Estes comandos são equivalentes e podem ser usados intercambiavelmente.</span><span class="sxs-lookup"><span data-stu-id="0188e-153">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="0188e-154">A partir do Windows PowerShell 3,0, `Where-Object` o adiciona operadores de comparação como parâmetros em um `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="0188e-154">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="0188e-155">A menos que especificado, todos os operadores diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-155">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="0188e-156">Antes do Windows PowerShell 3,0, os operadores de comparação no idioma do PowerShell poderiam ser usados somente em blocos de script.</span><span class="sxs-lookup"><span data-stu-id="0188e-156">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="0188e-157">Quando você fornece uma única **Propriedade** para `Where-Object` , o valor da propriedade é tratado como uma expressão booliana.</span><span class="sxs-lookup"><span data-stu-id="0188e-157">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="0188e-158">Quando o valor de **Length** não for zero, a expressão será avaliada como **true** .</span><span class="sxs-lookup"><span data-stu-id="0188e-158">When the value of **Length** is not zero, the expression evaluates to **True** .</span></span> <span data-ttu-id="0188e-159">Por exemplo: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="0188e-159">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="0188e-160">O exemplo anterior é funcionalmente equivalente a:</span><span class="sxs-lookup"><span data-stu-id="0188e-160">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="0188e-161">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0188e-161">EXAMPLES</span></span>

### <span data-ttu-id="0188e-162">Exemplo 1: obter serviços interrompidos</span><span class="sxs-lookup"><span data-stu-id="0188e-162">Example 1: Get stopped services</span></span>

<span data-ttu-id="0188e-163">Esses comandos obtêm uma lista de todos os serviços que estão atualmente interrompidos.</span><span class="sxs-lookup"><span data-stu-id="0188e-163">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="0188e-164">A `$_` variável automática representa cada objeto que é passado para o `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0188e-164">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="0188e-165">O primeiro comando usa o formato de bloco de script, o segundo comando usa o formato de instrução de comparação.</span><span class="sxs-lookup"><span data-stu-id="0188e-165">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="0188e-166">Os comandos são equivalentes e podem ser usados intercambiavelmente.</span><span class="sxs-lookup"><span data-stu-id="0188e-166">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="0188e-167">Exemplo 2: obter processos com base no conjunto de trabalho</span><span class="sxs-lookup"><span data-stu-id="0188e-167">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="0188e-168">Esses comandos listam os processos que têm um conjunto de trabalho maior que 250 megabytes (KB).</span><span class="sxs-lookup"><span data-stu-id="0188e-168">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="0188e-169">A sintaxe scriptblock e Statement é equivalente e pode ser usada de maneira intercambiável.</span><span class="sxs-lookup"><span data-stu-id="0188e-169">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="0188e-170">Exemplo 3: obter processos com base no nome do processo</span><span class="sxs-lookup"><span data-stu-id="0188e-170">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="0188e-171">Esses comandos obtêm os processos que têm um valor de propriedade **ProcessName** que começa com a letra `p` .</span><span class="sxs-lookup"><span data-stu-id="0188e-171">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="0188e-172">O operador **Match** permite que você use correspondências de expressão regulares.</span><span class="sxs-lookup"><span data-stu-id="0188e-172">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="0188e-173">A sintaxe scriptblock e Statement é equivalente e pode ser usada de maneira intercambiável.</span><span class="sxs-lookup"><span data-stu-id="0188e-173">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="0188e-174">Exemplo 4: usar o formato de instrução de comparação</span><span class="sxs-lookup"><span data-stu-id="0188e-174">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="0188e-175">Este exemplo mostra como usar o novo formato de instrução de comparação do `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0188e-175">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="0188e-176">O primeiro comando usa o formato de instrução de comparação.</span><span class="sxs-lookup"><span data-stu-id="0188e-176">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="0188e-177">Neste comando, nenhum alias é usado e todos os parâmetros incluem o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0188e-177">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="0188e-178">O segundo comando é o uso mais natural do formato de comando de comparação.</span><span class="sxs-lookup"><span data-stu-id="0188e-178">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="0188e-179">O `where` alias é substituído pelo nome do `Where-Object` cmdlet e todos os nomes de parâmetro opcionais são omitidos.</span><span class="sxs-lookup"><span data-stu-id="0188e-179">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="0188e-180">Exemplo 5: obter comandos com base em Propriedades</span><span class="sxs-lookup"><span data-stu-id="0188e-180">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="0188e-181">Este exemplo mostra como gravar comandos que retornam itens que são verdadeiros ou falsos, ou que tenham qualquer valor de uma propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="0188e-181">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="0188e-182">Cada exemplo mostra os formatos de bloco de script e de instrução de comparação para o comando.</span><span class="sxs-lookup"><span data-stu-id="0188e-182">Each example shows both the script block and comparison statement formats for the command.</span></span>

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### <span data-ttu-id="0188e-183">Exemplo 6: usar várias condições</span><span class="sxs-lookup"><span data-stu-id="0188e-183">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="0188e-184">Este exemplo mostra como criar um `Where-Object` comando com várias condições.</span><span class="sxs-lookup"><span data-stu-id="0188e-184">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="0188e-185">Esse comando obtém módulos não essenciais que suportam o recurso de Ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="0188e-185">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="0188e-186">O comando usa o parâmetro **listAvailable** do `Get-Module` cmdlet para obter todos os módulos no computador.</span><span class="sxs-lookup"><span data-stu-id="0188e-186">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="0188e-187">Um operador de pipeline ( `|` ) envia os módulos para o `Where-Object` cmdlet, que obtém os módulos cujos nomes não começam com Microsoft ou PS, e têm um valor para a propriedade **HelpInfoURI** , que informa ao PowerShell onde encontrar arquivos de ajuda atualizados para o módulo.</span><span class="sxs-lookup"><span data-stu-id="0188e-187">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="0188e-188">As instruções de comparação são conectadas pelo operador lógico **and** .</span><span class="sxs-lookup"><span data-stu-id="0188e-188">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="0188e-189">O exemplo usa o formato de comando de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="0188e-189">The example uses the script block command format.</span></span> <span data-ttu-id="0188e-190">Operadores lógicos, como **e** e **ou** , são válidos somente em blocos de script.</span><span class="sxs-lookup"><span data-stu-id="0188e-190">Logical operators, such as **And** and **Or** , are valid only in script blocks.</span></span> <span data-ttu-id="0188e-191">Você não pode usá-los no formato de instrução de comparação de um `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="0188e-191">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="0188e-192">Para obter mais informações sobre operadores lógicos do PowerShell, consulte [about_Logical_Operators](./About/about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="0188e-192">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="0188e-193">Para obter mais informações sobre o recurso de ajuda atualizável, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="0188e-193">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="0188e-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0188e-194">PARAMETERS</span></span>

### <span data-ttu-id="0188e-195">-CContains</span><span class="sxs-lookup"><span data-stu-id="0188e-195">-CContains</span></span>

<span data-ttu-id="0188e-196">Indica que esse cmdlet obtém objetos de uma coleção se o valor da Propriedade do objeto for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-196">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="0188e-197">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-197">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-198">Por exemplo: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="0188e-198">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="0188e-199">**CContains** se refere a uma coleção de valores e é true se a coleção contém um item que é uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-199">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="0188e-200">Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-200">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0188e-201">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-202">-CEQ</span><span class="sxs-lookup"><span data-stu-id="0188e-202">-CEQ</span></span>

<span data-ttu-id="0188e-203">Indica que esse cmdlet obtém objetos se o valor da propriedade for igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-203">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="0188e-204">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-204">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-205">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-206">-CGE</span><span class="sxs-lookup"><span data-stu-id="0188e-206">-CGE</span></span>

<span data-ttu-id="0188e-207">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-207">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="0188e-208">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-208">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-209">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-209">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-210">-CGT</span><span class="sxs-lookup"><span data-stu-id="0188e-210">-CGT</span></span>

<span data-ttu-id="0188e-211">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-211">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="0188e-212">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-212">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-213">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-213">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-214">-CIn</span><span class="sxs-lookup"><span data-stu-id="0188e-214">-CIn</span></span>

<span data-ttu-id="0188e-215">Indica que esse cmdlet obtém objetos se o valor da propriedade incluir o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-215">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="0188e-216">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-216">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-217">Por exemplo: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="0188e-217">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="0188e-218">**CIN** se assemelha a **CContains** , exceto que as posições de propriedade e valor são revertidas.</span><span class="sxs-lookup"><span data-stu-id="0188e-218">**CIn** resembles **CContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="0188e-219">Por exemplo, as seguintes instruções são ambas verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="0188e-219">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="0188e-220">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-221">-CLE</span><span class="sxs-lookup"><span data-stu-id="0188e-221">-CLE</span></span>

<span data-ttu-id="0188e-222">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-222">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="0188e-223">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-223">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-224">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-225">-CLike</span><span class="sxs-lookup"><span data-stu-id="0188e-225">-CLike</span></span>

<span data-ttu-id="0188e-226">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="0188e-226">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="0188e-227">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-227">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-228">Por exemplo: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="0188e-228">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="0188e-229">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-230">-CLT</span><span class="sxs-lookup"><span data-stu-id="0188e-230">-CLT</span></span>

<span data-ttu-id="0188e-231">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-231">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="0188e-232">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-232">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-233">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-234">-CMatch</span><span class="sxs-lookup"><span data-stu-id="0188e-234">-CMatch</span></span>

<span data-ttu-id="0188e-235">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="0188e-235">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="0188e-236">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-236">This operation is case-sensitive.</span></span> <span data-ttu-id="0188e-237">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="0188e-237">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0188e-238">Por exemplo: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="0188e-238">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="0188e-239">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-240">-CNE</span><span class="sxs-lookup"><span data-stu-id="0188e-240">-CNE</span></span>

<span data-ttu-id="0188e-241">Indica que esse cmdlet obtém objetos se o valor da propriedade for diferente do valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-241">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="0188e-242">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-242">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-243">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-244">-CNotContains</span><span class="sxs-lookup"><span data-stu-id="0188e-244">-CNotContains</span></span>

<span data-ttu-id="0188e-245">Indica que esse cmdlet obtém objetos se o valor da Propriedade do objeto não for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-245">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="0188e-246">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-246">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-247">Por exemplo: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="0188e-247">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="0188e-248">**Iscontains** e **CNotContains** se referem a uma coleção de valores e são verdadeiros quando a coleção não contém nenhum item que seja uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-248">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="0188e-249">Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-249">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0188e-250">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-251">-CNotIn</span><span class="sxs-lookup"><span data-stu-id="0188e-251">-CNotIn</span></span>

<span data-ttu-id="0188e-252">Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-252">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="0188e-253">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-253">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-254">Por exemplo: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="0188e-254">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="0188e-255">Os operadores **NotIn** e **CNotIn** são semelhantes a **iscontains** e **CNotContains** , exceto que as posições de propriedade e valor são revertidas.</span><span class="sxs-lookup"><span data-stu-id="0188e-255">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="0188e-256">Por exemplo, as seguintes instruções são verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="0188e-256">For example, the following statements are true.</span></span>

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-257">-CNotLike</span><span class="sxs-lookup"><span data-stu-id="0188e-257">-CNotLike</span></span>

<span data-ttu-id="0188e-258">Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="0188e-258">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="0188e-259">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-259">This operation is case-sensitive.</span></span>

<span data-ttu-id="0188e-260">Por exemplo: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="0188e-260">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="0188e-261">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-262">-CNotMatch</span><span class="sxs-lookup"><span data-stu-id="0188e-262">-CNotMatch</span></span>

<span data-ttu-id="0188e-263">Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="0188e-263">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="0188e-264">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0188e-264">This operation is case-sensitive.</span></span> <span data-ttu-id="0188e-265">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="0188e-265">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0188e-266">Por exemplo: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="0188e-266">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="0188e-267">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-268">-Contém</span><span class="sxs-lookup"><span data-stu-id="0188e-268">-Contains</span></span>

<span data-ttu-id="0188e-269">Indica que esse cmdlet obtém objetos se qualquer item no valor da Propriedade do objeto for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-269">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="0188e-270">Por exemplo: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="0188e-270">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="0188e-271">Se o valor da propriedade contiver um único objeto, o PowerShell o converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-271">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0188e-272">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-273">-EQ</span><span class="sxs-lookup"><span data-stu-id="0188e-273">-EQ</span></span>

<span data-ttu-id="0188e-274">Indica que esse cmdlet obtém objetos se o valor da propriedade for igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-274">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="0188e-275">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-276">-FilterScript</span><span class="sxs-lookup"><span data-stu-id="0188e-276">-FilterScript</span></span>

<span data-ttu-id="0188e-277">Especifica o bloco de script usado para filtrar os objetos.</span><span class="sxs-lookup"><span data-stu-id="0188e-277">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="0188e-278">Coloque o bloco de script entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="0188e-278">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="0188e-279">O nome do parâmetro, **filterscript** , é opcional.</span><span class="sxs-lookup"><span data-stu-id="0188e-279">The parameter name, **FilterScript** , is optional.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-280">-GE</span><span class="sxs-lookup"><span data-stu-id="0188e-280">-GE</span></span>

<span data-ttu-id="0188e-281">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-281">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="0188e-282">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-283">-GT</span><span class="sxs-lookup"><span data-stu-id="0188e-283">-GT</span></span>

<span data-ttu-id="0188e-284">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-284">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="0188e-285">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-286">-In</span><span class="sxs-lookup"><span data-stu-id="0188e-286">-In</span></span>

<span data-ttu-id="0188e-287">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a qualquer um dos valores especificados.</span><span class="sxs-lookup"><span data-stu-id="0188e-287">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="0188e-288">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0188e-288">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="0188e-289">Se o valor do parâmetro **Value** for um único objeto, o PowerShell o converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-289">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0188e-290">Se o valor da propriedade de um objeto for uma matriz, o PowerShell usará a igualdade de referência para determinar uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="0188e-290">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="0188e-291">`Where-Object` Retorna o objeto somente se o valor do parâmetro **Property** e qualquer valor de **Value** forem a mesma instância de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-291">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="0188e-292">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-293">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0188e-293">-InputObject</span></span>

<span data-ttu-id="0188e-294">Especifica os objetos a serem filtrados.</span><span class="sxs-lookup"><span data-stu-id="0188e-294">Specifies the objects to be filtered.</span></span> <span data-ttu-id="0188e-295">Você também pode canalizar os objetos para `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="0188e-295">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="0188e-296">Quando você usa o parâmetro **InputObject** com `Where-Object` , em vez de direcionar os resultados de comando para `Where-Object` , o valor **InputObject** é tratado como um único objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-296">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="0188e-297">Isso é verdadeiro mesmo se o valor for uma coleção que é o resultado de um comando, como `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="0188e-297">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="0188e-298">Como **InputObject** não pode retornar propriedades individuais de uma matriz ou coleção de objetos, recomendamos que, se você usar `Where-Object` o para filtrar uma coleção de objetos para os objetos que têm valores específicos em propriedades definidas, use `Where-Object` no pipeline, conforme mostrado nos exemplos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0188e-298">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-299">-É</span><span class="sxs-lookup"><span data-stu-id="0188e-299">-Is</span></span>

<span data-ttu-id="0188e-300">Indica que esse cmdlet obtém objetos se o valor da propriedade for uma instância do tipo .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-300">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="0188e-301">Inclua o nome do tipo entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="0188e-301">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="0188e-302">Por exemplo, `Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="0188e-302">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="0188e-303">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-303">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-304">-IsNot</span><span class="sxs-lookup"><span data-stu-id="0188e-304">-IsNot</span></span>

<span data-ttu-id="0188e-305">Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma instância do tipo .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-305">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="0188e-306">Por exemplo, `Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="0188e-306">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="0188e-307">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-307">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-308">-LE</span><span class="sxs-lookup"><span data-stu-id="0188e-308">-LE</span></span>

<span data-ttu-id="0188e-309">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-309">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="0188e-310">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-311">-Like</span><span class="sxs-lookup"><span data-stu-id="0188e-311">-Like</span></span>

<span data-ttu-id="0188e-312">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="0188e-312">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="0188e-313">Por exemplo: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="0188e-313">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="0188e-314">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-314">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-315">-LT</span><span class="sxs-lookup"><span data-stu-id="0188e-315">-LT</span></span>

<span data-ttu-id="0188e-316">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-316">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="0188e-317">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-317">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-318">-Correspondência</span><span class="sxs-lookup"><span data-stu-id="0188e-318">-Match</span></span>

<span data-ttu-id="0188e-319">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="0188e-319">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="0188e-320">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="0188e-320">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0188e-321">Por exemplo: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="0188e-321">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="0188e-322">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-323">-NE</span><span class="sxs-lookup"><span data-stu-id="0188e-323">-NE</span></span>

<span data-ttu-id="0188e-324">Indica que esse cmdlet obtém objetos se o valor da propriedade for diferente do valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-324">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="0188e-325">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-325">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-326">-Não</span><span class="sxs-lookup"><span data-stu-id="0188e-326">-Not</span></span>

<span data-ttu-id="0188e-327">Indica que esse cmdlet obtém objetos se a propriedade não existir ou se tiver um valor de NULL ou false.</span><span class="sxs-lookup"><span data-stu-id="0188e-327">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="0188e-328">Por exemplo: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="0188e-328">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="0188e-329">Esse parâmetro foi introduzido no Windows PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="0188e-329">This parameter was introduced in Windows PowerShell 6.1.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-330">-Não contém</span><span class="sxs-lookup"><span data-stu-id="0188e-330">-NotContains</span></span>

<span data-ttu-id="0188e-331">Indica que esse cmdlet obtém objetos se nenhum dos itens no valor da propriedade for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-331">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="0188e-332">Por exemplo: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="0188e-332">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="0188e-333">Não **contém** se refere a uma coleção de valores e será true se a coleção não contiver nenhum item que seja uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0188e-333">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="0188e-334">Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-334">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0188e-335">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-335">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-336">-NotIn</span><span class="sxs-lookup"><span data-stu-id="0188e-336">-NotIn</span></span>

<span data-ttu-id="0188e-337">Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma correspondência exata para qualquer um dos valores especificados.</span><span class="sxs-lookup"><span data-stu-id="0188e-337">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="0188e-338">Por exemplo: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="0188e-338">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="0188e-339">Se o valor de **Value** for um objeto único, o PowerShell o converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-339">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="0188e-340">Se o valor da propriedade de um objeto for uma matriz, o PowerShell usará a igualdade de referência para determinar uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="0188e-340">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="0188e-341">`Where-Object` Retorna o objeto somente se o valor da **Propriedade** e qualquer valor de **valor** não forem a mesma instância de um objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-341">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="0188e-342">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-342">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-343">-Não gosto</span><span class="sxs-lookup"><span data-stu-id="0188e-343">-NotLike</span></span>

<span data-ttu-id="0188e-344">Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="0188e-344">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="0188e-345">Por exemplo: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="0188e-345">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="0188e-346">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-346">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-347">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="0188e-347">-NotMatch</span></span>

<span data-ttu-id="0188e-348">Indica que esse cmdlet obtém objetos quando o valor da propriedade não corresponde à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="0188e-348">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="0188e-349">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="0188e-349">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="0188e-350">Por exemplo: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="0188e-350">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="0188e-351">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-351">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-352">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="0188e-352">-Property</span></span>

<span data-ttu-id="0188e-353">Especifica o nome de uma propriedade de objeto.</span><span class="sxs-lookup"><span data-stu-id="0188e-353">Specifies the name of an object property.</span></span> <span data-ttu-id="0188e-354">O nome do parâmetro, **Propriedade** , é opcional.</span><span class="sxs-lookup"><span data-stu-id="0188e-354">The parameter name, **Property** , is optional.</span></span>

<span data-ttu-id="0188e-355">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-355">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, CaseSensitiveNotLikeSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0188e-356">-Value</span><span class="sxs-lookup"><span data-stu-id="0188e-356">-Value</span></span>

<span data-ttu-id="0188e-357">Especifica um valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="0188e-357">Specifies a property value.</span></span> <span data-ttu-id="0188e-358">O nome do parâmetro, **Value** , é opcional.</span><span class="sxs-lookup"><span data-stu-id="0188e-358">The parameter name, **Value** , is optional.</span></span> <span data-ttu-id="0188e-359">Esse parâmetro aceita caracteres curinga quando usados com os seguintes parâmetros de comparação:</span><span class="sxs-lookup"><span data-stu-id="0188e-359">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="0188e-360">**CLike**</span><span class="sxs-lookup"><span data-stu-id="0188e-360">**CLike**</span></span>
- <span data-ttu-id="0188e-361">**CNotLike**</span><span class="sxs-lookup"><span data-stu-id="0188e-361">**CNotLike**</span></span>
- <span data-ttu-id="0188e-362">**Similar**</span><span class="sxs-lookup"><span data-stu-id="0188e-362">**Like**</span></span>
- <span data-ttu-id="0188e-363">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="0188e-363">**NotLike**</span></span>

<span data-ttu-id="0188e-364">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0188e-364">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Object
Parameter Sets: EqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="0188e-365">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0188e-365">CommonParameters</span></span>

<span data-ttu-id="0188e-366">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0188e-366">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0188e-367">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0188e-367">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0188e-368">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0188e-368">INPUTS</span></span>

### <span data-ttu-id="0188e-369">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="0188e-369">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0188e-370">É possível canalizar os objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0188e-370">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="0188e-371">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0188e-371">OUTPUTS</span></span>

### <span data-ttu-id="0188e-372">Objeto</span><span class="sxs-lookup"><span data-stu-id="0188e-372">Object</span></span>

<span data-ttu-id="0188e-373">Esse cmdlet retorna os itens selecionados do conjunto de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="0188e-373">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="0188e-374">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0188e-374">NOTES</span></span>

<span data-ttu-id="0188e-375">A partir do Windows PowerShell 4,0, `Where` e os `ForEach` métodos foram adicionados para uso com coleções.</span><span class="sxs-lookup"><span data-stu-id="0188e-375">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="0188e-376">Você pode ler mais sobre esses novos métodos aqui [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="0188e-376">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="0188e-377">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0188e-377">RELATED LINKS</span></span>

[<span data-ttu-id="0188e-378">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-378">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="0188e-379">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-379">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="0188e-380">Group-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-380">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="0188e-381">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-381">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="0188e-382">New-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-382">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="0188e-383">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-383">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="0188e-384">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-384">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="0188e-385">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="0188e-385">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
