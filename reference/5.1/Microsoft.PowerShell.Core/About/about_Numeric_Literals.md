---
description: Tanto o inteiro quanto os literais numéricos reais podem ter os sufixos tipo e multiplicador.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre literais numéricos
ms.openlocfilehash: 99fa8c1a751551d028fe6df0b0cec94e07f19c59
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196574"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="28a1b-103">Sobre literais numéricos</span><span class="sxs-lookup"><span data-stu-id="28a1b-103">About numeric literals</span></span>

<span data-ttu-id="28a1b-104">Há dois tipos de literais numéricos: inteiro e real.</span><span class="sxs-lookup"><span data-stu-id="28a1b-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="28a1b-105">Ambos podem ter um tipo e sufixos de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="28a1b-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="28a1b-106">Literais inteiros</span><span class="sxs-lookup"><span data-stu-id="28a1b-106">Integer literals</span></span>

<span data-ttu-id="28a1b-107">Literais inteiros podem ser escritos em notação decimal ou hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="28a1b-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="28a1b-108">Os literais hexadecimais são prefixados com `0x` para distingui-los de números decimais.</span><span class="sxs-lookup"><span data-stu-id="28a1b-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="28a1b-109">Os literais inteiros podem ter um sufixo de tipo e um sufixo de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="28a1b-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="28a1b-110">Sufixo</span><span class="sxs-lookup"><span data-stu-id="28a1b-110">Suffix</span></span> |       <span data-ttu-id="28a1b-111">Significado</span><span class="sxs-lookup"><span data-stu-id="28a1b-111">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="28a1b-112">l</span><span class="sxs-lookup"><span data-stu-id="28a1b-112">l</span></span>      | <span data-ttu-id="28a1b-113">tipo de dados Long</span><span class="sxs-lookup"><span data-stu-id="28a1b-113">long data type</span></span>      |
| <span data-ttu-id="28a1b-114">kb</span><span class="sxs-lookup"><span data-stu-id="28a1b-114">kb</span></span>     | <span data-ttu-id="28a1b-115">multiplicador de kilobytes</span><span class="sxs-lookup"><span data-stu-id="28a1b-115">kilobyte multiplier</span></span> |
| <span data-ttu-id="28a1b-116">mb</span><span class="sxs-lookup"><span data-stu-id="28a1b-116">mb</span></span>     | <span data-ttu-id="28a1b-117">multiplicador de megabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-117">megabyte multiplier</span></span> |
| <span data-ttu-id="28a1b-118">Reino</span><span class="sxs-lookup"><span data-stu-id="28a1b-118">gb</span></span>     | <span data-ttu-id="28a1b-119">multiplicador de Gigabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-119">gigabyte multiplier</span></span> |
| <span data-ttu-id="28a1b-120">TB</span><span class="sxs-lookup"><span data-stu-id="28a1b-120">tb</span></span>     | <span data-ttu-id="28a1b-121">multiplicador de terabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-121">terabyte multiplier</span></span> |
| <span data-ttu-id="28a1b-122">PB</span><span class="sxs-lookup"><span data-stu-id="28a1b-122">pb</span></span>     | <span data-ttu-id="28a1b-123">multiplicador petabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-123">petabyte multiplier</span></span> |

<span data-ttu-id="28a1b-124">O tipo de um inteiro literal é determinado por seu valor, o sufixo de tipo e o sufixo de multiplicador numérico.</span><span class="sxs-lookup"><span data-stu-id="28a1b-124">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="28a1b-125">Para um literal inteiro sem sufixo de tipo:</span><span class="sxs-lookup"><span data-stu-id="28a1b-125">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="28a1b-126">Se o valor puder ser representado por tipo `[int]` , que é seu tipo.</span><span class="sxs-lookup"><span data-stu-id="28a1b-126">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="28a1b-127">Caso contrário, se o valor puder ser representado pelo tipo `[long]` , esse será seu tipo.</span><span class="sxs-lookup"><span data-stu-id="28a1b-127">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="28a1b-128">Caso contrário, se o valor puder ser representado pelo tipo `[decimal]` , esse será seu tipo.</span><span class="sxs-lookup"><span data-stu-id="28a1b-128">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="28a1b-129">Caso contrário, ele é representado por tipo `[double]` .</span><span class="sxs-lookup"><span data-stu-id="28a1b-129">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="28a1b-130">Para um literal inteiro com um sufixo de tipo:</span><span class="sxs-lookup"><span data-stu-id="28a1b-130">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="28a1b-131">Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[int]` , seu tipo será `[int]` .</span><span class="sxs-lookup"><span data-stu-id="28a1b-131">If the type suffix is `u` and the value can be represented by type `[int]` then its type is `[int]`.</span></span>
- <span data-ttu-id="28a1b-132">Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[long]` , seu tipo será `[long]` .</span><span class="sxs-lookup"><span data-stu-id="28a1b-132">If the type suffix is `u` and the value can be represented by type `[long]` then its type is `[long]`.</span></span>
- <span data-ttu-id="28a1b-133">Se seu valor puder ser representado pelo tipo especificado, esse é seu tipo.</span><span class="sxs-lookup"><span data-stu-id="28a1b-133">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="28a1b-134">Caso contrário, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="28a1b-134">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="28a1b-135">Literais reais</span><span class="sxs-lookup"><span data-stu-id="28a1b-135">Real literals</span></span>

<span data-ttu-id="28a1b-136">Os literais reais só podem ser gravados em notação decimal.</span><span class="sxs-lookup"><span data-stu-id="28a1b-136">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="28a1b-137">Essa notação pode incluir valores fracionários após um ponto decimal e notação científica usando uma parte exponencial.</span><span class="sxs-lookup"><span data-stu-id="28a1b-137">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="28a1b-138">A parte exponencial inclui um ' e ' seguido por um sinal opcional (+/-) e um número que representa o expoente.</span><span class="sxs-lookup"><span data-stu-id="28a1b-138">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="28a1b-139">Por exemplo, o valor literal `1e2` é igual ao valor numérico 100.</span><span class="sxs-lookup"><span data-stu-id="28a1b-139">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="28a1b-140">Os literais reais podem ter um sufixo de tipo e um sufixo de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="28a1b-140">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="28a1b-141">Sufixo</span><span class="sxs-lookup"><span data-stu-id="28a1b-141">Suffix</span></span> |       <span data-ttu-id="28a1b-142">Significado</span><span class="sxs-lookup"><span data-stu-id="28a1b-142">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="28a1b-143">d</span><span class="sxs-lookup"><span data-stu-id="28a1b-143">d</span></span>      | <span data-ttu-id="28a1b-144">tipo de dados decimal</span><span class="sxs-lookup"><span data-stu-id="28a1b-144">decimal data type</span></span>   |
| <span data-ttu-id="28a1b-145">kb</span><span class="sxs-lookup"><span data-stu-id="28a1b-145">kb</span></span>     | <span data-ttu-id="28a1b-146">multiplicador de kilobytes</span><span class="sxs-lookup"><span data-stu-id="28a1b-146">kilobyte multiplier</span></span> |
| <span data-ttu-id="28a1b-147">mb</span><span class="sxs-lookup"><span data-stu-id="28a1b-147">mb</span></span>     | <span data-ttu-id="28a1b-148">multiplicador de megabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-148">megabyte multiplier</span></span> |
| <span data-ttu-id="28a1b-149">Reino</span><span class="sxs-lookup"><span data-stu-id="28a1b-149">gb</span></span>     | <span data-ttu-id="28a1b-150">multiplicador de Gigabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-150">gigabyte multiplier</span></span> |
| <span data-ttu-id="28a1b-151">TB</span><span class="sxs-lookup"><span data-stu-id="28a1b-151">tb</span></span>     | <span data-ttu-id="28a1b-152">multiplicador de terabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-152">terabyte multiplier</span></span> |
| <span data-ttu-id="28a1b-153">PB</span><span class="sxs-lookup"><span data-stu-id="28a1b-153">pb</span></span>     | <span data-ttu-id="28a1b-154">multiplicador petabyte</span><span class="sxs-lookup"><span data-stu-id="28a1b-154">petabyte multiplier</span></span> |

<span data-ttu-id="28a1b-155">Há dois tipos de literal real: Double e decimal.</span><span class="sxs-lookup"><span data-stu-id="28a1b-155">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="28a1b-156">Eles são indicados pela ausência ou presença, respectivamente, do sufixo de tipo decimal.</span><span class="sxs-lookup"><span data-stu-id="28a1b-156">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="28a1b-157">O PowerShell não dá suporte a uma representação literal de um `[float]` valor.</span><span class="sxs-lookup"><span data-stu-id="28a1b-157">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="28a1b-158">Um literal real duplo tem tipo `[double]` .</span><span class="sxs-lookup"><span data-stu-id="28a1b-158">A double real literal has type `[double]`.</span></span> <span data-ttu-id="28a1b-159">Um literal real decimal tem tipo `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="28a1b-159">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="28a1b-160">Zeros à direita na parte fracionária de um literal real decimal são significativos.</span><span class="sxs-lookup"><span data-stu-id="28a1b-160">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="28a1b-161">Se o valor dos dígitos da parte exponencial em um `[double]` literal real for menor que o mínimo suportado, o valor desse `[double]` literal real será 0.</span><span class="sxs-lookup"><span data-stu-id="28a1b-161">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="28a1b-162">Se o valor dos dígitos da parte exponencial em um `[decimal]` literal real for menor que o mínimo suportado, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="28a1b-162">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="28a1b-163">Se o valor dos dígitos da parte exponencial em um `[double]` ou `[decimal]` literal real for maior que o máximo suportado, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="28a1b-163">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="28a1b-164">A sintaxe permite que um literal real duplo tenha um sufixo de tipo longo.</span><span class="sxs-lookup"><span data-stu-id="28a1b-164">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="28a1b-165">O PowerShell trata esse caso como um literal inteiro cujo valor é representado por tipo `[long]` .</span><span class="sxs-lookup"><span data-stu-id="28a1b-165">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="28a1b-166">Esse recurso foi retido para compatibilidade com versões anteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28a1b-166">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="28a1b-167">No entanto, os programadores são desencorajados de usar literais inteiros desse formulário, pois podem facilmente obscurecer o valor real do literal.</span><span class="sxs-lookup"><span data-stu-id="28a1b-167">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="28a1b-168">Por exemplo, `1.2L` tem o valor 1, `1.2345e1L` tem o valor 12 e `1.2345e-5L` tem o valor 0, nenhum dos quais é imediatamente óbvio.</span><span class="sxs-lookup"><span data-stu-id="28a1b-168">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="28a1b-169">Multiplicadores numéricos</span><span class="sxs-lookup"><span data-stu-id="28a1b-169">Numeric multipliers</span></span>

<span data-ttu-id="28a1b-170">Para conveniência, inteiros e literais reais podem conter um multiplicador numérico, que indica um de um conjunto de potências usadas com frequência de 2.</span><span class="sxs-lookup"><span data-stu-id="28a1b-170">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="28a1b-171">O multiplicador numérico pode ser escrito em qualquer combinação de letras maiúsculas ou minúsculas.</span><span class="sxs-lookup"><span data-stu-id="28a1b-171">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="28a1b-172">Os sufixos de multiplicador podem ser usados em combinação com os `u` `ul` `l` sufixos, e de tipo.</span><span class="sxs-lookup"><span data-stu-id="28a1b-172">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="28a1b-173">Exemplos de multiplicador</span><span class="sxs-lookup"><span data-stu-id="28a1b-173">Multiplier examples</span></span>

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a><span data-ttu-id="28a1b-174">Aceleradores de tipo numérico</span><span class="sxs-lookup"><span data-stu-id="28a1b-174">Numeric type accelerators</span></span>

<span data-ttu-id="28a1b-175">O PowerShell dá suporte aos seguintes aceleradores de tipos:</span><span class="sxs-lookup"><span data-stu-id="28a1b-175">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="28a1b-176">Acelerador</span><span class="sxs-lookup"><span data-stu-id="28a1b-176">Accelerator</span></span> |         <span data-ttu-id="28a1b-177">Observação</span><span class="sxs-lookup"><span data-stu-id="28a1b-177">Note</span></span>         |           <span data-ttu-id="28a1b-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="28a1b-178">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="28a1b-179">Byte (não assinado)</span><span class="sxs-lookup"><span data-stu-id="28a1b-179">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="28a1b-180">Byte (assinado)</span><span class="sxs-lookup"><span data-stu-id="28a1b-180">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="28a1b-181">inteiro de 16 bits</span><span class="sxs-lookup"><span data-stu-id="28a1b-181">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="28a1b-182">inteiro de 16 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="28a1b-182">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="28a1b-183">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="28a1b-183">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="28a1b-184">alias para `[int32]`</span><span class="sxs-lookup"><span data-stu-id="28a1b-184">alias for `[int32]`</span></span>  | <span data-ttu-id="28a1b-185">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="28a1b-185">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="28a1b-186">inteiro de 32 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="28a1b-186">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="28a1b-187">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="28a1b-187">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="28a1b-188">alias para `[int64]`</span><span class="sxs-lookup"><span data-stu-id="28a1b-188">alias for `[int64]`</span></span>  | <span data-ttu-id="28a1b-189">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="28a1b-189">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="28a1b-190">inteiro de 64 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="28a1b-190">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="28a1b-191">Consulte a [estrutura BigInteger][bigint]</span><span class="sxs-lookup"><span data-stu-id="28a1b-191">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="28a1b-192">Ponto flutuante de precisão única</span><span class="sxs-lookup"><span data-stu-id="28a1b-192">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="28a1b-193">alias para `[single]`</span><span class="sxs-lookup"><span data-stu-id="28a1b-193">alias for `[single]`</span></span> | <span data-ttu-id="28a1b-194">Ponto flutuante de precisão única</span><span class="sxs-lookup"><span data-stu-id="28a1b-194">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="28a1b-195">Ponto flutuante de precisão dupla</span><span class="sxs-lookup"><span data-stu-id="28a1b-195">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="28a1b-196">ponto flutuante de 128 bits</span><span class="sxs-lookup"><span data-stu-id="28a1b-196">128-bit floating point</span></span>           |

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="28a1b-197">Trabalhando com outros tipos numéricos</span><span class="sxs-lookup"><span data-stu-id="28a1b-197">Working with other numeric types</span></span>

<span data-ttu-id="28a1b-198">Para trabalhar com qualquer outro tipo numérico, você deve usar aceleradores de tipo, que não está sem alguns problemas.</span><span class="sxs-lookup"><span data-stu-id="28a1b-198">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="28a1b-199">Por exemplo, valores inteiros altos são sempre analisados como Double antes de serem convertidos em qualquer outro tipo.</span><span class="sxs-lookup"><span data-stu-id="28a1b-199">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="28a1b-200">O valor é analisado como um duplo primeiro, perdendo a precisão nos intervalos mais altos.</span><span class="sxs-lookup"><span data-stu-id="28a1b-200">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="28a1b-201">Para evitar esse problema, insira valores como cadeias de caracteres e, em seguida, converta-os:</span><span class="sxs-lookup"><span data-stu-id="28a1b-201">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="28a1b-202">Exemplos</span><span class="sxs-lookup"><span data-stu-id="28a1b-202">Examples</span></span>

<span data-ttu-id="28a1b-203">A tabela a seguir contém vários exemplos de literais numéricos e lista seu tipo e valor:</span><span class="sxs-lookup"><span data-stu-id="28a1b-203">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="28a1b-204">Número</span><span class="sxs-lookup"><span data-stu-id="28a1b-204">Number</span></span>  |  <span data-ttu-id="28a1b-205">Tipo</span><span class="sxs-lookup"><span data-stu-id="28a1b-205">Type</span></span>   |    <span data-ttu-id="28a1b-206">Valor</span><span class="sxs-lookup"><span data-stu-id="28a1b-206">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="28a1b-207">100</span><span class="sxs-lookup"><span data-stu-id="28a1b-207">100</span></span> | <span data-ttu-id="28a1b-208">Int32</span><span class="sxs-lookup"><span data-stu-id="28a1b-208">Int32</span></span>   |          <span data-ttu-id="28a1b-209">100</span><span class="sxs-lookup"><span data-stu-id="28a1b-209">100</span></span> |
|     <span data-ttu-id="28a1b-210">100D</span><span class="sxs-lookup"><span data-stu-id="28a1b-210">100D</span></span> | <span data-ttu-id="28a1b-211">Decimal</span><span class="sxs-lookup"><span data-stu-id="28a1b-211">Decimal</span></span> |          <span data-ttu-id="28a1b-212">100</span><span class="sxs-lookup"><span data-stu-id="28a1b-212">100</span></span> |
|     <span data-ttu-id="28a1b-213">100l</span><span class="sxs-lookup"><span data-stu-id="28a1b-213">100l</span></span> | <span data-ttu-id="28a1b-214">Int64</span><span class="sxs-lookup"><span data-stu-id="28a1b-214">Int64</span></span>   |          <span data-ttu-id="28a1b-215">100</span><span class="sxs-lookup"><span data-stu-id="28a1b-215">100</span></span> |
|      <span data-ttu-id="28a1b-216">1e2</span><span class="sxs-lookup"><span data-stu-id="28a1b-216">1e2</span></span> | <span data-ttu-id="28a1b-217">Duplo</span><span class="sxs-lookup"><span data-stu-id="28a1b-217">Double</span></span>  |          <span data-ttu-id="28a1b-218">100</span><span class="sxs-lookup"><span data-stu-id="28a1b-218">100</span></span> |
|     <span data-ttu-id="28a1b-219">1. E2</span><span class="sxs-lookup"><span data-stu-id="28a1b-219">1.e2</span></span> | <span data-ttu-id="28a1b-220">Duplo</span><span class="sxs-lookup"><span data-stu-id="28a1b-220">Double</span></span>  |          <span data-ttu-id="28a1b-221">100</span><span class="sxs-lookup"><span data-stu-id="28a1b-221">100</span></span> |
|    <span data-ttu-id="28a1b-222">0x1e2</span><span class="sxs-lookup"><span data-stu-id="28a1b-222">0x1e2</span></span> | <span data-ttu-id="28a1b-223">Int32</span><span class="sxs-lookup"><span data-stu-id="28a1b-223">Int32</span></span>   |          <span data-ttu-id="28a1b-224">482</span><span class="sxs-lookup"><span data-stu-id="28a1b-224">482</span></span> |
|   <span data-ttu-id="28a1b-225">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="28a1b-225">0x1e2L</span></span> | <span data-ttu-id="28a1b-226">Int64</span><span class="sxs-lookup"><span data-stu-id="28a1b-226">Int64</span></span>   |          <span data-ttu-id="28a1b-227">482</span><span class="sxs-lookup"><span data-stu-id="28a1b-227">482</span></span> |
|   <span data-ttu-id="28a1b-228">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="28a1b-228">0x1e2D</span></span> | <span data-ttu-id="28a1b-229">Int32</span><span class="sxs-lookup"><span data-stu-id="28a1b-229">Int32</span></span>   |         <span data-ttu-id="28a1b-230">7725</span><span class="sxs-lookup"><span data-stu-id="28a1b-230">7725</span></span> |
|     <span data-ttu-id="28a1b-231">482D</span><span class="sxs-lookup"><span data-stu-id="28a1b-231">482D</span></span> | <span data-ttu-id="28a1b-232">Decimal</span><span class="sxs-lookup"><span data-stu-id="28a1b-232">Decimal</span></span> |          <span data-ttu-id="28a1b-233">482</span><span class="sxs-lookup"><span data-stu-id="28a1b-233">482</span></span> |
|    <span data-ttu-id="28a1b-234">482gb</span><span class="sxs-lookup"><span data-stu-id="28a1b-234">482gb</span></span> | <span data-ttu-id="28a1b-235">Int64</span><span class="sxs-lookup"><span data-stu-id="28a1b-235">Int64</span></span>   | <span data-ttu-id="28a1b-236">517543559168</span><span class="sxs-lookup"><span data-stu-id="28a1b-236">517543559168</span></span> |
| <span data-ttu-id="28a1b-237">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="28a1b-237">0x1e2lgb</span></span> | <span data-ttu-id="28a1b-238">Int64</span><span class="sxs-lookup"><span data-stu-id="28a1b-238">Int64</span></span>   | <span data-ttu-id="28a1b-239">517543559168</span><span class="sxs-lookup"><span data-stu-id="28a1b-239">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="28a1b-240">Comandos que se parecem com literais numéricos</span><span class="sxs-lookup"><span data-stu-id="28a1b-240">Commands that look like numeric literals</span></span>

<span data-ttu-id="28a1b-241">Qualquer comando que se pareça com um literal numérico deve ser executado usando o operador Call ( `&` ), caso contrário, ele será interpretado como um número do tipo associado.</span><span class="sxs-lookup"><span data-stu-id="28a1b-241">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="28a1b-242">Acessar propriedades e métodos de objetos numéricos</span><span class="sxs-lookup"><span data-stu-id="28a1b-242">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="28a1b-243">Para acessar um membro de um literal numérico, há casos em que você precisa colocar o literal entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="28a1b-243">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="28a1b-244">O literal não tem um ponto decimal</span><span class="sxs-lookup"><span data-stu-id="28a1b-244">The literal does not have a decimal point</span></span>
- <span data-ttu-id="28a1b-245">O literal não tem nenhum dígito após o ponto decimal</span><span class="sxs-lookup"><span data-stu-id="28a1b-245">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="28a1b-246">O literal não tem um sufixo</span><span class="sxs-lookup"><span data-stu-id="28a1b-246">The literal does not have a suffix</span></span>

<span data-ttu-id="28a1b-247">Por exemplo, o exemplo a seguir falha:</span><span class="sxs-lookup"><span data-stu-id="28a1b-247">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="28a1b-248">Os exemplos a seguir funcionam:</span><span class="sxs-lookup"><span data-stu-id="28a1b-248">The following examples work:</span></span>

```
PS> 2L.GetType().Name
Int64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="28a1b-249">Os dois primeiros exemplos funcionam sem colocar o valor literal entre parênteses porque o analisador do PowerShell pode determinar onde o literal numérico termina e o método **GetType** é iniciado.</span><span class="sxs-lookup"><span data-stu-id="28a1b-249">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
