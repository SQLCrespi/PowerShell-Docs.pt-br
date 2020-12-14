---
description: Descreve os operadores que comparam valores no PowerShell.
Locale: en-US
ms.date: 12/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: ba671ae51d458a2e0074a85d4de859795c20a3d5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97069896"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="eabad-103">Sobre operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="eabad-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="eabad-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="eabad-104">Short description</span></span>
<span data-ttu-id="eabad-105">Descreve os operadores que comparam valores no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eabad-105">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="eabad-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="eabad-106">Long description</span></span>

<span data-ttu-id="eabad-107">Os operadores de comparação permitem especificar condições para comparar valores e localizar valores que correspondam aos padrões especificados.</span><span class="sxs-lookup"><span data-stu-id="eabad-107">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="eabad-108">Para usar um operador de comparação, especifique os valores que você deseja comparar junto com um operador que separa esses valores.</span><span class="sxs-lookup"><span data-stu-id="eabad-108">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="eabad-109">O PowerShell inclui os seguintes operadores de comparação:</span><span class="sxs-lookup"><span data-stu-id="eabad-109">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="eabad-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="eabad-110">Type</span></span>        | <span data-ttu-id="eabad-111">Operadores</span><span class="sxs-lookup"><span data-stu-id="eabad-111">Operators</span></span>    | <span data-ttu-id="eabad-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="eabad-112">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="eabad-113">Igualitário</span><span class="sxs-lookup"><span data-stu-id="eabad-113">Equality</span></span>    | <span data-ttu-id="eabad-114">-eq</span><span class="sxs-lookup"><span data-stu-id="eabad-114">-eq</span></span>          | <span data-ttu-id="eabad-115">equals</span><span class="sxs-lookup"><span data-stu-id="eabad-115">equals</span></span>                                      |
|             | <span data-ttu-id="eabad-116">-ne</span><span class="sxs-lookup"><span data-stu-id="eabad-116">-ne</span></span>          | <span data-ttu-id="eabad-117">Não é igual a</span><span class="sxs-lookup"><span data-stu-id="eabad-117">not equals</span></span>                                  |
|             | <span data-ttu-id="eabad-118">-gt</span><span class="sxs-lookup"><span data-stu-id="eabad-118">-gt</span></span>          | <span data-ttu-id="eabad-119">maior que</span><span class="sxs-lookup"><span data-stu-id="eabad-119">greater than</span></span>                                |
|             | <span data-ttu-id="eabad-120">-ge</span><span class="sxs-lookup"><span data-stu-id="eabad-120">-ge</span></span>          | <span data-ttu-id="eabad-121">maior ou igual</span><span class="sxs-lookup"><span data-stu-id="eabad-121">greater than or equal</span></span>                       |
|             | <span data-ttu-id="eabad-122">-lt</span><span class="sxs-lookup"><span data-stu-id="eabad-122">-lt</span></span>          | <span data-ttu-id="eabad-123">menor que</span><span class="sxs-lookup"><span data-stu-id="eabad-123">less than</span></span>                                   |
|             | <span data-ttu-id="eabad-124">-le</span><span class="sxs-lookup"><span data-stu-id="eabad-124">-le</span></span>          | <span data-ttu-id="eabad-125">menor ou igual</span><span class="sxs-lookup"><span data-stu-id="eabad-125">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="eabad-126">Matching</span><span class="sxs-lookup"><span data-stu-id="eabad-126">Matching</span></span>    | <span data-ttu-id="eabad-127">-like</span><span class="sxs-lookup"><span data-stu-id="eabad-127">-like</span></span>        | <span data-ttu-id="eabad-128">Retorna true quando a cadeia de caracteres corresponde ao curinga</span><span class="sxs-lookup"><span data-stu-id="eabad-128">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="eabad-129">pattern</span><span class="sxs-lookup"><span data-stu-id="eabad-129">pattern</span></span>                                     |
|             | <span data-ttu-id="eabad-130">-notlike</span><span class="sxs-lookup"><span data-stu-id="eabad-130">-notlike</span></span>     | <span data-ttu-id="eabad-131">Retorna true quando a cadeia de caracteres não corresponde</span><span class="sxs-lookup"><span data-stu-id="eabad-131">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="eabad-132">padrão de curinga</span><span class="sxs-lookup"><span data-stu-id="eabad-132">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="eabad-133">-match</span><span class="sxs-lookup"><span data-stu-id="eabad-133">-match</span></span>       | <span data-ttu-id="eabad-134">Retorna true quando a cadeia de caracteres corresponde ao Regex</span><span class="sxs-lookup"><span data-stu-id="eabad-134">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="eabad-135">padrão $matches contém cadeias de caracteres correspondentes</span><span class="sxs-lookup"><span data-stu-id="eabad-135">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="eabad-136">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="eabad-136">-notmatch</span></span>    | <span data-ttu-id="eabad-137">Retorna true quando a cadeia de caracteres não corresponde</span><span class="sxs-lookup"><span data-stu-id="eabad-137">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="eabad-138">padrão Regex; $matches contém correspondência</span><span class="sxs-lookup"><span data-stu-id="eabad-138">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="eabad-139">cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="eabad-139">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="eabad-140">Contenção</span><span class="sxs-lookup"><span data-stu-id="eabad-140">Containment</span></span> | <span data-ttu-id="eabad-141">-contains</span><span class="sxs-lookup"><span data-stu-id="eabad-141">-contains</span></span>    | <span data-ttu-id="eabad-142">Retorna true quando o valor de referência está contido</span><span class="sxs-lookup"><span data-stu-id="eabad-142">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="eabad-143">em uma coleção</span><span class="sxs-lookup"><span data-stu-id="eabad-143">in a collection</span></span>                             |
|             | <span data-ttu-id="eabad-144">-notcontains</span><span class="sxs-lookup"><span data-stu-id="eabad-144">-notcontains</span></span> | <span data-ttu-id="eabad-145">Retorna true quando o valor de referência não é</span><span class="sxs-lookup"><span data-stu-id="eabad-145">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="eabad-146">contido em uma coleção</span><span class="sxs-lookup"><span data-stu-id="eabad-146">contained in a collection</span></span>                   |
|             | <span data-ttu-id="eabad-147">-in</span><span class="sxs-lookup"><span data-stu-id="eabad-147">-in</span></span>          | <span data-ttu-id="eabad-148">Retorna true quando o valor de teste está contido em um</span><span class="sxs-lookup"><span data-stu-id="eabad-148">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="eabad-149">collection</span><span class="sxs-lookup"><span data-stu-id="eabad-149">collection</span></span>                                  |
|             | <span data-ttu-id="eabad-150">-notin</span><span class="sxs-lookup"><span data-stu-id="eabad-150">-notin</span></span>       | <span data-ttu-id="eabad-151">Retorna true quando o valor de teste não está contido</span><span class="sxs-lookup"><span data-stu-id="eabad-151">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="eabad-152">em uma coleção</span><span class="sxs-lookup"><span data-stu-id="eabad-152">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="eabad-153">Substituição</span><span class="sxs-lookup"><span data-stu-id="eabad-153">Replacement</span></span> | <span data-ttu-id="eabad-154">-substituir</span><span class="sxs-lookup"><span data-stu-id="eabad-154">-replace</span></span>     | <span data-ttu-id="eabad-155">Substitui um padrão de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="eabad-155">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="eabad-156">Tipo</span><span class="sxs-lookup"><span data-stu-id="eabad-156">Type</span></span>        | <span data-ttu-id="eabad-157">-é</span><span class="sxs-lookup"><span data-stu-id="eabad-157">-is</span></span>          | <span data-ttu-id="eabad-158">Retornará true se ambos os objetos forem iguais</span><span class="sxs-lookup"><span data-stu-id="eabad-158">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="eabad-159">tipo</span><span class="sxs-lookup"><span data-stu-id="eabad-159">type</span></span>                                        |
|             | <span data-ttu-id="eabad-160">-IsNot</span><span class="sxs-lookup"><span data-stu-id="eabad-160">-isnot</span></span>       | <span data-ttu-id="eabad-161">Retornará true se os objetos não forem iguais</span><span class="sxs-lookup"><span data-stu-id="eabad-161">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="eabad-162">tipo</span><span class="sxs-lookup"><span data-stu-id="eabad-162">type</span></span>                                        |

<span data-ttu-id="eabad-163">Por padrão, todos os operadores de comparação não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="eabad-163">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="eabad-164">Para tornar um operador de comparação que diferencia maiúsculas de minúsculas, preceda o nome do operador com um `c` .</span><span class="sxs-lookup"><span data-stu-id="eabad-164">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="eabad-165">Por exemplo, a versão de diferenciação de maiúsculas e minúsculas do `-eq` é `-ceq` .</span><span class="sxs-lookup"><span data-stu-id="eabad-165">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="eabad-166">Para tornar a diferenciação de maiúsculas e minúsculas explícita, preceda o operador com um `i` .</span><span class="sxs-lookup"><span data-stu-id="eabad-166">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="eabad-167">Por exemplo, a versão explicitamente não diferencia maiúsculas de minúsculas de `-eq` é `-ieq` .</span><span class="sxs-lookup"><span data-stu-id="eabad-167">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="eabad-168">Quando a entrada para um operador é um valor escalar, os operadores de comparação retornam um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="eabad-168">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="eabad-169">Quando a entrada é uma coleção de valores, os operadores de comparação retornam quaisquer valores correspondentes.</span><span class="sxs-lookup"><span data-stu-id="eabad-169">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="eabad-170">Se não houver nenhuma correspondência em uma coleção, os operadores de comparação retornarão uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="eabad-170">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="eabad-171">As exceções são os operadores de confinamento, os operadores in e os operadores de tipo, que sempre retornam um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="eabad-171">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="eabad-172">Se você precisar comparar um valor para `$null` você deve colocar `$null` no lado esquerdo da comparação.</span><span class="sxs-lookup"><span data-stu-id="eabad-172">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="eabad-173">Quando você compara `$null` a um **objeto []** , o resultado é **false** porque o objeto de comparação é uma matriz.</span><span class="sxs-lookup"><span data-stu-id="eabad-173">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="eabad-174">Quando você compara uma matriz com `$null` o, a comparação filtra quaisquer `$null` valores armazenados na matriz.</span><span class="sxs-lookup"><span data-stu-id="eabad-174">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="eabad-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-175">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

## <a name="equality-operators"></a><span data-ttu-id="eabad-176">Operadores de igualdade</span><span class="sxs-lookup"><span data-stu-id="eabad-176">Equality operators</span></span>

<span data-ttu-id="eabad-177">Os operadores de igualdade ( `-eq` , `-ne` ) retornam um valor de true ou as correspondências quando um ou mais valores de entrada são idênticos ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="eabad-177">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="eabad-178">O padrão inteiro deve corresponder a um valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="eabad-178">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="eabad-179">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-179">Example:</span></span>

### <a name="-eq"></a><span data-ttu-id="eabad-180">-eq</span><span class="sxs-lookup"><span data-stu-id="eabad-180">-eq</span></span>

<span data-ttu-id="eabad-181">Descrição: igual a.</span><span class="sxs-lookup"><span data-stu-id="eabad-181">Description: Equal to.</span></span> <span data-ttu-id="eabad-182">Inclui um valor idêntico.</span><span class="sxs-lookup"><span data-stu-id="eabad-182">Includes an identical value.</span></span>

<span data-ttu-id="eabad-183">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-183">Example:</span></span>

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

### <a name="-ne"></a><span data-ttu-id="eabad-184">-ne</span><span class="sxs-lookup"><span data-stu-id="eabad-184">-ne</span></span>

<span data-ttu-id="eabad-185">Descrição: diferente de.</span><span class="sxs-lookup"><span data-stu-id="eabad-185">Description: Not equal to.</span></span> <span data-ttu-id="eabad-186">Inclui um valor diferente.</span><span class="sxs-lookup"><span data-stu-id="eabad-186">Includes a different value.</span></span>

<span data-ttu-id="eabad-187">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-187">Example:</span></span>

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

### <a name="-gt"></a><span data-ttu-id="eabad-188">-gt</span><span class="sxs-lookup"><span data-stu-id="eabad-188">-gt</span></span>

<span data-ttu-id="eabad-189">Descrição: maior que.</span><span class="sxs-lookup"><span data-stu-id="eabad-189">Description: Greater-than.</span></span>

<span data-ttu-id="eabad-190">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-190">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="eabad-191">Isso não deve ser confundido com `>` o operador maior que em muitas outras linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="eabad-191">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="eabad-192">No PowerShell, `>` é usado para redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="eabad-192">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="eabad-193">Para obter mais informações, consulte [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span><span class="sxs-lookup"><span data-stu-id="eabad-193">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

### <a name="-ge"></a><span data-ttu-id="eabad-194">-ge</span><span class="sxs-lookup"><span data-stu-id="eabad-194">-ge</span></span>

<span data-ttu-id="eabad-195">Descrição: maior que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="eabad-195">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="eabad-196">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-196">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

### <a name="-lt"></a><span data-ttu-id="eabad-197">-lt</span><span class="sxs-lookup"><span data-stu-id="eabad-197">-lt</span></span>

<span data-ttu-id="eabad-198">Descrição: menor que.</span><span class="sxs-lookup"><span data-stu-id="eabad-198">Description: Less-than.</span></span>

<span data-ttu-id="eabad-199">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-199">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

### <a name="-le"></a><span data-ttu-id="eabad-200">-le</span><span class="sxs-lookup"><span data-stu-id="eabad-200">-le</span></span>

<span data-ttu-id="eabad-201">Descrição: menor que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="eabad-201">Description: Less-than or equal to.</span></span>

<span data-ttu-id="eabad-202">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-202">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

## <a name="matching-operators"></a><span data-ttu-id="eabad-203">Operadores correspondentes</span><span class="sxs-lookup"><span data-stu-id="eabad-203">Matching operators</span></span>

<span data-ttu-id="eabad-204">Os operadores like ( `-like` e `-notlike` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões curinga.</span><span class="sxs-lookup"><span data-stu-id="eabad-204">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="eabad-205">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="eabad-205">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="eabad-206">Os operadores de correspondência ( `-match` e `-notmatch` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="eabad-206">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="eabad-207">Os operadores de correspondência preenchem a `$Matches` variável automática quando a entrada (o argumento do lado esquerdo) para o operador é um único objeto escalar.</span><span class="sxs-lookup"><span data-stu-id="eabad-207">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="eabad-208">Quando a entrada é escalar, os `-match` `-notmatch` operadores e retornam um valor booliano e definem o valor da `$Matches` variável automática para os componentes correspondentes do argumento.</span><span class="sxs-lookup"><span data-stu-id="eabad-208">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="eabad-209">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="eabad-209">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

### <a name="-like"></a><span data-ttu-id="eabad-210">-like</span><span class="sxs-lookup"><span data-stu-id="eabad-210">-like</span></span>

<span data-ttu-id="eabad-211">Descrição: correspondência usando o caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="eabad-211">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="eabad-212">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-212">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

### <a name="-notlike"></a><span data-ttu-id="eabad-213">-notlike</span><span class="sxs-lookup"><span data-stu-id="eabad-213">-notlike</span></span>

<span data-ttu-id="eabad-214">Descrição: não corresponde usando o caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="eabad-214">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="eabad-215">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-215">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="eabad-216">-match</span><span class="sxs-lookup"><span data-stu-id="eabad-216">-match</span></span>

<span data-ttu-id="eabad-217">Descrição: corresponde a uma cadeia de caracteres usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="eabad-217">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="eabad-218">Quando a entrada é escalar, ela popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="eabad-218">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="eabad-219">Se a entrada for uma coleção, os `-match` `-notmatch` operadores e retornarão os membros correspondentes dessa coleção, mas o operador não preencherá a `$Matches` variável.</span><span class="sxs-lookup"><span data-stu-id="eabad-219">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="eabad-220">Por exemplo, o comando a seguir envia uma coleção de cadeias de caracteres para o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="eabad-220">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="eabad-221">O `-match` operador retorna os itens na coleção que correspondem.</span><span class="sxs-lookup"><span data-stu-id="eabad-221">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="eabad-222">Ele não preenche a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="eabad-222">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="eabad-223">Por outro lado, o comando a seguir envia uma única cadeia de caracteres para o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="eabad-223">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="eabad-224">O `-match` operador retorna um valor booliano e popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="eabad-224">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="eabad-225">A `$Matches` variável automática é uma **tabela de hash**.</span><span class="sxs-lookup"><span data-stu-id="eabad-225">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="eabad-226">Se nenhum agrupamento ou captura for usado, apenas uma chave será populada.</span><span class="sxs-lookup"><span data-stu-id="eabad-226">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="eabad-227">A `0` chave representa todo o texto que foi correspondido.</span><span class="sxs-lookup"><span data-stu-id="eabad-227">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="eabad-228">Para obter mais informações sobre agrupamento e captura usando expressões regulares, consulte [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="eabad-228">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="eabad-229">É importante observar que a tabela de `$Matches` hash conterá apenas a primeira ocorrência de qualquer padrão correspondente.</span><span class="sxs-lookup"><span data-stu-id="eabad-229">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="eabad-230">A `0` chave é um **número inteiro**.</span><span class="sxs-lookup"><span data-stu-id="eabad-230">The `0` key is an **Integer**.</span></span> <span data-ttu-id="eabad-231">Você pode usar qualquer método de **Hashtable** para acessar o valor armazenado.</span><span class="sxs-lookup"><span data-stu-id="eabad-231">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

<span data-ttu-id="eabad-232">O `-notmatch` operador popula a `$Matches` variável automática quando a entrada é escalar e o resultado é false, quando detecta uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="eabad-232">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

### <a name="-notmatch"></a><span data-ttu-id="eabad-233">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="eabad-233">-notmatch</span></span>

<span data-ttu-id="eabad-234">Descrição: não corresponde a uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eabad-234">Description: Does not match a string.</span></span> <span data-ttu-id="eabad-235">Usa expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="eabad-235">Uses regular expressions.</span></span> <span data-ttu-id="eabad-236">Quando a entrada é escalar, ela popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="eabad-236">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="eabad-237">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-237">Example:</span></span>

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

## <a name="containment-operators"></a><span data-ttu-id="eabad-238">Operadores de confinamento</span><span class="sxs-lookup"><span data-stu-id="eabad-238">Containment operators</span></span>

<span data-ttu-id="eabad-239">Os operadores de confinamento ( `-contains` e `-notcontains` ) são semelhantes aos operadores de igualdade.</span><span class="sxs-lookup"><span data-stu-id="eabad-239">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="eabad-240">No entanto, os operadores de confinamento sempre retornam um valor booliano, mesmo quando a entrada é uma coleção.</span><span class="sxs-lookup"><span data-stu-id="eabad-240">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="eabad-241">Além disso, ao contrário dos operadores de igualdade, os operadores de confinamento retornam um valor assim que detectam a primeira correspondência.</span><span class="sxs-lookup"><span data-stu-id="eabad-241">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="eabad-242">Os operadores de igualdade avaliam todas as entradas e retornam todas as correspondências na coleção.</span><span class="sxs-lookup"><span data-stu-id="eabad-242">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

### <a name="-contains"></a><span data-ttu-id="eabad-243">-contains</span><span class="sxs-lookup"><span data-stu-id="eabad-243">-contains</span></span>

<span data-ttu-id="eabad-244">Descrição: operador de contenção.</span><span class="sxs-lookup"><span data-stu-id="eabad-244">Description: Containment operator.</span></span> <span data-ttu-id="eabad-245">Informa se uma coleção de valores de referência inclui um único valor de teste.</span><span class="sxs-lookup"><span data-stu-id="eabad-245">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="eabad-246">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="eabad-246">Always returns a Boolean value.</span></span> <span data-ttu-id="eabad-247">Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-247">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="eabad-248">Quando o valor de teste é uma coleção, o operador Contains usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-248">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="eabad-249">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="eabad-249">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="eabad-250">Em uma coleção muito grande, o `-contains` operador retorna resultados mais rapidamente do que o operador igual a.</span><span class="sxs-lookup"><span data-stu-id="eabad-250">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="eabad-251">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="eabad-251">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="eabad-252">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="eabad-252">Examples:</span></span>

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

### <a name="-notcontains"></a><span data-ttu-id="eabad-253">-notcontains</span><span class="sxs-lookup"><span data-stu-id="eabad-253">-notcontains</span></span>

<span data-ttu-id="eabad-254">Descrição: operador de contenção.</span><span class="sxs-lookup"><span data-stu-id="eabad-254">Description: Containment operator.</span></span> <span data-ttu-id="eabad-255">Informa se uma coleção de valores de referência inclui um único valor de teste.</span><span class="sxs-lookup"><span data-stu-id="eabad-255">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="eabad-256">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="eabad-256">Always returns a Boolean value.</span></span> <span data-ttu-id="eabad-257">Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-257">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="eabad-258">Quando o valor de teste é uma coleção, o operador não Contains usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-258">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="eabad-259">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="eabad-259">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="eabad-260">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="eabad-260">Examples:</span></span>

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

### <a name="-in"></a><span data-ttu-id="eabad-261">-in</span><span class="sxs-lookup"><span data-stu-id="eabad-261">-in</span></span>

<span data-ttu-id="eabad-262">Descrição: no operador.</span><span class="sxs-lookup"><span data-stu-id="eabad-262">Description: In operator.</span></span> <span data-ttu-id="eabad-263">Informa se um valor de teste aparece em uma coleção de valores de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-263">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="eabad-264">Sempre retornar como valor booliano.</span><span class="sxs-lookup"><span data-stu-id="eabad-264">Always return as Boolean value.</span></span> <span data-ttu-id="eabad-265">Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-265">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="eabad-266">Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-266">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="eabad-267">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="eabad-267">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="eabad-268">O `-in` operador foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="eabad-268">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="eabad-269">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="eabad-269">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="eabad-270">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="eabad-270">Examples:</span></span>

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

### <a name="-notin"></a><span data-ttu-id="eabad-271">-notin</span><span class="sxs-lookup"><span data-stu-id="eabad-271">-notin</span></span>

<span data-ttu-id="eabad-272">Descrição: informa se um valor de teste aparece em uma coleção de valores de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-272">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="eabad-273">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="eabad-273">Always returns a Boolean value.</span></span> <span data-ttu-id="eabad-274">Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-274">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="eabad-275">Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="eabad-275">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="eabad-276">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="eabad-276">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="eabad-277">O `-notin` operador foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="eabad-277">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="eabad-278">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="eabad-278">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="eabad-279">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="eabad-279">Examples:</span></span>

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

## <a name="replacement-operator"></a><span data-ttu-id="eabad-280">Operador de substituição</span><span class="sxs-lookup"><span data-stu-id="eabad-280">Replacement Operator</span></span>

<span data-ttu-id="eabad-281">O `-replace` operador tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="eabad-281">The `-replace` operator has the following syntax:</span></span>

`<input> -replace <original>, <substitute>`

<span data-ttu-id="eabad-282">O `<original>` espaço reservado é uma expressão regular que corresponde aos caracteres a serem substituídos.</span><span class="sxs-lookup"><span data-stu-id="eabad-282">The `<original>` placeholder is a regular expression matching the characters to be replaced.</span></span> <span data-ttu-id="eabad-283">O `<substitute>` espaço reservado é uma cadeia de caracteres literal que os substitui.</span><span class="sxs-lookup"><span data-stu-id="eabad-283">The `<substitute>` placeholder is a literal string that replaces them.</span></span>

<span data-ttu-id="eabad-284">O operador substitui todo ou parte de um valor pelo valor especificado usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="eabad-284">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="eabad-285">Você pode usar o operador para muitas tarefas administrativas, como renomear arquivos.</span><span class="sxs-lookup"><span data-stu-id="eabad-285">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="eabad-286">Por exemplo, o comando a seguir altera as extensões de nome de arquivo de todos os `.txt` arquivos para `.log` :</span><span class="sxs-lookup"><span data-stu-id="eabad-286">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

### <a name="case-sensitive-matches"></a><span data-ttu-id="eabad-287">Correspondências diferenciando maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="eabad-287">Case-sensitive matches</span></span>

<span data-ttu-id="eabad-288">Por padrão, o `-replace` operador não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="eabad-288">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="eabad-289">Para torná-lo sensível a maiúsculas e minúsculas, use `-creplace` .</span><span class="sxs-lookup"><span data-stu-id="eabad-289">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="eabad-290">Para torná-lo explicitamente não diferencia maiúsculas de minúsculas, use `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="eabad-290">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="eabad-291">Considere os exemplos a seguir:</span><span class="sxs-lookup"><span data-stu-id="eabad-291">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
Cook
```

```powershell
PS> "book" -ireplace "B", "C"
Cook
```

```powershell
PS> "book" -creplace "B", "C"
book
```

### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="eabad-292">Substituições em expressões regulares</span><span class="sxs-lookup"><span data-stu-id="eabad-292">Substitutions in regular expressions</span></span>

<span data-ttu-id="eabad-293">Também é possível usar expressões regulares para substituir texto dinamicamente usando grupos de captura e substituições.</span><span class="sxs-lookup"><span data-stu-id="eabad-293">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="eabad-294">Os grupos de captura podem ser referenciados na `<substitute>` cadeia de caracteres usando o caractere de cifrão ( `$` ) antes do identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="eabad-294">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="eabad-295">Os grupos de captura podem ser referenciados por **número** ou **nome**</span><span class="sxs-lookup"><span data-stu-id="eabad-295">Capture groups can be referenced by **Number** or **Name**</span></span>

- <span data-ttu-id="eabad-296">Por grupos de captura de **número** , são numerados da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="eabad-296">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  PS> "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="eabad-297">Os grupos de captura de **nomes** também podem ser referenciados pelo nome.</span><span class="sxs-lookup"><span data-stu-id="eabad-297">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  PS> "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  FABRIKAM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="eabad-298">Como o `$` caractere é usado na expansão da cadeia de caracteres, você deve usar as cadeias de caracteres literais ou escapar o `$` caractere.</span><span class="sxs-lookup"><span data-stu-id="eabad-298">Since the `$` character is used in string expansion, you must use literal strings or escape the `$` character.</span></span>
>
> ```powershell
> PS> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> Hello Universe
> ```
>
> <span data-ttu-id="eabad-299">Além disso, como o `$` caractere é usado na substituição, você deve escapar de qualquer instância na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eabad-299">Additionally, since the `$` character is used in substitution, you must escape any instances in your string.</span></span>
>
> ```powershell
> PS> '5.72' -replace '(.+)', '$$$1'
> $5.72
> ```

<span data-ttu-id="eabad-300">Para saber mais, veja [about_Regular_Expressions](about_Regular_Expressions.md) e [substituições em expressões regulares](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span><span class="sxs-lookup"><span data-stu-id="eabad-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="eabad-301">Substituindo em uma coleção</span><span class="sxs-lookup"><span data-stu-id="eabad-301">Substituting in a collection</span></span>

<span data-ttu-id="eabad-302">Quando o `<input>` para o `-replace` operador é uma coleção, o PowerShell aplica a substituição a todos os valores na coleção.</span><span class="sxs-lookup"><span data-stu-id="eabad-302">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="eabad-303">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-303">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

## <a name="type-comparison"></a><span data-ttu-id="eabad-304">Comparação de tipos</span><span class="sxs-lookup"><span data-stu-id="eabad-304">Type comparison</span></span>

<span data-ttu-id="eabad-305">Os operadores de comparação de tipo ( `-is` e `-isnot` ) são usados para determinar se um objeto é um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="eabad-305">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

### <a name="-is"></a><span data-ttu-id="eabad-306">-é</span><span class="sxs-lookup"><span data-stu-id="eabad-306">-is</span></span>

<span data-ttu-id="eabad-307">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="eabad-307">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="eabad-308">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-308">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

### <a name="-isnot"></a><span data-ttu-id="eabad-309">-IsNot</span><span class="sxs-lookup"><span data-stu-id="eabad-309">-isnot</span></span>

<span data-ttu-id="eabad-310">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="eabad-310">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="eabad-311">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="eabad-311">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="eabad-312">Veja também</span><span class="sxs-lookup"><span data-stu-id="eabad-312">See also</span></span>

- [<span data-ttu-id="eabad-313">about_Operators</span><span class="sxs-lookup"><span data-stu-id="eabad-313">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="eabad-314">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="eabad-314">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="eabad-315">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="eabad-315">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="eabad-316">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="eabad-316">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="eabad-317">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="eabad-317">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="eabad-318">Where-Object</span><span class="sxs-lookup"><span data-stu-id="eabad-318">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
