---
description: Tanto o inteiro quanto os literais numéricos reais podem ter os sufixos tipo e multiplicador.
Locale: en-US
ms.date: 04/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre literais numéricos
ms.openlocfilehash: 19ed71c2571a6cd343adf622a8cf71d6e5589aff
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354976"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="6ce9b-103">Sobre literais numéricos</span><span class="sxs-lookup"><span data-stu-id="6ce9b-103">About numeric literals</span></span>

<span data-ttu-id="6ce9b-104">Há dois tipos de literais numéricos: inteiro e real.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="6ce9b-105">Ambos podem ter um tipo e sufixos de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="6ce9b-106">Literais inteiros</span><span class="sxs-lookup"><span data-stu-id="6ce9b-106">Integer literals</span></span>

<span data-ttu-id="6ce9b-107">Os literais inteiros podem ser gravados em notação decimal, hexadecimal ou binária.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-107">Integer literals can be written in decimal, hexadecimal, or binary notation.</span></span>
<span data-ttu-id="6ce9b-108">Os literais hexadecimais são prefixados com `0x` e os literais binários são prefixados com `0b` para diferenciá-los de números decimais.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-108">Hexadecimal literals are prefixed with `0x` and binary literals are prefixed with `0b` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="6ce9b-109">Os literais inteiros podem ter um sufixo de tipo e um sufixo de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="6ce9b-110">Sufixo</span><span class="sxs-lookup"><span data-stu-id="6ce9b-110">Suffix</span></span> |            <span data-ttu-id="6ce9b-111">Significado</span><span class="sxs-lookup"><span data-stu-id="6ce9b-111">Meaning</span></span>             |          <span data-ttu-id="6ce9b-112">Observação</span><span class="sxs-lookup"><span data-stu-id="6ce9b-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="6ce9b-113">s</span><span class="sxs-lookup"><span data-stu-id="6ce9b-113">y</span></span>      | <span data-ttu-id="6ce9b-114">tipo de dados byte assinado</span><span class="sxs-lookup"><span data-stu-id="6ce9b-114">signed byte data type</span></span>          | <span data-ttu-id="6ce9b-115">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="6ce9b-116">uy</span><span class="sxs-lookup"><span data-stu-id="6ce9b-116">uy</span></span>     | <span data-ttu-id="6ce9b-117">tipo de dados byte não assinado</span><span class="sxs-lookup"><span data-stu-id="6ce9b-117">unsigned byte data type</span></span>        | <span data-ttu-id="6ce9b-118">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="6ce9b-119">s</span><span class="sxs-lookup"><span data-stu-id="6ce9b-119">s</span></span>      | <span data-ttu-id="6ce9b-120">tipo de dados curto</span><span class="sxs-lookup"><span data-stu-id="6ce9b-120">short data type</span></span>                | <span data-ttu-id="6ce9b-121">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="6ce9b-122">us</span><span class="sxs-lookup"><span data-stu-id="6ce9b-122">us</span></span>     | <span data-ttu-id="6ce9b-123">tipo de dados curto não assinado</span><span class="sxs-lookup"><span data-stu-id="6ce9b-123">unsigned short data type</span></span>       | <span data-ttu-id="6ce9b-124">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="6ce9b-125">l</span><span class="sxs-lookup"><span data-stu-id="6ce9b-125">l</span></span>      | <span data-ttu-id="6ce9b-126">tipo de dados Long</span><span class="sxs-lookup"><span data-stu-id="6ce9b-126">long data type</span></span>                 |                         |
| <span data-ttu-id="6ce9b-127">u</span><span class="sxs-lookup"><span data-stu-id="6ce9b-127">u</span></span>      | <span data-ttu-id="6ce9b-128">tipo de dados int ou Long não assinado</span><span class="sxs-lookup"><span data-stu-id="6ce9b-128">unsigned int or long data type</span></span> | <span data-ttu-id="6ce9b-129">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="6ce9b-130">UL</span><span class="sxs-lookup"><span data-stu-id="6ce9b-130">ul</span></span>     | <span data-ttu-id="6ce9b-131">tipo de dados Long não assinado</span><span class="sxs-lookup"><span data-stu-id="6ce9b-131">unsigned long data type</span></span>        | <span data-ttu-id="6ce9b-132">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="6ce9b-133">n</span><span class="sxs-lookup"><span data-stu-id="6ce9b-133">n</span></span>      | <span data-ttu-id="6ce9b-134">Tipo de dados BigInteger</span><span class="sxs-lookup"><span data-stu-id="6ce9b-134">BigInteger data type</span></span>           | <span data-ttu-id="6ce9b-135">Adicionado no PowerShell 7,0</span><span class="sxs-lookup"><span data-stu-id="6ce9b-135">Added in PowerShell 7.0</span></span> |
| <span data-ttu-id="6ce9b-136">kb</span><span class="sxs-lookup"><span data-stu-id="6ce9b-136">kb</span></span>     | <span data-ttu-id="6ce9b-137">multiplicador de kilobytes</span><span class="sxs-lookup"><span data-stu-id="6ce9b-137">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="6ce9b-138">mb</span><span class="sxs-lookup"><span data-stu-id="6ce9b-138">mb</span></span>     | <span data-ttu-id="6ce9b-139">multiplicador de megabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-139">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="6ce9b-140">Reino</span><span class="sxs-lookup"><span data-stu-id="6ce9b-140">gb</span></span>     | <span data-ttu-id="6ce9b-141">multiplicador de Gigabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-141">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="6ce9b-142">TB</span><span class="sxs-lookup"><span data-stu-id="6ce9b-142">tb</span></span>     | <span data-ttu-id="6ce9b-143">multiplicador de terabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-143">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="6ce9b-144">PB</span><span class="sxs-lookup"><span data-stu-id="6ce9b-144">pb</span></span>     | <span data-ttu-id="6ce9b-145">multiplicador petabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-145">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="6ce9b-146">O tipo de um inteiro literal é determinado por seu valor, o sufixo de tipo e o sufixo de multiplicador numérico.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-146">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="6ce9b-147">Para um literal inteiro sem sufixo de tipo:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-147">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="6ce9b-148">Se o valor puder ser representado por tipo `[int]` , que é seu tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-148">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="6ce9b-149">Caso contrário, se o valor puder ser representado pelo tipo `[long]` , esse será seu tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-149">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="6ce9b-150">Caso contrário, se o valor puder ser representado pelo tipo `[decimal]` , esse será seu tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-150">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="6ce9b-151">Caso contrário, ele é representado por tipo `[double]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-151">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="6ce9b-152">Para um literal inteiro com um sufixo de tipo:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-152">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="6ce9b-153">Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[uint]` , seu tipo será `[uint]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-153">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="6ce9b-154">Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[ulong]` , seu tipo será `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-154">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="6ce9b-155">Se seu valor puder ser representado pelo tipo especificado, esse é seu tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-155">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="6ce9b-156">Caso contrário, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-156">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="6ce9b-157">Literais reais</span><span class="sxs-lookup"><span data-stu-id="6ce9b-157">Real literals</span></span>

<span data-ttu-id="6ce9b-158">Os literais reais só podem ser gravados em notação decimal.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-158">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="6ce9b-159">Essa notação pode incluir valores fracionários após um ponto decimal e notação científica usando uma parte exponencial.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-159">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="6ce9b-160">A parte exponencial inclui um ' e ' seguido por um sinal opcional (+/-) e um número que representa o expoente.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-160">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="6ce9b-161">Por exemplo, o valor literal `1e2` é igual ao valor numérico 100.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-161">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="6ce9b-162">Os literais reais podem ter um sufixo de tipo e um sufixo de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-162">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="6ce9b-163">Sufixo</span><span class="sxs-lookup"><span data-stu-id="6ce9b-163">Suffix</span></span> |       <span data-ttu-id="6ce9b-164">Significado</span><span class="sxs-lookup"><span data-stu-id="6ce9b-164">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="6ce9b-165">d</span><span class="sxs-lookup"><span data-stu-id="6ce9b-165">d</span></span>      | <span data-ttu-id="6ce9b-166">tipo de dados decimal</span><span class="sxs-lookup"><span data-stu-id="6ce9b-166">decimal data type</span></span>   |
| <span data-ttu-id="6ce9b-167">kb</span><span class="sxs-lookup"><span data-stu-id="6ce9b-167">kb</span></span>     | <span data-ttu-id="6ce9b-168">multiplicador de kilobytes</span><span class="sxs-lookup"><span data-stu-id="6ce9b-168">kilobyte multiplier</span></span> |
| <span data-ttu-id="6ce9b-169">mb</span><span class="sxs-lookup"><span data-stu-id="6ce9b-169">mb</span></span>     | <span data-ttu-id="6ce9b-170">multiplicador de megabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-170">megabyte multiplier</span></span> |
| <span data-ttu-id="6ce9b-171">Reino</span><span class="sxs-lookup"><span data-stu-id="6ce9b-171">gb</span></span>     | <span data-ttu-id="6ce9b-172">multiplicador de Gigabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-172">gigabyte multiplier</span></span> |
| <span data-ttu-id="6ce9b-173">TB</span><span class="sxs-lookup"><span data-stu-id="6ce9b-173">tb</span></span>     | <span data-ttu-id="6ce9b-174">multiplicador de terabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-174">terabyte multiplier</span></span> |
| <span data-ttu-id="6ce9b-175">PB</span><span class="sxs-lookup"><span data-stu-id="6ce9b-175">pb</span></span>     | <span data-ttu-id="6ce9b-176">multiplicador petabyte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-176">petabyte multiplier</span></span> |

<span data-ttu-id="6ce9b-177">Há dois tipos de literal real: Double e decimal.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-177">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="6ce9b-178">Eles são indicados pela ausência ou presença, respectivamente, do sufixo de tipo decimal.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-178">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="6ce9b-179">O PowerShell não dá suporte a uma representação literal de um `[float]` valor.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-179">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="6ce9b-180">Um literal real duplo tem tipo `[double]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-180">A double real literal has type `[double]`.</span></span> <span data-ttu-id="6ce9b-181">Um literal real decimal tem tipo `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-181">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="6ce9b-182">Zeros à direita na parte fracionária de um literal real decimal são significativos.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-182">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="6ce9b-183">Se o valor dos dígitos da parte exponencial em um `[double]` literal real for menor que o mínimo suportado, o valor desse `[double]` literal real será 0.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-183">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="6ce9b-184">Se o valor dos dígitos da parte exponencial em um `[decimal]` literal real for menor que o mínimo suportado, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-184">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="6ce9b-185">Se o valor dos dígitos da parte exponencial em um `[double]` ou `[decimal]` literal real for maior que o máximo suportado, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-185">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce9b-186">A sintaxe permite que um literal real duplo tenha um sufixo de tipo longo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-186">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="6ce9b-187">O PowerShell trata esse caso como um literal inteiro cujo valor é representado por tipo `[long]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-187">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="6ce9b-188">Esse recurso foi retido para compatibilidade com versões anteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-188">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="6ce9b-189">No entanto, os programadores são desencorajados de usar literais inteiros desse formulário, pois podem facilmente obscurecer o valor real do literal.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-189">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="6ce9b-190">Por exemplo, `1.2L` tem o valor 1, `1.2345e1L` tem o valor 12 e `1.2345e-5L` tem o valor 0, nenhum dos quais é imediatamente óbvio.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-190">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="6ce9b-191">Multiplicadores numéricos</span><span class="sxs-lookup"><span data-stu-id="6ce9b-191">Numeric multipliers</span></span>

<span data-ttu-id="6ce9b-192">Para conveniência, inteiros e literais reais podem conter um multiplicador numérico, que indica um de um conjunto de potências usadas com frequência de 2.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-192">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="6ce9b-193">O multiplicador numérico pode ser escrito em qualquer combinação de letras maiúsculas ou minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-193">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="6ce9b-194">Os sufixos de multiplicador podem ser usados em combinação com quaisquer sufixos de tipo, mas devem estar presentes após o sufixo de tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-194">The multiplier suffixes can be used in combination with any type suffixes, but must be present after the type suffix.</span></span> <span data-ttu-id="6ce9b-195">Por exemplo, o literal `100gbL` está malformado, mas o literal `100Lgb` é válido.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-195">For example, the literal `100gbL` is malformed, but the literal `100Lgb` is valid.</span></span>

<span data-ttu-id="6ce9b-196">Se um multiplicador criar um valor que exceda os valores possíveis para o tipo numérico que o sufixo especifica, o literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-196">If a multiplier creates a value that exceeds the possible values for the numeric type that the suffix specifies, the literal is malformed.</span></span> <span data-ttu-id="6ce9b-197">Por exemplo, o literal `1usgb` está malformado, porque o valor é maior do que o `1gb` permitido para o `[ushort]` tipo especificado pelo `us` sufixo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-197">For example, the literal `1usgb` is malformed, because the value `1gb` is larger than what is permitted for the `[ushort]` type specified by the `us` suffix.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="6ce9b-198">Exemplos de multiplicador</span><span class="sxs-lookup"><span data-stu-id="6ce9b-198">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="6ce9b-199">Aceleradores de tipo numérico</span><span class="sxs-lookup"><span data-stu-id="6ce9b-199">Numeric type accelerators</span></span>

<span data-ttu-id="6ce9b-200">O PowerShell dá suporte aos seguintes aceleradores de tipos:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-200">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="6ce9b-201">Acelerador</span><span class="sxs-lookup"><span data-stu-id="6ce9b-201">Accelerator</span></span> |         <span data-ttu-id="6ce9b-202">Observação</span><span class="sxs-lookup"><span data-stu-id="6ce9b-202">Note</span></span>         |           <span data-ttu-id="6ce9b-203">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ce9b-203">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="6ce9b-204">Byte (não assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-204">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="6ce9b-205">Byte (assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-205">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="6ce9b-206">inteiro de 16 bits</span><span class="sxs-lookup"><span data-stu-id="6ce9b-206">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="6ce9b-207">alias para `[int16]`</span><span class="sxs-lookup"><span data-stu-id="6ce9b-207">alias for `[int16]`</span></span>  | <span data-ttu-id="6ce9b-208">inteiro de 16 bits</span><span class="sxs-lookup"><span data-stu-id="6ce9b-208">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="6ce9b-209">inteiro de 16 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-209">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="6ce9b-210">alias para `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="6ce9b-210">alias for `[uint16]`</span></span> | <span data-ttu-id="6ce9b-211">inteiro de 16 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-211">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="6ce9b-212">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="6ce9b-212">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="6ce9b-213">alias para `[int32]`</span><span class="sxs-lookup"><span data-stu-id="6ce9b-213">alias for `[int32]`</span></span>  | <span data-ttu-id="6ce9b-214">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="6ce9b-214">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="6ce9b-215">inteiro de 32 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-215">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="6ce9b-216">alias para `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="6ce9b-216">alias for `[uint32]`</span></span> | <span data-ttu-id="6ce9b-217">inteiro de 32 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-217">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="6ce9b-218">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="6ce9b-218">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="6ce9b-219">alias para `[int64]`</span><span class="sxs-lookup"><span data-stu-id="6ce9b-219">alias for `[int64]`</span></span>  | <span data-ttu-id="6ce9b-220">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="6ce9b-220">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="6ce9b-221">inteiro de 64 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-221">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="6ce9b-222">alias para `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="6ce9b-222">alias for `[uint64]`</span></span> | <span data-ttu-id="6ce9b-223">inteiro de 64 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-223">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="6ce9b-224">Consulte a [estrutura BigInteger][bigint]</span><span class="sxs-lookup"><span data-stu-id="6ce9b-224">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="6ce9b-225">Ponto flutuante de precisão única</span><span class="sxs-lookup"><span data-stu-id="6ce9b-225">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="6ce9b-226">alias para `[single]`</span><span class="sxs-lookup"><span data-stu-id="6ce9b-226">alias for `[single]`</span></span> | <span data-ttu-id="6ce9b-227">Ponto flutuante de precisão única</span><span class="sxs-lookup"><span data-stu-id="6ce9b-227">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="6ce9b-228">Ponto flutuante de precisão dupla</span><span class="sxs-lookup"><span data-stu-id="6ce9b-228">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="6ce9b-229">ponto flutuante de 128 bits</span><span class="sxs-lookup"><span data-stu-id="6ce9b-229">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="6ce9b-230">Os seguintes aceleradores de tipos foram adicionados no PowerShell 6,2: `[short]` ,, `[ushort]` `[uint]` , `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-230">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

## <a name="examples"></a><span data-ttu-id="6ce9b-231">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6ce9b-231">Examples</span></span>

<span data-ttu-id="6ce9b-232">A tabela a seguir contém vários exemplos de literais numéricos e lista seu tipo e valor:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-232">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|   <span data-ttu-id="6ce9b-233">Número</span><span class="sxs-lookup"><span data-stu-id="6ce9b-233">Number</span></span>    |    <span data-ttu-id="6ce9b-234">Tipo</span><span class="sxs-lookup"><span data-stu-id="6ce9b-234">Type</span></span>    |    <span data-ttu-id="6ce9b-235">Valor</span><span class="sxs-lookup"><span data-stu-id="6ce9b-235">Value</span></span>     |
| ----------: | ---------- | -----------: |
|         <span data-ttu-id="6ce9b-236">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-236">100</span></span> | <span data-ttu-id="6ce9b-237">Int32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-237">Int32</span></span>      |          <span data-ttu-id="6ce9b-238">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-238">100</span></span> |
|        <span data-ttu-id="6ce9b-239">100u</span><span class="sxs-lookup"><span data-stu-id="6ce9b-239">100u</span></span> | <span data-ttu-id="6ce9b-240">UInt32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-240">UInt32</span></span>     |          <span data-ttu-id="6ce9b-241">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-241">100</span></span> |
|        <span data-ttu-id="6ce9b-242">100D</span><span class="sxs-lookup"><span data-stu-id="6ce9b-242">100D</span></span> | <span data-ttu-id="6ce9b-243">Decimal</span><span class="sxs-lookup"><span data-stu-id="6ce9b-243">Decimal</span></span>    |          <span data-ttu-id="6ce9b-244">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-244">100</span></span> |
|        <span data-ttu-id="6ce9b-245">100l</span><span class="sxs-lookup"><span data-stu-id="6ce9b-245">100l</span></span> | <span data-ttu-id="6ce9b-246">Int64</span><span class="sxs-lookup"><span data-stu-id="6ce9b-246">Int64</span></span>      |          <span data-ttu-id="6ce9b-247">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-247">100</span></span> |
|       <span data-ttu-id="6ce9b-248">100uL</span><span class="sxs-lookup"><span data-stu-id="6ce9b-248">100uL</span></span> | <span data-ttu-id="6ce9b-249">UInt64</span><span class="sxs-lookup"><span data-stu-id="6ce9b-249">UInt64</span></span>     |          <span data-ttu-id="6ce9b-250">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-250">100</span></span> |
|       <span data-ttu-id="6ce9b-251">100us</span><span class="sxs-lookup"><span data-stu-id="6ce9b-251">100us</span></span> | <span data-ttu-id="6ce9b-252">UInt16</span><span class="sxs-lookup"><span data-stu-id="6ce9b-252">UInt16</span></span>     |          <span data-ttu-id="6ce9b-253">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-253">100</span></span> |
|       <span data-ttu-id="6ce9b-254">100uy</span><span class="sxs-lookup"><span data-stu-id="6ce9b-254">100uy</span></span> | <span data-ttu-id="6ce9b-255">Byte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-255">Byte</span></span>       |          <span data-ttu-id="6ce9b-256">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-256">100</span></span> |
|        <span data-ttu-id="6ce9b-257">100y</span><span class="sxs-lookup"><span data-stu-id="6ce9b-257">100y</span></span> | <span data-ttu-id="6ce9b-258">SByte</span><span class="sxs-lookup"><span data-stu-id="6ce9b-258">SByte</span></span>      |          <span data-ttu-id="6ce9b-259">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-259">100</span></span> |
|         <span data-ttu-id="6ce9b-260">1e2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-260">1e2</span></span> | <span data-ttu-id="6ce9b-261">Duplo</span><span class="sxs-lookup"><span data-stu-id="6ce9b-261">Double</span></span>     |          <span data-ttu-id="6ce9b-262">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-262">100</span></span> |
|        <span data-ttu-id="6ce9b-263">1. E2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-263">1.e2</span></span> | <span data-ttu-id="6ce9b-264">Duplo</span><span class="sxs-lookup"><span data-stu-id="6ce9b-264">Double</span></span>     |          <span data-ttu-id="6ce9b-265">100</span><span class="sxs-lookup"><span data-stu-id="6ce9b-265">100</span></span> |
|       <span data-ttu-id="6ce9b-266">0x1e2</span><span class="sxs-lookup"><span data-stu-id="6ce9b-266">0x1e2</span></span> | <span data-ttu-id="6ce9b-267">Int32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-267">Int32</span></span>      |          <span data-ttu-id="6ce9b-268">482</span><span class="sxs-lookup"><span data-stu-id="6ce9b-268">482</span></span> |
|      <span data-ttu-id="6ce9b-269">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="6ce9b-269">0x1e2L</span></span> | <span data-ttu-id="6ce9b-270">Int64</span><span class="sxs-lookup"><span data-stu-id="6ce9b-270">Int64</span></span>      |          <span data-ttu-id="6ce9b-271">482</span><span class="sxs-lookup"><span data-stu-id="6ce9b-271">482</span></span> |
|      <span data-ttu-id="6ce9b-272">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="6ce9b-272">0x1e2D</span></span> | <span data-ttu-id="6ce9b-273">Int32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-273">Int32</span></span>      |         <span data-ttu-id="6ce9b-274">7725</span><span class="sxs-lookup"><span data-stu-id="6ce9b-274">7725</span></span> |
|        <span data-ttu-id="6ce9b-275">482D</span><span class="sxs-lookup"><span data-stu-id="6ce9b-275">482D</span></span> | <span data-ttu-id="6ce9b-276">Decimal</span><span class="sxs-lookup"><span data-stu-id="6ce9b-276">Decimal</span></span>    |          <span data-ttu-id="6ce9b-277">482</span><span class="sxs-lookup"><span data-stu-id="6ce9b-277">482</span></span> |
|       <span data-ttu-id="6ce9b-278">482gb</span><span class="sxs-lookup"><span data-stu-id="6ce9b-278">482gb</span></span> | <span data-ttu-id="6ce9b-279">Int64</span><span class="sxs-lookup"><span data-stu-id="6ce9b-279">Int64</span></span>      | <span data-ttu-id="6ce9b-280">517543559168</span><span class="sxs-lookup"><span data-stu-id="6ce9b-280">517543559168</span></span> |
|      <span data-ttu-id="6ce9b-281">482ngb</span><span class="sxs-lookup"><span data-stu-id="6ce9b-281">482ngb</span></span> | <span data-ttu-id="6ce9b-282">BigInteger</span><span class="sxs-lookup"><span data-stu-id="6ce9b-282">BigInteger</span></span> | <span data-ttu-id="6ce9b-283">517543559168</span><span class="sxs-lookup"><span data-stu-id="6ce9b-283">517543559168</span></span> |
|    <span data-ttu-id="6ce9b-284">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="6ce9b-284">0x1e2lgb</span></span> | <span data-ttu-id="6ce9b-285">Int64</span><span class="sxs-lookup"><span data-stu-id="6ce9b-285">Int64</span></span>      | <span data-ttu-id="6ce9b-286">517543559168</span><span class="sxs-lookup"><span data-stu-id="6ce9b-286">517543559168</span></span> |
|   <span data-ttu-id="6ce9b-287">0b1011011</span><span class="sxs-lookup"><span data-stu-id="6ce9b-287">0b1011011</span></span> | <span data-ttu-id="6ce9b-288">Int32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-288">Int32</span></span>      |           <span data-ttu-id="6ce9b-289">91</span><span class="sxs-lookup"><span data-stu-id="6ce9b-289">91</span></span> |
|     <span data-ttu-id="6ce9b-290">0xFFFFs</span><span class="sxs-lookup"><span data-stu-id="6ce9b-290">0xFFFFs</span></span> | <span data-ttu-id="6ce9b-291">Int16</span><span class="sxs-lookup"><span data-stu-id="6ce9b-291">Int16</span></span>      |           <span data-ttu-id="6ce9b-292">-1</span><span class="sxs-lookup"><span data-stu-id="6ce9b-292">-1</span></span> |
|  <span data-ttu-id="6ce9b-293">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="6ce9b-293">0xFFFFFFFF</span></span> | <span data-ttu-id="6ce9b-294">Int32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-294">Int32</span></span>      |           <span data-ttu-id="6ce9b-295">-1</span><span class="sxs-lookup"><span data-stu-id="6ce9b-295">-1</span></span> |
| <span data-ttu-id="6ce9b-296">-0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="6ce9b-296">-0xFFFFFFFF</span></span> | <span data-ttu-id="6ce9b-297">Int32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-297">Int32</span></span>      |            <span data-ttu-id="6ce9b-298">1</span><span class="sxs-lookup"><span data-stu-id="6ce9b-298">1</span></span> |
| <span data-ttu-id="6ce9b-299">0xFFFFFFFFu</span><span class="sxs-lookup"><span data-stu-id="6ce9b-299">0xFFFFFFFFu</span></span> | <span data-ttu-id="6ce9b-300">UInt32</span><span class="sxs-lookup"><span data-stu-id="6ce9b-300">UInt32</span></span>     |   <span data-ttu-id="6ce9b-301">4294967295</span><span class="sxs-lookup"><span data-stu-id="6ce9b-301">4294967295</span></span> |

### <a name="working-with-binary-or-hexadecimal-numbers"></a><span data-ttu-id="6ce9b-302">Trabalhando com números binários ou hexadecimais</span><span class="sxs-lookup"><span data-stu-id="6ce9b-302">Working with binary or hexadecimal numbers</span></span>

<span data-ttu-id="6ce9b-303">Os literais binários ou hexadecimais excessivamente grandes podem retornar como `[bigint]` em vez de falhar na análise, se e somente se o `n` sufixo for especificado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-303">Overly large binary or hexadecimal literals can return as `[bigint]` rather than failing the parse, if and only if the `n` suffix is specified.</span></span> <span data-ttu-id="6ce9b-304">No entanto, os bits de sinal ainda são respeitados acima dos `[decimal]` intervalos pares:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-304">Sign bits are still respected above even `[decimal]` ranges, however:</span></span>

- <span data-ttu-id="6ce9b-305">Se uma cadeia de caracteres binária for de um múltiplo de 8 bits de comprimento, o bit mais alto será tratado como o bit de sinal.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-305">If a binary string is some multiple of 8 bits long, the highest bit is treated as the sign bit.</span></span>
- <span data-ttu-id="6ce9b-306">Se uma cadeia de caracteres hexadecimal, que tem um comprimento múltiplo de 8, tiver o primeiro dígito com 8 ou superior, o numeral será tratado como negativo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-306">If a hex string, which has a length that is a multiple of 8, has the first digit with 8 or higher, the numeral is treated as negative.</span></span>

<span data-ttu-id="6ce9b-307">A especificação de um sufixo não assinado em literais binários e hexadecimais ignora o sinal de bits.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-307">Specifying an unsigned suffix on binary and hex literals ignores sign bits.</span></span> <span data-ttu-id="6ce9b-308">Por exemplo, `0xFFFFFFFF` retorna `-1` , mas `0xFFFFFFFFu` retorna o `[uint]::MaxValue` de 4294967295.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-308">For example, `0xFFFFFFFF` returns `-1`, but `0xFFFFFFFFu` returns the `[uint]::MaxValue` of 4294967295.</span></span>

<span data-ttu-id="6ce9b-309">No PowerShell 7,1, o uso de um sufixo de tipo em um literal hexadecimal agora retorna um valor assinado desse tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-309">In PowerShell 7.1, using a type suffix on a hex literal now returns a signed value of that type.</span></span> <span data-ttu-id="6ce9b-310">Por exemplo, no PowerShell 7,0, a expressão `0xFFFFs` retorna um erro porque o valor positivo é muito grande para um `[int16]` tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-310">For example, in PowerShell 7.0 the expression `0xFFFFs` returns an error because the positive value is too large for an `[int16]` type.</span></span>
<span data-ttu-id="6ce9b-311">O PowerShell 7,1 interpreta isso como `-1` é um `[int16]` tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-311">PowerShell 7.1 interprets this as `-1` that is an `[int16]` type.</span></span>

<span data-ttu-id="6ce9b-312">A prefixação do literal com um `0` irá ignorá-lo e ser tratado como não assinado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-312">Prefixing the literal with a `0` will bypass this and be treated as unsigned.</span></span>
<span data-ttu-id="6ce9b-313">Por exemplo: `0b011111111`.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-313">For example: `0b011111111`.</span></span> <span data-ttu-id="6ce9b-314">Isso pode ser necessário ao trabalhar com literais no `[bigint]` intervalo, pois os `u` `n` sufixos e não podem ser combinados.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-314">This can be necessary when working with literals in the `[bigint]` range, as the `u` and `n` suffixes cannot be combined.</span></span>

<span data-ttu-id="6ce9b-315">Você também pode negar literais binários e hexadecimais usando o `-` prefixo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-315">You can also negate binary and hex literals using the `-` prefix.</span></span> <span data-ttu-id="6ce9b-316">Isso pode resultar em um número positivo desde que os bits de sinal sejam permitidos.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-316">This can result in a positive number since sign bits are permitted.</span></span>

<span data-ttu-id="6ce9b-317">Os bits de sinal são aceitos para numerais com sufixo BigInteger:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-317">Sign bits are accepted for BigInteger-suffixed numerals:</span></span>

- <span data-ttu-id="6ce9b-318">O Hex com sufixo BigInteger trata o alto bit de qualquer literal com um comprimento múltiplo de 8 caracteres como o bit de sinal.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-318">BigInteger-suffixed hex treats the high bit of any literal with a length multiple of 8 characters as the sign bit.</span></span> <span data-ttu-id="6ce9b-319">O comprimento não inclui o `0x` prefixo ou quaisquer sufixos.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-319">The length does not include the `0x` prefix or any suffixes.</span></span>
- <span data-ttu-id="6ce9b-320">O binário BigInteger-suffix aceita a entrada de bits em 96 e 128 caracteres e a cada 8 caracteres após.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-320">BigInteger-suffixed binary accepts sign bits at 96 and 128 characters, and at every 8 characters after.</span></span>

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="6ce9b-321">Comandos que se parecem com literais numéricos</span><span class="sxs-lookup"><span data-stu-id="6ce9b-321">Commands that look like numeric literals</span></span>

<span data-ttu-id="6ce9b-322">Qualquer comando que se pareça com um literal numérico válido deve ser executado usando o operador Call ( `&` ), caso contrário, ele será interpretado como um número.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-322">Any command that looks like a valid numeric literal must be executed using the call operator (`&`), otherwise it is interpreted as a number.</span></span> <span data-ttu-id="6ce9b-323">Literais malformados com sintaxe válida `1usgb` , como resultarão no seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-323">Malformed literals with valid syntax like `1usgb` will result in the following error:</span></span>

```
PS> 1usgb
At line:1 char:6
+ 1usgb
+      ~
The numeric constant 1usgb is not valid.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : BadNumericConstant
```

<span data-ttu-id="6ce9b-324">No entanto, literais malformados com sintaxe inválida como `1gbus` serão interpretados como uma cadeia de caracteres Bare padrão e podem ser interpretados como um nome de comando válido em contextos onde os comandos podem ser chamados.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-324">However, malformed literals with invalid syntax like `1gbus` will be interpreted as a standard bare string, and can be interpreted as a valid command name in contexts where commands may be called.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="6ce9b-325">Acessar propriedades e métodos de objetos numéricos</span><span class="sxs-lookup"><span data-stu-id="6ce9b-325">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="6ce9b-326">Para acessar um membro de um literal numérico, há casos em que você precisa colocar o literal entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-326">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="6ce9b-327">O literal não tem um ponto decimal</span><span class="sxs-lookup"><span data-stu-id="6ce9b-327">The literal does not have a decimal point</span></span>
- <span data-ttu-id="6ce9b-328">O literal não tem nenhum dígito após o ponto decimal</span><span class="sxs-lookup"><span data-stu-id="6ce9b-328">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="6ce9b-329">O literal não tem um sufixo</span><span class="sxs-lookup"><span data-stu-id="6ce9b-329">The literal does not have a suffix</span></span>

<span data-ttu-id="6ce9b-330">Por exemplo, o exemplo a seguir falha:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-330">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="6ce9b-331">Os exemplos a seguir funcionam:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-331">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="6ce9b-332">Os dois primeiros exemplos funcionam sem colocar o valor literal entre parênteses porque o analisador do PowerShell pode determinar onde o literal numérico termina e o método **GetType** é iniciado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-332">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

## <a name="how-powershell-parses-numeric-literals"></a><span data-ttu-id="6ce9b-333">Como o PowerShell analisa literais numéricos</span><span class="sxs-lookup"><span data-stu-id="6ce9b-333">How PowerShell parses numeric literals</span></span>

<span data-ttu-id="6ce9b-334">O PowerShell v 7.0 mudou a forma como os literais numéricos são analisados para habilitar os novos recursos.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-334">PowerShell v7.0 changed the way numeric literals are parsed to enable the new features.</span></span>

### <a name="parsing-real-numeric-literals"></a><span data-ttu-id="6ce9b-335">Analisando literais numéricos reais</span><span class="sxs-lookup"><span data-stu-id="6ce9b-335">Parsing real numeric literals</span></span>

<span data-ttu-id="6ce9b-336">Se o literal contiver um ponto decimal ou a notação e-Notation, a cadeia de caracteres literal será analisada em um número real.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-336">If the literal contains a decimal point or the e-notation, the literal string is parsed a real number.</span></span>

- <span data-ttu-id="6ce9b-337">Se o sufixo decimal estiver presente diretamente no `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-337">If the decimal-suffix is present then directly into `[decimal]`.</span></span>
- <span data-ttu-id="6ce9b-338">Caso contrário, analise como `[Double]` e aplique multiplicador ao valor.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-338">Else, parse as `[Double]` and apply multiplier to the value.</span></span> <span data-ttu-id="6ce9b-339">Em seguida, verifique os sufixos de tipo e tente convertê-los no tipo apropriado.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-339">Then check the type suffixes and attempt to cast into appropriate type.</span></span>
- <span data-ttu-id="6ce9b-340">Se a cadeia de caracteres não tiver nenhum sufixo de tipo, analise como `[Double]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-340">If the string has no type suffix, then parse as `[Double]`.</span></span>

### <a name="paring-integer-numeric-literals"></a><span data-ttu-id="6ce9b-341">Literais numéricos de número inteiro emparelhamento</span><span class="sxs-lookup"><span data-stu-id="6ce9b-341">Paring integer numeric literals</span></span>

<span data-ttu-id="6ce9b-342">Os literais de tipo inteiro são analisados usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-342">Integer type literals are parsed using the following steps:</span></span>

1. <span data-ttu-id="6ce9b-343">Determinar o formato de base</span><span class="sxs-lookup"><span data-stu-id="6ce9b-343">Determine the radix format</span></span>
   - <span data-ttu-id="6ce9b-344">Para formatos binários, analise em `[BigInteger]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-344">For binary formats, parse into `[BigInteger]`.</span></span>
   - <span data-ttu-id="6ce9b-345">Para formatos hexadecimais, analise o `[BigInteger]` uso de Casies especiais para manter os comportamentos originais quando o valor estiver no `[int]` `[long]` intervalo ou.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-345">For hexidecimal formats, parse into `[BigInteger]` using special casies to retain original behaviours when the value is in the `[int]` or `[long]` range.</span></span>
   - <span data-ttu-id="6ce9b-346">Se nem binário nem Hex, analise normalmente como um `[BigInteger]` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-346">If neither binary nor hex, parse normally as a `[BigInteger]`.</span></span>
2. <span data-ttu-id="6ce9b-347">Aplique o valor de multiplicador antes de tentar qualquer conversão para garantir que os limites de tipo possam ser verificados adequadamente sem estouros.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-347">Apply the multiplier value before attempting any casts to ensure type bounds can be appropriately checked without overflows.</span></span>
3. <span data-ttu-id="6ce9b-348">Verifique os sufixos de tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-348">Check type suffixes.</span></span>
   - <span data-ttu-id="6ce9b-349">Verifique os limites de tipo e tente analisar nesse tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-349">Check type bounds and attempt to parse into that type.</span></span>
   - <span data-ttu-id="6ce9b-350">Se nenhum sufixo for usado, o valor será associado, marcado na seguinte ordem, resultando no primeiro teste bem-sucedido que determina o tipo do número.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-350">If no suffix is used, then the value is bounds-checked in the following order, resulting in the first successful test determining the type of the number.</span></span>
     - `[int]`
     - `[long]`
     - <span data-ttu-id="6ce9b-351">`[decimal]` (somente literais de base 10)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-351">`[decimal]` (base-10 literals only)</span></span>
     - <span data-ttu-id="6ce9b-352">`[double]` (somente literais de base 10)</span><span class="sxs-lookup"><span data-stu-id="6ce9b-352">`[double]` (base-10 literals only)</span></span>
   - <span data-ttu-id="6ce9b-353">Se o valor estiver fora do `[long]` intervalo para números Hex e binários, a análise falhará.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-353">If the value is outside the `[long]` range for hex and binary numbers, the parse fails.</span></span>
   - <span data-ttu-id="6ce9b-354">Se o valor estiver fora do `[double]` intervalo para o número de base 10, a análise falhará.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-354">If the value is outside the `[double]` range for base 10 number, the parse fails.</span></span>
   - <span data-ttu-id="6ce9b-355">Valores mais altos devem ser gravados explicitamente usando o `n` sufixo para analisar o literal como um `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="6ce9b-355">Higher values must be explicitly written using the `n` suffix to parse the literal as a `BigInteger`.</span></span>

### <a name="parsing-large-value-literals"></a><span data-ttu-id="6ce9b-356">Analisando literais de valor grande</span><span class="sxs-lookup"><span data-stu-id="6ce9b-356">Parsing large value literals</span></span>

<span data-ttu-id="6ce9b-357">Anteriormente, valores inteiros mais altos eram analisados como duplo antes de serem convertidos em qualquer outro tipo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-357">Previously, higher integer values were parsed as double before being cast to any other type.</span></span> <span data-ttu-id="6ce9b-358">Isso resulta em uma perda de precisão nos intervalos mais altos.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-358">This results in a loss of precision in the higher ranges.</span></span> <span data-ttu-id="6ce9b-359">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-359">For example:</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="6ce9b-360">Para evitar esse problema, você tinha que escrever valores como cadeias de caracteres e, em seguida, convertê-los:</span><span class="sxs-lookup"><span data-stu-id="6ce9b-360">To avoid this problem you had to write values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="6ce9b-361">No PowerShell 7,0, você deve usar o `N` sufixo.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-361">In PowerShell 7.0 you must use the `N` suffix.</span></span>

```
PS> 111111111111111111111111111111111111111111111111111111n
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="6ce9b-362">Além disso, os valores entre `[ulong]::MaxValue` e `[decimal]::MaxValue` devem ser indicados usando o sufixo decimal `D` para manter a precisão.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-362">Also values between `[ulong]::MaxValue` and `[decimal]::MaxValue` should be denoted using the decimal-suffix `D` to maintain accuracy.</span></span> <span data-ttu-id="6ce9b-363">Sem o sufixo, esses valores são analisados como `[Double]` usando o modo de análise real.</span><span class="sxs-lookup"><span data-stu-id="6ce9b-363">Without the suffix, these values are parsed as `[Double]` using the real-parsing mode.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
