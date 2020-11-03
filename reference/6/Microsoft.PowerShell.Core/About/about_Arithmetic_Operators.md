---
description: Descreve os operadores que executam aritmética no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arithmetic_Operators
ms.openlocfilehash: c7885e31e4b5b661473d5241b6629bbe05810824
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195790"
---
# <a name="about-arithmetic-operators"></a><span data-ttu-id="78720-104">Sobre operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="78720-104">About Arithmetic Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="78720-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="78720-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="78720-106">Descreve os operadores que executam aritmética no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78720-106">Describes the operators that perform arithmetic in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="78720-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="78720-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="78720-108">Os operadores aritméticos calculam valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="78720-108">Arithmetic operators calculate numeric values.</span></span> <span data-ttu-id="78720-109">Você pode usar um ou mais operadores aritméticos para adicionar, subtrair, multiplicar e dividir valores e para calcular o resto (módulo) de uma operação de divisão.</span><span class="sxs-lookup"><span data-stu-id="78720-109">You can use one or more arithmetic operators to add, subtract, multiply, and divide values, and to calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="78720-110">Além disso, o operador de adição ( `+` ) e o operador de multiplicação ( `*` ) também operam em cadeias de caracteres, matrizes e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="78720-110">In addition, the addition operator (`+`) and multiplication operator (`*`) also operate on strings, arrays, and hash tables.</span></span> <span data-ttu-id="78720-111">O operador de adição concatena a entrada.</span><span class="sxs-lookup"><span data-stu-id="78720-111">The addition operator concatenates the input.</span></span> <span data-ttu-id="78720-112">O operador de multiplicação retorna várias cópias da entrada.</span><span class="sxs-lookup"><span data-stu-id="78720-112">The multiplication operator returns multiple copies of the input.</span></span> <span data-ttu-id="78720-113">Você pode até mesmo misturar tipos de objeto em uma instrução aritmética.</span><span class="sxs-lookup"><span data-stu-id="78720-113">You can even mix object types in an arithmetic statement.</span></span> <span data-ttu-id="78720-114">O método usado para avaliar a instrução é determinado pelo tipo do objeto mais à esquerda na expressão.</span><span class="sxs-lookup"><span data-stu-id="78720-114">The method that is used to evaluate the statement is determined by the type of the leftmost object in the expression.</span></span>

<span data-ttu-id="78720-115">A partir do PowerShell 2,0, todos os operadores aritméticos funcionam em números de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="78720-115">Beginning in PowerShell 2.0, all arithmetic operators work on 64-bit numbers.</span></span>

<span data-ttu-id="78720-116">A partir do PowerShell 3,0, o `-shr` (Shift-Right) e `-shl` (Shift-Left) são adicionados para dar suporte à aritmética de bits no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78720-116">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are added to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="78720-117">O PowerShell dá suporte aos seguintes operadores aritméticos:</span><span class="sxs-lookup"><span data-stu-id="78720-117">PowerShell supports the following arithmetic operators:</span></span>

|<span data-ttu-id="78720-118">Operador</span><span class="sxs-lookup"><span data-stu-id="78720-118">Operator</span></span>|<span data-ttu-id="78720-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="78720-119">Description</span></span>                       |<span data-ttu-id="78720-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="78720-120">Example</span></span>                      |
|--------|----------------------------------|-----------------------------|
| +      |<span data-ttu-id="78720-121">Adiciona números inteiros; Concatena</span><span class="sxs-lookup"><span data-stu-id="78720-121">Adds integers; concatenates</span></span>       |`6 + 2`                      |
|        |<span data-ttu-id="78720-122">cadeias de caracteres, matrizes e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="78720-122">strings, arrays, and hash tables.</span></span> |`"file" + "name"`            |
|        |                                  |`@(1, "one") + @(2.0, "two")`|
|        |                                  |`@{"one" = 1} + @{"two" = 2}`|
| -      |<span data-ttu-id="78720-123">Subtrai um valor de outro</span><span class="sxs-lookup"><span data-stu-id="78720-123">Subtracts one value from another</span></span>  |`6 - 2`                      |
|        |<span data-ttu-id="78720-124">value</span><span class="sxs-lookup"><span data-stu-id="78720-124">value</span></span>                             |                             |
| -      |<span data-ttu-id="78720-125">Faz com que um número seja um número negativo</span><span class="sxs-lookup"><span data-stu-id="78720-125">Makes a number a negative number</span></span>  |`-6`                         |
|        |                                  |`(Get-Date).AddDays(-1)`     |
| *      |<span data-ttu-id="78720-126">Multiplicar números ou copiar cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="78720-126">Multiply numbers or copy strings</span></span>  |`6 * 2`                      |
|        |<span data-ttu-id="78720-127">e matrizes o número especificado</span><span class="sxs-lookup"><span data-stu-id="78720-127">and arrays the specified number</span></span>   |`@("!") * 4`                 |
|        |<span data-ttu-id="78720-128">de vezes.</span><span class="sxs-lookup"><span data-stu-id="78720-128">of times.</span></span>                         |`"!" * 3`                    |
| /      |<span data-ttu-id="78720-129">Compara dois valores.</span><span class="sxs-lookup"><span data-stu-id="78720-129">Divides two values.</span></span>               |`6 / 2`                      |
| %      |<span data-ttu-id="78720-130">Módulo – retorna o restante de</span><span class="sxs-lookup"><span data-stu-id="78720-130">Modulus - returns the remainder of</span></span>|`7 % 2`                      |
|        |<span data-ttu-id="78720-131">uma operação de divisão.</span><span class="sxs-lookup"><span data-stu-id="78720-131">a division operation.</span></span>             |                             |
|<span data-ttu-id="78720-132">-banda</span><span class="sxs-lookup"><span data-stu-id="78720-132">-band</span></span>   |<span data-ttu-id="78720-133">AND bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-133">Bitwise AND</span></span>                       |`5 -band 3`                  |
|<span data-ttu-id="78720-134">-bnot</span><span class="sxs-lookup"><span data-stu-id="78720-134">-bnot</span></span>   |<span data-ttu-id="78720-135">NOT bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-135">Bitwise NOT</span></span>                       |`-bnot 5`                    |
|<span data-ttu-id="78720-136">-Bor</span><span class="sxs-lookup"><span data-stu-id="78720-136">-bor</span></span>    |<span data-ttu-id="78720-137">OR bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-137">Bitwise OR</span></span>                        |`5 -bor 0x03`                |
|<span data-ttu-id="78720-138">-bxor</span><span class="sxs-lookup"><span data-stu-id="78720-138">-bxor</span></span>   |<span data-ttu-id="78720-139">XOR bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-139">Bitwise XOR</span></span>                       |`5 -bxor 3`                  |
|<span data-ttu-id="78720-140">-shl</span><span class="sxs-lookup"><span data-stu-id="78720-140">-shl</span></span>    |<span data-ttu-id="78720-141">Desloca bits para a esquerda</span><span class="sxs-lookup"><span data-stu-id="78720-141">Shifts bits to the left</span></span>           |`102 -shl 2`                 |
|<span data-ttu-id="78720-142">-shr</span><span class="sxs-lookup"><span data-stu-id="78720-142">-shr</span></span>    |<span data-ttu-id="78720-143">Desloca bits para a direita</span><span class="sxs-lookup"><span data-stu-id="78720-143">Shifts bits to the right</span></span>          |`102 -shr 2`                 |

<span data-ttu-id="78720-144">Os operadores de bit a bit só funcionam em tipos inteiros.</span><span class="sxs-lookup"><span data-stu-id="78720-144">The bitwise operators only work on integer types.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="78720-145">PRECEDÊNCIA DE OPERADOR</span><span class="sxs-lookup"><span data-stu-id="78720-145">OPERATOR PRECEDENCE</span></span>

<span data-ttu-id="78720-146">O PowerShell processa operadores aritméticos na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="78720-146">PowerShell processes arithmetic operators in the following order:</span></span>

|<span data-ttu-id="78720-147">Precedência</span><span class="sxs-lookup"><span data-stu-id="78720-147">Precedence</span></span>|<span data-ttu-id="78720-148">Operador</span><span class="sxs-lookup"><span data-stu-id="78720-148">Operator</span></span>          |<span data-ttu-id="78720-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="78720-149">Description</span></span>                            |
|----------|------------------|---------------------------------------|
|<span data-ttu-id="78720-150">1</span><span class="sxs-lookup"><span data-stu-id="78720-150">1</span></span>         | `()`             |<span data-ttu-id="78720-151">Parênteses</span><span class="sxs-lookup"><span data-stu-id="78720-151">Parentheses</span></span>                            |
|<span data-ttu-id="78720-152">2</span><span class="sxs-lookup"><span data-stu-id="78720-152">2</span></span>         | `-`              |<span data-ttu-id="78720-153">Para um número negativo ou um operador unário</span><span class="sxs-lookup"><span data-stu-id="78720-153">For a negative number or unary operator</span></span>|
|<span data-ttu-id="78720-154">3</span><span class="sxs-lookup"><span data-stu-id="78720-154">3</span></span>         | <span data-ttu-id="78720-155">`*`, `/`, `%`</span><span class="sxs-lookup"><span data-stu-id="78720-155">`*`, `/`, `%`</span></span>    |<span data-ttu-id="78720-156">Para multiplicação e divisão</span><span class="sxs-lookup"><span data-stu-id="78720-156">For multiplication and division</span></span>        |
|<span data-ttu-id="78720-157">4</span><span class="sxs-lookup"><span data-stu-id="78720-157">4</span></span>         | <span data-ttu-id="78720-158">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="78720-158">`+`, `-`</span></span>         |<span data-ttu-id="78720-159">Para adição e subtração</span><span class="sxs-lookup"><span data-stu-id="78720-159">For addition and subtraction</span></span>           |
|<span data-ttu-id="78720-160">5</span><span class="sxs-lookup"><span data-stu-id="78720-160">5</span></span>         | <span data-ttu-id="78720-161">`-band`, `-bnot`</span><span class="sxs-lookup"><span data-stu-id="78720-161">`-band`, `-bnot`</span></span> |<span data-ttu-id="78720-162">Para operações de bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-162">For bitwise operations</span></span>                 |
|<span data-ttu-id="78720-163">5</span><span class="sxs-lookup"><span data-stu-id="78720-163">5</span></span>         | <span data-ttu-id="78720-164">`-bor`, `-bxor`</span><span class="sxs-lookup"><span data-stu-id="78720-164">`-bor`, `-bxor`</span></span>  |<span data-ttu-id="78720-165">Para operações de bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-165">For bitwise operations</span></span>                 |
|<span data-ttu-id="78720-166">5</span><span class="sxs-lookup"><span data-stu-id="78720-166">5</span></span>         | <span data-ttu-id="78720-167">`-shr`, `-shl`</span><span class="sxs-lookup"><span data-stu-id="78720-167">`-shr`, `-shl`</span></span>   |<span data-ttu-id="78720-168">Para operações de bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-168">For bitwise operations</span></span>                 |

<span data-ttu-id="78720-169">O PowerShell processa as expressões da esquerda para a direita de acordo com as regras de precedência.</span><span class="sxs-lookup"><span data-stu-id="78720-169">PowerShell processes the expressions from left to right according to the precedence rules.</span></span> <span data-ttu-id="78720-170">Os exemplos a seguir mostram o efeito das regras de precedência:</span><span class="sxs-lookup"><span data-stu-id="78720-170">The following examples show the effect of the precedence rules:</span></span>

|<span data-ttu-id="78720-171">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-171">Expression</span></span> |<span data-ttu-id="78720-172">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-172">Result</span></span>|
|-----------|------|
|`3+6/3*4`  |`11`  |
|`3+6/(3*4)`|`3.5` |
|`(3+6)/3*4`|`12`  |

<span data-ttu-id="78720-173">A ordem na qual o PowerShell avalia expressões pode ser diferente de outras linguagens de programação e script que você usou.</span><span class="sxs-lookup"><span data-stu-id="78720-173">The order in which PowerShell evaluates expressions might differ from other programming and scripting languages that you have used.</span></span> <span data-ttu-id="78720-174">O exemplo a seguir mostra uma instrução de atribuição complicada.</span><span class="sxs-lookup"><span data-stu-id="78720-174">The following example shows a complicated assignment statement.</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$b[$a] = $c[$a++]
```

<span data-ttu-id="78720-175">Neste exemplo, a expressão `$a++` é avaliada antes de `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="78720-175">In this example, the expression `$a++` is evaluated before `$b[$a]`.</span></span>
<span data-ttu-id="78720-176">Avaliar `$a++` altera o valor de `$a` depois que ele é usado na instrução `$c[$a++]` ; Mas, antes de ser usado em `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="78720-176">Evaluating `$a++` changes the value of `$a` after it is used in the statement `$c[$a++]`; but, before it is used in `$b[$a]`.</span></span> <span data-ttu-id="78720-177">A variável `$a` em `$b[$a]` Equals `1` , não `0` ; portanto, a instrução atribui um valor a `$b[1]` , não `$b[0]` .</span><span class="sxs-lookup"><span data-stu-id="78720-177">The variable `$a` in `$b[$a]` equals `1`, not `0`; so, the statement assigns a value to `$b[1]`, not `$b[0]`.</span></span>

<span data-ttu-id="78720-178">O código acima é equivalente a:</span><span class="sxs-lookup"><span data-stu-id="78720-178">The above code is equivalent to:</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$tmp = $c[$a]
$a = $a + 1
$b[$a] = $tmp
```

## <a name="division-and-rounding"></a><span data-ttu-id="78720-179">DIVISÃO E ARREDONDAMENTO</span><span class="sxs-lookup"><span data-stu-id="78720-179">DIVISION AND ROUNDING</span></span>

<span data-ttu-id="78720-180">Quando o quociente de uma operação de divisão é um inteiro, o PowerShell arredonda o valor para o número inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="78720-180">When the quotient of a division operation is an integer, PowerShell rounds the value to the nearest integer.</span></span> <span data-ttu-id="78720-181">Quando o valor é `.5` , ele arredonda para o inteiro par mais próximo.</span><span class="sxs-lookup"><span data-stu-id="78720-181">When the value is `.5`, it rounds to the nearest even integer.</span></span>

<span data-ttu-id="78720-182">O exemplo a seguir mostra o efeito do arredondamento para o inteiro par mais próximo.</span><span class="sxs-lookup"><span data-stu-id="78720-182">The following example shows the effect of rounding to the nearest even integer.</span></span>

|<span data-ttu-id="78720-183">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-183">Expression</span></span>      |<span data-ttu-id="78720-184">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-184">Result</span></span>|
|----------------|------|
|`[int]( 5 / 2 )`|`2`   |
|`[int]( 7 / 2 )`|`4`   |

<span data-ttu-id="78720-185">Observe como **_5/2_ = 2,5** é arredondado para **2** .</span><span class="sxs-lookup"><span data-stu-id="78720-185">Notice how **_5/2_ = 2.5** gets rounded to **2** .</span></span> <span data-ttu-id="78720-186">Mas, **_7/2_ = 3,5** é arredondado para **4** .</span><span class="sxs-lookup"><span data-stu-id="78720-186">But, **_7/2_ = 3.5** gets rounded to **4** .</span></span>

<span data-ttu-id="78720-187">Você pode usar a `[Math]` classe para obter um comportamento de arredondamento diferente.</span><span class="sxs-lookup"><span data-stu-id="78720-187">You can use the `[Math]` class to get different rounding behavior.</span></span>

|                          <span data-ttu-id="78720-188">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-188">Expression</span></span>                          | <span data-ttu-id="78720-189">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-189">Result</span></span> |
| ------------------------------------------------------------ | ------ |
| `[int][Math]::Round(5 / 2,[MidpointRounding]::AwayFromZero)` | `3`    |
| `[int][Math]::Ceiling(5 / 2)`                                | `3`    |
| `[int][Math]::Floor(5 / 2)`                                  | `2`    |

<span data-ttu-id="78720-190">Para obter mais informações, consulte o método [Math. Round](/dotnet/api/system.math.round) .</span><span class="sxs-lookup"><span data-stu-id="78720-190">For more information, see the [Math.Round](/dotnet/api/system.math.round) method.</span></span>

## <a name="adding-and-multiplying-non-numeric-types"></a><span data-ttu-id="78720-191">ADICIONANDO E MULTIPLICANDO TIPOS NÃO NUMÉRICOS</span><span class="sxs-lookup"><span data-stu-id="78720-191">ADDING AND MULTIPLYING NON-NUMERIC TYPES</span></span>

<span data-ttu-id="78720-192">Você pode adicionar números, cadeias de caracteres, matrizes e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="78720-192">You can add numbers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="78720-193">E, você pode multiplicar números, cadeias de caracteres e matrizes.</span><span class="sxs-lookup"><span data-stu-id="78720-193">And, you can multiply numbers, strings, and arrays.</span></span> <span data-ttu-id="78720-194">No entanto, não é possível multiplicar tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="78720-194">However, you cannot multiply hash tables.</span></span>

<span data-ttu-id="78720-195">Quando você adiciona cadeias de caracteres, matrizes ou tabelas de hash, os elementos são concatenados.</span><span class="sxs-lookup"><span data-stu-id="78720-195">When you add strings, arrays, or hash tables, the elements are concatenated.</span></span> <span data-ttu-id="78720-196">Quando você concatena coleções, como matrizes ou tabelas de hash, é criado um novo objeto que contém os objetos de ambas as coleções.</span><span class="sxs-lookup"><span data-stu-id="78720-196">When you concatenate collections, such as arrays or hash tables, a new object is created that contains the objects from both collections.</span></span> <span data-ttu-id="78720-197">Se você tentar concatenar tabelas de hash que têm a mesma chave, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="78720-197">If you try to concatenate hash tables that have the same key, the operation fails.</span></span>

<span data-ttu-id="78720-198">Por exemplo, os comandos a seguir criam duas matrizes e, em seguida, as adicionam:</span><span class="sxs-lookup"><span data-stu-id="78720-198">For example, the following commands create two arrays and then add them:</span></span>

```powershell
$a = 1,2,3
$b = "A","B","C"
$a + $b
```

```output
1
2
3
A
B
C
```

<span data-ttu-id="78720-199">Você também pode executar operações aritméticas em objetos de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="78720-199">You can also perform arithmetic operations on objects of different types.</span></span>
<span data-ttu-id="78720-200">A operação que o PowerShell executa é determinada pelo tipo de estrutura de Microsoft .NET do objeto mais à esquerda na operação.</span><span class="sxs-lookup"><span data-stu-id="78720-200">The operation that PowerShell performs is determined by the Microsoft .NET Framework type of the leftmost object in the operation.</span></span> <span data-ttu-id="78720-201">O PowerShell tenta converter todos os objetos na operação para o tipo de .NET Framework do primeiro objeto.</span><span class="sxs-lookup"><span data-stu-id="78720-201">PowerShell tries to convert all the objects in the operation to the .NET Framework type of the first object.</span></span> <span data-ttu-id="78720-202">Se tiver sucesso na conversão dos objetos, ele executará a operação apropriada para o tipo de .NET Framework do primeiro objeto.</span><span class="sxs-lookup"><span data-stu-id="78720-202">If it succeeds in converting the objects, it performs the operation appropriate to the .NET Framework type of the first object.</span></span> <span data-ttu-id="78720-203">Se houver falha na conversão de qualquer um dos objetos, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="78720-203">If it fails to convert any of the objects, the operation fails.</span></span>

<span data-ttu-id="78720-204">Os exemplos a seguir demonstram o uso dos operadores de adição e multiplicação; em operações que incluem tipos de objeto diferentes.</span><span class="sxs-lookup"><span data-stu-id="78720-204">The following examples demonstrate the use of the addition and multiplication operators; in operations that include different object types.</span></span> <span data-ttu-id="78720-205">Suponha que `$array = 1,2,3` :</span><span class="sxs-lookup"><span data-stu-id="78720-205">Assume `$array = 1,2,3`:</span></span>

|<span data-ttu-id="78720-206">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-206">Expression</span></span>       |<span data-ttu-id="78720-207">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-207">Result</span></span>                 |
|-----------------|-----------------------|
|`"file" + 16`    |`file16`               |
|`$array + 16`    |<span data-ttu-id="78720-208">`1`,`2`,`3`,`16`</span><span class="sxs-lookup"><span data-stu-id="78720-208">`1`,`2`,`3`,`16`</span></span>       |
|`$array + "file"`|<span data-ttu-id="78720-209">`1`,`2`,`3`,`file`</span><span class="sxs-lookup"><span data-stu-id="78720-209">`1`,`2`,`3`,`file`</span></span>     |
|`$array * 2`     |<span data-ttu-id="78720-210">`1`,`2`,`3`,`1`,`2`,`3`</span><span class="sxs-lookup"><span data-stu-id="78720-210">`1`,`2`,`3`,`1`,`2`,`3`</span></span>|
|`"file" * 3`     |`filefilefile`         |

<span data-ttu-id="78720-211">Como o método usado para avaliar instruções é determinado pelo objeto mais à esquerda, a adição e a multiplicação no PowerShell não são estritamente comutadores.</span><span class="sxs-lookup"><span data-stu-id="78720-211">Because the method that is used to evaluate statements is determined by the leftmost object, addition and multiplication in PowerShell are not strictly commutative.</span></span> <span data-ttu-id="78720-212">Por exemplo, `(a + b)` nem sempre é igual `(b + a)` e `(ab)` nem sempre é igual a `(ba)` .</span><span class="sxs-lookup"><span data-stu-id="78720-212">For example, `(a + b)` does not always equal `(b + a)`, and `(ab)` does not always equal `(ba)`.</span></span>

<span data-ttu-id="78720-213">Os exemplos a seguir demonstram esse princípio:</span><span class="sxs-lookup"><span data-stu-id="78720-213">The following examples demonstrate this principle:</span></span>

|<span data-ttu-id="78720-214">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-214">Expression</span></span>   |<span data-ttu-id="78720-215">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-215">Result</span></span>                                               |
|-------------|-----------------------------------------------------|
|`"file" + 16`|`file16`                                             |
|`16 + "file"`|`Cannot convert value "file" to type "System.Int32".`|
|             |`Error: "Input string was not in a correct format."` |
|             |`At line:1 char:1`                                   |
|             |<span data-ttu-id="78720-216">+ 16 + "arquivo" "</span><span class="sxs-lookup"><span data-stu-id="78720-216">+ 16 + "file"\`</span></span>                                       |

<span data-ttu-id="78720-217">As tabelas de hash são um caso um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="78720-217">Hash tables are a slightly different case.</span></span> <span data-ttu-id="78720-218">Você pode adicionar tabelas de hash a outra tabela de hash, desde que as tabelas de hash adicionadas não tenham chaves duplicadas.</span><span class="sxs-lookup"><span data-stu-id="78720-218">You can add hash tables to another hash table, as long as, the added hash tables don't have duplicate keys.</span></span>

<span data-ttu-id="78720-219">O exemplo a seguir mostra como adicionar tabelas de hash entre si.</span><span class="sxs-lookup"><span data-stu-id="78720-219">The following example show how to add hash tables to each other.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c2="Server02"}
$hash1 + $hash2
```

```output
Name                           Value
----                           -----
c2                             Server02
a                              1
b                              2
c1                             Server01
c                              3
```

<span data-ttu-id="78720-220">O exemplo a seguir gera um erro porque uma das chaves é duplicada em ambas as tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="78720-220">The following example throws an error because one of the keys is duplicated in both hash tables.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c="Server02"}
$hash1 + $hash2
```

```output
Item has already been added. Key in dictionary: 'c'  Key being added: 'c'
At line:3 char:1
+ $hash1 + $hash2
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], ArgumentException
    + FullyQualifiedErrorId : System.ArgumentException
```

<span data-ttu-id="78720-221">Além disso, você pode adicionar uma tabela de hash a uma matriz; e, toda a tabela de hash se torna um item na matriz.</span><span class="sxs-lookup"><span data-stu-id="78720-221">Also, you can add a hash table to an array; and, the entire hash table becomes an item in the array.</span></span>

```powershell
$array1 = @(0, "Hello World", [datetime]::Now)
$hash1 = @{a=1; b=2}
$array2 = $array1 + $hash1
$array2
```

```output
0
Hello World

Monday, June 12, 2017 3:05:46 PM

Key   : a
Value : 1
Name  : a

Key   : b
Value : 2
Name  : b
```

<span data-ttu-id="78720-222">No entanto, você não pode adicionar nenhum outro tipo a uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="78720-222">However, you cannot add any other type to a hash table.</span></span>

```powershell
$hash1 + 2
```

```output
A hash table can only be added to another hash table.
At line:3 char:1
+ $hash1 + 2
```

<span data-ttu-id="78720-223">Embora os operadores de adição sejam muito úteis, use os operadores de atribuição para adicionar elementos a tabelas de hash e matrizes.</span><span class="sxs-lookup"><span data-stu-id="78720-223">Although the addition operators are very useful, use the assignment operators to add elements to hash tables and arrays.</span></span> <span data-ttu-id="78720-224">Para obter mais informações, consulte [about_assignment_operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="78720-224">For more information see [about_assignment_operators](about_Assignment_Operators.md).</span></span> <span data-ttu-id="78720-225">Os exemplos a seguir usam o `+=` operador de atribuição para adicionar itens a uma matriz:</span><span class="sxs-lookup"><span data-stu-id="78720-225">The following examples use the `+=` assignment operator to add items to an array:</span></span>

```powershell
$array = @()
(0..9).foreach{ $array += $_ }
$array
```

```output
0
1
2
```

## <a name="type-conversion-to-accommodate-result"></a><span data-ttu-id="78720-226">CONVERSÃO DE TIPO PARA ACOMODAR O RESULTADO</span><span class="sxs-lookup"><span data-stu-id="78720-226">TYPE CONVERSION TO ACCOMMODATE RESULT</span></span>

<span data-ttu-id="78720-227">O PowerShell seleciona automaticamente o tipo numérico .NET Framework que melhor expresse o resultado sem perder a precisão.</span><span class="sxs-lookup"><span data-stu-id="78720-227">PowerShell automatically selects the .NET Framework numeric type that best expresses the result without losing precision.</span></span> <span data-ttu-id="78720-228">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="78720-228">For example:</span></span>

```powershell
2 + 3.1

(2). GetType().FullName
(2 + 3.1).GetType().FullName
```

```output
5.1
System.Int32
System.Double
```

<span data-ttu-id="78720-229">Se o resultado de uma operação for muito grande para o tipo, o tipo do resultado será ampliado para acomodar o resultado, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="78720-229">If the result of an operation is too large for the type, the type of the result is widened to accommodate the result, as in the following example:</span></span>

```powershell
(512MB).GetType().FullName
(512MB * 512MB).GetType().FullName
```

```output
System.Int32
System.Double
```

<span data-ttu-id="78720-230">O tipo do resultado não será necessariamente o mesmo que um dos operandos.</span><span class="sxs-lookup"><span data-stu-id="78720-230">The type of the result will not necessarily be the same as one of the operands.</span></span> <span data-ttu-id="78720-231">No exemplo a seguir, o valor negativo não pode ser convertido em um inteiro sem sinal e o inteiro não assinado é muito grande para ser convertido em `Int32` :</span><span class="sxs-lookup"><span data-stu-id="78720-231">In the following example, the negative value cannot be cast to an unsigned integer, and the unsigned integer is too large to be cast to `Int32`:</span></span>

```powershell
([int32]::minvalue + [uint32]::maxvalue).gettype().fullname
```

```output
System.Int64
```

<span data-ttu-id="78720-232">Neste exemplo, `Int64` pode acomodar ambos os tipos.</span><span class="sxs-lookup"><span data-stu-id="78720-232">In this example, `Int64` can accommodate both types.</span></span>

<span data-ttu-id="78720-233">O `System.Decimal` tipo é uma exceção.</span><span class="sxs-lookup"><span data-stu-id="78720-233">The `System.Decimal` type is an exception.</span></span> <span data-ttu-id="78720-234">Se um dos operandos tiver o tipo decimal, o resultado será do tipo decimal.</span><span class="sxs-lookup"><span data-stu-id="78720-234">If either operand has the Decimal type, the result will be of the Decimal type.</span></span> <span data-ttu-id="78720-235">Se o resultado for muito grande para o tipo decimal, ele não será convertido em Double.</span><span class="sxs-lookup"><span data-stu-id="78720-235">If the result is too large for the Decimal type, it will not be cast to Double.</span></span> <span data-ttu-id="78720-236">Em vez disso, ocorre um erro.</span><span class="sxs-lookup"><span data-stu-id="78720-236">Instead, an error results.</span></span>

|<span data-ttu-id="78720-237">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-237">Expression</span></span>               |<span data-ttu-id="78720-238">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-238">Result</span></span>                                         |
|-------------------------|-----------------------------------------------|
|`[Decimal]::maxvalue`    |`79228162514264337593543950335`                |
|`[Decimal]::maxvalue + 1`|`Value was either too large or too small for a`|
|                         |`Decimal.`                                     |

## <a name="arithmetic-operators-and-variables"></a><span data-ttu-id="78720-239">VARIÁVEIS E OPERADORES ARITMÉTICOS</span><span class="sxs-lookup"><span data-stu-id="78720-239">ARITHMETIC OPERATORS AND VARIABLES</span></span>

<span data-ttu-id="78720-240">Você também pode usar operadores aritméticos com variáveis.</span><span class="sxs-lookup"><span data-stu-id="78720-240">You can also use arithmetic operators with variables.</span></span> <span data-ttu-id="78720-241">Os operadores atuam nos valores das variáveis.</span><span class="sxs-lookup"><span data-stu-id="78720-241">The operators act on the values of the variables.</span></span> <span data-ttu-id="78720-242">Os exemplos a seguir demonstram o uso de operadores aritméticos com variáveis:</span><span class="sxs-lookup"><span data-stu-id="78720-242">The following examples demonstrate the use of arithmetic operators with variables:</span></span>

| <span data-ttu-id="78720-243">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-243">Expression</span></span>                                    |<span data-ttu-id="78720-244">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-244">Result</span></span>      |
|-----------------------------------------------|------------|
|`$intA = 6`<br/>`$intB = 4`<br/>`$intA + $intB`|`10`        |
|`$a = "Power"`<br/>`$b = "Shell"`<br/>`$a + $b`|`PowerShell`|

## <a name="arithmetic-operators-and-commands"></a><span data-ttu-id="78720-245">OPERADORES ARITMÉTICOS E COMANDOS</span><span class="sxs-lookup"><span data-stu-id="78720-245">ARITHMETIC OPERATORS AND COMMANDS</span></span>

<span data-ttu-id="78720-246">Normalmente, você usa os operadores aritméticos em expressões com números, cadeias de caracteres e matrizes.</span><span class="sxs-lookup"><span data-stu-id="78720-246">Typically, you use the arithmetic operators in expressions with numbers, strings, and arrays.</span></span> <span data-ttu-id="78720-247">No entanto, você também pode usar operadores aritméticos com os objetos que os comandos retornam e com as propriedades desses objetos.</span><span class="sxs-lookup"><span data-stu-id="78720-247">However, you can also use arithmetic operators with the objects that commands return and with the properties of those objects.</span></span>

<span data-ttu-id="78720-248">Os exemplos a seguir mostram como usar os operadores aritméticos em expressões com comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="78720-248">The following examples show how to use the arithmetic operators in expressions with PowerShell commands:</span></span>

```powershell
(get-date) + (new-timespan -day 1)
```

<span data-ttu-id="78720-249">O operador de parênteses força a avaliação do `get-date` cmdlet e a avaliação da `new-timespan -day 1` expressão do cmdlet, nessa ordem.</span><span class="sxs-lookup"><span data-stu-id="78720-249">The parenthesis operator forces the evaluation of the `get-date` cmdlet and the evaluation of the `new-timespan -day 1` cmdlet expression, in that order.</span></span> <span data-ttu-id="78720-250">Os dois resultados são então adicionados usando o `+` operador.</span><span class="sxs-lookup"><span data-stu-id="78720-250">Both results are then added using the `+` operator.</span></span>

```powershell
Get-Process | Where-Object { ($_.ws * 2) -gt 50mb }
```

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
   1896      39    50968      30620   264 1,572.55   1104 explorer
  12802      78   188468      81032   753 3,676.39   5676 OUTLOOK
    660       9    36168      26956   143    12.20    988 PowerShell
    561      14     6592      28144   110 1,010.09    496 services
   3476      80    34664      26092   234 ...45.69    876 svchost
    967      30    58804      59496   416   930.97   2508 WINWORD
```

<span data-ttu-id="78720-251">Na expressão acima, cada espaço de trabalho do processo ( `$_.ws` ) é multiplicado por `2` ; e o resultado é comparado com o `50mb` para ver se ele é maior que isso.</span><span class="sxs-lookup"><span data-stu-id="78720-251">In the above expression, each process working space (`$_.ws`) is multiplied by `2`; and, the result, compared against `50mb` to see if it is greater than that.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="78720-252">Operadores bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-252">Bitwise Operators</span></span>

<span data-ttu-id="78720-253">O PowerShell dá suporte aos operadores bit a bit padrão, incluindo AND bit-a-e ( `-bAnd` ), os operadores or (and) de or bitais inclusivos e exclusivos ( `-bOr` and `-bXor` ) e bit-a-not ( `-bNot` ).</span><span class="sxs-lookup"><span data-stu-id="78720-253">PowerShell supports the standard bitwise operators, including bitwise-AND (`-bAnd`), the inclusive and exclusive bitwise-OR operators (`-bOr` and `-bXor`), and bitwise-NOT (`-bNot`).</span></span>

<span data-ttu-id="78720-254">A partir do PowerShell 2,0, todos os operadores de bit a ponto funcionam com inteiros de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="78720-254">Beginning in PowerShell 2.0, all bitwise operators work with 64-bit integers.</span></span>

<span data-ttu-id="78720-255">A partir do PowerShell 3,0, o `-shr` (Shift-Right) e `-shl` (Shift-Left) são introduzidos para dar suporte à aritmética de ponto a bit no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78720-255">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are introduced to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="78720-256">O PowerShell dá suporte aos operadores bit a seguir.</span><span class="sxs-lookup"><span data-stu-id="78720-256">PowerShell supports the following bitwise operators.</span></span>

| <span data-ttu-id="78720-257">Operador</span><span class="sxs-lookup"><span data-stu-id="78720-257">Operator</span></span> | <span data-ttu-id="78720-258">Descrição</span><span class="sxs-lookup"><span data-stu-id="78720-258">Description</span></span>            | <span data-ttu-id="78720-259">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-259">Expression</span></span>   | <span data-ttu-id="78720-260">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-260">Result</span></span> |
| -------- | ---------------------- | ------------ | ------ |
| `-band`  | <span data-ttu-id="78720-261">AND bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-261">Bitwise AND</span></span>            | `10 -band 3` | <span data-ttu-id="78720-262">2</span><span class="sxs-lookup"><span data-stu-id="78720-262">2</span></span>      |
| `-bor`   | <span data-ttu-id="78720-263">OR-bit (inclusivo)</span><span class="sxs-lookup"><span data-stu-id="78720-263">Bitwise OR (inclusive)</span></span> | `10 -bor 3`  | <span data-ttu-id="78720-264">11</span><span class="sxs-lookup"><span data-stu-id="78720-264">11</span></span>     |
| `-bxor`  | <span data-ttu-id="78720-265">OR-bit (exclusivo)</span><span class="sxs-lookup"><span data-stu-id="78720-265">Bitwise OR (exclusive)</span></span> | `10 -bxor 3` | <span data-ttu-id="78720-266">9</span><span class="sxs-lookup"><span data-stu-id="78720-266">9</span></span>      |
| `-bnot`  | <span data-ttu-id="78720-267">NOT bit a bit</span><span class="sxs-lookup"><span data-stu-id="78720-267">Bitwise NOT</span></span>            | `-bNot 10`   | <span data-ttu-id="78720-268">-11</span><span class="sxs-lookup"><span data-stu-id="78720-268">-11</span></span>    |
| `-shl`   | <span data-ttu-id="78720-269">SHIFT-esquerda</span><span class="sxs-lookup"><span data-stu-id="78720-269">Shift-left</span></span>             | `102 -shl 2` | <span data-ttu-id="78720-270">408</span><span class="sxs-lookup"><span data-stu-id="78720-270">408</span></span>    |
| `-shr`   | <span data-ttu-id="78720-271">SHIFT-direita</span><span class="sxs-lookup"><span data-stu-id="78720-271">Shift-right</span></span>            | `102 -shr 1` | <span data-ttu-id="78720-272">51</span><span class="sxs-lookup"><span data-stu-id="78720-272">51</span></span>     |

<span data-ttu-id="78720-273">Os operadores bit a bit atuam no formato binário de um valor.</span><span class="sxs-lookup"><span data-stu-id="78720-273">Bitwise operators act on the binary format of a value.</span></span> <span data-ttu-id="78720-274">Por exemplo, a estrutura de bits para o número 10 é 00001010 (com base em 1 byte) e a estrutura de bits para o número 3 é 00000011.</span><span class="sxs-lookup"><span data-stu-id="78720-274">For example, the bit structure for the number 10 is 00001010 (based on 1 byte), and the bit structure for the number 3 is 00000011.</span></span> <span data-ttu-id="78720-275">Quando você usa um operador bit a bit para comparar 10 a 3, os bits individuais em cada byte são comparados.</span><span class="sxs-lookup"><span data-stu-id="78720-275">When you use a bitwise operator to compare 10 to 3, the individual bits in each byte are compared.</span></span>

<span data-ttu-id="78720-276">Em uma operação AND de bits, o bit resultante é definido como 1 somente quando ambos os bits de entrada são 1.</span><span class="sxs-lookup"><span data-stu-id="78720-276">In a bitwise AND operation, the resulting bit is set to 1 only when both input bits are 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bAND
0010      ( 2)
```

<span data-ttu-id="78720-277">Em uma operação (inclusiva) de bit (inclusive), o bit resultante é definido como 1 quando um ou ambos os bits de entrada são 1.</span><span class="sxs-lookup"><span data-stu-id="78720-277">In a bitwise OR (inclusive) operation, the resulting bit is set to 1 when either or both input bits are 1.</span></span> <span data-ttu-id="78720-278">O bit resultante é definido como 0 somente quando ambos os bits de entrada são definidos como 0.</span><span class="sxs-lookup"><span data-stu-id="78720-278">The resulting bit is set to 0 only when both input bits are set to 0.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bOR (inclusive)
1011      (11)
```

<span data-ttu-id="78720-279">Em uma operação OR (exclusiva) de bit (), o bit resultante é definido como 1 somente quando um bit de entrada é 1.</span><span class="sxs-lookup"><span data-stu-id="78720-279">In a bitwise OR (exclusive) operation, the resulting bit is set to 1 only when one input bit is 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bXOR (exclusive)
1001      ( 9)
```

<span data-ttu-id="78720-280">O operador nonbit-a NOT é um operador unário que produz o complemento binário do valor.</span><span class="sxs-lookup"><span data-stu-id="78720-280">The bitwise NOT operator is a unary operator that produces the binary complement of the value.</span></span> <span data-ttu-id="78720-281">Um bit de 1 é definido como 0 e um bit de 0 é definido como 1.</span><span class="sxs-lookup"><span data-stu-id="78720-281">A bit of 1 is set to 0 and a bit of 0 is set to 1.</span></span>

<span data-ttu-id="78720-282">Por exemplo, o complemento binário de 0 é-1, o inteiro não assinado máximo (0xFFFFFFFF) e o complemento binário de-1 é 0.</span><span class="sxs-lookup"><span data-stu-id="78720-282">For example, the binary complement of 0 is -1, the maximum unsigned integer (0xffffffff), and the binary complement of -1 is 0.</span></span>

```powershell
-bNot 10
```

```Output
-11
```

```
0000 0000 0000 1010  (10)
------------------------- bNOT
1111 1111 1111 0101  (-11, xfffffff5)
```

<span data-ttu-id="78720-283">Em uma operação de deslocamento para a esquerda de bit-a-ponto, todos os bits são movidos para a esquerda, em que "n" é o valor do operando direito.</span><span class="sxs-lookup"><span data-stu-id="78720-283">In a bitwise shift-left operation, all bits are moved "n" places to the left, where "n" is the value of the right operand.</span></span> <span data-ttu-id="78720-284">Um zero é inserido no lugar.</span><span class="sxs-lookup"><span data-stu-id="78720-284">A zero is inserted in the ones place.</span></span>

<span data-ttu-id="78720-285">Quando o operando esquerdo é um valor inteiro (32 bits), os 5 bits inferiores do operando direito determinam quantos bits do operando esquerdo são deslocados.</span><span class="sxs-lookup"><span data-stu-id="78720-285">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="78720-286">Quando o operando esquerdo é um valor longo (64 bits), os 6 bits inferiores do operando à direita determinam quantos bits do operando esquerdo são deslocados.</span><span class="sxs-lookup"><span data-stu-id="78720-286">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="78720-287">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-287">Expression</span></span> |<span data-ttu-id="78720-288">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-288">Result</span></span>|<span data-ttu-id="78720-289">Resultado binário</span><span class="sxs-lookup"><span data-stu-id="78720-289">Binary Result</span></span>|
|-----------|------|-------------|
|`21 -shl 0`|<span data-ttu-id="78720-290">21</span><span class="sxs-lookup"><span data-stu-id="78720-290">21</span></span>    |<span data-ttu-id="78720-291">0001 0101</span><span class="sxs-lookup"><span data-stu-id="78720-291">0001 0101</span></span>    |
|`21 -shl 1`|<span data-ttu-id="78720-292">42</span><span class="sxs-lookup"><span data-stu-id="78720-292">42</span></span>    |<span data-ttu-id="78720-293">0010 1010</span><span class="sxs-lookup"><span data-stu-id="78720-293">0010 1010</span></span>    |
|`21 -shl 2`|<span data-ttu-id="78720-294">84</span><span class="sxs-lookup"><span data-stu-id="78720-294">84</span></span>    |<span data-ttu-id="78720-295">0101 0100</span><span class="sxs-lookup"><span data-stu-id="78720-295">0101 0100</span></span>    |

<span data-ttu-id="78720-296">Em uma operação Shift-Right de bit-a-ponto, todos os bits são movidos para "n" locais à direita, onde "n" é especificado pelo operando à direita.</span><span class="sxs-lookup"><span data-stu-id="78720-296">In a bitwise shift-right operation, all bits are moved "n" places to the right, where "n" is specified by the right operand.</span></span> <span data-ttu-id="78720-297">O operador Shift-Right (-SHR) insere um zero no lugar à esquerda ao deslocar um valor positivo ou não assinado para a direita.</span><span class="sxs-lookup"><span data-stu-id="78720-297">The shift-right operator (-shr) inserts a zero in the left-most place when shifting a positive or unsigned value to the right.</span></span>

<span data-ttu-id="78720-298">Quando o operando esquerdo é um valor inteiro (32 bits), os 5 bits inferiores do operando direito determinam quantos bits do operando esquerdo são deslocados.</span><span class="sxs-lookup"><span data-stu-id="78720-298">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="78720-299">Quando o operando esquerdo é um valor longo (64 bits), os 6 bits inferiores do operando à direita determinam quantos bits do operando esquerdo são deslocados.</span><span class="sxs-lookup"><span data-stu-id="78720-299">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="78720-300">Expression</span><span class="sxs-lookup"><span data-stu-id="78720-300">Expression</span></span>              |<span data-ttu-id="78720-301">Resultado</span><span class="sxs-lookup"><span data-stu-id="78720-301">Result</span></span>      |<span data-ttu-id="78720-302">Binário</span><span class="sxs-lookup"><span data-stu-id="78720-302">Binary</span></span>     |<span data-ttu-id="78720-303">Hex</span><span class="sxs-lookup"><span data-stu-id="78720-303">Hex</span></span>         |
|------------------------|------------|-----------|------------|
|`21 -shr 0`             | <span data-ttu-id="78720-304">21</span><span class="sxs-lookup"><span data-stu-id="78720-304">21</span></span>         | <span data-ttu-id="78720-305">0001 0101</span><span class="sxs-lookup"><span data-stu-id="78720-305">0001 0101</span></span> | <span data-ttu-id="78720-306">0x15</span><span class="sxs-lookup"><span data-stu-id="78720-306">0x15</span></span>       |
|`21 -shr 1`             | <span data-ttu-id="78720-307">10</span><span class="sxs-lookup"><span data-stu-id="78720-307">10</span></span>         | <span data-ttu-id="78720-308">0000 1010</span><span class="sxs-lookup"><span data-stu-id="78720-308">0000 1010</span></span> | <span data-ttu-id="78720-309">0x0A</span><span class="sxs-lookup"><span data-stu-id="78720-309">0x0A</span></span>       |
|`21 -shr 2`             | <span data-ttu-id="78720-310">5</span><span class="sxs-lookup"><span data-stu-id="78720-310">5</span></span>          | <span data-ttu-id="78720-311">0000 0101</span><span class="sxs-lookup"><span data-stu-id="78720-311">0000 0101</span></span> | <span data-ttu-id="78720-312">0x05</span><span class="sxs-lookup"><span data-stu-id="78720-312">0x05</span></span>       |
|`21 -shr 31`            | <span data-ttu-id="78720-313">0</span><span class="sxs-lookup"><span data-stu-id="78720-313">0</span></span>          | <span data-ttu-id="78720-314">0000 0000</span><span class="sxs-lookup"><span data-stu-id="78720-314">0000 0000</span></span> | <span data-ttu-id="78720-315">0x00</span><span class="sxs-lookup"><span data-stu-id="78720-315">0x00</span></span>       |
|`21 -shr 32`            | <span data-ttu-id="78720-316">21</span><span class="sxs-lookup"><span data-stu-id="78720-316">21</span></span>         | <span data-ttu-id="78720-317">0001 0101</span><span class="sxs-lookup"><span data-stu-id="78720-317">0001 0101</span></span> | <span data-ttu-id="78720-318">0x15</span><span class="sxs-lookup"><span data-stu-id="78720-318">0x15</span></span>       |
|`21 -shr 64`            | <span data-ttu-id="78720-319">21</span><span class="sxs-lookup"><span data-stu-id="78720-319">21</span></span>         | <span data-ttu-id="78720-320">0001 0101</span><span class="sxs-lookup"><span data-stu-id="78720-320">0001 0101</span></span> | <span data-ttu-id="78720-321">0x15</span><span class="sxs-lookup"><span data-stu-id="78720-321">0x15</span></span>       |
|`21 -shr 65`            | <span data-ttu-id="78720-322">10</span><span class="sxs-lookup"><span data-stu-id="78720-322">10</span></span>         | <span data-ttu-id="78720-323">0000 1010</span><span class="sxs-lookup"><span data-stu-id="78720-323">0000 1010</span></span> | <span data-ttu-id="78720-324">0x0A</span><span class="sxs-lookup"><span data-stu-id="78720-324">0x0A</span></span>       |
|`21 -shr 66`            | <span data-ttu-id="78720-325">5</span><span class="sxs-lookup"><span data-stu-id="78720-325">5</span></span>          | <span data-ttu-id="78720-326">0000 0101</span><span class="sxs-lookup"><span data-stu-id="78720-326">0000 0101</span></span> | <span data-ttu-id="78720-327">0x05</span><span class="sxs-lookup"><span data-stu-id="78720-327">0x05</span></span>       |
|`[int]::MaxValue -shr 1`| <span data-ttu-id="78720-328">1073741823</span><span class="sxs-lookup"><span data-stu-id="78720-328">1073741823</span></span> |           | <span data-ttu-id="78720-329">0x3FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="78720-329">0x3FFFFFFF</span></span> |
|`[int]::MinValue -shr 1`| <span data-ttu-id="78720-330">-1073741824</span><span class="sxs-lookup"><span data-stu-id="78720-330">-1073741824</span></span>|           | <span data-ttu-id="78720-331">0xC0000000</span><span class="sxs-lookup"><span data-stu-id="78720-331">0xC0000000</span></span> |
|`-1 -shr 1`             | <span data-ttu-id="78720-332">-1</span><span class="sxs-lookup"><span data-stu-id="78720-332">-1</span></span>         |           | <span data-ttu-id="78720-333">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="78720-333">0xFFFFFFFF</span></span> |

## <a name="see-also"></a><span data-ttu-id="78720-334">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="78720-334">SEE ALSO</span></span>

- [<span data-ttu-id="78720-335">about_arrays</span><span class="sxs-lookup"><span data-stu-id="78720-335">about_arrays</span></span>](about_Arrays.md)
- [<span data-ttu-id="78720-336">about_assignment_operators</span><span class="sxs-lookup"><span data-stu-id="78720-336">about_assignment_operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="78720-337">about_comparison_operators</span><span class="sxs-lookup"><span data-stu-id="78720-337">about_comparison_operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="78720-338">about_hash_tables</span><span class="sxs-lookup"><span data-stu-id="78720-338">about_hash_tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="78720-339">about_operators</span><span class="sxs-lookup"><span data-stu-id="78720-339">about_operators</span></span>](about_Operators.md)
- [<span data-ttu-id="78720-340">about_variables</span><span class="sxs-lookup"><span data-stu-id="78720-340">about_variables</span></span>](about_Variables.md)
- [<span data-ttu-id="78720-341">Obter Data</span><span class="sxs-lookup"><span data-stu-id="78720-341">Get-Date</span></span>](xref:Microsoft.PowerShell.Utility.Get-Date)
- [<span data-ttu-id="78720-342">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="78720-342">New-TimeSpan</span></span>](xref:Microsoft.PowerShell.Utility.New-TimeSpan)
