---
description: Tanto o inteiro quanto os literais numéricos reais podem ter os sufixos tipo e multiplicador.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre literais numéricos
ms.openlocfilehash: dc1a55dbec1f0de99e06011645e6884b37480233
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354813"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="cd3bf-103">Sobre literais numéricos</span><span class="sxs-lookup"><span data-stu-id="cd3bf-103">About numeric literals</span></span>

<span data-ttu-id="cd3bf-104">Há dois tipos de literais numéricos: inteiro e real.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="cd3bf-105">Ambos podem ter um tipo e sufixos de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="cd3bf-106">Literais inteiros</span><span class="sxs-lookup"><span data-stu-id="cd3bf-106">Integer literals</span></span>

<span data-ttu-id="cd3bf-107">Literais inteiros podem ser escritos em notação decimal ou hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="cd3bf-108">Os literais hexadecimais são prefixados com `0x` para distingui-los de números decimais.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="cd3bf-109">Os literais inteiros podem ter um sufixo de tipo e um sufixo de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="cd3bf-110">Sufixo</span><span class="sxs-lookup"><span data-stu-id="cd3bf-110">Suffix</span></span> |            <span data-ttu-id="cd3bf-111">Significado</span><span class="sxs-lookup"><span data-stu-id="cd3bf-111">Meaning</span></span>             |          <span data-ttu-id="cd3bf-112">Observação</span><span class="sxs-lookup"><span data-stu-id="cd3bf-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="cd3bf-113">s</span><span class="sxs-lookup"><span data-stu-id="cd3bf-113">y</span></span>      | <span data-ttu-id="cd3bf-114">tipo de dados byte assinado</span><span class="sxs-lookup"><span data-stu-id="cd3bf-114">signed byte data type</span></span>          | <span data-ttu-id="cd3bf-115">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cd3bf-116">uy</span><span class="sxs-lookup"><span data-stu-id="cd3bf-116">uy</span></span>     | <span data-ttu-id="cd3bf-117">tipo de dados byte não assinado</span><span class="sxs-lookup"><span data-stu-id="cd3bf-117">unsigned byte data type</span></span>        | <span data-ttu-id="cd3bf-118">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cd3bf-119">s</span><span class="sxs-lookup"><span data-stu-id="cd3bf-119">s</span></span>      | <span data-ttu-id="cd3bf-120">tipo de dados curto</span><span class="sxs-lookup"><span data-stu-id="cd3bf-120">short data type</span></span>                | <span data-ttu-id="cd3bf-121">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cd3bf-122">us</span><span class="sxs-lookup"><span data-stu-id="cd3bf-122">us</span></span>     | <span data-ttu-id="cd3bf-123">tipo de dados curto não assinado</span><span class="sxs-lookup"><span data-stu-id="cd3bf-123">unsigned short data type</span></span>       | <span data-ttu-id="cd3bf-124">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cd3bf-125">l</span><span class="sxs-lookup"><span data-stu-id="cd3bf-125">l</span></span>      | <span data-ttu-id="cd3bf-126">tipo de dados Long</span><span class="sxs-lookup"><span data-stu-id="cd3bf-126">long data type</span></span>                 |                         |
| <span data-ttu-id="cd3bf-127">u</span><span class="sxs-lookup"><span data-stu-id="cd3bf-127">u</span></span>      | <span data-ttu-id="cd3bf-128">tipo de dados int ou Long não assinado</span><span class="sxs-lookup"><span data-stu-id="cd3bf-128">unsigned int or long data type</span></span> | <span data-ttu-id="cd3bf-129">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cd3bf-130">UL</span><span class="sxs-lookup"><span data-stu-id="cd3bf-130">ul</span></span>     | <span data-ttu-id="cd3bf-131">tipo de dados Long não assinado</span><span class="sxs-lookup"><span data-stu-id="cd3bf-131">unsigned long data type</span></span>        | <span data-ttu-id="cd3bf-132">Adicionado no PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="cd3bf-133">kb</span><span class="sxs-lookup"><span data-stu-id="cd3bf-133">kb</span></span>     | <span data-ttu-id="cd3bf-134">multiplicador de kilobytes</span><span class="sxs-lookup"><span data-stu-id="cd3bf-134">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="cd3bf-135">mb</span><span class="sxs-lookup"><span data-stu-id="cd3bf-135">mb</span></span>     | <span data-ttu-id="cd3bf-136">multiplicador de megabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-136">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="cd3bf-137">Reino</span><span class="sxs-lookup"><span data-stu-id="cd3bf-137">gb</span></span>     | <span data-ttu-id="cd3bf-138">multiplicador de Gigabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-138">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="cd3bf-139">TB</span><span class="sxs-lookup"><span data-stu-id="cd3bf-139">tb</span></span>     | <span data-ttu-id="cd3bf-140">multiplicador de terabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-140">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="cd3bf-141">PB</span><span class="sxs-lookup"><span data-stu-id="cd3bf-141">pb</span></span>     | <span data-ttu-id="cd3bf-142">multiplicador petabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-142">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="cd3bf-143">O tipo de um inteiro literal é determinado por seu valor, o sufixo de tipo e o sufixo de multiplicador numérico.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-143">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="cd3bf-144">Para um literal inteiro sem sufixo de tipo:</span><span class="sxs-lookup"><span data-stu-id="cd3bf-144">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="cd3bf-145">Se o valor puder ser representado por tipo `[int]` , que é seu tipo.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-145">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="cd3bf-146">Caso contrário, se o valor puder ser representado pelo tipo `[long]` , esse será seu tipo.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-146">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="cd3bf-147">Caso contrário, se o valor puder ser representado pelo tipo `[decimal]` , esse será seu tipo.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-147">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="cd3bf-148">Caso contrário, ele é representado por tipo `[double]` .</span><span class="sxs-lookup"><span data-stu-id="cd3bf-148">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="cd3bf-149">Para um literal inteiro com um sufixo de tipo:</span><span class="sxs-lookup"><span data-stu-id="cd3bf-149">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="cd3bf-150">Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[uint]` , seu tipo será `[uint]` .</span><span class="sxs-lookup"><span data-stu-id="cd3bf-150">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="cd3bf-151">Se o sufixo de tipo for `u` e o valor puder ser representado pelo tipo `[ulong]` , seu tipo será `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="cd3bf-151">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="cd3bf-152">Se seu valor puder ser representado pelo tipo especificado, esse é seu tipo.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-152">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="cd3bf-153">Caso contrário, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-153">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="cd3bf-154">Literais reais</span><span class="sxs-lookup"><span data-stu-id="cd3bf-154">Real literals</span></span>

<span data-ttu-id="cd3bf-155">Os literais reais só podem ser gravados em notação decimal.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-155">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="cd3bf-156">Essa notação pode incluir valores fracionários após um ponto decimal e notação científica usando uma parte exponencial.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-156">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="cd3bf-157">A parte exponencial inclui um ' e ' seguido por um sinal opcional (+/-) e um número que representa o expoente.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-157">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="cd3bf-158">Por exemplo, o valor literal `1e2` é igual ao valor numérico 100.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-158">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="cd3bf-159">Os literais reais podem ter um sufixo de tipo e um sufixo de multiplicador.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-159">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="cd3bf-160">Sufixo</span><span class="sxs-lookup"><span data-stu-id="cd3bf-160">Suffix</span></span> |       <span data-ttu-id="cd3bf-161">Significado</span><span class="sxs-lookup"><span data-stu-id="cd3bf-161">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="cd3bf-162">d</span><span class="sxs-lookup"><span data-stu-id="cd3bf-162">d</span></span>      | <span data-ttu-id="cd3bf-163">tipo de dados decimal</span><span class="sxs-lookup"><span data-stu-id="cd3bf-163">decimal data type</span></span>   |
| <span data-ttu-id="cd3bf-164">kb</span><span class="sxs-lookup"><span data-stu-id="cd3bf-164">kb</span></span>     | <span data-ttu-id="cd3bf-165">multiplicador de kilobytes</span><span class="sxs-lookup"><span data-stu-id="cd3bf-165">kilobyte multiplier</span></span> |
| <span data-ttu-id="cd3bf-166">mb</span><span class="sxs-lookup"><span data-stu-id="cd3bf-166">mb</span></span>     | <span data-ttu-id="cd3bf-167">multiplicador de megabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-167">megabyte multiplier</span></span> |
| <span data-ttu-id="cd3bf-168">Reino</span><span class="sxs-lookup"><span data-stu-id="cd3bf-168">gb</span></span>     | <span data-ttu-id="cd3bf-169">multiplicador de Gigabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-169">gigabyte multiplier</span></span> |
| <span data-ttu-id="cd3bf-170">TB</span><span class="sxs-lookup"><span data-stu-id="cd3bf-170">tb</span></span>     | <span data-ttu-id="cd3bf-171">multiplicador de terabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-171">terabyte multiplier</span></span> |
| <span data-ttu-id="cd3bf-172">PB</span><span class="sxs-lookup"><span data-stu-id="cd3bf-172">pb</span></span>     | <span data-ttu-id="cd3bf-173">multiplicador petabyte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-173">petabyte multiplier</span></span> |

<span data-ttu-id="cd3bf-174">Há dois tipos de literal real: Double e decimal.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-174">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="cd3bf-175">Eles são indicados pela ausência ou presença, respectivamente, do sufixo de tipo decimal.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-175">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="cd3bf-176">O PowerShell não dá suporte a uma representação literal de um `[float]` valor.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-176">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="cd3bf-177">Um literal real duplo tem tipo `[double]` .</span><span class="sxs-lookup"><span data-stu-id="cd3bf-177">A double real literal has type `[double]`.</span></span> <span data-ttu-id="cd3bf-178">Um literal real decimal tem tipo `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="cd3bf-178">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="cd3bf-179">Zeros à direita na parte fracionária de um literal real decimal são significativos.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-179">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="cd3bf-180">Se o valor dos dígitos da parte exponencial em um `[double]` literal real for menor que o mínimo suportado, o valor desse `[double]` literal real será 0.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-180">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="cd3bf-181">Se o valor dos dígitos da parte exponencial em um `[decimal]` literal real for menor que o mínimo suportado, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-181">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="cd3bf-182">Se o valor dos dígitos da parte exponencial em um `[double]` ou `[decimal]` literal real for maior que o máximo suportado, esse literal será malformado.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-182">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="cd3bf-183">A sintaxe permite que um literal real duplo tenha um sufixo de tipo longo.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-183">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="cd3bf-184">O PowerShell trata esse caso como um literal inteiro cujo valor é representado por tipo `[long]` .</span><span class="sxs-lookup"><span data-stu-id="cd3bf-184">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="cd3bf-185">Esse recurso foi retido para compatibilidade com versões anteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-185">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="cd3bf-186">No entanto, os programadores são desencorajados de usar literais inteiros desse formulário, pois podem facilmente obscurecer o valor real do literal.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-186">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="cd3bf-187">Por exemplo, `1.2L` tem o valor 1, `1.2345e1L` tem o valor 12 e `1.2345e-5L` tem o valor 0, nenhum dos quais é imediatamente óbvio.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-187">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="cd3bf-188">Multiplicadores numéricos</span><span class="sxs-lookup"><span data-stu-id="cd3bf-188">Numeric multipliers</span></span>

<span data-ttu-id="cd3bf-189">Para conveniência, inteiros e literais reais podem conter um multiplicador numérico, que indica um de um conjunto de potências usadas com frequência de 2.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-189">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="cd3bf-190">O multiplicador numérico pode ser escrito em qualquer combinação de letras maiúsculas ou minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-190">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="cd3bf-191">Os sufixos de multiplicador podem ser usados em combinação com os `u` `ul` `l` sufixos, e de tipo.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-191">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="cd3bf-192">Exemplos de multiplicador</span><span class="sxs-lookup"><span data-stu-id="cd3bf-192">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="cd3bf-193">Aceleradores de tipo numérico</span><span class="sxs-lookup"><span data-stu-id="cd3bf-193">Numeric type accelerators</span></span>

<span data-ttu-id="cd3bf-194">O PowerShell dá suporte aos seguintes aceleradores de tipos:</span><span class="sxs-lookup"><span data-stu-id="cd3bf-194">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="cd3bf-195">Acelerador</span><span class="sxs-lookup"><span data-stu-id="cd3bf-195">Accelerator</span></span> |         <span data-ttu-id="cd3bf-196">Observação</span><span class="sxs-lookup"><span data-stu-id="cd3bf-196">Note</span></span>         |           <span data-ttu-id="cd3bf-197">Descrição</span><span class="sxs-lookup"><span data-stu-id="cd3bf-197">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="cd3bf-198">Byte (não assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-198">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="cd3bf-199">Byte (assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-199">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="cd3bf-200">inteiro de 16 bits</span><span class="sxs-lookup"><span data-stu-id="cd3bf-200">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="cd3bf-201">alias para `[int16]`</span><span class="sxs-lookup"><span data-stu-id="cd3bf-201">alias for `[int16]`</span></span>  | <span data-ttu-id="cd3bf-202">inteiro de 16 bits</span><span class="sxs-lookup"><span data-stu-id="cd3bf-202">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="cd3bf-203">inteiro de 16 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-203">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="cd3bf-204">alias para `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="cd3bf-204">alias for `[uint16]`</span></span> | <span data-ttu-id="cd3bf-205">inteiro de 16 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-205">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="cd3bf-206">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="cd3bf-206">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="cd3bf-207">alias para `[int32]`</span><span class="sxs-lookup"><span data-stu-id="cd3bf-207">alias for `[int32]`</span></span>  | <span data-ttu-id="cd3bf-208">Inteiro de 32 bits</span><span class="sxs-lookup"><span data-stu-id="cd3bf-208">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="cd3bf-209">inteiro de 32 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-209">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="cd3bf-210">alias para `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="cd3bf-210">alias for `[uint32]`</span></span> | <span data-ttu-id="cd3bf-211">inteiro de 32 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-211">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="cd3bf-212">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="cd3bf-212">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="cd3bf-213">alias para `[int64]`</span><span class="sxs-lookup"><span data-stu-id="cd3bf-213">alias for `[int64]`</span></span>  | <span data-ttu-id="cd3bf-214">Inteiro de 64 bits</span><span class="sxs-lookup"><span data-stu-id="cd3bf-214">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="cd3bf-215">inteiro de 64 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-215">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="cd3bf-216">alias para `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="cd3bf-216">alias for `[uint64]`</span></span> | <span data-ttu-id="cd3bf-217">inteiro de 64 bits (não assinado)</span><span class="sxs-lookup"><span data-stu-id="cd3bf-217">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="cd3bf-218">Consulte a [estrutura BigInteger][bigint]</span><span class="sxs-lookup"><span data-stu-id="cd3bf-218">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="cd3bf-219">Ponto flutuante de precisão única</span><span class="sxs-lookup"><span data-stu-id="cd3bf-219">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="cd3bf-220">alias para `[single]`</span><span class="sxs-lookup"><span data-stu-id="cd3bf-220">alias for `[single]`</span></span> | <span data-ttu-id="cd3bf-221">Ponto flutuante de precisão única</span><span class="sxs-lookup"><span data-stu-id="cd3bf-221">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="cd3bf-222">Ponto flutuante de precisão dupla</span><span class="sxs-lookup"><span data-stu-id="cd3bf-222">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="cd3bf-223">ponto flutuante de 128 bits</span><span class="sxs-lookup"><span data-stu-id="cd3bf-223">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="cd3bf-224">Os seguintes aceleradores de tipos foram adicionados no PowerShell 6,2: `[short]` ,, `[ushort]` `[uint]` , `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="cd3bf-224">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="cd3bf-225">Trabalhando com outros tipos numéricos</span><span class="sxs-lookup"><span data-stu-id="cd3bf-225">Working with other numeric types</span></span>

<span data-ttu-id="cd3bf-226">Para trabalhar com qualquer outro tipo numérico, você deve usar aceleradores de tipo, que não está sem alguns problemas.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-226">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="cd3bf-227">Por exemplo, valores inteiros altos são sempre analisados como Double antes de serem convertidos em qualquer outro tipo.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-227">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="cd3bf-228">O valor é analisado como um duplo primeiro, perdendo a precisão nos intervalos mais altos.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-228">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="cd3bf-229">Para evitar esse problema, insira valores como cadeias de caracteres e, em seguida, converta-os:</span><span class="sxs-lookup"><span data-stu-id="cd3bf-229">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="cd3bf-230">Exemplos</span><span class="sxs-lookup"><span data-stu-id="cd3bf-230">Examples</span></span>

<span data-ttu-id="cd3bf-231">A tabela a seguir contém vários exemplos de literais numéricos e lista seu tipo e valor:</span><span class="sxs-lookup"><span data-stu-id="cd3bf-231">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="cd3bf-232">Número</span><span class="sxs-lookup"><span data-stu-id="cd3bf-232">Number</span></span>  |  <span data-ttu-id="cd3bf-233">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd3bf-233">Type</span></span>   |    <span data-ttu-id="cd3bf-234">Valor</span><span class="sxs-lookup"><span data-stu-id="cd3bf-234">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="cd3bf-235">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-235">100</span></span> | <span data-ttu-id="cd3bf-236">Int32</span><span class="sxs-lookup"><span data-stu-id="cd3bf-236">Int32</span></span>   |          <span data-ttu-id="cd3bf-237">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-237">100</span></span> |
|     <span data-ttu-id="cd3bf-238">100D</span><span class="sxs-lookup"><span data-stu-id="cd3bf-238">100D</span></span> | <span data-ttu-id="cd3bf-239">Decimal</span><span class="sxs-lookup"><span data-stu-id="cd3bf-239">Decimal</span></span> |          <span data-ttu-id="cd3bf-240">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-240">100</span></span> |
|     <span data-ttu-id="cd3bf-241">100l</span><span class="sxs-lookup"><span data-stu-id="cd3bf-241">100l</span></span> | <span data-ttu-id="cd3bf-242">Int64</span><span class="sxs-lookup"><span data-stu-id="cd3bf-242">Int64</span></span>   |          <span data-ttu-id="cd3bf-243">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-243">100</span></span> |
|    <span data-ttu-id="cd3bf-244">100uL</span><span class="sxs-lookup"><span data-stu-id="cd3bf-244">100uL</span></span> | <span data-ttu-id="cd3bf-245">UInt64</span><span class="sxs-lookup"><span data-stu-id="cd3bf-245">UInt64</span></span>  |          <span data-ttu-id="cd3bf-246">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-246">100</span></span> |
|    <span data-ttu-id="cd3bf-247">100us</span><span class="sxs-lookup"><span data-stu-id="cd3bf-247">100us</span></span> | <span data-ttu-id="cd3bf-248">UInt16</span><span class="sxs-lookup"><span data-stu-id="cd3bf-248">UInt16</span></span>  |          <span data-ttu-id="cd3bf-249">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-249">100</span></span> |
|    <span data-ttu-id="cd3bf-250">100uy</span><span class="sxs-lookup"><span data-stu-id="cd3bf-250">100uy</span></span> | <span data-ttu-id="cd3bf-251">Byte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-251">Byte</span></span>    |          <span data-ttu-id="cd3bf-252">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-252">100</span></span> |
|     <span data-ttu-id="cd3bf-253">100y</span><span class="sxs-lookup"><span data-stu-id="cd3bf-253">100y</span></span> | <span data-ttu-id="cd3bf-254">SByte</span><span class="sxs-lookup"><span data-stu-id="cd3bf-254">SByte</span></span>   |          <span data-ttu-id="cd3bf-255">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-255">100</span></span> |
|      <span data-ttu-id="cd3bf-256">1e2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-256">1e2</span></span> | <span data-ttu-id="cd3bf-257">Duplo</span><span class="sxs-lookup"><span data-stu-id="cd3bf-257">Double</span></span>  |          <span data-ttu-id="cd3bf-258">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-258">100</span></span> |
|     <span data-ttu-id="cd3bf-259">1. E2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-259">1.e2</span></span> | <span data-ttu-id="cd3bf-260">Duplo</span><span class="sxs-lookup"><span data-stu-id="cd3bf-260">Double</span></span>  |          <span data-ttu-id="cd3bf-261">100</span><span class="sxs-lookup"><span data-stu-id="cd3bf-261">100</span></span> |
|    <span data-ttu-id="cd3bf-262">0x1e2</span><span class="sxs-lookup"><span data-stu-id="cd3bf-262">0x1e2</span></span> | <span data-ttu-id="cd3bf-263">Int32</span><span class="sxs-lookup"><span data-stu-id="cd3bf-263">Int32</span></span>   |          <span data-ttu-id="cd3bf-264">482</span><span class="sxs-lookup"><span data-stu-id="cd3bf-264">482</span></span> |
|   <span data-ttu-id="cd3bf-265">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="cd3bf-265">0x1e2L</span></span> | <span data-ttu-id="cd3bf-266">Int64</span><span class="sxs-lookup"><span data-stu-id="cd3bf-266">Int64</span></span>   |          <span data-ttu-id="cd3bf-267">482</span><span class="sxs-lookup"><span data-stu-id="cd3bf-267">482</span></span> |
|   <span data-ttu-id="cd3bf-268">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="cd3bf-268">0x1e2D</span></span> | <span data-ttu-id="cd3bf-269">Int32</span><span class="sxs-lookup"><span data-stu-id="cd3bf-269">Int32</span></span>   |         <span data-ttu-id="cd3bf-270">7725</span><span class="sxs-lookup"><span data-stu-id="cd3bf-270">7725</span></span> |
|     <span data-ttu-id="cd3bf-271">482D</span><span class="sxs-lookup"><span data-stu-id="cd3bf-271">482D</span></span> | <span data-ttu-id="cd3bf-272">Decimal</span><span class="sxs-lookup"><span data-stu-id="cd3bf-272">Decimal</span></span> |          <span data-ttu-id="cd3bf-273">482</span><span class="sxs-lookup"><span data-stu-id="cd3bf-273">482</span></span> |
|    <span data-ttu-id="cd3bf-274">482gb</span><span class="sxs-lookup"><span data-stu-id="cd3bf-274">482gb</span></span> | <span data-ttu-id="cd3bf-275">Int64</span><span class="sxs-lookup"><span data-stu-id="cd3bf-275">Int64</span></span>   | <span data-ttu-id="cd3bf-276">517543559168</span><span class="sxs-lookup"><span data-stu-id="cd3bf-276">517543559168</span></span> |
| <span data-ttu-id="cd3bf-277">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="cd3bf-277">0x1e2lgb</span></span> | <span data-ttu-id="cd3bf-278">Int64</span><span class="sxs-lookup"><span data-stu-id="cd3bf-278">Int64</span></span>   | <span data-ttu-id="cd3bf-279">517543559168</span><span class="sxs-lookup"><span data-stu-id="cd3bf-279">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="cd3bf-280">Comandos que se parecem com literais numéricos</span><span class="sxs-lookup"><span data-stu-id="cd3bf-280">Commands that look like numeric literals</span></span>

<span data-ttu-id="cd3bf-281">Qualquer comando que se pareça com um literal numérico deve ser executado usando o operador Call ( `&` ), caso contrário, ele será interpretado como um número do tipo associado.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-281">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="cd3bf-282">Acessar propriedades e métodos de objetos numéricos</span><span class="sxs-lookup"><span data-stu-id="cd3bf-282">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="cd3bf-283">Para acessar um membro de um literal numérico, há casos em que você precisa colocar o literal entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-283">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="cd3bf-284">O literal não tem um ponto decimal</span><span class="sxs-lookup"><span data-stu-id="cd3bf-284">The literal does not have a decimal point</span></span>
- <span data-ttu-id="cd3bf-285">O literal não tem nenhum dígito após o ponto decimal</span><span class="sxs-lookup"><span data-stu-id="cd3bf-285">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="cd3bf-286">O literal não tem um sufixo</span><span class="sxs-lookup"><span data-stu-id="cd3bf-286">The literal does not have a suffix</span></span>

<span data-ttu-id="cd3bf-287">Por exemplo, o exemplo a seguir falha:</span><span class="sxs-lookup"><span data-stu-id="cd3bf-287">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="cd3bf-288">Os exemplos a seguir funcionam:</span><span class="sxs-lookup"><span data-stu-id="cd3bf-288">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="cd3bf-289">Os dois primeiros exemplos funcionam sem colocar o valor literal entre parênteses porque o analisador do PowerShell pode determinar onde o literal numérico termina e o método **GetType** é iniciado.</span><span class="sxs-lookup"><span data-stu-id="cd3bf-289">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
