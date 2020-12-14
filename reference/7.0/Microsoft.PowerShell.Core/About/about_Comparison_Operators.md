---
description: Descreve os operadores que comparam valores no PowerShell.
Locale: en-US
ms.date: 12/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: dbda5371224345a2e22dd281c17ae0d7c928aad6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97090219"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="01e93-103">Sobre operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="01e93-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="01e93-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="01e93-104">Short description</span></span>
<span data-ttu-id="01e93-105">Descreve os operadores que comparam valores no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01e93-105">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="01e93-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="01e93-106">Long description</span></span>

<span data-ttu-id="01e93-107">Os operadores de comparação permitem especificar condições para comparar valores e localizar valores que correspondam aos padrões especificados.</span><span class="sxs-lookup"><span data-stu-id="01e93-107">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="01e93-108">Para usar um operador de comparação, especifique os valores que você deseja comparar junto com um operador que separa esses valores.</span><span class="sxs-lookup"><span data-stu-id="01e93-108">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="01e93-109">O PowerShell inclui os seguintes operadores de comparação:</span><span class="sxs-lookup"><span data-stu-id="01e93-109">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="01e93-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="01e93-110">Type</span></span>        | <span data-ttu-id="01e93-111">Operadores</span><span class="sxs-lookup"><span data-stu-id="01e93-111">Operators</span></span>    | <span data-ttu-id="01e93-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="01e93-112">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="01e93-113">Igualitário</span><span class="sxs-lookup"><span data-stu-id="01e93-113">Equality</span></span>    | <span data-ttu-id="01e93-114">-eq</span><span class="sxs-lookup"><span data-stu-id="01e93-114">-eq</span></span>          | <span data-ttu-id="01e93-115">equals</span><span class="sxs-lookup"><span data-stu-id="01e93-115">equals</span></span>                                      |
|             | <span data-ttu-id="01e93-116">-ne</span><span class="sxs-lookup"><span data-stu-id="01e93-116">-ne</span></span>          | <span data-ttu-id="01e93-117">Não é igual a</span><span class="sxs-lookup"><span data-stu-id="01e93-117">not equals</span></span>                                  |
|             | <span data-ttu-id="01e93-118">-gt</span><span class="sxs-lookup"><span data-stu-id="01e93-118">-gt</span></span>          | <span data-ttu-id="01e93-119">maior que</span><span class="sxs-lookup"><span data-stu-id="01e93-119">greater than</span></span>                                |
|             | <span data-ttu-id="01e93-120">-ge</span><span class="sxs-lookup"><span data-stu-id="01e93-120">-ge</span></span>          | <span data-ttu-id="01e93-121">maior ou igual</span><span class="sxs-lookup"><span data-stu-id="01e93-121">greater than or equal</span></span>                       |
|             | <span data-ttu-id="01e93-122">-lt</span><span class="sxs-lookup"><span data-stu-id="01e93-122">-lt</span></span>          | <span data-ttu-id="01e93-123">menor que</span><span class="sxs-lookup"><span data-stu-id="01e93-123">less than</span></span>                                   |
|             | <span data-ttu-id="01e93-124">-le</span><span class="sxs-lookup"><span data-stu-id="01e93-124">-le</span></span>          | <span data-ttu-id="01e93-125">menor ou igual</span><span class="sxs-lookup"><span data-stu-id="01e93-125">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="01e93-126">Matching</span><span class="sxs-lookup"><span data-stu-id="01e93-126">Matching</span></span>    | <span data-ttu-id="01e93-127">-like</span><span class="sxs-lookup"><span data-stu-id="01e93-127">-like</span></span>        | <span data-ttu-id="01e93-128">Retorna true quando a cadeia de caracteres corresponde ao curinga</span><span class="sxs-lookup"><span data-stu-id="01e93-128">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="01e93-129">pattern</span><span class="sxs-lookup"><span data-stu-id="01e93-129">pattern</span></span>                                     |
|             | <span data-ttu-id="01e93-130">-notlike</span><span class="sxs-lookup"><span data-stu-id="01e93-130">-notlike</span></span>     | <span data-ttu-id="01e93-131">Retorna true quando a cadeia de caracteres não corresponde</span><span class="sxs-lookup"><span data-stu-id="01e93-131">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="01e93-132">padrão de curinga</span><span class="sxs-lookup"><span data-stu-id="01e93-132">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="01e93-133">-match</span><span class="sxs-lookup"><span data-stu-id="01e93-133">-match</span></span>       | <span data-ttu-id="01e93-134">Retorna true quando a cadeia de caracteres corresponde ao Regex</span><span class="sxs-lookup"><span data-stu-id="01e93-134">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="01e93-135">padrão $matches contém cadeias de caracteres correspondentes</span><span class="sxs-lookup"><span data-stu-id="01e93-135">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="01e93-136">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="01e93-136">-notmatch</span></span>    | <span data-ttu-id="01e93-137">Retorna true quando a cadeia de caracteres não corresponde</span><span class="sxs-lookup"><span data-stu-id="01e93-137">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="01e93-138">padrão Regex; $matches contém correspondência</span><span class="sxs-lookup"><span data-stu-id="01e93-138">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="01e93-139">cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e93-139">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="01e93-140">Contenção</span><span class="sxs-lookup"><span data-stu-id="01e93-140">Containment</span></span> | <span data-ttu-id="01e93-141">-contains</span><span class="sxs-lookup"><span data-stu-id="01e93-141">-contains</span></span>    | <span data-ttu-id="01e93-142">Retorna true quando o valor de referência está contido</span><span class="sxs-lookup"><span data-stu-id="01e93-142">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="01e93-143">em uma coleção</span><span class="sxs-lookup"><span data-stu-id="01e93-143">in a collection</span></span>                             |
|             | <span data-ttu-id="01e93-144">-notcontains</span><span class="sxs-lookup"><span data-stu-id="01e93-144">-notcontains</span></span> | <span data-ttu-id="01e93-145">Retorna true quando o valor de referência não é</span><span class="sxs-lookup"><span data-stu-id="01e93-145">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="01e93-146">contido em uma coleção</span><span class="sxs-lookup"><span data-stu-id="01e93-146">contained in a collection</span></span>                   |
|             | <span data-ttu-id="01e93-147">-in</span><span class="sxs-lookup"><span data-stu-id="01e93-147">-in</span></span>          | <span data-ttu-id="01e93-148">Retorna true quando o valor de teste está contido em um</span><span class="sxs-lookup"><span data-stu-id="01e93-148">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="01e93-149">collection</span><span class="sxs-lookup"><span data-stu-id="01e93-149">collection</span></span>                                  |
|             | <span data-ttu-id="01e93-150">-notin</span><span class="sxs-lookup"><span data-stu-id="01e93-150">-notin</span></span>       | <span data-ttu-id="01e93-151">Retorna true quando o valor de teste não está contido</span><span class="sxs-lookup"><span data-stu-id="01e93-151">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="01e93-152">em uma coleção</span><span class="sxs-lookup"><span data-stu-id="01e93-152">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="01e93-153">Substituição</span><span class="sxs-lookup"><span data-stu-id="01e93-153">Replacement</span></span> | <span data-ttu-id="01e93-154">-substituir</span><span class="sxs-lookup"><span data-stu-id="01e93-154">-replace</span></span>     | <span data-ttu-id="01e93-155">Substitui um padrão de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e93-155">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="01e93-156">Tipo</span><span class="sxs-lookup"><span data-stu-id="01e93-156">Type</span></span>        | <span data-ttu-id="01e93-157">-é</span><span class="sxs-lookup"><span data-stu-id="01e93-157">-is</span></span>          | <span data-ttu-id="01e93-158">Retornará true se ambos os objetos forem iguais</span><span class="sxs-lookup"><span data-stu-id="01e93-158">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="01e93-159">tipo</span><span class="sxs-lookup"><span data-stu-id="01e93-159">type</span></span>                                        |
|             | <span data-ttu-id="01e93-160">-IsNot</span><span class="sxs-lookup"><span data-stu-id="01e93-160">-isnot</span></span>       | <span data-ttu-id="01e93-161">Retornará true se os objetos não forem iguais</span><span class="sxs-lookup"><span data-stu-id="01e93-161">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="01e93-162">tipo</span><span class="sxs-lookup"><span data-stu-id="01e93-162">type</span></span>                                        |

<span data-ttu-id="01e93-163">Por padrão, todos os operadores de comparação não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="01e93-163">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="01e93-164">Para tornar um operador de comparação que diferencia maiúsculas de minúsculas, preceda o nome do operador com um `c` .</span><span class="sxs-lookup"><span data-stu-id="01e93-164">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="01e93-165">Por exemplo, a versão de diferenciação de maiúsculas e minúsculas do `-eq` é `-ceq` .</span><span class="sxs-lookup"><span data-stu-id="01e93-165">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="01e93-166">Para tornar a diferenciação de maiúsculas e minúsculas explícita, preceda o operador com um `i` .</span><span class="sxs-lookup"><span data-stu-id="01e93-166">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="01e93-167">Por exemplo, a versão explicitamente não diferencia maiúsculas de minúsculas de `-eq` é `-ieq` .</span><span class="sxs-lookup"><span data-stu-id="01e93-167">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="01e93-168">Quando a entrada para um operador é um valor escalar, os operadores de comparação retornam um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="01e93-168">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="01e93-169">Quando a entrada é uma coleção de valores, os operadores de comparação retornam quaisquer valores correspondentes.</span><span class="sxs-lookup"><span data-stu-id="01e93-169">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="01e93-170">Se não houver nenhuma correspondência em uma coleção, os operadores de comparação retornarão uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="01e93-170">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="01e93-171">As exceções são os operadores de confinamento, os operadores in e os operadores de tipo, que sempre retornam um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="01e93-171">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="01e93-172">Se você precisar comparar um valor para `$null` você deve colocar `$null` no lado esquerdo da comparação.</span><span class="sxs-lookup"><span data-stu-id="01e93-172">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="01e93-173">Quando você compara `$null` a um **objeto []** , o resultado é **false** porque o objeto de comparação é uma matriz.</span><span class="sxs-lookup"><span data-stu-id="01e93-173">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="01e93-174">Quando você compara uma matriz com `$null` o, a comparação filtra quaisquer `$null` valores armazenados na matriz.</span><span class="sxs-lookup"><span data-stu-id="01e93-174">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="01e93-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-175">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

## <a name="equality-operators"></a><span data-ttu-id="01e93-176">Operadores de igualdade</span><span class="sxs-lookup"><span data-stu-id="01e93-176">Equality operators</span></span>

<span data-ttu-id="01e93-177">Os operadores de igualdade ( `-eq` , `-ne` ) retornam um valor de true ou as correspondências quando um ou mais valores de entrada são idênticos ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="01e93-177">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="01e93-178">O padrão inteiro deve corresponder a um valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="01e93-178">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="01e93-179">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-179">Example:</span></span>

### <a name="-eq"></a><span data-ttu-id="01e93-180">-eq</span><span class="sxs-lookup"><span data-stu-id="01e93-180">-eq</span></span>

<span data-ttu-id="01e93-181">Descrição: igual a.</span><span class="sxs-lookup"><span data-stu-id="01e93-181">Description: Equal to.</span></span> <span data-ttu-id="01e93-182">Inclui um valor idêntico.</span><span class="sxs-lookup"><span data-stu-id="01e93-182">Includes an identical value.</span></span>

<span data-ttu-id="01e93-183">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-183">Example:</span></span>

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

### <a name="-ne"></a><span data-ttu-id="01e93-184">-ne</span><span class="sxs-lookup"><span data-stu-id="01e93-184">-ne</span></span>

<span data-ttu-id="01e93-185">Descrição: diferente de.</span><span class="sxs-lookup"><span data-stu-id="01e93-185">Description: Not equal to.</span></span> <span data-ttu-id="01e93-186">Inclui um valor diferente.</span><span class="sxs-lookup"><span data-stu-id="01e93-186">Includes a different value.</span></span>

<span data-ttu-id="01e93-187">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-187">Example:</span></span>

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

### <a name="-gt"></a><span data-ttu-id="01e93-188">-gt</span><span class="sxs-lookup"><span data-stu-id="01e93-188">-gt</span></span>

<span data-ttu-id="01e93-189">Descrição: maior que.</span><span class="sxs-lookup"><span data-stu-id="01e93-189">Description: Greater-than.</span></span>

<span data-ttu-id="01e93-190">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-190">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="01e93-191">Isso não deve ser confundido com `>` o operador maior que em muitas outras linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="01e93-191">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="01e93-192">No PowerShell, `>` é usado para redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="01e93-192">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="01e93-193">Para obter mais informações, consulte [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span><span class="sxs-lookup"><span data-stu-id="01e93-193">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

### <a name="-ge"></a><span data-ttu-id="01e93-194">-ge</span><span class="sxs-lookup"><span data-stu-id="01e93-194">-ge</span></span>

<span data-ttu-id="01e93-195">Descrição: maior que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="01e93-195">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="01e93-196">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-196">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

### <a name="-lt"></a><span data-ttu-id="01e93-197">-lt</span><span class="sxs-lookup"><span data-stu-id="01e93-197">-lt</span></span>

<span data-ttu-id="01e93-198">Descrição: menor que.</span><span class="sxs-lookup"><span data-stu-id="01e93-198">Description: Less-than.</span></span>

<span data-ttu-id="01e93-199">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-199">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

### <a name="-le"></a><span data-ttu-id="01e93-200">-le</span><span class="sxs-lookup"><span data-stu-id="01e93-200">-le</span></span>

<span data-ttu-id="01e93-201">Descrição: menor que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="01e93-201">Description: Less-than or equal to.</span></span>

<span data-ttu-id="01e93-202">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-202">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

## <a name="matching-operators"></a><span data-ttu-id="01e93-203">Operadores correspondentes</span><span class="sxs-lookup"><span data-stu-id="01e93-203">Matching operators</span></span>

<span data-ttu-id="01e93-204">Os operadores like ( `-like` e `-notlike` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões curinga.</span><span class="sxs-lookup"><span data-stu-id="01e93-204">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="01e93-205">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="01e93-205">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="01e93-206">Os operadores de correspondência ( `-match` e `-notmatch` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="01e93-206">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="01e93-207">Os operadores de correspondência preenchem a `$Matches` variável automática quando a entrada (o argumento do lado esquerdo) para o operador é um único objeto escalar.</span><span class="sxs-lookup"><span data-stu-id="01e93-207">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="01e93-208">Quando a entrada é escalar, os `-match` `-notmatch` operadores e retornam um valor booliano e definem o valor da `$Matches` variável automática para os componentes correspondentes do argumento.</span><span class="sxs-lookup"><span data-stu-id="01e93-208">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="01e93-209">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="01e93-209">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

### <a name="-like"></a><span data-ttu-id="01e93-210">-like</span><span class="sxs-lookup"><span data-stu-id="01e93-210">-like</span></span>

<span data-ttu-id="01e93-211">Descrição: correspondência usando o caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="01e93-211">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="01e93-212">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-212">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

### <a name="-notlike"></a><span data-ttu-id="01e93-213">-notlike</span><span class="sxs-lookup"><span data-stu-id="01e93-213">-notlike</span></span>

<span data-ttu-id="01e93-214">Descrição: não corresponde usando o caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="01e93-214">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="01e93-215">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-215">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="01e93-216">-match</span><span class="sxs-lookup"><span data-stu-id="01e93-216">-match</span></span>

<span data-ttu-id="01e93-217">Descrição: corresponde a uma cadeia de caracteres usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="01e93-217">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="01e93-218">Quando a entrada é escalar, ela popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="01e93-218">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="01e93-219">Se a entrada for uma coleção, os `-match` `-notmatch` operadores e retornarão os membros correspondentes dessa coleção, mas o operador não preencherá a `$Matches` variável.</span><span class="sxs-lookup"><span data-stu-id="01e93-219">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="01e93-220">Por exemplo, o comando a seguir envia uma coleção de cadeias de caracteres para o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="01e93-220">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="01e93-221">O `-match` operador retorna os itens na coleção que correspondem.</span><span class="sxs-lookup"><span data-stu-id="01e93-221">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="01e93-222">Ele não preenche a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="01e93-222">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="01e93-223">Por outro lado, o comando a seguir envia uma única cadeia de caracteres para o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="01e93-223">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="01e93-224">O `-match` operador retorna um valor booliano e popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="01e93-224">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="01e93-225">A `$Matches` variável automática é uma **tabela de hash**.</span><span class="sxs-lookup"><span data-stu-id="01e93-225">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="01e93-226">Se nenhum agrupamento ou captura for usado, apenas uma chave será populada.</span><span class="sxs-lookup"><span data-stu-id="01e93-226">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="01e93-227">A `0` chave representa todo o texto que foi correspondido.</span><span class="sxs-lookup"><span data-stu-id="01e93-227">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="01e93-228">Para obter mais informações sobre agrupamento e captura usando expressões regulares, consulte [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="01e93-228">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="01e93-229">É importante observar que a tabela de `$Matches` hash conterá apenas a primeira ocorrência de qualquer padrão correspondente.</span><span class="sxs-lookup"><span data-stu-id="01e93-229">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="01e93-230">A `0` chave é um **número inteiro**.</span><span class="sxs-lookup"><span data-stu-id="01e93-230">The `0` key is an **Integer**.</span></span> <span data-ttu-id="01e93-231">Você pode usar qualquer método de **Hashtable** para acessar o valor armazenado.</span><span class="sxs-lookup"><span data-stu-id="01e93-231">You can use any **Hashtable** method to access the value stored.</span></span>
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

<span data-ttu-id="01e93-232">O `-notmatch` operador popula a `$Matches` variável automática quando a entrada é escalar e o resultado é false, quando detecta uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="01e93-232">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

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

### <a name="-notmatch"></a><span data-ttu-id="01e93-233">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="01e93-233">-notmatch</span></span>

<span data-ttu-id="01e93-234">Descrição: não corresponde a uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="01e93-234">Description: Does not match a string.</span></span> <span data-ttu-id="01e93-235">Usa expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="01e93-235">Uses regular expressions.</span></span> <span data-ttu-id="01e93-236">Quando a entrada é escalar, ela popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="01e93-236">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="01e93-237">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-237">Example:</span></span>

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

## <a name="containment-operators"></a><span data-ttu-id="01e93-238">Operadores de confinamento</span><span class="sxs-lookup"><span data-stu-id="01e93-238">Containment operators</span></span>

<span data-ttu-id="01e93-239">Os operadores de confinamento ( `-contains` e `-notcontains` ) são semelhantes aos operadores de igualdade.</span><span class="sxs-lookup"><span data-stu-id="01e93-239">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="01e93-240">No entanto, os operadores de confinamento sempre retornam um valor booliano, mesmo quando a entrada é uma coleção.</span><span class="sxs-lookup"><span data-stu-id="01e93-240">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="01e93-241">Além disso, ao contrário dos operadores de igualdade, os operadores de confinamento retornam um valor assim que detectam a primeira correspondência.</span><span class="sxs-lookup"><span data-stu-id="01e93-241">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="01e93-242">Os operadores de igualdade avaliam todas as entradas e retornam todas as correspondências na coleção.</span><span class="sxs-lookup"><span data-stu-id="01e93-242">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

### <a name="-contains"></a><span data-ttu-id="01e93-243">-contains</span><span class="sxs-lookup"><span data-stu-id="01e93-243">-contains</span></span>

<span data-ttu-id="01e93-244">Descrição: operador de contenção.</span><span class="sxs-lookup"><span data-stu-id="01e93-244">Description: Containment operator.</span></span> <span data-ttu-id="01e93-245">Informa se uma coleção de valores de referência inclui um único valor de teste.</span><span class="sxs-lookup"><span data-stu-id="01e93-245">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="01e93-246">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="01e93-246">Always returns a Boolean value.</span></span> <span data-ttu-id="01e93-247">Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-247">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="01e93-248">Quando o valor de teste é uma coleção, o operador Contains usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-248">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="01e93-249">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="01e93-249">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="01e93-250">Em uma coleção muito grande, o `-contains` operador retorna resultados mais rapidamente do que o operador igual a.</span><span class="sxs-lookup"><span data-stu-id="01e93-250">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="01e93-251">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01e93-251">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="01e93-252">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="01e93-252">Examples:</span></span>

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

### <a name="-notcontains"></a><span data-ttu-id="01e93-253">-notcontains</span><span class="sxs-lookup"><span data-stu-id="01e93-253">-notcontains</span></span>

<span data-ttu-id="01e93-254">Descrição: operador de contenção.</span><span class="sxs-lookup"><span data-stu-id="01e93-254">Description: Containment operator.</span></span> <span data-ttu-id="01e93-255">Informa se uma coleção de valores de referência inclui um único valor de teste.</span><span class="sxs-lookup"><span data-stu-id="01e93-255">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="01e93-256">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="01e93-256">Always returns a Boolean value.</span></span> <span data-ttu-id="01e93-257">Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-257">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="01e93-258">Quando o valor de teste é uma coleção, o operador não Contains usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-258">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="01e93-259">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01e93-259">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="01e93-260">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="01e93-260">Examples:</span></span>

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

### <a name="-in"></a><span data-ttu-id="01e93-261">-in</span><span class="sxs-lookup"><span data-stu-id="01e93-261">-in</span></span>

<span data-ttu-id="01e93-262">Descrição: no operador.</span><span class="sxs-lookup"><span data-stu-id="01e93-262">Description: In operator.</span></span> <span data-ttu-id="01e93-263">Informa se um valor de teste aparece em uma coleção de valores de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-263">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="01e93-264">Sempre retornar como valor booliano.</span><span class="sxs-lookup"><span data-stu-id="01e93-264">Always return as Boolean value.</span></span> <span data-ttu-id="01e93-265">Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-265">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="01e93-266">Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-266">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="01e93-267">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="01e93-267">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="01e93-268">O `-in` operador foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="01e93-268">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="01e93-269">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01e93-269">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="01e93-270">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="01e93-270">Examples:</span></span>

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

### <a name="-notin"></a><span data-ttu-id="01e93-271">-notin</span><span class="sxs-lookup"><span data-stu-id="01e93-271">-notin</span></span>

<span data-ttu-id="01e93-272">Descrição: informa se um valor de teste aparece em uma coleção de valores de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-272">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="01e93-273">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="01e93-273">Always returns a Boolean value.</span></span> <span data-ttu-id="01e93-274">Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-274">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="01e93-275">Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="01e93-275">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="01e93-276">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="01e93-276">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="01e93-277">O `-notin` operador foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="01e93-277">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="01e93-278">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01e93-278">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="01e93-279">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="01e93-279">Examples:</span></span>

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

## <a name="replacement-operator"></a><span data-ttu-id="01e93-280">Operador de substituição</span><span class="sxs-lookup"><span data-stu-id="01e93-280">Replacement Operator</span></span>

<span data-ttu-id="01e93-281">O `-replace` operador tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01e93-281">The `-replace` operator has the following syntax:</span></span>

`<input> -replace <original>, <substitute>`

<span data-ttu-id="01e93-282">O `<original>` espaço reservado é uma expressão regular que corresponde aos caracteres a serem substituídos.</span><span class="sxs-lookup"><span data-stu-id="01e93-282">The `<original>` placeholder is a regular expression matching the characters to be replaced.</span></span> <span data-ttu-id="01e93-283">O `<substitute>` espaço reservado é uma cadeia de caracteres literal que os substitui.</span><span class="sxs-lookup"><span data-stu-id="01e93-283">The `<substitute>` placeholder is a literal string that replaces them.</span></span>

<span data-ttu-id="01e93-284">O operador substitui todo ou parte de um valor pelo valor especificado usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="01e93-284">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="01e93-285">Você pode usar o operador para muitas tarefas administrativas, como renomear arquivos.</span><span class="sxs-lookup"><span data-stu-id="01e93-285">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="01e93-286">Por exemplo, o comando a seguir altera as extensões de nome de arquivo de todos os `.txt` arquivos para `.log` :</span><span class="sxs-lookup"><span data-stu-id="01e93-286">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

### <a name="case-sensitive-matches"></a><span data-ttu-id="01e93-287">Correspondências diferenciando maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="01e93-287">Case-sensitive matches</span></span>

<span data-ttu-id="01e93-288">Por padrão, o `-replace` operador não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="01e93-288">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="01e93-289">Para torná-lo sensível a maiúsculas e minúsculas, use `-creplace` .</span><span class="sxs-lookup"><span data-stu-id="01e93-289">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="01e93-290">Para torná-lo explicitamente não diferencia maiúsculas de minúsculas, use `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="01e93-290">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="01e93-291">Considere os exemplos a seguir:</span><span class="sxs-lookup"><span data-stu-id="01e93-291">Consider the following examples:</span></span>

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

### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="01e93-292">Substituições em expressões regulares</span><span class="sxs-lookup"><span data-stu-id="01e93-292">Substitutions in regular expressions</span></span>

<span data-ttu-id="01e93-293">Também é possível usar expressões regulares para substituir texto dinamicamente usando grupos de captura e substituições.</span><span class="sxs-lookup"><span data-stu-id="01e93-293">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="01e93-294">Os grupos de captura podem ser referenciados na `<substitute>` cadeia de caracteres usando o caractere de cifrão ( `$` ) antes do identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="01e93-294">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="01e93-295">Os grupos de captura podem ser referenciados por **número** ou **nome**</span><span class="sxs-lookup"><span data-stu-id="01e93-295">Capture groups can be referenced by **Number** or **Name**</span></span>

- <span data-ttu-id="01e93-296">Por grupos de captura de **número** , são numerados da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="01e93-296">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  PS> "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="01e93-297">Os grupos de captura de **nomes** também podem ser referenciados pelo nome.</span><span class="sxs-lookup"><span data-stu-id="01e93-297">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  PS> "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  FABRIKAM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="01e93-298">Como o `$` caractere é usado na expansão da cadeia de caracteres, você deverá usar as cadeias de caracteres literais ou escapar o `$` caractere.</span><span class="sxs-lookup"><span data-stu-id="01e93-298">Since the `$` character is used in string expansion, you will must use literal strings or escape the `$` character.</span></span>
>
> ```powershell
> PS> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> Hello Universe
> ```
>
> <span data-ttu-id="01e93-299">Além disso, como o `$` caractere é usado na substituição, você deve escapar de qualquer instância na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="01e93-299">Additionally, since the `$` character is used in substitution, you must escape any instances in your string.</span></span>
>
> ```powershell
> PS> '5.72' -replace '(.+)', '$$$1'
> $5.72
> ```

<span data-ttu-id="01e93-300">Para saber mais, veja [about_Regular_Expressions](about_Regular_Expressions.md) e [substituições em expressões regulares](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span><span class="sxs-lookup"><span data-stu-id="01e93-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="01e93-301">Substituindo em uma coleção</span><span class="sxs-lookup"><span data-stu-id="01e93-301">Substituting in a collection</span></span>

<span data-ttu-id="01e93-302">Quando o `<input>` para o `-replace` operador é uma coleção, o PowerShell aplica a substituição a todos os valores na coleção.</span><span class="sxs-lookup"><span data-stu-id="01e93-302">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="01e93-303">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-303">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="scriptblock-substitutions"></a><span data-ttu-id="01e93-304">Substituições de ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="01e93-304">ScriptBlock substitutions</span></span>

<span data-ttu-id="01e93-305">A partir do PowerShell 6, você pode usar um argumento **scriptblock** para o texto de _substituição_ .</span><span class="sxs-lookup"><span data-stu-id="01e93-305">Beginning in PowerShell 6, you can use a **ScriptBlock** argument for the _Substitution_ text.</span></span> <span data-ttu-id="01e93-306">O **scriptblock** será executado para cada correspondência encontrada na cadeia de caracteres de _entrada_ .</span><span class="sxs-lookup"><span data-stu-id="01e93-306">The **ScriptBlock** will execute for each match found in the _input_ string.</span></span>

<span data-ttu-id="01e93-307">Dentro do **scriptblock**, use a `$_` variável automática para fazer referência ao objeto **System. Text. RegularExpressions. Match** atual.</span><span class="sxs-lookup"><span data-stu-id="01e93-307">Within the **ScriptBlock**, use the `$_` automatic variable to refer to the current **System.Text.RegularExpressions.Match** object.</span></span> <span data-ttu-id="01e93-308">O objeto **Match** fornece acesso ao texto de entrada atual que está sendo substituído, bem como outras informações úteis.</span><span class="sxs-lookup"><span data-stu-id="01e93-308">The **Match** object gives you access to the current input text being replaced, as well as other useful information.</span></span>

<span data-ttu-id="01e93-309">Este exemplo substitui cada sequência de três decimais pelo caractere equivalente.</span><span class="sxs-lookup"><span data-stu-id="01e93-309">This example replaces each sequence of three decimals with the character equivalent.</span></span> <span data-ttu-id="01e93-310">O **scriptblock** é executado para cada conjunto de três decimais que precisa ser substituído.</span><span class="sxs-lookup"><span data-stu-id="01e93-310">The **ScriptBlock** is run for each set of three decimals that needs to be replaced.</span></span>

```powershell
PS> "072101108108111" -replace "\d{3}", {[char][int]$_.Value}
Hello
```

## <a name="type-comparison"></a><span data-ttu-id="01e93-311">Comparação de tipos</span><span class="sxs-lookup"><span data-stu-id="01e93-311">Type comparison</span></span>

<span data-ttu-id="01e93-312">Os operadores de comparação de tipo ( `-is` e `-isnot` ) são usados para determinar se um objeto é um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="01e93-312">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

### <a name="-is"></a><span data-ttu-id="01e93-313">-é</span><span class="sxs-lookup"><span data-stu-id="01e93-313">-is</span></span>

<span data-ttu-id="01e93-314">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01e93-314">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="01e93-315">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-315">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

### <a name="-isnot"></a><span data-ttu-id="01e93-316">-IsNot</span><span class="sxs-lookup"><span data-stu-id="01e93-316">-isnot</span></span>

<span data-ttu-id="01e93-317">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="01e93-317">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="01e93-318">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="01e93-318">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="01e93-319">Veja também</span><span class="sxs-lookup"><span data-stu-id="01e93-319">See also</span></span>

- [<span data-ttu-id="01e93-320">about_Operators</span><span class="sxs-lookup"><span data-stu-id="01e93-320">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="01e93-321">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="01e93-321">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="01e93-322">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="01e93-322">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="01e93-323">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="01e93-323">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="01e93-324">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="01e93-324">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="01e93-325">Where-Object</span><span class="sxs-lookup"><span data-stu-id="01e93-325">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
