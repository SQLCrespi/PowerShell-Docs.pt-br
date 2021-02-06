---
description: Descreve os operadores que conectam instruções no PowerShell.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 8602551f3ecf74027b59715e1f47aab1b10bea92
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595549"
---
# <a name="about_logical_operators"></a><span data-ttu-id="419bd-103">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="419bd-103">about_Logical_Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="419bd-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="419bd-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="419bd-105">Descreve os operadores que conectam instruções no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="419bd-105">Describes the operators that connect statements in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="419bd-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="419bd-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="419bd-107">Os operadores lógicos do PowerShell conectam expressões e instruções, permitindo que você use uma única expressão para testar várias condições.</span><span class="sxs-lookup"><span data-stu-id="419bd-107">The PowerShell logical operators connect expressions and statements, allowing you to use a single expression to test for multiple conditions.</span></span>

<span data-ttu-id="419bd-108">Por exemplo, a instrução a seguir usa o operador and e o operador OR para conectar três instruções condicionais.</span><span class="sxs-lookup"><span data-stu-id="419bd-108">For example, the following statement uses the and operator and the or operator to connect three conditional statements.</span></span> <span data-ttu-id="419bd-109">A instrução é verdadeira somente quando o valor de $a é maior que o valor de $b e $a ou $b é menor que</span><span class="sxs-lookup"><span data-stu-id="419bd-109">The statement is true only when the value of $a is greater than the value of $b, and either $a or $b is less than</span></span>
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

<span data-ttu-id="419bd-110">O PowerShell dá suporte aos seguintes operadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="419bd-110">PowerShell supports the following logical operators.</span></span>

|<span data-ttu-id="419bd-111">Operador</span><span class="sxs-lookup"><span data-stu-id="419bd-111">Operator</span></span>|<span data-ttu-id="419bd-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="419bd-112">Description</span></span>                        |<span data-ttu-id="419bd-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="419bd-113">Example</span></span>                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |<span data-ttu-id="419bd-114">AND Lógico.</span><span class="sxs-lookup"><span data-stu-id="419bd-114">Logical AND.</span></span> <span data-ttu-id="419bd-115">VERDADEIRO quando ambos</span><span class="sxs-lookup"><span data-stu-id="419bd-115">TRUE when both</span></span>        |`(1 -eq 1) -and (1 -eq 2)`|
|        |<span data-ttu-id="419bd-116">as instruções são verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="419bd-116">statements are TRUE.</span></span>               |`False`                   |
|`-or`   |<span data-ttu-id="419bd-117">OR Lógico.</span><span class="sxs-lookup"><span data-stu-id="419bd-117">Logical OR.</span></span> <span data-ttu-id="419bd-118">VERDADEIRO quando o</span><span class="sxs-lookup"><span data-stu-id="419bd-118">TRUE when either</span></span>       |`(1 -eq 1) -or (1 -eq 2)` |
|        |<span data-ttu-id="419bd-119">a instrução é verdadeira.</span><span class="sxs-lookup"><span data-stu-id="419bd-119">statement is TRUE.</span></span>                 |`True`                    |
|`-xor`  |<span data-ttu-id="419bd-120">Lógico exclusivo ou.</span><span class="sxs-lookup"><span data-stu-id="419bd-120">Logical EXCLUSIVE OR.</span></span> <span data-ttu-id="419bd-121">VERDADEIRO quando</span><span class="sxs-lookup"><span data-stu-id="419bd-121">TRUE when</span></span>    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |<span data-ttu-id="419bd-122">apenas uma instrução é verdadeira</span><span class="sxs-lookup"><span data-stu-id="419bd-122">only one statement is TRUE</span></span>         |`False`                   |
|`-not`  |<span data-ttu-id="419bd-123">Não lógico.</span><span class="sxs-lookup"><span data-stu-id="419bd-123">Logical not.</span></span> <span data-ttu-id="419bd-124">Nega a instrução</span><span class="sxs-lookup"><span data-stu-id="419bd-124">Negates the statement</span></span> |`-not (1 -eq 1)`          |
|        |<span data-ttu-id="419bd-125">a seguir.</span><span class="sxs-lookup"><span data-stu-id="419bd-125">that follows.</span></span>                      |`False`                   |
|`!`     |<span data-ttu-id="419bd-126">Mesmo que `-not`</span><span class="sxs-lookup"><span data-stu-id="419bd-126">Same as `-not`</span></span>                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 <span data-ttu-id="419bd-127">Observação:</span><span class="sxs-lookup"><span data-stu-id="419bd-127">Note:</span></span>

<span data-ttu-id="419bd-128">Os exemplos anteriores também usam o operador de comparação igual a `-eq` .</span><span class="sxs-lookup"><span data-stu-id="419bd-128">The previous examples also use the equal to comparison operator `-eq`.</span></span> <span data-ttu-id="419bd-129">Para obter mais informações, consulte [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="419bd-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span> <span data-ttu-id="419bd-130">Os exemplos também usam os valores Boolianos de inteiros.</span><span class="sxs-lookup"><span data-stu-id="419bd-130">The examples also use the Boolean values of integers.</span></span> <span data-ttu-id="419bd-131">O inteiro 0 tem um valor de FALSE.</span><span class="sxs-lookup"><span data-stu-id="419bd-131">The integer 0 has a value of FALSE.</span></span> <span data-ttu-id="419bd-132">Todos os outros inteiros têm um valor de TRUE.</span><span class="sxs-lookup"><span data-stu-id="419bd-132">All other integers have a value of TRUE.</span></span>

<span data-ttu-id="419bd-133">A sintaxe dos operadores lógicos é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="419bd-133">The syntax of the logical operators is as follows:</span></span>

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

<span data-ttu-id="419bd-134">As instruções que usam os operadores lógicos retornam valores Boolianos (TRUE ou FALSE).</span><span class="sxs-lookup"><span data-stu-id="419bd-134">Statements that use the logical operators return Boolean (TRUE or FALSE) values.</span></span>

<span data-ttu-id="419bd-135">Os operadores lógicos do PowerShell avaliam apenas as instruções necessárias para determinar o valor da verdade da instrução.</span><span class="sxs-lookup"><span data-stu-id="419bd-135">The PowerShell logical operators evaluate only the statements required to determine the truth value of the statement.</span></span> <span data-ttu-id="419bd-136">Se o operando esquerdo em uma instrução que contém o operador and for FALSE, o operando direito não será avaliado.</span><span class="sxs-lookup"><span data-stu-id="419bd-136">If the left operand in a statement that contains the and operator is FALSE, the right operand is not evaluated.</span></span>
<span data-ttu-id="419bd-137">Se o operando esquerdo em uma instrução que contém a instrução ou for TRUE, o operando direito não será avaliado.</span><span class="sxs-lookup"><span data-stu-id="419bd-137">If the left operand in a statement that contains the or statement is TRUE, the right operand is not evaluated.</span></span> <span data-ttu-id="419bd-138">Como resultado, você pode usar essas instruções da mesma maneira que usaria a `If` instrução.</span><span class="sxs-lookup"><span data-stu-id="419bd-138">As a result, you can use these statements in the same way that you would use the `If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="419bd-139">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="419bd-139">SEE ALSO</span></span>

[<span data-ttu-id="419bd-140">about_Operators</span><span class="sxs-lookup"><span data-stu-id="419bd-140">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="419bd-141">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="419bd-141">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="419bd-142">about_Comparison_operators</span><span class="sxs-lookup"><span data-stu-id="419bd-142">about_Comparison_operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="419bd-143">about_If</span><span class="sxs-lookup"><span data-stu-id="419bd-143">about_If</span></span>](about_If.md)

