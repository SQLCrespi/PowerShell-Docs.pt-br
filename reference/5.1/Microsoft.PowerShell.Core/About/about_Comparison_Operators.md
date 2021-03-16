---
description: Descreve os operadores que comparam valores no PowerShell.
Locale: en-US
ms.date: 03/15/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: ec8ce1a241676911795e76f0934d40fd8ad18bd8
ms.sourcegitcommit: 080c8b05a1242348c365fe1684457e873325f11e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103483395"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="f0e56-103">Sobre operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="f0e56-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="f0e56-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f0e56-104">Short description</span></span>

<span data-ttu-id="f0e56-105">Os operadores de comparação no PowerShell podem comparar dois valores ou filtrar elementos de uma coleção em relação a um valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="f0e56-105">The comparison operators in PowerShell can either compare two values or filter elements of a collection against an input value.</span></span>

## <a name="long-description"></a><span data-ttu-id="f0e56-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f0e56-106">Long description</span></span>

<span data-ttu-id="f0e56-107">Os operadores de comparação permitem comparar valores ou localizar valores que correspondem aos padrões especificados.</span><span class="sxs-lookup"><span data-stu-id="f0e56-107">Comparison operators let you compare values or finding values that match specified patterns.</span></span> <span data-ttu-id="f0e56-108">O PowerShell inclui os seguintes operadores de comparação:</span><span class="sxs-lookup"><span data-stu-id="f0e56-108">PowerShell includes the following comparison operators:</span></span>

|    <span data-ttu-id="f0e56-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="f0e56-109">Type</span></span>     |   <span data-ttu-id="f0e56-110">Operador</span><span class="sxs-lookup"><span data-stu-id="f0e56-110">Operator</span></span>   |              <span data-ttu-id="f0e56-111">Teste de comparação</span><span class="sxs-lookup"><span data-stu-id="f0e56-111">Comparison test</span></span>              |
| ----------- | ------------ | ----------------------------------------- |
| <span data-ttu-id="f0e56-112">Igualitário</span><span class="sxs-lookup"><span data-stu-id="f0e56-112">Equality</span></span>    | <span data-ttu-id="f0e56-113">-eq</span><span class="sxs-lookup"><span data-stu-id="f0e56-113">-eq</span></span>          | <span data-ttu-id="f0e56-114">equals</span><span class="sxs-lookup"><span data-stu-id="f0e56-114">equals</span></span>                                    |
|             | <span data-ttu-id="f0e56-115">-ne</span><span class="sxs-lookup"><span data-stu-id="f0e56-115">-ne</span></span>          | <span data-ttu-id="f0e56-116">Não é igual a</span><span class="sxs-lookup"><span data-stu-id="f0e56-116">not equals</span></span>                                |
|             | <span data-ttu-id="f0e56-117">-gt</span><span class="sxs-lookup"><span data-stu-id="f0e56-117">-gt</span></span>          | <span data-ttu-id="f0e56-118">maior que</span><span class="sxs-lookup"><span data-stu-id="f0e56-118">greater than</span></span>                              |
|             | <span data-ttu-id="f0e56-119">-ge</span><span class="sxs-lookup"><span data-stu-id="f0e56-119">-ge</span></span>          | <span data-ttu-id="f0e56-120">maior ou igual</span><span class="sxs-lookup"><span data-stu-id="f0e56-120">greater than or equal</span></span>                     |
|             | <span data-ttu-id="f0e56-121">-lt</span><span class="sxs-lookup"><span data-stu-id="f0e56-121">-lt</span></span>          | <span data-ttu-id="f0e56-122">menor que</span><span class="sxs-lookup"><span data-stu-id="f0e56-122">less than</span></span>                                 |
|             | <span data-ttu-id="f0e56-123">-le</span><span class="sxs-lookup"><span data-stu-id="f0e56-123">-le</span></span>          | <span data-ttu-id="f0e56-124">menor ou igual</span><span class="sxs-lookup"><span data-stu-id="f0e56-124">less than or equal</span></span>                        |
| <span data-ttu-id="f0e56-125">Matching</span><span class="sxs-lookup"><span data-stu-id="f0e56-125">Matching</span></span>    | <span data-ttu-id="f0e56-126">-like</span><span class="sxs-lookup"><span data-stu-id="f0e56-126">-like</span></span>        | <span data-ttu-id="f0e56-127">Cadeia de caracteres corresponde ao padrão curinga</span><span class="sxs-lookup"><span data-stu-id="f0e56-127">string matches wildcard pattern</span></span>           |
|             | <span data-ttu-id="f0e56-128">-notlike</span><span class="sxs-lookup"><span data-stu-id="f0e56-128">-notlike</span></span>     | <span data-ttu-id="f0e56-129">a cadeia de caracteres não corresponde ao padrão curinga</span><span class="sxs-lookup"><span data-stu-id="f0e56-129">string does not match wildcard pattern</span></span>    |
|             | <span data-ttu-id="f0e56-130">-match</span><span class="sxs-lookup"><span data-stu-id="f0e56-130">-match</span></span>       | <span data-ttu-id="f0e56-131">Cadeia de caracteres corresponde ao padrão Regex</span><span class="sxs-lookup"><span data-stu-id="f0e56-131">string matches regex pattern</span></span>              |
|             | <span data-ttu-id="f0e56-132">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="f0e56-132">-notmatch</span></span>    | <span data-ttu-id="f0e56-133">a cadeia de caracteres não corresponde ao padrão Regex</span><span class="sxs-lookup"><span data-stu-id="f0e56-133">string does not match regex pattern</span></span>       |
| <span data-ttu-id="f0e56-134">Substituição</span><span class="sxs-lookup"><span data-stu-id="f0e56-134">Replacement</span></span> | <span data-ttu-id="f0e56-135">-substituir</span><span class="sxs-lookup"><span data-stu-id="f0e56-135">-replace</span></span>     | <span data-ttu-id="f0e56-136">Substitui cadeias de caracteres correspondentes a um padrão Regex</span><span class="sxs-lookup"><span data-stu-id="f0e56-136">replaces strings matching a regex pattern</span></span> |
| <span data-ttu-id="f0e56-137">Contenção</span><span class="sxs-lookup"><span data-stu-id="f0e56-137">Containment</span></span> | <span data-ttu-id="f0e56-138">-contains</span><span class="sxs-lookup"><span data-stu-id="f0e56-138">-contains</span></span>    | <span data-ttu-id="f0e56-139">a coleção contém um valor</span><span class="sxs-lookup"><span data-stu-id="f0e56-139">collection contains a value</span></span>               |
|             | <span data-ttu-id="f0e56-140">-notcontains</span><span class="sxs-lookup"><span data-stu-id="f0e56-140">-notcontains</span></span> | <span data-ttu-id="f0e56-141">a coleção não contém um valor</span><span class="sxs-lookup"><span data-stu-id="f0e56-141">collection does not contain a value</span></span>       |
|             | <span data-ttu-id="f0e56-142">-in</span><span class="sxs-lookup"><span data-stu-id="f0e56-142">-in</span></span>          | <span data-ttu-id="f0e56-143">o valor está em uma coleção</span><span class="sxs-lookup"><span data-stu-id="f0e56-143">value is in a collection</span></span>                  |
|             | <span data-ttu-id="f0e56-144">-notin</span><span class="sxs-lookup"><span data-stu-id="f0e56-144">-notin</span></span>       | <span data-ttu-id="f0e56-145">o valor não está em uma coleção</span><span class="sxs-lookup"><span data-stu-id="f0e56-145">value is not in a collection</span></span>              |
| <span data-ttu-id="f0e56-146">Type</span><span class="sxs-lookup"><span data-stu-id="f0e56-146">Type</span></span>        | <span data-ttu-id="f0e56-147">-é</span><span class="sxs-lookup"><span data-stu-id="f0e56-147">-is</span></span>          | <span data-ttu-id="f0e56-148">ambos os objetos são do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="f0e56-148">both objects are the same type</span></span>            |
|             | <span data-ttu-id="f0e56-149">-IsNot</span><span class="sxs-lookup"><span data-stu-id="f0e56-149">-isnot</span></span>       | <span data-ttu-id="f0e56-150">os objetos não são do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="f0e56-150">the objects are not the same type</span></span>         |

## <a name="common-features"></a><span data-ttu-id="f0e56-151">Recursos comuns</span><span class="sxs-lookup"><span data-stu-id="f0e56-151">Common features</span></span>

<span data-ttu-id="f0e56-152">Por padrão, todos os operadores de comparação não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f0e56-152">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="f0e56-153">Para tornar um operador de comparação que diferencia maiúsculas de minúsculas, adicione um `c` após o `-` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-153">To make a comparison operator case-sensitive, add a `c` after the `-`.</span></span> <span data-ttu-id="f0e56-154">Por exemplo, `-ceq` é a versão que diferencia maiúsculas de minúsculas do `-eq` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-154">For example, `-ceq` is the case-sensitive version of `-eq`.</span></span> <span data-ttu-id="f0e56-155">Para tornar a diferenciação de maiúsculas e minúsculas explícita, adicione um `i` antes `-` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-155">To make the case-insensitivity explicit, add an `i` before `-`.</span></span> <span data-ttu-id="f0e56-156">Por exemplo, `-ieq` é a versão explicitamente sem diferenciação de maiúsculas e minúsculas do `-eq` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-156">For example, `-ieq` is the explicitly case-insensitive version of `-eq`.</span></span>

<span data-ttu-id="f0e56-157">Quando a entrada de um operador é um valor escalar, o operador retorna um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="f0e56-157">When the input of an operator is a scalar value, the operator returns a **Boolean** value.</span></span> <span data-ttu-id="f0e56-158">Quando a entrada é uma coleção, o operador retorna os elementos da coleção que correspondem ao valor do lado direito da expressão.</span><span class="sxs-lookup"><span data-stu-id="f0e56-158">When the input is a collection, the operator returns the elements of the collection that match the right-hand value of the expression.</span></span>
<span data-ttu-id="f0e56-159">Se não houver nenhuma correspondência na coleção, os operadores de comparação retornarão uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="f0e56-159">If there are no matches in the collection, comparison operators return an empty array.</span></span> <span data-ttu-id="f0e56-160">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-160">For example:</span></span>

```powershell
$a = (1, 2 -eq 3)
$a.GetType().Name
$a.Count
```

```output
Object[]
0
```

<span data-ttu-id="f0e56-161">Há algumas exceções:</span><span class="sxs-lookup"><span data-stu-id="f0e56-161">There are a few exceptions:</span></span>

- <span data-ttu-id="f0e56-162">Os operadores de contenção e de tipo sempre retornam um valor **booliano**</span><span class="sxs-lookup"><span data-stu-id="f0e56-162">The containment and type operators always return a **Boolean** value</span></span>
- <span data-ttu-id="f0e56-163">O `-replace` operador retorna o resultado de substituição</span><span class="sxs-lookup"><span data-stu-id="f0e56-163">The `-replace` operator returns the replacement result</span></span>
- <span data-ttu-id="f0e56-164">Os `-match` `-notmatch` operadores e também preenchem a `$Matches` variável automática, a menos que o lado esquerdo da expressão seja uma coleção.</span><span class="sxs-lookup"><span data-stu-id="f0e56-164">The `-match` and `-notmatch` operators also populate the `$Matches` automatic variable unless the left-hand side of the expression is a collection.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="f0e56-165">Operadores de igualdade</span><span class="sxs-lookup"><span data-stu-id="f0e56-165">Equality operators</span></span>

### <a name="-eq-and--ne"></a><span data-ttu-id="f0e56-166">-eq e -ne</span><span class="sxs-lookup"><span data-stu-id="f0e56-166">-eq and -ne</span></span>

<span data-ttu-id="f0e56-167">Quando o lado esquerdo for escalar, `-eq` retornará **true** se o lado direito for uma correspondência exata, caso contrário, `-eq` retornará **false**.</span><span class="sxs-lookup"><span data-stu-id="f0e56-167">When the left-hand side is scalar, `-eq` returns **True** if the right-hand side is an exact match, otherwise, `-eq` returns **False**.</span></span> <span data-ttu-id="f0e56-168">`-ne` faz o oposto; retorna **false** quando ambos os lados correspondem; caso contrário, `-ne` retornará true.</span><span class="sxs-lookup"><span data-stu-id="f0e56-168">`-ne` does the opposite; it returns **False** when both sides match; otherwise, `-ne` returns True.</span></span>

<span data-ttu-id="f0e56-169">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-169">Example:</span></span>

```powershell
2 -eq 2                 # Output: True
2 -eq 3                 # Output: False
"abc" -eq "abc"         # Output: True
"abc" -eq "abc", "def"  # Output: False
"abc" -ne "def"         # Output: True
"abc" -ne "abc"         # Output: False
"abc" -ne "abc", "def"  # Output: True
```

<span data-ttu-id="f0e56-170">Quando o lado esquerdo é uma coleção, `-eq` retorna os membros que correspondem ao lado direito, enquanto `-ne` os filtra.</span><span class="sxs-lookup"><span data-stu-id="f0e56-170">When the left-hand side is a collection, `-eq` returns those members that match the right-hand side, while `-ne` filters them out.</span></span>

<span data-ttu-id="f0e56-171">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-171">Example:</span></span>

```powershell
1,2,3 -eq 2             # Output: 2
"abc", "def" -eq "abc"  # Output: abc
"abc", "def" -ne "abc"  # Output: def
```

<span data-ttu-id="f0e56-172">Esses operadores processam todos os elementos da coleção.</span><span class="sxs-lookup"><span data-stu-id="f0e56-172">These operators process all elements of the collection.</span></span> <span data-ttu-id="f0e56-173">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-173">Example:</span></span>

```powershell
"zzz", "def", "zzz" -eq "zzz"
```

```output
zzz
zzz
```

<span data-ttu-id="f0e56-174">Os operadores de igualdade aceitam quaisquer dois objetos, não apenas um escalar ou uma coleção.</span><span class="sxs-lookup"><span data-stu-id="f0e56-174">The equality operators accept any two objects, not just a scalar or collection.</span></span>
<span data-ttu-id="f0e56-175">Mas não há garantia de que o resultado da comparação seja significativo para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="f0e56-175">But the comparison result is not guaranteed to be meaningful for the end-user.</span></span>
<span data-ttu-id="f0e56-176">O exemplo a seguir demonstra o problema.</span><span class="sxs-lookup"><span data-stu-id="f0e56-176">The following example demonstrates the issue.</span></span>

```powershell
class MyFileInfoSet {
    [String]$File
    [Int64]$Size
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
False
```

<span data-ttu-id="f0e56-177">Neste exemplo, criamos dois objetos com propriedades idênticas.</span><span class="sxs-lookup"><span data-stu-id="f0e56-177">In this example, we created two objects with identical properties.</span></span> <span data-ttu-id="f0e56-178">No entanto, o resultado do teste de igualdade é **false** porque eles são objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="f0e56-178">Yet, the equality test result is **False** because they are different objects.</span></span> <span data-ttu-id="f0e56-179">Para criar classes comparáveis, você precisa implementar [System. IEquatable \<T> ][2] em sua classe.</span><span class="sxs-lookup"><span data-stu-id="f0e56-179">To create comparable classes, you need to implement [System.IEquatable\<T>][2] in your class.</span></span> <span data-ttu-id="f0e56-180">O exemplo a seguir demonstra a implementação parcial de uma classe **Myfileinfoset** que implementa [System. \<T> IEquatable][2] e tem duas propriedades, **File** e **size**.</span><span class="sxs-lookup"><span data-stu-id="f0e56-180">The following example demonstrates the partial implementation of a **MyFileInfoSet** class that implements [System.IEquatable\<T>][2] and has two properties, **File** and **Size**.</span></span> <span data-ttu-id="f0e56-181">O `Equals()` método retornará true se as propriedades de arquivo e tamanho de dois objetos **myfileinfoset** forem iguais.</span><span class="sxs-lookup"><span data-stu-id="f0e56-181">The `Equals()` method returns True if the File and Size properties of two **MyFileInfoSet** objects are the same.</span></span>

```powershell
class MyFileInfoSet : System.IEquatable[Object] {
    [String]$File
    [Int64]$Size

    [bool] Equals([Object] $obj) {
        return ($this.File -eq $obj.File) -and ($this.Size -eq $obj.Size)
    }
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
True
```

<span data-ttu-id="f0e56-182">Um exemplo proeminente de comparação de objetos arbitrários é descobrir se eles são nulos.</span><span class="sxs-lookup"><span data-stu-id="f0e56-182">A prominent example of comparing arbitrary objects is to find out if they are null.</span></span> <span data-ttu-id="f0e56-183">Mas se você precisar determinar se uma variável é `$null` , deverá colocar `$null` no lado esquerdo do operador de igualdade.</span><span class="sxs-lookup"><span data-stu-id="f0e56-183">But if you need to determine whether a variable is `$null`, you must put `$null` on the left-hand side of the equality operator.</span></span> <span data-ttu-id="f0e56-184">Colocá-lo no lado direito não faz o que você espera.</span><span class="sxs-lookup"><span data-stu-id="f0e56-184">Putting it on the right-hand side does not do what you expect.</span></span>

<span data-ttu-id="f0e56-185">Por exemplo, deixe que `$a` seja uma matriz que contém elementos nulos:</span><span class="sxs-lookup"><span data-stu-id="f0e56-185">For example, let `$a` be an array containing null elements:</span></span>

```powershell
$a = 1, 2, $null, 4, $null, 6
```

<span data-ttu-id="f0e56-186">Os testes a seguir `$a` não são nulos.</span><span class="sxs-lookup"><span data-stu-id="f0e56-186">The following tests that `$a` is not null.</span></span>

```powershell
$null -ne $a
```

```output
True
```

<span data-ttu-id="f0e56-187">No entanto, a seguir, os Filers saem de todos os elementos nulos de `$a` :</span><span class="sxs-lookup"><span data-stu-id="f0e56-187">The following, however, filers out all null elements from `$a`:</span></span>

```powershell
$a -ne $null # Output: 1, 2, 4, 6
```

```output
1
2
4
6
```

### <a name="-gt--ge--lt-and--le"></a><span data-ttu-id="f0e56-188">-gt,-GE,-lt e-Le</span><span class="sxs-lookup"><span data-stu-id="f0e56-188">-gt, -ge, -lt, and -le</span></span>

<span data-ttu-id="f0e56-189">`-gt`, `-ge` , `-lt` e `-le` se comportar de forma muito semelhante.</span><span class="sxs-lookup"><span data-stu-id="f0e56-189">`-gt`, `-ge`, `-lt`, and `-le` behave very similarly.</span></span> <span data-ttu-id="f0e56-190">Quando ambos os lados são escalares, eles retornam **true** ou **false** , dependendo de como os dois lados se comparam:</span><span class="sxs-lookup"><span data-stu-id="f0e56-190">When both sides are scalar they return **True** or **False** depending on how the two sides compare:</span></span>

| <span data-ttu-id="f0e56-191">Operador</span><span class="sxs-lookup"><span data-stu-id="f0e56-191">Operator</span></span> | <span data-ttu-id="f0e56-192">Retorna verdadeiro quando...</span><span class="sxs-lookup"><span data-stu-id="f0e56-192">Returns True when...</span></span>                   |
| -------- | -------------------------------------- |
| <span data-ttu-id="f0e56-193">-gt</span><span class="sxs-lookup"><span data-stu-id="f0e56-193">-gt</span></span>      | <span data-ttu-id="f0e56-194">O lado esquerdo é maior</span><span class="sxs-lookup"><span data-stu-id="f0e56-194">The left-hand side is greater</span></span>          |
| <span data-ttu-id="f0e56-195">-ge</span><span class="sxs-lookup"><span data-stu-id="f0e56-195">-ge</span></span>      | <span data-ttu-id="f0e56-196">O lado esquerdo é maior ou igual a</span><span class="sxs-lookup"><span data-stu-id="f0e56-196">The left-hand side is greater or equal</span></span> |
| <span data-ttu-id="f0e56-197">-lt</span><span class="sxs-lookup"><span data-stu-id="f0e56-197">-lt</span></span>      | <span data-ttu-id="f0e56-198">O lado esquerdo é menor</span><span class="sxs-lookup"><span data-stu-id="f0e56-198">The left-hand side is smaller</span></span>          |
| <span data-ttu-id="f0e56-199">-le</span><span class="sxs-lookup"><span data-stu-id="f0e56-199">-le</span></span>      | <span data-ttu-id="f0e56-200">O lado esquerdo é menor ou igual a</span><span class="sxs-lookup"><span data-stu-id="f0e56-200">The left-hand side is smaller or equal</span></span> |

<span data-ttu-id="f0e56-201">Nos exemplos a seguir, todas as instruções retornam true.</span><span class="sxs-lookup"><span data-stu-id="f0e56-201">In the following examples, all statements return True.</span></span>

```powershell
8 -gt 6  # Output: True
8 -ge 8  # Output: True
6 -lt 8  # Output: True
8 -le 8  # Output: True
```

> [!NOTE]
> <span data-ttu-id="f0e56-202">Na maioria das linguagens de programação, o operador maior que é `>` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-202">In most programming languages the greater-than operator is `>`.</span></span> <span data-ttu-id="f0e56-203">No PowerShell, esse caractere é usado para redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="f0e56-203">In PowerShell, this character is used for redirection.</span></span> <span data-ttu-id="f0e56-204">Para obter detalhes, consulte [about_Redirection][3].</span><span class="sxs-lookup"><span data-stu-id="f0e56-204">For details, see [about_Redirection][3].</span></span>

<span data-ttu-id="f0e56-205">Quando o lado esquerdo é uma coleção, esses operadores comparam cada membro da coleção com o lado direito.</span><span class="sxs-lookup"><span data-stu-id="f0e56-205">When the left-hand side is a collection, these operators compare each member of the collection with the right-hand side.</span></span> <span data-ttu-id="f0e56-206">Dependendo de sua lógica, eles mantêm ou descartam o membro.</span><span class="sxs-lookup"><span data-stu-id="f0e56-206">Depending on their logic, they either keep or discard the member.</span></span>

<span data-ttu-id="f0e56-207">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-207">Example:</span></span>

```powershell
$a=5, 6, 7, 8, 9

Write-Output "Test collection:"
$a

Write-Output "`nMembers greater than 7"
$a -gt 7

Write-Output "`nMembers greater than or equal to 7"
$a -ge 7

Write-Output "`nMembers smaller than 7"
$a -lt 7

Write-Output "`nMembers smaller than or equal to 7"
$a -le 7
```

```output
Test collection:
5
6
7
8
9

Members greater than 7
8
9

Members greater than or equal to 7
7
8
9

Members smaller than 7
5
6

Members smaller than or equal to 7
5
6
7
```

<span data-ttu-id="f0e56-208">Esses operadores funcionam com qualquer classe que implemente [System. IComparable][1].</span><span class="sxs-lookup"><span data-stu-id="f0e56-208">These operators work with any class that implements [System.IComparable][1].</span></span>

<span data-ttu-id="f0e56-209">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="f0e56-209">Examples:</span></span>

```powershell
# Date comparison
[DateTime]'2001-11-12' -lt [DateTime]'2020-08-01' # True

# Sorting order comparison
'a' -lt 'z'           # True; 'a' comes before 'z'
'macOS' -ilt 'MacOS'  # False
'MacOS' -ilt 'macOS'  # False
'macOS' -clt 'MacOS'  # True; 'm' comes before 'M'
```

<span data-ttu-id="f0e56-210">O exemplo a seguir demonstra que não há nenhum símbolo em um teclado American QWERTY que é classificado após ' a '.</span><span class="sxs-lookup"><span data-stu-id="f0e56-210">The following example demonstrates that there is no symbol on an American QWERTY keyboard that gets sorted after 'a'.</span></span> <span data-ttu-id="f0e56-211">Ele alimenta um conjunto contendo todos esses símbolos para o `-gt` operador para compará-los com ' a '.</span><span class="sxs-lookup"><span data-stu-id="f0e56-211">It feeds a set containing all such symbols to the `-gt` operator to compare them against 'a'.</span></span> <span data-ttu-id="f0e56-212">A saída é uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="f0e56-212">The output is an empty array.</span></span>

```powershell
$a=' ','`','~','!','@','#','$','%','^','&','*','(',')','_','+','-','=',
   '{','}','[',']',':',';','"','''','\','|','/','?','.','>',',','<'
$a -gt 'a'
# Output: Nothing
```

<span data-ttu-id="f0e56-213">Se os dois lados dos operadores não forem razoavelmente comparáveis, esses operadores gerarão um erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="f0e56-213">If the two sides of the operators are not reasonably comparable, these operators raise a non-terminating error.</span></span>

## <a name="matching-operators"></a><span data-ttu-id="f0e56-214">Operadores correspondentes</span><span class="sxs-lookup"><span data-stu-id="f0e56-214">Matching operators</span></span>

<span data-ttu-id="f0e56-215">Os operadores de correspondência ( `-like` , `-notlike` , e `-match` `-notmatch` ) localizam elementos que correspondem ou não correspondem a um padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="f0e56-215">The matching operators (`-like`, `-notlike`, `-match`, and `-notmatch`) find elements that match or do not match a specified pattern.</span></span> <span data-ttu-id="f0e56-216">O padrão para `-like` e `-notlike` é uma expressão curinga (contendo `*` , `?` e `[ ]` ), enquanto `-match` e `-notmatch` aceita uma expressão regular (Regex).</span><span class="sxs-lookup"><span data-stu-id="f0e56-216">The pattern for `-like` and `-notlike` is a wildcard expression (containing `*`, `?`, and `[ ]`), while `-match` and `-notmatch` accept a regular expression (Regex).</span></span>

<span data-ttu-id="f0e56-217">A sintaxe do é:</span><span class="sxs-lookup"><span data-stu-id="f0e56-217">The syntax is:</span></span>

```
<string[]> -like    <wildcard-expression>
<string[]> -notlike <wildcard-expression>
<string[]> -match    <regular-expression>
<string[]> -notmatch <regular-expression>
```

<span data-ttu-id="f0e56-218">Quando a entrada desses operadores é um valor escalar, eles retornam um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="f0e56-218">When the input of these operators is a scalar value, they return a **Boolean** value.</span></span> <span data-ttu-id="f0e56-219">Quando a entrada é uma coleção de valores, os operadores retornam quaisquer membros correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f0e56-219">When the input is a collection of values, the operators return any matching members.</span></span> <span data-ttu-id="f0e56-220">Se não houver nenhuma correspondência em uma coleção, os operadores retornarão uma matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="f0e56-220">If there are no matches in a collection, the operators return an empty array.</span></span>

### <a name="-like-and--notlike"></a><span data-ttu-id="f0e56-221">-like e-não gosto</span><span class="sxs-lookup"><span data-stu-id="f0e56-221">-like and -notlike</span></span>

<span data-ttu-id="f0e56-222">`-like` e `-notlike` se comportar de forma semelhante `-eq` e `-ne` , mas o lado direito pode ser uma cadeia de caracteres que contém [curingas](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="f0e56-222">`-like` and `-notlike` behave similarly to `-eq` and `-ne`, but the right-hand side could be a string containing [wildcards](about_Wildcards.md).</span></span>

<span data-ttu-id="f0e56-223">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-223">Example:</span></span>

```powershell
"PowerShell" -like    "*shell"           # Output: True
"PowerShell" -notlike "*shell"           # Output: False
"PowerShell" -like    "Power?hell"       # Output: True
"PowerShell" -notlike "Power?hell"       # Output: False
"PowerShell" -like    "Power[p-w]hell"   # Output: True
"PowerShell" -notlike "Power[p-w]hell"   # Output: False

"PowerShell", "Server" -like "*shell"    # Output: PowerShell
"PowerShell", "Server" -notlike "*shell" # Output: Server
```

### <a name="-match-and--notmatch"></a><span data-ttu-id="f0e56-224">-Match e-cormatch</span><span class="sxs-lookup"><span data-stu-id="f0e56-224">-match and -notmatch</span></span>

<span data-ttu-id="f0e56-225">`-match` e `-notmatch` use expressões regulares para pesquisar por padrão nos valores do lado esquerdo.</span><span class="sxs-lookup"><span data-stu-id="f0e56-225">`-match` and `-notmatch` use regular expressions to search for pattern in the left-hand side values.</span></span> <span data-ttu-id="f0e56-226">As expressões regulares podem corresponder a padrões complexos, como endereços de email, caminhos UNC ou números de telefone formatados.</span><span class="sxs-lookup"><span data-stu-id="f0e56-226">Regular expressions can match complex patterns like email addresses, UNC paths, or formatted phone numbers.</span></span> <span data-ttu-id="f0e56-227">A cadeia de caracteres do lado direito deve aderir às regras de [expressões regulares](about_Regular_Expressions.md) .</span><span class="sxs-lookup"><span data-stu-id="f0e56-227">The right-hand side string must adhere to the [regular expressions](about_Regular_Expressions.md) rules.</span></span>

<span data-ttu-id="f0e56-228">Exemplos escalares:</span><span class="sxs-lookup"><span data-stu-id="f0e56-228">Scalar examples:</span></span>

```powershell
# Partial match test, showing how differently -match and -like behave
"PowerShell" -match 'shell'        # Output: True
"PowerShell" -like  'shell'        # Output: False

# Regex syntax test
"PowerShell" -match    '^Power\w+' # Output: True
'bag'        -notmatch 'b[iou]g'   # Output: True
```

<span data-ttu-id="f0e56-229">Se a entrada for uma coleção, os operadores retornarão os membros correspondentes dessa coleção e a `$Matches` variável automática será `$null` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-229">If the input is a collection, the operators return the matching members of that collection and the `$Matches` automatic variable is `$null`.</span></span>

<span data-ttu-id="f0e56-230">Exemplos de coleção:</span><span class="sxs-lookup"><span data-stu-id="f0e56-230">Collection examples:</span></span>

```powershell
"PowerShell", "Super PowerShell", "Power's hell" -match '^Power\w+'
# Output: PowerShell

"Rhell", "Chell", "Mel", "Smell", "Shell" -match "hell"
# Output: Rhell, Chell, Shell

"Bag", "Beg", "Big", "Bog", "Bug"  -match 'b[iou]g'
#Output: Big, Bog, Bug

"Bag", "Beg", "Big", "Bog", "Bug"  -notmatch 'b[iou]g'
#Output: Bag, Beg
```

<span data-ttu-id="f0e56-231">`-match` e `-notmatch` dão suporte a grupos de captura Regex.</span><span class="sxs-lookup"><span data-stu-id="f0e56-231">`-match` and `-notmatch` support regex capture groups.</span></span> <span data-ttu-id="f0e56-232">Cada vez que eles são executados, eles substituem a `$Matches` variável automática.</span><span class="sxs-lookup"><span data-stu-id="f0e56-232">Each time they run, they overwrite the `$Matches` automatic variable.</span></span> <span data-ttu-id="f0e56-233">Quando `<input>` é uma coleção, a `$Matches` variável é `$null` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-233">When `<input>` is a collection the `$Matches` variable is `$null`.</span></span> <span data-ttu-id="f0e56-234">`$Matches` é uma **tabela de hash** que sempre tem uma chave chamada ' 0 ', que armazena toda a correspondência.</span><span class="sxs-lookup"><span data-stu-id="f0e56-234">`$Matches` is a **Hashtable** that always has a key named '0', which stores the entire match.</span></span> <span data-ttu-id="f0e56-235">Se a expressão regular contiver grupos de captura, o `$Matches` conterá chaves adicionais para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="f0e56-235">If the regular expression contains capture groups, the `$Matches` contains additional keys for each group.</span></span>

<span data-ttu-id="f0e56-236">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-236">Example:</span></span>

```powershell
$string = 'The last logged on user was CONTOSO\jsmith'
$string -match 'was (?<domain>.+)\\(?<user>.+)'

$Matches

Write-Output "`nDomain name:"
$Matches.domain

Write-Output "`nUser name:"
$Matches.user
```

```output
True

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

Domain name:
CONTOSO

User name:
jsmith
```

<span data-ttu-id="f0e56-237">Para obter detalhes, consulte [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f0e56-237">For details, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

## <a name="replacement-operator"></a><span data-ttu-id="f0e56-238">Operador de substituição</span><span class="sxs-lookup"><span data-stu-id="f0e56-238">Replacement operator</span></span>

### <a name="replacement-with-regular-expressions"></a><span data-ttu-id="f0e56-239">Substituição com expressões regulares</span><span class="sxs-lookup"><span data-stu-id="f0e56-239">Replacement with regular expressions</span></span>

<span data-ttu-id="f0e56-240">Como `-match` , o `-replace` operador usa expressões regulares para localizar o padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="f0e56-240">Like `-match`, the `-replace` operator uses regular expressions to find the specified pattern.</span></span> <span data-ttu-id="f0e56-241">Mas, ao contrário `-match` , ele substitui as correspondências por outro valor especificado.</span><span class="sxs-lookup"><span data-stu-id="f0e56-241">But unlike `-match`, it replaces the matches with another specified value.</span></span>

<span data-ttu-id="f0e56-242">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f0e56-242">Syntax:</span></span>

```
<input> -replace <regular-expression>, <substitute>
```

<span data-ttu-id="f0e56-243">O operador substitui todo ou parte de um valor pelo valor especificado usando expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="f0e56-243">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="f0e56-244">Você pode usar o operador para muitas tarefas administrativas, como renomear arquivos.</span><span class="sxs-lookup"><span data-stu-id="f0e56-244">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="f0e56-245">Por exemplo, o comando a seguir altera as extensões de nome de arquivo de todos os `.txt` arquivos para `.log` :</span><span class="sxs-lookup"><span data-stu-id="f0e56-245">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="f0e56-246">Por padrão, o `-replace` operador não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f0e56-246">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="f0e56-247">Para torná-lo sensível a maiúsculas e minúsculas, use `-creplace` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-247">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="f0e56-248">Para torná-lo explicitamente não diferencia maiúsculas de minúsculas, use `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-248">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="f0e56-249">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="f0e56-249">Examples:</span></span>

```powershell
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

```Output
Cook
book
```

### <a name="regular-expressions-substitutions"></a><span data-ttu-id="f0e56-250">Substituições de expressões regulares</span><span class="sxs-lookup"><span data-stu-id="f0e56-250">Regular expressions substitutions</span></span>

<span data-ttu-id="f0e56-251">Também é possível usar expressões regulares para substituir texto dinamicamente usando grupos de captura e substituições.</span><span class="sxs-lookup"><span data-stu-id="f0e56-251">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="f0e56-252">Os grupos de captura podem ser referenciados na `<substitute>` cadeia de caracteres usando o caractere de cifrão ( `$` ) antes do identificador de grupo.</span><span class="sxs-lookup"><span data-stu-id="f0e56-252">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="f0e56-253">No exemplo a seguir, o `-replace` operador aceita um nome de usuário na forma `DomainName\Username` e converte para o `Username@DomainName` formato:</span><span class="sxs-lookup"><span data-stu-id="f0e56-253">In the following example, the `-replace` operator accepts a username in the form of `DomainName\Username` and converts to the `Username@DomainName` format:</span></span>

```powershell
$SearchExp = '^(?<DomainName>[\w-.]+)\\(?<Username>[\w-.]+)$'
$ReplaceExp = '${Username}@${DomainName}'

'Contoso.local\John.Doe' -replace $SearchExp,$ReplaceExp
```

```output
John.Doe@Contoso.local
```

> [!WARNING]
> <span data-ttu-id="f0e56-254">O `$` caractere tem funções syntatic no PowerShell e em expressões regulares:</span><span class="sxs-lookup"><span data-stu-id="f0e56-254">The `$` character has syntatic roles in both PowerShell and regular expressions:</span></span>
>
> - <span data-ttu-id="f0e56-255">No PowerShell, entre aspas duplas, ele designa variáveis e atua como um operador de subexpressão.</span><span class="sxs-lookup"><span data-stu-id="f0e56-255">In PowerShell, between double quotation marks, it designates variables and acts as a subexpression operator.</span></span>
> - <span data-ttu-id="f0e56-256">Em cadeias de caracteres de pesquisa Regex, ele denota o fim da linha</span><span class="sxs-lookup"><span data-stu-id="f0e56-256">In Regex search strings, it denotes end of the line</span></span>
> - <span data-ttu-id="f0e56-257">Em cadeias de caracteres de substituição Regex, ele denota grupos capturados. Certifique-se de colocar suas expressões regulares entre aspas simples ou inserir um caractere de acento grave ( `` ` `` ) antes delas.</span><span class="sxs-lookup"><span data-stu-id="f0e56-257">In Regex substitution strings, it denotes captured groups.Be sure to either put your regular expressions between single quotation marks or insert a backtick (`` ` ``) character before them.</span></span>

<span data-ttu-id="f0e56-258">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-258">For example:</span></span>

```powershell
$1 = 'Goodbye'

'Hello World' -replace '(\w+) \w+', "$1 Universe"
# Output: Goodbye Universe

'Hello World' -replace '(\w+) \w+', '$1 Universe'
# Output: Hello Universe
```

<span data-ttu-id="f0e56-259">`$$` em Regex, denota um literal `$` .</span><span class="sxs-lookup"><span data-stu-id="f0e56-259">`$$` in Regex denotes a literal `$`.</span></span> <span data-ttu-id="f0e56-260">Isso `$$` na cadeia de caracteres de substituição para incluir um literal `$` na substituição resultante.</span><span class="sxs-lookup"><span data-stu-id="f0e56-260">This `$$` in the substitution string to include a literal `$` in the resulting replacement.</span></span> <span data-ttu-id="f0e56-261">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-261">For example:</span></span>

```powershell
'5.72' -replace '(.+)', '$ $1' # Output: $ 5.72
'5.72' -replace '(.+)', '$$$1' # Output: $5.72
'5.72' -replace '(.+)', '$$1'  # Output: $1
```

<span data-ttu-id="f0e56-262">Para saber mais, confira [about_Regular_Expressions](about_Regular_Expressions.md) e [substituições em expressões regulares][4].</span><span class="sxs-lookup"><span data-stu-id="f0e56-262">To learn more, see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions][4].</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="f0e56-263">Substituindo em uma coleção</span><span class="sxs-lookup"><span data-stu-id="f0e56-263">Substituting in a collection</span></span>

<span data-ttu-id="f0e56-264">Quando o `<input>` para o `-replace` operador é uma coleção, o PowerShell aplica a substituição a todos os valores na coleção.</span><span class="sxs-lookup"><span data-stu-id="f0e56-264">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="f0e56-265">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-265">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

## <a name="containment-operators"></a><span data-ttu-id="f0e56-266">Operadores de confinamento</span><span class="sxs-lookup"><span data-stu-id="f0e56-266">Containment operators</span></span>

<span data-ttu-id="f0e56-267">Os operadores de confinamento ( `-contains` , `-notcontains` , e `-in` `-notin` ) são semelhantes aos operadores de igualdade, exceto que sempre retornam um valor **booliano** , mesmo quando a entrada é uma coleção.</span><span class="sxs-lookup"><span data-stu-id="f0e56-267">The containment operators (`-contains`, `-notcontains`, `-in`, and `-notin`) are similar to the equality operators, except that they always return a **Boolean** value, even when the input is a collection.</span></span> <span data-ttu-id="f0e56-268">Esses operadores param de comparar assim que detectam a primeira correspondência, enquanto os operadores de igualdade avaliam todos os membros de entrada.</span><span class="sxs-lookup"><span data-stu-id="f0e56-268">These operators stop comparing as soon as they detect the first match, whereas the equality operators evaluate all input members.</span></span> <span data-ttu-id="f0e56-269">Em uma coleção muito grande, esses operadores retornam mais rápido do que os operadores de igualdade.</span><span class="sxs-lookup"><span data-stu-id="f0e56-269">In a very large collection, these operators return quicker than the equality operators.</span></span>

<span data-ttu-id="f0e56-270">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f0e56-270">Syntax:</span></span>

```
<Collection> -contains <Test-object>
<Collection> -notcontains <Test-object>
<Test-object> -in <Collection>
<Test-object> -notin <Collection>
```

### <a name="-contains-and--notcontains"></a><span data-ttu-id="f0e56-271">-Contains e-iscontains</span><span class="sxs-lookup"><span data-stu-id="f0e56-271">-contains and -notcontains</span></span>

<span data-ttu-id="f0e56-272">Esses operadores informam se um conjunto inclui um determinado elemento.</span><span class="sxs-lookup"><span data-stu-id="f0e56-272">These operators tell whether a set includes a certain element.</span></span> <span data-ttu-id="f0e56-273">`-contains` Retorna true quando o lado direito (objeto de teste) corresponde a um dos elementos no conjunto.</span><span class="sxs-lookup"><span data-stu-id="f0e56-273">`-contains` returns True when the right-hand side (test object) matches one of the elements in the set.</span></span> <span data-ttu-id="f0e56-274">`-notcontains` Retorna false em vez disso.</span><span class="sxs-lookup"><span data-stu-id="f0e56-274">`-notcontains` returns False instead.</span></span> <span data-ttu-id="f0e56-275">Quando o objeto de teste é uma coleção, esses operadores usam igualdade de referência, ou seja, eles verificam se um dos elementos do conjunto é a mesma instância do objeto de teste.</span><span class="sxs-lookup"><span data-stu-id="f0e56-275">When the test object is a collection, these operators use reference equality, i.e. they check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="f0e56-276">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="f0e56-276">Examples:</span></span>

```powershell
"abc", "def" -contains "def"                  # Output: True
"abc", "def" -notcontains "def"               # Output: False
"Windows", "PowerShell" -contains "Shell"     # Output: False
"Windows", "PowerShell" -notcontains "Shell"  # Output: True
"abc", "def", "ghi" -contains "abc", "def"    # Output: False
"abc", "def", "ghi" -notcontains "abc", "def" # Output: True
```

<span data-ttu-id="f0e56-277">Exemplos mais complexos:</span><span class="sxs-lookup"><span data-stu-id="f0e56-277">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$DomainServers -contains $thisComputer
# Output: True

$a = "abc", "def"
"abc", "def", "ghi" -contains $a # Output: False
$a, "ghi" -contains $a           # Output: True
```

### <a name="-in-and--notin"></a><span data-ttu-id="f0e56-278">-in e-notin</span><span class="sxs-lookup"><span data-stu-id="f0e56-278">-in and -notin</span></span>

<span data-ttu-id="f0e56-279">Os `-in` operadores e `notin` foram introduzidos no PowerShell 3 como a inversa sintática dos `contains` `-notcontain` operadores e.</span><span class="sxs-lookup"><span data-stu-id="f0e56-279">The `-in` and -`notin` operators were introduced in PowerShell 3 as the syntactic reverse of the of `contains` and `-notcontain` operators.</span></span> <span data-ttu-id="f0e56-280">`-in` retorna **true** quando o lado esquerdo corresponde a `<test-object>` um dos elementos no conjunto.</span><span class="sxs-lookup"><span data-stu-id="f0e56-280">`-in` returns **True** when the left-hand side `<test-object>` matches one of the elements in the set.</span></span> <span data-ttu-id="f0e56-281">`-notin` retorna **false** em vez disso.</span><span class="sxs-lookup"><span data-stu-id="f0e56-281">`-notin` returns **False** instead.</span></span> <span data-ttu-id="f0e56-282">Quando o objeto de teste é um conjunto, esses operadores usam a igualdade de referência para verificar se um dos elementos do conjunto é a mesma instância do objeto de teste.</span><span class="sxs-lookup"><span data-stu-id="f0e56-282">When the test object is a set, these operators use reference equality to check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="f0e56-283">Os exemplos a seguir fazem a mesma coisa que os exemplos para `-contain` e `-notcontain` fazem, mas são escritos com `-in` e `-notin` em vez disso.</span><span class="sxs-lookup"><span data-stu-id="f0e56-283">The following examples do the same thing that the examples for `-contain` and `-notcontain` do, but they are written with `-in` and `-notin` instead.</span></span>

```powershell
"def" -in "abc", "def"                  # Output: True
"def" -notin "abc", "def"               # Output: False
"Shell" -in "Windows", "PowerShell"     # Output: False
"Shell" -notin "Windows", "PowerShell"  # Output: True
"abc", "def" -in "abc", "def", "ghi"    # Output: False
"abc", "def" -notin "abc", "def", "ghi" # Output: True
```

<span data-ttu-id="f0e56-284">Exemplos mais complexos:</span><span class="sxs-lookup"><span data-stu-id="f0e56-284">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$thisComputer -in $DomainServers
# Output: True

$a = "abc", "def"
$a -in "abc", "def", "ghi" # Output: False
$a -in $a, "ghi"           # Output: True
```

## <a name="type-comparison"></a><span data-ttu-id="f0e56-285">Comparação de tipos</span><span class="sxs-lookup"><span data-stu-id="f0e56-285">Type comparison</span></span>

<span data-ttu-id="f0e56-286">Os operadores de comparação de tipo ( `-is` e `-isnot` ) são usados para determinar se um objeto é um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="f0e56-286">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

<span data-ttu-id="f0e56-287">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f0e56-287">Syntax:</span></span>

```powershell
<object> -is <type-reference>
<object> -isnot <type-reference>
```

<span data-ttu-id="f0e56-288">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0e56-288">Example:</span></span>

```powershell
$a = 1
$b = "1"
$a -is [int]           # Output: True
$a -is $b.GetType()    # Output: False
$b -isnot [int]        # Output: True
$a -isnot $b.GetType() # Output: True
```

## <a name="see-also"></a><span data-ttu-id="f0e56-289">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="f0e56-289">SEE ALSO</span></span>

- [<span data-ttu-id="f0e56-290">about_Operators</span><span class="sxs-lookup"><span data-stu-id="f0e56-290">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="f0e56-291">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="f0e56-291">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="f0e56-292">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="f0e56-292">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="f0e56-293">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="f0e56-293">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="f0e56-294">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="f0e56-294">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="f0e56-295">Where-Object</span><span class="sxs-lookup"><span data-stu-id="f0e56-295">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)

[1]: /dotnet/api/system.icomparable
[2]: /dotnet/api/system.iequatable-1
[3]: /dotnet/api/system.text.regularexpressions.match
[4]: about_Redirection.md#potential-confusion-with-comparison-operators
[5]: /dotnet/standard/base-types/substitutions-in-regular-expressions
