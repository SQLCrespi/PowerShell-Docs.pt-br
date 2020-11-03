---
description: Descreve os operadores que comparam valores no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: b6076e20ad3ecbe9f2def157bb20bdb3bee5b7ad
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196467"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="36310-104">Sobre operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="36310-104">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="36310-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="36310-105">Short description</span></span>
<span data-ttu-id="36310-106">Descreve os operadores que comparam valores no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36310-106">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="36310-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="36310-107">Long description</span></span>

<span data-ttu-id="36310-108">Os operadores de comparação permitem especificar condições para comparar valores e localizar valores que correspondam aos padrões especificados.</span><span class="sxs-lookup"><span data-stu-id="36310-108">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="36310-109">Para usar um operador de comparação, especifique os valores que você deseja comparar junto com um operador que separa esses valores.</span><span class="sxs-lookup"><span data-stu-id="36310-109">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="36310-110">O PowerShell inclui os seguintes operadores de comparação:</span><span class="sxs-lookup"><span data-stu-id="36310-110">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="36310-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="36310-111">Type</span></span>        | <span data-ttu-id="36310-112">Operadores</span><span class="sxs-lookup"><span data-stu-id="36310-112">Operators</span></span>    | <span data-ttu-id="36310-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="36310-113">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="36310-114">Igualitário</span><span class="sxs-lookup"><span data-stu-id="36310-114">Equality</span></span>    | <span data-ttu-id="36310-115">-eq</span><span class="sxs-lookup"><span data-stu-id="36310-115">-eq</span></span>          | <span data-ttu-id="36310-116">igual a</span><span class="sxs-lookup"><span data-stu-id="36310-116">equals</span></span>                                      |
|             | <span data-ttu-id="36310-117">-ne</span><span class="sxs-lookup"><span data-stu-id="36310-117">-ne</span></span>          | <span data-ttu-id="36310-118">Não é igual a</span><span class="sxs-lookup"><span data-stu-id="36310-118">not equals</span></span>                                  |
|             | <span data-ttu-id="36310-119">-gt</span><span class="sxs-lookup"><span data-stu-id="36310-119">-gt</span></span>          | <span data-ttu-id="36310-120">maior que</span><span class="sxs-lookup"><span data-stu-id="36310-120">greater than</span></span>                                |
|             | <span data-ttu-id="36310-121">-ge</span><span class="sxs-lookup"><span data-stu-id="36310-121">-ge</span></span>          | <span data-ttu-id="36310-122">maior ou igual</span><span class="sxs-lookup"><span data-stu-id="36310-122">greater than or equal</span></span>                       |
|             | <span data-ttu-id="36310-123">-lt</span><span class="sxs-lookup"><span data-stu-id="36310-123">-lt</span></span>          | <span data-ttu-id="36310-124">menor que</span><span class="sxs-lookup"><span data-stu-id="36310-124">less than</span></span>                                   |
|             | <span data-ttu-id="36310-125">-le</span><span class="sxs-lookup"><span data-stu-id="36310-125">-le</span></span>          | <span data-ttu-id="36310-126">menor ou igual</span><span class="sxs-lookup"><span data-stu-id="36310-126">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="36310-127">Matching</span><span class="sxs-lookup"><span data-stu-id="36310-127">Matching</span></span>    | <span data-ttu-id="36310-128">-like</span><span class="sxs-lookup"><span data-stu-id="36310-128">-like</span></span>        | <span data-ttu-id="36310-129">Retorna true quando a cadeia de caracteres corresponde ao curinga</span><span class="sxs-lookup"><span data-stu-id="36310-129">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="36310-130">pattern</span><span class="sxs-lookup"><span data-stu-id="36310-130">pattern</span></span>                                     |
|             | <span data-ttu-id="36310-131">-notlike</span><span class="sxs-lookup"><span data-stu-id="36310-131">-notlike</span></span>     | <span data-ttu-id="36310-132">Retorna true quando a cadeia de caracteres não corresponde</span><span class="sxs-lookup"><span data-stu-id="36310-132">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="36310-133">padrão de curinga</span><span class="sxs-lookup"><span data-stu-id="36310-133">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="36310-134">-match</span><span class="sxs-lookup"><span data-stu-id="36310-134">-match</span></span>       | <span data-ttu-id="36310-135">Retorna true quando a cadeia de caracteres corresponde ao Regex</span><span class="sxs-lookup"><span data-stu-id="36310-135">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="36310-136">padrão $matches contém cadeias de caracteres correspondentes</span><span class="sxs-lookup"><span data-stu-id="36310-136">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="36310-137">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="36310-137">-notmatch</span></span>    | <span data-ttu-id="36310-138">Retorna true quando a cadeia de caracteres não corresponde</span><span class="sxs-lookup"><span data-stu-id="36310-138">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="36310-139">padrão Regex; $matches contém correspondência</span><span class="sxs-lookup"><span data-stu-id="36310-139">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="36310-140">cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="36310-140">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="36310-141">Contenção</span><span class="sxs-lookup"><span data-stu-id="36310-141">Containment</span></span> | <span data-ttu-id="36310-142">-contains</span><span class="sxs-lookup"><span data-stu-id="36310-142">-contains</span></span>    | <span data-ttu-id="36310-143">Retorna true quando o valor de referência está contido</span><span class="sxs-lookup"><span data-stu-id="36310-143">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="36310-144">em uma coleção</span><span class="sxs-lookup"><span data-stu-id="36310-144">in a collection</span></span>                             |
|             | <span data-ttu-id="36310-145">-notcontains</span><span class="sxs-lookup"><span data-stu-id="36310-145">-notcontains</span></span> | <span data-ttu-id="36310-146">Retorna true quando o valor de referência não é</span><span class="sxs-lookup"><span data-stu-id="36310-146">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="36310-147">contido em uma coleção</span><span class="sxs-lookup"><span data-stu-id="36310-147">contained in a collection</span></span>                   |
|             | <span data-ttu-id="36310-148">-in</span><span class="sxs-lookup"><span data-stu-id="36310-148">-in</span></span>          | <span data-ttu-id="36310-149">Retorna true quando o valor de teste está contido em um</span><span class="sxs-lookup"><span data-stu-id="36310-149">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="36310-150">collection</span><span class="sxs-lookup"><span data-stu-id="36310-150">collection</span></span>                                  |
|             | <span data-ttu-id="36310-151">-notin</span><span class="sxs-lookup"><span data-stu-id="36310-151">-notin</span></span>       | <span data-ttu-id="36310-152">Retorna true quando o valor de teste não está contido</span><span class="sxs-lookup"><span data-stu-id="36310-152">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="36310-153">em uma coleção</span><span class="sxs-lookup"><span data-stu-id="36310-153">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="36310-154">Substituição</span><span class="sxs-lookup"><span data-stu-id="36310-154">Replacement</span></span> | <span data-ttu-id="36310-155">-substituir</span><span class="sxs-lookup"><span data-stu-id="36310-155">-replace</span></span>     | <span data-ttu-id="36310-156">Substitui um padrão de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="36310-156">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="36310-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="36310-157">Type</span></span>        | <span data-ttu-id="36310-158">-é</span><span class="sxs-lookup"><span data-stu-id="36310-158">-is</span></span>          | <span data-ttu-id="36310-159">Retornará true se ambos os objetos forem iguais</span><span class="sxs-lookup"><span data-stu-id="36310-159">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="36310-160">tipo</span><span class="sxs-lookup"><span data-stu-id="36310-160">type</span></span>                                        |
|             | <span data-ttu-id="36310-161">-IsNot</span><span class="sxs-lookup"><span data-stu-id="36310-161">-isnot</span></span>       | <span data-ttu-id="36310-162">Retornará true se os objetos não forem iguais</span><span class="sxs-lookup"><span data-stu-id="36310-162">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="36310-163">tipo</span><span class="sxs-lookup"><span data-stu-id="36310-163">type</span></span>                                        |

<span data-ttu-id="36310-164">Por padrão, todos os operadores de comparação não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="36310-164">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="36310-165">Para tornar um operador de comparação que diferencia maiúsculas de minúsculas, preceda o nome do operador com um `c` .</span><span class="sxs-lookup"><span data-stu-id="36310-165">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="36310-166">Por exemplo, a versão de diferenciação de maiúsculas e minúsculas do `-eq` é `-ceq` .</span><span class="sxs-lookup"><span data-stu-id="36310-166">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="36310-167">Para tornar a diferenciação de maiúsculas e minúsculas explícita, preceda o operador com um `i` .</span><span class="sxs-lookup"><span data-stu-id="36310-167">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="36310-168">Por exemplo, a versão explicitamente não diferencia maiúsculas de minúsculas de `-eq` é `-ieq` .</span><span class="sxs-lookup"><span data-stu-id="36310-168">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="36310-169">Quando a entrada para um operador é um valor escalar, os operadores de comparação retornam um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="36310-169">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="36310-170">Quando a entrada é uma coleção de valores, os operadores de comparação retornam quaisquer valores correspondentes.</span><span class="sxs-lookup"><span data-stu-id="36310-170">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="36310-171">Se não houver nenhuma correspondência em uma coleção, os operadores de comparação retornarão uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="36310-171">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="36310-172">As exceções são os operadores de confinamento, os operadores in e os operadores de tipo, que sempre retornam um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="36310-172">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="36310-173">Se você precisar comparar um valor para `$null` você deve colocar `$null` no lado esquerdo da comparação.</span><span class="sxs-lookup"><span data-stu-id="36310-173">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="36310-174">Quando você compara `$null` a um **objeto []** , o resultado é **false** porque o objeto de comparação é uma matriz.</span><span class="sxs-lookup"><span data-stu-id="36310-174">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="36310-175">Quando você compara uma matriz com `$null` o, a comparação filtra quaisquer `$null` valores armazenados na matriz.</span><span class="sxs-lookup"><span data-stu-id="36310-175">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="36310-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-176">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a><span data-ttu-id="36310-177">Operadores de igualdade</span><span class="sxs-lookup"><span data-stu-id="36310-177">Equality Operators</span></span>

<span data-ttu-id="36310-178">Os operadores de igualdade ( `-eq` , `-ne` ) retornam um valor de true ou as correspondências quando um ou mais valores de entrada são idênticos ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="36310-178">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="36310-179">O padrão inteiro deve corresponder a um valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="36310-179">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="36310-180">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-180">Example:</span></span>

#### <a name="-eq"></a><span data-ttu-id="36310-181">-eq</span><span class="sxs-lookup"><span data-stu-id="36310-181">-eq</span></span>

<span data-ttu-id="36310-182">Descrição: igual a.</span><span class="sxs-lookup"><span data-stu-id="36310-182">Description: Equal to.</span></span> <span data-ttu-id="36310-183">Inclui um valor idêntico.</span><span class="sxs-lookup"><span data-stu-id="36310-183">Includes an identical value.</span></span>

<span data-ttu-id="36310-184">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-184">Example:</span></span>

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

#### <a name="-ne"></a><span data-ttu-id="36310-185">-ne</span><span class="sxs-lookup"><span data-stu-id="36310-185">-ne</span></span>

<span data-ttu-id="36310-186">Descrição: diferente de.</span><span class="sxs-lookup"><span data-stu-id="36310-186">Description: Not equal to.</span></span> <span data-ttu-id="36310-187">Inclui um valor diferente.</span><span class="sxs-lookup"><span data-stu-id="36310-187">Includes a different value.</span></span>

<span data-ttu-id="36310-188">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-188">Example:</span></span>

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

#### <a name="-gt"></a><span data-ttu-id="36310-189">-gt</span><span class="sxs-lookup"><span data-stu-id="36310-189">-gt</span></span>

<span data-ttu-id="36310-190">Descrição: maior que.</span><span class="sxs-lookup"><span data-stu-id="36310-190">Description: Greater-than.</span></span>

<span data-ttu-id="36310-191">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-191">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="36310-192">Isso não deve ser confundido com `>` o operador maior que em muitas outras linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="36310-192">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="36310-193">No PowerShell, `>` é usado para redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="36310-193">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="36310-194">Para obter mais informações, consulte [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span><span class="sxs-lookup"><span data-stu-id="36310-194">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

#### <a name="-ge"></a><span data-ttu-id="36310-195">-ge</span><span class="sxs-lookup"><span data-stu-id="36310-195">-ge</span></span>

<span data-ttu-id="36310-196">Descrição: maior que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="36310-196">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="36310-197">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-197">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a><span data-ttu-id="36310-198">-lt</span><span class="sxs-lookup"><span data-stu-id="36310-198">-lt</span></span>

<span data-ttu-id="36310-199">Descrição: menor que.</span><span class="sxs-lookup"><span data-stu-id="36310-199">Description: Less-than.</span></span>

<span data-ttu-id="36310-200">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-200">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a><span data-ttu-id="36310-201">-le</span><span class="sxs-lookup"><span data-stu-id="36310-201">-le</span></span>

<span data-ttu-id="36310-202">Descrição: menor que ou igual a.</span><span class="sxs-lookup"><span data-stu-id="36310-202">Description: Less-than or equal to.</span></span>

<span data-ttu-id="36310-203">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-203">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a><span data-ttu-id="36310-204">Operadores correspondentes</span><span class="sxs-lookup"><span data-stu-id="36310-204">Matching Operators</span></span>

<span data-ttu-id="36310-205">Os operadores like ( `-like` e `-notlike` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões curinga.</span><span class="sxs-lookup"><span data-stu-id="36310-205">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="36310-206">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="36310-206">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="36310-207">Os operadores de correspondência ( `-match` e `-notmatch` ) localizam elementos que correspondem ou não correspondem a um padrão especificado usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="36310-207">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="36310-208">Os operadores de correspondência preenchem a `$Matches` variável automática quando a entrada (o argumento do lado esquerdo) para o operador é um único objeto escalar.</span><span class="sxs-lookup"><span data-stu-id="36310-208">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="36310-209">Quando a entrada é escalar, os `-match` `-notmatch` operadores e retornam um valor booliano e definem o valor da `$Matches` variável automática para os componentes correspondentes do argumento.</span><span class="sxs-lookup"><span data-stu-id="36310-209">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="36310-210">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="36310-210">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a><span data-ttu-id="36310-211">-like</span><span class="sxs-lookup"><span data-stu-id="36310-211">-like</span></span>

<span data-ttu-id="36310-212">Descrição: correspondência usando o caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="36310-212">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="36310-213">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-213">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a><span data-ttu-id="36310-214">-notlike</span><span class="sxs-lookup"><span data-stu-id="36310-214">-notlike</span></span>

<span data-ttu-id="36310-215">Descrição: não corresponde usando o caractere curinga ( \* ).</span><span class="sxs-lookup"><span data-stu-id="36310-215">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="36310-216">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-216">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="36310-217">-match</span><span class="sxs-lookup"><span data-stu-id="36310-217">-match</span></span>

<span data-ttu-id="36310-218">Descrição: corresponde a uma cadeia de caracteres usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="36310-218">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="36310-219">Quando a entrada é escalar, ela popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="36310-219">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="36310-220">Se a entrada for uma coleção, os `-match` `-notmatch` operadores e retornarão os membros correspondentes dessa coleção, mas o operador não preencherá a `$Matches` variável.</span><span class="sxs-lookup"><span data-stu-id="36310-220">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="36310-221">Por exemplo, o comando a seguir envia uma coleção de cadeias de caracteres para o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="36310-221">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="36310-222">O `-match` operador retorna os itens na coleção que correspondem.</span><span class="sxs-lookup"><span data-stu-id="36310-222">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="36310-223">Ele não preenche a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="36310-223">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="36310-224">Por outro lado, o comando a seguir envia uma única cadeia de caracteres para o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="36310-224">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="36310-225">O `-match` operador retorna um valor booliano e popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="36310-225">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="36310-226">A `$Matches` variável automática é uma **tabela de hash** .</span><span class="sxs-lookup"><span data-stu-id="36310-226">The `$Matches` automatic variable is a **Hashtable** .</span></span> <span data-ttu-id="36310-227">Se nenhum agrupamento ou captura for usado, apenas uma chave será populada.</span><span class="sxs-lookup"><span data-stu-id="36310-227">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="36310-228">A `0` chave representa todo o texto que foi correspondido.</span><span class="sxs-lookup"><span data-stu-id="36310-228">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="36310-229">Para obter mais informações sobre agrupamento e captura usando expressões regulares, consulte [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="36310-229">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="36310-230">É importante observar que a tabela de `$Matches` hash conterá apenas a primeira ocorrência de qualquer padrão correspondente.</span><span class="sxs-lookup"><span data-stu-id="36310-230">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="36310-231">A `0` chave é um **número inteiro** .</span><span class="sxs-lookup"><span data-stu-id="36310-231">The `0` key is an **Integer** .</span></span> <span data-ttu-id="36310-232">Você pode usar qualquer método de **Hashtable** para acessar o valor armazenado.</span><span class="sxs-lookup"><span data-stu-id="36310-232">You can use any **Hashtable** method to access the value stored.</span></span>
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

<span data-ttu-id="36310-233">O `-notmatch` operador popula a `$Matches` variável automática quando a entrada é escalar e o resultado é false, quando detecta uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="36310-233">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

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

#### <a name="-notmatch"></a><span data-ttu-id="36310-234">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="36310-234">-notmatch</span></span>

<span data-ttu-id="36310-235">Descrição: não corresponde a uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="36310-235">Description: Does not match a string.</span></span> <span data-ttu-id="36310-236">Usa expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="36310-236">Uses regular expressions.</span></span> <span data-ttu-id="36310-237">Quando a entrada é escalar, ela popula a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="36310-237">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="36310-238">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-238">Example:</span></span>

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

### <a name="containment-operators"></a><span data-ttu-id="36310-239">Operadores de confinamento</span><span class="sxs-lookup"><span data-stu-id="36310-239">Containment Operators</span></span>

<span data-ttu-id="36310-240">Os operadores de confinamento ( `-contains` e `-notcontains` ) são semelhantes aos operadores de igualdade.</span><span class="sxs-lookup"><span data-stu-id="36310-240">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="36310-241">No entanto, os operadores de confinamento sempre retornam um valor booliano, mesmo quando a entrada é uma coleção.</span><span class="sxs-lookup"><span data-stu-id="36310-241">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="36310-242">Além disso, ao contrário dos operadores de igualdade, os operadores de confinamento retornam um valor assim que detectam a primeira correspondência.</span><span class="sxs-lookup"><span data-stu-id="36310-242">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="36310-243">Os operadores de igualdade avaliam todas as entradas e retornam todas as correspondências na coleção.</span><span class="sxs-lookup"><span data-stu-id="36310-243">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

#### <a name="-contains"></a><span data-ttu-id="36310-244">-contains</span><span class="sxs-lookup"><span data-stu-id="36310-244">-contains</span></span>

<span data-ttu-id="36310-245">Descrição: operador de contenção.</span><span class="sxs-lookup"><span data-stu-id="36310-245">Description: Containment operator.</span></span> <span data-ttu-id="36310-246">Informa se uma coleção de valores de referência inclui um único valor de teste.</span><span class="sxs-lookup"><span data-stu-id="36310-246">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="36310-247">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="36310-247">Always returns a Boolean value.</span></span> <span data-ttu-id="36310-248">Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-248">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="36310-249">Quando o valor de teste é uma coleção, o operador Contains usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-249">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="36310-250">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="36310-250">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="36310-251">Em uma coleção muito grande, o `-contains` operador retorna resultados mais rapidamente do que o operador igual a.</span><span class="sxs-lookup"><span data-stu-id="36310-251">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="36310-252">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="36310-252">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="36310-253">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="36310-253">Examples:</span></span>

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

#### <a name="-notcontains"></a><span data-ttu-id="36310-254">-notcontains</span><span class="sxs-lookup"><span data-stu-id="36310-254">-notcontains</span></span>

<span data-ttu-id="36310-255">Descrição: operador de contenção.</span><span class="sxs-lookup"><span data-stu-id="36310-255">Description: Containment operator.</span></span> <span data-ttu-id="36310-256">Informa se uma coleção de valores de referência inclui um único valor de teste.</span><span class="sxs-lookup"><span data-stu-id="36310-256">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="36310-257">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="36310-257">Always returns a Boolean value.</span></span> <span data-ttu-id="36310-258">Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-258">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="36310-259">Quando o valor de teste é uma coleção, o operador não Contains usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-259">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="36310-260">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="36310-260">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="36310-261">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="36310-261">Examples:</span></span>

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

#### <a name="-in"></a><span data-ttu-id="36310-262">-in</span><span class="sxs-lookup"><span data-stu-id="36310-262">-in</span></span>

<span data-ttu-id="36310-263">Descrição: no operador.</span><span class="sxs-lookup"><span data-stu-id="36310-263">Description: In operator.</span></span> <span data-ttu-id="36310-264">Informa se um valor de teste aparece em uma coleção de valores de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-264">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="36310-265">Sempre retornar como valor booliano.</span><span class="sxs-lookup"><span data-stu-id="36310-265">Always return as Boolean value.</span></span> <span data-ttu-id="36310-266">Retorna TRUE somente quando o valor de teste corresponde exatamente a pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-266">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="36310-267">Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-267">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="36310-268">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="36310-268">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="36310-269">O `-in` operador foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="36310-269">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="36310-270">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="36310-270">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="36310-271">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="36310-271">Examples:</span></span>

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

#### <a name="-notin"></a><span data-ttu-id="36310-272">-notin</span><span class="sxs-lookup"><span data-stu-id="36310-272">-notin</span></span>

<span data-ttu-id="36310-273">Descrição: informa se um valor de teste aparece em uma coleção de valores de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-273">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="36310-274">Sempre retorna um valor booliano.</span><span class="sxs-lookup"><span data-stu-id="36310-274">Always returns a Boolean value.</span></span> <span data-ttu-id="36310-275">Retorna TRUE quando o valor de teste não é uma correspondência exata para pelo menos um dos valores de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-275">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="36310-276">Quando o valor de teste é uma coleção, o operador in usa a igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="36310-276">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="36310-277">Retorna TRUE somente quando um dos valores de referência é a mesma instância do objeto de valor de teste.</span><span class="sxs-lookup"><span data-stu-id="36310-277">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="36310-278">O `-notin` operador foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="36310-278">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="36310-279">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="36310-279">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="36310-280">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="36310-280">Examples:</span></span>

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

### <a name="replacement-operator"></a><span data-ttu-id="36310-281">Operador de substituição</span><span class="sxs-lookup"><span data-stu-id="36310-281">Replacement Operator</span></span>

<span data-ttu-id="36310-282">O `-replace` operador substitui todo ou parte de um valor pelo valor especificado usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="36310-282">The `-replace` operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="36310-283">Você pode usar o `-replace` operador para muitas tarefas administrativas, como renomear arquivos.</span><span class="sxs-lookup"><span data-stu-id="36310-283">You can use the `-replace` operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="36310-284">Por exemplo, o comando a seguir altera as extensões de nome de arquivo de todos os arquivos. txt para. log:</span><span class="sxs-lookup"><span data-stu-id="36310-284">For example, the following command changes the file name extensions of all .txt files to .log:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="36310-285">A sintaxe do `-replace` operador é a seguinte, em que o `<original>` espaço reservado representa os caracteres a serem substituídos e o `<substitute>` espaço reservado representa os caracteres que os substituirão:</span><span class="sxs-lookup"><span data-stu-id="36310-285">The syntax of the `-replace` operator is as follows, where the `<original>` placeholder represents the characters to be replaced, and the `<substitute>` placeholder represents the characters that will replace them:</span></span>

`<input> <operator> <original>, <substitute>`

<span data-ttu-id="36310-286">Por padrão, o `-replace` operador não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="36310-286">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="36310-287">Para torná-lo sensível a maiúsculas e minúsculas, use `-creplace` .</span><span class="sxs-lookup"><span data-stu-id="36310-287">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="36310-288">Para torná-lo explicitamente não diferencia maiúsculas de minúsculas, use `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="36310-288">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="36310-289">Considere os seguintes exemplos:</span><span class="sxs-lookup"><span data-stu-id="36310-289">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

<span data-ttu-id="36310-290">Também é possível usar expressões regulares para substituir texto dinamicamente usando grupos de captura e substituições.</span><span class="sxs-lookup"><span data-stu-id="36310-290">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="36310-291">Para obter mais informações, consulte [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="36310-291">For more information, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="36310-292">Substituições em expressões regulares</span><span class="sxs-lookup"><span data-stu-id="36310-292">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="36310-293">Além disso, os grupos de captura podem ser referenciados na \<substitute\> cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="36310-293">Additionally, capturing groups can be referenced in the \<substitute\> string.</span></span>
<span data-ttu-id="36310-294">Isso é feito usando o `$` caractere antes do identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="36310-294">This is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="36310-295">Duas das maneiras de fazer referência a grupos de captura é por **número** e por **nome**</span><span class="sxs-lookup"><span data-stu-id="36310-295">Two of the ways to reference capturing groups is by **Number** and by **Name**</span></span>

- <span data-ttu-id="36310-296">Por **número** , os -
   grupos de captura são numerados da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="36310-296">By **Number** -
Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="36310-297">Os grupos de captura de **nomes** -
   também podem ser referenciados pelo nome.</span><span class="sxs-lookup"><span data-stu-id="36310-297">By **Name** -
Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKOM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="36310-298">Como o `$` caractere é usado na expansão da cadeia de caracteres, você precisará usar cadeias literais com substituição ou escapar o `$` caractere.</span><span class="sxs-lookup"><span data-stu-id="36310-298">Since the `$` character is used in string expansion, you will need to use literal strings with substitution, or escape the `$` character.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> ```
>
> <span data-ttu-id="36310-299">Além disso, como o `$` caractere é usado na substituição, você precisará escapar de qualquer instância na cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="36310-299">Additionally, since the `$` character is used in substitution, you will need to escape any instances in your string.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> ```
>
> ```Output
> $5.72
> ```

<span data-ttu-id="36310-300">Para saber mais, veja [about_Regular_Expressions](about_Regular_Expressions.md) e [substituições em expressões regulares](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span><span class="sxs-lookup"><span data-stu-id="36310-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="type-comparison"></a><span data-ttu-id="36310-301">Comparação de tipos</span><span class="sxs-lookup"><span data-stu-id="36310-301">Type comparison</span></span>

<span data-ttu-id="36310-302">Os operadores de comparação de tipo ( `-is` e `-isnot` ) são usados para determinar se um objeto é um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="36310-302">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

#### <a name="-is"></a><span data-ttu-id="36310-303">-é</span><span class="sxs-lookup"><span data-stu-id="36310-303">-is</span></span>

<span data-ttu-id="36310-304">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="36310-304">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="36310-305">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-305">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a><span data-ttu-id="36310-306">-IsNot</span><span class="sxs-lookup"><span data-stu-id="36310-306">-isnot</span></span>

<span data-ttu-id="36310-307">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="36310-307">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="36310-308">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36310-308">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="36310-309">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="36310-309">SEE ALSO</span></span>

- [<span data-ttu-id="36310-310">about_Operators</span><span class="sxs-lookup"><span data-stu-id="36310-310">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="36310-311">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="36310-311">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="36310-312">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="36310-312">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="36310-313">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="36310-313">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="36310-314">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="36310-314">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="36310-315">Where-Object</span><span class="sxs-lookup"><span data-stu-id="36310-315">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
