---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: aaee09926c93bb8c8e72efb5fd4ea34e2fc67391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193486"
---
# <span data-ttu-id="a551f-103">Where-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-103">Where-Object</span></span>

## <span data-ttu-id="a551f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a551f-104">SYNOPSIS</span></span>
<span data-ttu-id="a551f-105">Seleciona objetos de uma coleção com base em seus valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="a551f-105">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="a551f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a551f-106">SYNTAX</span></span>

### <span data-ttu-id="a551f-107">Igualset (padrão)</span><span class="sxs-lookup"><span data-stu-id="a551f-107">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ] [<CommonParameters>]
```

### <span data-ttu-id="a551f-108">ScriptBlockset</span><span class="sxs-lookup"><span data-stu-id="a551f-108">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="a551f-109">Matchset</span><span class="sxs-lookup"><span data-stu-id="a551f-109">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-Match]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-110">CaseSensitiveEqualSet</span><span class="sxs-lookup"><span data-stu-id="a551f-110">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CEQ] [<CommonParameters>]
```

### <span data-ttu-id="a551f-111">Não Igualset</span><span class="sxs-lookup"><span data-stu-id="a551f-111">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-NE] [<CommonParameters>]
```

### <span data-ttu-id="a551f-112">CaseSensitiveNotEqualSet</span><span class="sxs-lookup"><span data-stu-id="a551f-112">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CNE] [<CommonParameters>]
```

### <span data-ttu-id="a551f-113">GreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="a551f-113">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-GT] [<CommonParameters>]
```

### <span data-ttu-id="a551f-114">CaseSensitiveGreaterThanSet</span><span class="sxs-lookup"><span data-stu-id="a551f-114">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CGT] [<CommonParameters>]
```

### <span data-ttu-id="a551f-115">LessThanSet</span><span class="sxs-lookup"><span data-stu-id="a551f-115">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-LT] [<CommonParameters>]
```

### <span data-ttu-id="a551f-116">CaseSensitiveLessThanSet</span><span class="sxs-lookup"><span data-stu-id="a551f-116">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CLT] [<CommonParameters>]
```

### <span data-ttu-id="a551f-117">GreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="a551f-117">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-GE] [<CommonParameters>]
```

### <span data-ttu-id="a551f-118">CaseSensitiveGreaterOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="a551f-118">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CGE] [<CommonParameters>]
```

### <span data-ttu-id="a551f-119">LessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="a551f-119">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-LE] [<CommonParameters>]
```

### <span data-ttu-id="a551f-120">CaseSensitiveLessOrEqualSet</span><span class="sxs-lookup"><span data-stu-id="a551f-120">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CLE] [<CommonParameters>]
```

### <span data-ttu-id="a551f-121">Likeset</span><span class="sxs-lookup"><span data-stu-id="a551f-121">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-Like] [<CommonParameters>]
```

### <span data-ttu-id="a551f-122">CaseSensitiveLikeSet</span><span class="sxs-lookup"><span data-stu-id="a551f-122">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CLike] [<CommonParameters>]
```

### <span data-ttu-id="a551f-123">Não gosto de</span><span class="sxs-lookup"><span data-stu-id="a551f-123">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-NotLike] [<CommonParameters>]
```

### <span data-ttu-id="a551f-124">CaseSensitiveNotLikeSet</span><span class="sxs-lookup"><span data-stu-id="a551f-124">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CNotLike]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-125">CaseSensitiveMatchSet</span><span class="sxs-lookup"><span data-stu-id="a551f-125">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CMatch] [<CommonParameters>]
```

### <span data-ttu-id="a551f-126">Não Correspondenteset</span><span class="sxs-lookup"><span data-stu-id="a551f-126">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-NotMatch]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-127">CaseSensitiveNotMatchSet</span><span class="sxs-lookup"><span data-stu-id="a551f-127">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CNotMatch]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-128">Contémset</span><span class="sxs-lookup"><span data-stu-id="a551f-128">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-Contains]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-129">CaseSensitiveContainsSet</span><span class="sxs-lookup"><span data-stu-id="a551f-129">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CContains]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-130">Não contém Oset</span><span class="sxs-lookup"><span data-stu-id="a551f-130">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-NotContains]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-131">CaseSensitiveNotContainsSet</span><span class="sxs-lookup"><span data-stu-id="a551f-131">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CNotContains]
 [<CommonParameters>]
```

### <span data-ttu-id="a551f-132">Levo</span><span class="sxs-lookup"><span data-stu-id="a551f-132">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-In] [<CommonParameters>]
```

### <span data-ttu-id="a551f-133">CaseSensitiveInSet</span><span class="sxs-lookup"><span data-stu-id="a551f-133">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CIn] [<CommonParameters>]
```

### <span data-ttu-id="a551f-134">Não inserir</span><span class="sxs-lookup"><span data-stu-id="a551f-134">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-NotIn] [<CommonParameters>]
```

### <span data-ttu-id="a551f-135">CaseSensitiveNotInSet</span><span class="sxs-lookup"><span data-stu-id="a551f-135">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-CNotIn] [<CommonParameters>]
```

### <span data-ttu-id="a551f-136">IsSet</span><span class="sxs-lookup"><span data-stu-id="a551f-136">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-Is] [<CommonParameters>]
```

### <span data-ttu-id="a551f-137">Isnotset</span><span class="sxs-lookup"><span data-stu-id="a551f-137">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-IsNot] [<CommonParameters>]
```

## <span data-ttu-id="a551f-138">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a551f-138">DESCRIPTION</span></span>

<span data-ttu-id="a551f-139">O `Where-Object` cmdlet seleciona objetos que têm valores de propriedade específicos da coleção de objetos que são passados para ele.</span><span class="sxs-lookup"><span data-stu-id="a551f-139">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="a551f-140">Por exemplo, você pode usar o `Where-Object` cmdlet para selecionar os arquivos que foram criados após uma determinada data, eventos com uma ID específica ou computadores que usam uma versão específica do Windows.</span><span class="sxs-lookup"><span data-stu-id="a551f-140">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="a551f-141">A partir do Windows PowerShell 3,0, há duas maneiras diferentes de construir um `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="a551f-141">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="a551f-142">**Bloco de script** .</span><span class="sxs-lookup"><span data-stu-id="a551f-142">**Script block** .</span></span> <span data-ttu-id="a551f-143">Você pode usar um bloco de script para especificar o nome da propriedade, um operador de comparação e um valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="a551f-143">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="a551f-144">`Where-Object` Retorna todos os objetos para os quais a instrução de bloco de script é verdadeira.</span><span class="sxs-lookup"><span data-stu-id="a551f-144">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="a551f-145">Por exemplo, o comando a seguir obtém os processos na classe de prioridade normal, ou seja, processos em que o valor da propriedade **PriorityClass** é igual a normal.</span><span class="sxs-lookup"><span data-stu-id="a551f-145">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="a551f-146">Todos os operadores de comparação do PowerShell são válidos no formato de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="a551f-146">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="a551f-147">Para obter mais informações sobre operadores de comparação, consulte [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="a551f-147">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="a551f-148">**Instrução de comparação** .</span><span class="sxs-lookup"><span data-stu-id="a551f-148">**Comparison statement** .</span></span> <span data-ttu-id="a551f-149">Você também pode escrever uma instrução de comparação, que é muito mais como uma linguagem natural.</span><span class="sxs-lookup"><span data-stu-id="a551f-149">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="a551f-150">Instruções de comparação foram introduzidas no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-150">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="a551f-151">Por exemplo, os comandos a seguir também obtêm processos que têm uma classe de prioridade normal.</span><span class="sxs-lookup"><span data-stu-id="a551f-151">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="a551f-152">Estes comandos são equivalentes e podem ser usados intercambiavelmente.</span><span class="sxs-lookup"><span data-stu-id="a551f-152">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="a551f-153">A partir do Windows PowerShell 3,0, `Where-Object` o adiciona operadores de comparação como parâmetros em um `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="a551f-153">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="a551f-154">A menos que especificado, todos os operadores diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-154">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="a551f-155">Antes do Windows PowerShell 3,0, os operadores de comparação no idioma do PowerShell poderiam ser usados somente em blocos de script.</span><span class="sxs-lookup"><span data-stu-id="a551f-155">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="a551f-156">Quando você fornece uma única **Propriedade** para `Where-Object` , o valor da propriedade é tratado como uma expressão booliana.</span><span class="sxs-lookup"><span data-stu-id="a551f-156">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="a551f-157">Quando o valor de **Length** não for zero, a expressão será avaliada como **true** .</span><span class="sxs-lookup"><span data-stu-id="a551f-157">When the value of **Length** is not zero, the expression evaluates to **True** .</span></span> <span data-ttu-id="a551f-158">Por exemplo: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="a551f-158">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="a551f-159">O exemplo anterior é funcionalmente equivalente a:</span><span class="sxs-lookup"><span data-stu-id="a551f-159">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="a551f-160">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a551f-160">EXAMPLES</span></span>

### <span data-ttu-id="a551f-161">Exemplo 1: obter serviços interrompidos</span><span class="sxs-lookup"><span data-stu-id="a551f-161">Example 1: Get stopped services</span></span>

<span data-ttu-id="a551f-162">Esses comandos obtêm uma lista de todos os serviços que estão atualmente interrompidos.</span><span class="sxs-lookup"><span data-stu-id="a551f-162">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="a551f-163">A `$_` variável automática representa cada objeto que é passado para o `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a551f-163">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="a551f-164">O primeiro comando usa o formato de bloco de script, o segundo comando usa o formato de instrução de comparação.</span><span class="sxs-lookup"><span data-stu-id="a551f-164">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="a551f-165">Os comandos são equivalentes e podem ser usados intercambiavelmente.</span><span class="sxs-lookup"><span data-stu-id="a551f-165">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="a551f-166">Exemplo 2: obter processos com base no conjunto de trabalho</span><span class="sxs-lookup"><span data-stu-id="a551f-166">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="a551f-167">Esses comandos listam os processos que têm um conjunto de trabalho maior que 250 megabytes (KB).</span><span class="sxs-lookup"><span data-stu-id="a551f-167">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="a551f-168">A sintaxe scriptblock e Statement é equivalente e pode ser usada de maneira intercambiável.</span><span class="sxs-lookup"><span data-stu-id="a551f-168">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="a551f-169">Exemplo 3: obter processos com base no nome do processo</span><span class="sxs-lookup"><span data-stu-id="a551f-169">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="a551f-170">Esses comandos obtêm os processos que têm um valor de propriedade **ProcessName** que começa com a letra `p` .</span><span class="sxs-lookup"><span data-stu-id="a551f-170">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="a551f-171">O operador **Match** permite que você use correspondências de expressão regulares.</span><span class="sxs-lookup"><span data-stu-id="a551f-171">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="a551f-172">A sintaxe scriptblock e Statement é equivalente e pode ser usada de maneira intercambiável.</span><span class="sxs-lookup"><span data-stu-id="a551f-172">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="a551f-173">Exemplo 4: usar o formato de instrução de comparação</span><span class="sxs-lookup"><span data-stu-id="a551f-173">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="a551f-174">Este exemplo mostra como usar o novo formato de instrução de comparação do `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a551f-174">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="a551f-175">O primeiro comando usa o formato de instrução de comparação.</span><span class="sxs-lookup"><span data-stu-id="a551f-175">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="a551f-176">Neste comando, nenhum alias é usado e todos os parâmetros incluem o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="a551f-176">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="a551f-177">O segundo comando é o uso mais natural do formato de comando de comparação.</span><span class="sxs-lookup"><span data-stu-id="a551f-177">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="a551f-178">O `where` alias é substituído pelo nome do `Where-Object` cmdlet e todos os nomes de parâmetro opcionais são omitidos.</span><span class="sxs-lookup"><span data-stu-id="a551f-178">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="a551f-179">Exemplo 5: obter comandos com base em Propriedades</span><span class="sxs-lookup"><span data-stu-id="a551f-179">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="a551f-180">Este exemplo mostra como gravar comandos que retornam itens que são verdadeiros ou falsos, ou que tenham qualquer valor de uma propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="a551f-180">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="a551f-181">Cada exemplo mostra os formatos de bloco de script e de instrução de comparação para o comando.</span><span class="sxs-lookup"><span data-stu-id="a551f-181">Each example shows both the script block and comparison statement formats for the command.</span></span>

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

### <span data-ttu-id="a551f-182">Exemplo 6: usar várias condições</span><span class="sxs-lookup"><span data-stu-id="a551f-182">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="a551f-183">Este exemplo mostra como criar um `Where-Object` comando com várias condições.</span><span class="sxs-lookup"><span data-stu-id="a551f-183">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="a551f-184">Esse comando obtém módulos não essenciais que suportam o recurso de Ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="a551f-184">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="a551f-185">O comando usa o parâmetro **listAvailable** do `Get-Module` cmdlet para obter todos os módulos no computador.</span><span class="sxs-lookup"><span data-stu-id="a551f-185">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="a551f-186">Um operador de pipeline ( `|` ) envia os módulos para o `Where-Object` cmdlet, que obtém os módulos cujos nomes não começam com Microsoft ou PS, e têm um valor para a propriedade **HelpInfoURI** , que informa ao PowerShell onde encontrar arquivos de ajuda atualizados para o módulo.</span><span class="sxs-lookup"><span data-stu-id="a551f-186">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="a551f-187">As instruções de comparação são conectadas pelo operador lógico **and** .</span><span class="sxs-lookup"><span data-stu-id="a551f-187">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="a551f-188">O exemplo usa o formato de comando de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="a551f-188">The example uses the script block command format.</span></span> <span data-ttu-id="a551f-189">Operadores lógicos, como **e** e **ou** , são válidos somente em blocos de script.</span><span class="sxs-lookup"><span data-stu-id="a551f-189">Logical operators, such as **And** and **Or** , are valid only in script blocks.</span></span> <span data-ttu-id="a551f-190">Você não pode usá-los no formato de instrução de comparação de um `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="a551f-190">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="a551f-191">Para obter mais informações sobre operadores lógicos do PowerShell, consulte [about_Logical_Operators](./About/about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="a551f-191">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="a551f-192">Para obter mais informações sobre o recurso de ajuda atualizável, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="a551f-192">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="a551f-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a551f-193">PARAMETERS</span></span>

### <span data-ttu-id="a551f-194">-CContains</span><span class="sxs-lookup"><span data-stu-id="a551f-194">-CContains</span></span>

<span data-ttu-id="a551f-195">Indica que esse cmdlet obtém objetos de uma coleção se o valor da Propriedade do objeto for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-195">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="a551f-196">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-196">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-197">Por exemplo: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="a551f-197">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="a551f-198">**CContains** se refere a uma coleção de valores e é true se a coleção contém um item que é uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-198">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="a551f-199">Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-199">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="a551f-200">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-200">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-201">-CEQ</span><span class="sxs-lookup"><span data-stu-id="a551f-201">-CEQ</span></span>

<span data-ttu-id="a551f-202">Indica que esse cmdlet obtém objetos se o valor da propriedade for igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-202">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="a551f-203">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-203">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-204">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-205">-CGE</span><span class="sxs-lookup"><span data-stu-id="a551f-205">-CGE</span></span>

<span data-ttu-id="a551f-206">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-206">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="a551f-207">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-207">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-208">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-209">-CGT</span><span class="sxs-lookup"><span data-stu-id="a551f-209">-CGT</span></span>

<span data-ttu-id="a551f-210">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-210">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="a551f-211">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-211">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-212">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-213">-CIn</span><span class="sxs-lookup"><span data-stu-id="a551f-213">-CIn</span></span>

<span data-ttu-id="a551f-214">Indica que esse cmdlet obtém objetos se o valor da propriedade incluir o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-214">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="a551f-215">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-215">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-216">Por exemplo: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="a551f-216">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="a551f-217">**CIN** se assemelha a **CContains** , exceto que as posições de propriedade e valor são revertidas.</span><span class="sxs-lookup"><span data-stu-id="a551f-217">**CIn** resembles **CContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="a551f-218">Por exemplo, as seguintes instruções são ambas verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="a551f-218">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="a551f-219">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-219">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-220">-CLE</span><span class="sxs-lookup"><span data-stu-id="a551f-220">-CLE</span></span>

<span data-ttu-id="a551f-221">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-221">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="a551f-222">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-222">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-223">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-223">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-224">-CLike</span><span class="sxs-lookup"><span data-stu-id="a551f-224">-CLike</span></span>

<span data-ttu-id="a551f-225">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="a551f-225">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="a551f-226">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-226">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-227">Por exemplo: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="a551f-227">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="a551f-228">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-229">-CLT</span><span class="sxs-lookup"><span data-stu-id="a551f-229">-CLT</span></span>

<span data-ttu-id="a551f-230">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-230">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="a551f-231">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-231">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-232">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-233">-CMatch</span><span class="sxs-lookup"><span data-stu-id="a551f-233">-CMatch</span></span>

<span data-ttu-id="a551f-234">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="a551f-234">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="a551f-235">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-235">This operation is case-sensitive.</span></span> <span data-ttu-id="a551f-236">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="a551f-236">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="a551f-237">Por exemplo: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="a551f-237">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="a551f-238">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-238">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-239">-CNE</span><span class="sxs-lookup"><span data-stu-id="a551f-239">-CNE</span></span>

<span data-ttu-id="a551f-240">Indica que esse cmdlet obtém objetos se o valor da propriedade for diferente do valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-240">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="a551f-241">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-241">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-242">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-242">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-243">-CNotContains</span><span class="sxs-lookup"><span data-stu-id="a551f-243">-CNotContains</span></span>

<span data-ttu-id="a551f-244">Indica que esse cmdlet obtém objetos se o valor da Propriedade do objeto não for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-244">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="a551f-245">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-245">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-246">Por exemplo: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="a551f-246">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="a551f-247">**Iscontains** e **CNotContains** se referem a uma coleção de valores e são verdadeiros quando a coleção não contém nenhum item que seja uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-247">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="a551f-248">Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-248">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="a551f-249">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-250">-CNotIn</span><span class="sxs-lookup"><span data-stu-id="a551f-250">-CNotIn</span></span>

<span data-ttu-id="a551f-251">Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-251">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="a551f-252">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-252">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-253">Por exemplo: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="a551f-253">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="a551f-254">Os operadores **NotIn** e **CNotIn** são semelhantes a **iscontains** e **CNotContains** , exceto que as posições de propriedade e valor são revertidas.</span><span class="sxs-lookup"><span data-stu-id="a551f-254">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="a551f-255">Por exemplo, as seguintes instruções são verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="a551f-255">For example, the following statements are true.</span></span>

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

### <span data-ttu-id="a551f-256">-CNotLike</span><span class="sxs-lookup"><span data-stu-id="a551f-256">-CNotLike</span></span>

<span data-ttu-id="a551f-257">Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="a551f-257">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="a551f-258">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-258">This operation is case-sensitive.</span></span>

<span data-ttu-id="a551f-259">Por exemplo: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="a551f-259">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="a551f-260">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-261">-CNotMatch</span><span class="sxs-lookup"><span data-stu-id="a551f-261">-CNotMatch</span></span>

<span data-ttu-id="a551f-262">Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="a551f-262">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="a551f-263">Esta operação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a551f-263">This operation is case-sensitive.</span></span> <span data-ttu-id="a551f-264">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="a551f-264">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="a551f-265">Por exemplo: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="a551f-265">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="a551f-266">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-266">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-267">-Contém</span><span class="sxs-lookup"><span data-stu-id="a551f-267">-Contains</span></span>

<span data-ttu-id="a551f-268">Indica que esse cmdlet obtém objetos se qualquer item no valor da Propriedade do objeto for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-268">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="a551f-269">Por exemplo: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="a551f-269">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="a551f-270">Se o valor da propriedade contiver um único objeto, o PowerShell o converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-270">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="a551f-271">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-272">-EQ</span><span class="sxs-lookup"><span data-stu-id="a551f-272">-EQ</span></span>

<span data-ttu-id="a551f-273">Indica que esse cmdlet obtém objetos se o valor da propriedade for igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-273">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="a551f-274">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-274">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-275">-FilterScript</span><span class="sxs-lookup"><span data-stu-id="a551f-275">-FilterScript</span></span>

<span data-ttu-id="a551f-276">Especifica o bloco de script usado para filtrar os objetos.</span><span class="sxs-lookup"><span data-stu-id="a551f-276">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="a551f-277">Coloque o bloco de script entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="a551f-277">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="a551f-278">O nome do parâmetro, **filterscript** , é opcional.</span><span class="sxs-lookup"><span data-stu-id="a551f-278">The parameter name, **FilterScript** , is optional.</span></span>

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

### <span data-ttu-id="a551f-279">-GE</span><span class="sxs-lookup"><span data-stu-id="a551f-279">-GE</span></span>

<span data-ttu-id="a551f-280">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-280">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="a551f-281">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-282">-GT</span><span class="sxs-lookup"><span data-stu-id="a551f-282">-GT</span></span>

<span data-ttu-id="a551f-283">Indica que esse cmdlet obtém objetos se o valor da propriedade for maior que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-283">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="a551f-284">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-284">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-285">-In</span><span class="sxs-lookup"><span data-stu-id="a551f-285">-In</span></span>

<span data-ttu-id="a551f-286">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a qualquer um dos valores especificados.</span><span class="sxs-lookup"><span data-stu-id="a551f-286">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="a551f-287">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a551f-287">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="a551f-288">Se o valor do parâmetro **Value** for um único objeto, o PowerShell o converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-288">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="a551f-289">Se o valor da propriedade de um objeto for uma matriz, o PowerShell usará a igualdade de referência para determinar uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="a551f-289">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="a551f-290">`Where-Object` Retorna o objeto somente se o valor do parâmetro **Property** e qualquer valor de **Value** forem a mesma instância de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-290">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="a551f-291">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-291">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-292">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a551f-292">-InputObject</span></span>

<span data-ttu-id="a551f-293">Especifica os objetos a serem filtrados.</span><span class="sxs-lookup"><span data-stu-id="a551f-293">Specifies the objects to be filtered.</span></span> <span data-ttu-id="a551f-294">Você também pode canalizar os objetos para `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="a551f-294">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="a551f-295">Quando você usa o parâmetro **InputObject** com `Where-Object` , em vez de direcionar os resultados de comando para `Where-Object` , o valor **InputObject** é tratado como um único objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-295">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="a551f-296">Isso é verdadeiro mesmo se o valor for uma coleção que é o resultado de um comando, como `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="a551f-296">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="a551f-297">Como **InputObject** não pode retornar propriedades individuais de uma matriz ou coleção de objetos, recomendamos que, se você usar `Where-Object` o para filtrar uma coleção de objetos para os objetos que têm valores específicos em propriedades definidas, use `Where-Object` no pipeline, conforme mostrado nos exemplos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a551f-297">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="a551f-298">-É</span><span class="sxs-lookup"><span data-stu-id="a551f-298">-Is</span></span>

<span data-ttu-id="a551f-299">Indica que esse cmdlet obtém objetos se o valor da propriedade for uma instância do tipo .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-299">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="a551f-300">Inclua o nome do tipo entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="a551f-300">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="a551f-301">Por exemplo, `Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="a551f-301">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="a551f-302">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-302">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-303">-IsNot</span><span class="sxs-lookup"><span data-stu-id="a551f-303">-IsNot</span></span>

<span data-ttu-id="a551f-304">Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma instância do tipo .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-304">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="a551f-305">Por exemplo, `Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="a551f-305">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="a551f-306">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-306">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-307">-LE</span><span class="sxs-lookup"><span data-stu-id="a551f-307">-LE</span></span>

<span data-ttu-id="a551f-308">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-308">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="a551f-309">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-309">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-310">-Like</span><span class="sxs-lookup"><span data-stu-id="a551f-310">-Like</span></span>

<span data-ttu-id="a551f-311">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="a551f-311">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="a551f-312">Por exemplo: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="a551f-312">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="a551f-313">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-313">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-314">-LT</span><span class="sxs-lookup"><span data-stu-id="a551f-314">-LT</span></span>

<span data-ttu-id="a551f-315">Indica que esse cmdlet obtém objetos se o valor da propriedade for menor que o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-315">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="a551f-316">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-317">-Correspondência</span><span class="sxs-lookup"><span data-stu-id="a551f-317">-Match</span></span>

<span data-ttu-id="a551f-318">Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="a551f-318">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="a551f-319">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="a551f-319">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="a551f-320">Por exemplo: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="a551f-320">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="a551f-321">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-321">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-322">-NE</span><span class="sxs-lookup"><span data-stu-id="a551f-322">-NE</span></span>

<span data-ttu-id="a551f-323">Indica que esse cmdlet obtém objetos se o valor da propriedade for diferente do valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-323">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="a551f-324">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-324">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-325">-Não contém</span><span class="sxs-lookup"><span data-stu-id="a551f-325">-NotContains</span></span>

<span data-ttu-id="a551f-326">Indica que esse cmdlet obtém objetos se nenhum dos itens no valor da propriedade for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-326">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="a551f-327">Por exemplo: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="a551f-327">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="a551f-328">Não **contém** se refere a uma coleção de valores e será true se a coleção não contiver nenhum item que seja uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a551f-328">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="a551f-329">Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-329">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="a551f-330">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-330">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-331">-NotIn</span><span class="sxs-lookup"><span data-stu-id="a551f-331">-NotIn</span></span>

<span data-ttu-id="a551f-332">Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma correspondência exata para qualquer um dos valores especificados.</span><span class="sxs-lookup"><span data-stu-id="a551f-332">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="a551f-333">Por exemplo: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="a551f-333">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="a551f-334">Se o valor de **Value** for um objeto único, o PowerShell o converterá em uma coleção de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-334">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="a551f-335">Se o valor da propriedade de um objeto for uma matriz, o PowerShell usará a igualdade de referência para determinar uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="a551f-335">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="a551f-336">`Where-Object` Retorna o objeto somente se o valor da **Propriedade** e qualquer valor de **valor** não forem a mesma instância de um objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-336">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="a551f-337">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-337">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-338">-Não gosto</span><span class="sxs-lookup"><span data-stu-id="a551f-338">-NotLike</span></span>

<span data-ttu-id="a551f-339">Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder a um valor que inclui caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="a551f-339">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="a551f-340">Por exemplo: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="a551f-340">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="a551f-341">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-341">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-342">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="a551f-342">-NotMatch</span></span>

<span data-ttu-id="a551f-343">Indica que esse cmdlet obtém objetos quando o valor da propriedade não corresponde à expressão regular especificada.</span><span class="sxs-lookup"><span data-stu-id="a551f-343">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="a551f-344">Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="a551f-344">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="a551f-345">Por exemplo: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="a551f-345">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="a551f-346">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-346">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a551f-347">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="a551f-347">-Property</span></span>

<span data-ttu-id="a551f-348">Especifica o nome de uma propriedade de objeto.</span><span class="sxs-lookup"><span data-stu-id="a551f-348">Specifies the name of an object property.</span></span> <span data-ttu-id="a551f-349">O nome do parâmetro, **Propriedade** , é opcional.</span><span class="sxs-lookup"><span data-stu-id="a551f-349">The parameter name, **Property** , is optional.</span></span>

<span data-ttu-id="a551f-350">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-350">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, MatchSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a551f-351">-Value</span><span class="sxs-lookup"><span data-stu-id="a551f-351">-Value</span></span>

<span data-ttu-id="a551f-352">Especifica um valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="a551f-352">Specifies a property value.</span></span> <span data-ttu-id="a551f-353">O nome do parâmetro, **Value** , é opcional.</span><span class="sxs-lookup"><span data-stu-id="a551f-353">The parameter name, **Value** , is optional.</span></span> <span data-ttu-id="a551f-354">Esse parâmetro aceita caracteres curinga quando usados com os seguintes parâmetros de comparação:</span><span class="sxs-lookup"><span data-stu-id="a551f-354">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="a551f-355">**CLike**</span><span class="sxs-lookup"><span data-stu-id="a551f-355">**CLike**</span></span>
- <span data-ttu-id="a551f-356">**CNotLike**</span><span class="sxs-lookup"><span data-stu-id="a551f-356">**CNotLike**</span></span>
- <span data-ttu-id="a551f-357">**Similar**</span><span class="sxs-lookup"><span data-stu-id="a551f-357">**Like**</span></span>
- <span data-ttu-id="a551f-358">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="a551f-358">**NotLike**</span></span>

<span data-ttu-id="a551f-359">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a551f-359">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: EqualSet, MatchSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a551f-360">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a551f-360">CommonParameters</span></span>

<span data-ttu-id="a551f-361">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a551f-361">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a551f-362">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a551f-362">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a551f-363">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a551f-363">INPUTS</span></span>

### <span data-ttu-id="a551f-364">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="a551f-364">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a551f-365">É possível canalizar os objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a551f-365">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="a551f-366">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a551f-366">OUTPUTS</span></span>

### <span data-ttu-id="a551f-367">Objeto</span><span class="sxs-lookup"><span data-stu-id="a551f-367">Object</span></span>

<span data-ttu-id="a551f-368">Esse cmdlet retorna os itens selecionados do conjunto de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a551f-368">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="a551f-369">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a551f-369">NOTES</span></span>

<span data-ttu-id="a551f-370">A partir do Windows PowerShell 4,0, `Where` e os `ForEach` métodos foram adicionados para uso com coleções.</span><span class="sxs-lookup"><span data-stu-id="a551f-370">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="a551f-371">Você pode ler mais sobre esses novos métodos aqui [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="a551f-371">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="a551f-372">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a551f-372">RELATED LINKS</span></span>

[<span data-ttu-id="a551f-373">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-373">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="a551f-374">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-374">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="a551f-375">Group-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-375">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="a551f-376">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-376">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="a551f-377">New-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-377">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="a551f-378">Select-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-378">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="a551f-379">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-379">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="a551f-380">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="a551f-380">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
