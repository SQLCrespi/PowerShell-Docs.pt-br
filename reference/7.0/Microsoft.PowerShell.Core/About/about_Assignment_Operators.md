---
description: Descreve como usar operadores para atribuir valores a variáveis.
keywords: powershell, cmdlet
ms.date: 04/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: fba0c5f5e5263af15eb3d56f1c42a881057afc46
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196079"
---
# <a name="about-assignment-operators"></a><span data-ttu-id="4c3f8-104">Sobre operadores de atribuição</span><span class="sxs-lookup"><span data-stu-id="4c3f8-104">About Assignment Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="4c3f8-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="4c3f8-105">Short description</span></span>
<span data-ttu-id="4c3f8-106">Descreve como usar operadores para atribuir valores a variáveis.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-106">Describes how to use operators to assign values to variables.</span></span>

## <a name="long-description"></a><span data-ttu-id="4c3f8-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="4c3f8-107">Long description</span></span>

<span data-ttu-id="4c3f8-108">Os operadores de atribuição atribuem um ou mais valores a uma variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-108">Assignment operators assign one or more values to a variable.</span></span> <span data-ttu-id="4c3f8-109">Eles podem executar operações numéricas nos valores antes da atribuição.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-109">They can perform numeric operations on the values before the assignment.</span></span>

<span data-ttu-id="4c3f8-110">O PowerShell dá suporte aos seguintes operadores de atribuição.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-110">PowerShell supports the following assignment operators.</span></span>

|<span data-ttu-id="4c3f8-111">Operador</span><span class="sxs-lookup"><span data-stu-id="4c3f8-111">Operator</span></span>|<span data-ttu-id="4c3f8-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c3f8-112">Description</span></span>                                                  |
|--------|-------------------------------------------------------------|
|=       |<span data-ttu-id="4c3f8-113">Define o valor de uma variável para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-113">Sets the value of a variable to the specified value.</span></span>         |
|+=      |<span data-ttu-id="4c3f8-114">Aumenta o valor de uma variável pelo valor especificado ou</span><span class="sxs-lookup"><span data-stu-id="4c3f8-114">Increases the value of a variable by the specified value, or</span></span> |
|        |<span data-ttu-id="4c3f8-115">acrescenta o valor especificado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-115">appends the specified value to the existing value.</span></span>           |
|-=      |<span data-ttu-id="4c3f8-116">Diminui o valor de uma variável pelo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-116">Decreases the value of a variable by the specified value.</span></span>    |
|*=      |<span data-ttu-id="4c3f8-117">Multiplica o valor de uma variável pelo valor especificado ou</span><span class="sxs-lookup"><span data-stu-id="4c3f8-117">Multiplies the value of a variable by the specified value, or</span></span>|
|        |<span data-ttu-id="4c3f8-118">acrescenta o valor especificado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-118">appends the specified value to the existing value.</span></span>           |
|/=      |<span data-ttu-id="4c3f8-119">Divide o valor de uma variável pelo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-119">Divides the value of a variable by the specified value.</span></span>      |
|%=      |<span data-ttu-id="4c3f8-120">Divide o valor de uma variável pelo valor especificado e</span><span class="sxs-lookup"><span data-stu-id="4c3f8-120">Divides the value of a variable by the specified value and</span></span>   |
|        |<span data-ttu-id="4c3f8-121">em seguida, atribui o resto (módulo) à variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-121">then assigns the remainder (modulus) to the variable.</span></span>        |
|++      |<span data-ttu-id="4c3f8-122">Aumenta o valor de uma variável, Propriedade atribuível ou</span><span class="sxs-lookup"><span data-stu-id="4c3f8-122">Increases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="4c3f8-123">elemento de matriz em 1.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-123">array element by 1.</span></span>                                          |
|--      |<span data-ttu-id="4c3f8-124">Diminui o valor de uma variável, Propriedade atribuível ou</span><span class="sxs-lookup"><span data-stu-id="4c3f8-124">Decreases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="4c3f8-125">elemento de matriz em 1.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-125">array element by 1.</span></span>                                          |

## <a name="syntax"></a><span data-ttu-id="4c3f8-126">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c3f8-126">Syntax</span></span>

<span data-ttu-id="4c3f8-127">A sintaxe dos operadores de atribuição é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-127">The syntax of the assignment operators is as follows:</span></span>

<span data-ttu-id="4c3f8-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span><span class="sxs-lookup"><span data-stu-id="4c3f8-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span></span>

<span data-ttu-id="4c3f8-129">As expressões atribuíveis incluem variáveis e propriedades.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-129">Assignable expressions include variables and properties.</span></span> <span data-ttu-id="4c3f8-130">O valor pode ser um único valor, uma matriz de valores ou um comando, expressão ou instrução.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-130">The value can be a single value, an array of values, or a command, expression, or statement.</span></span>

<span data-ttu-id="4c3f8-131">Os operadores de incremento e decremento são operadores unários.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-131">The increment and decrement operators are unary operators.</span></span> <span data-ttu-id="4c3f8-132">Cada uma tem versões de prefixo e sufixo.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-132">Each has prefix and postfix versions.</span></span>

`<assignable-expression><operator>`
`<operator><assignable-expression>`

<span data-ttu-id="4c3f8-133">A expressão atribuível deve ser um número ou deve ser conversível em um número.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-133">The assignable expression must be a number or it must be convertible to a number.</span></span>

## <a name="assigning-values"></a><span data-ttu-id="4c3f8-134">Atribuindo valores</span><span class="sxs-lookup"><span data-stu-id="4c3f8-134">Assigning values</span></span>

<span data-ttu-id="4c3f8-135">Variáveis são nomes de espaços de memória que armazenam valores.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-135">Variables are named memory spaces that store values.</span></span> <span data-ttu-id="4c3f8-136">Você armazena os valores em variáveis usando o operador de atribuição `=` .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-136">You store the values in variables by using the assignment operator `=`.</span></span> <span data-ttu-id="4c3f8-137">O novo valor pode substituir o valor existente da variável ou você pode acrescentar um novo valor ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-137">The new value can replace the existing value of the variable, or you can append a new value to the existing value.</span></span>

<span data-ttu-id="4c3f8-138">O operador de atribuição básica é o sinal de igual `=` `(ASCII 61)` .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-138">The basic assignment operator is the equal sign `=` `(ASCII 61)`.</span></span> <span data-ttu-id="4c3f8-139">Por exemplo, a instrução a seguir atribui o valor PowerShell à `$MyShell` variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-139">For example, the following statement assigns the value PowerShell to the `$MyShell` variable:</span></span>

```powershell
$MyShell = "PowerShell"
```

<span data-ttu-id="4c3f8-140">Quando você atribui um valor a uma variável no PowerShell, a variável é criada, caso ainda não exista.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-140">When you assign a value to a variable in PowerShell, the variable is created if it did not already exist.</span></span> <span data-ttu-id="4c3f8-141">Por exemplo, a primeira das duas instruções de atribuição a seguir cria a `$a` variável e atribui um valor de 6 a `$a` .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-141">For example, the first of the following two assignment statements creates the `$a` variable and assigns a value of 6 to `$a`.</span></span> <span data-ttu-id="4c3f8-142">A segunda instrução de atribuição atribui um valor de 12 a `$a` .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-142">The second assignment statement assigns a value of 12 to `$a`.</span></span> <span data-ttu-id="4c3f8-143">A primeira instrução cria uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-143">The first statement creates a new variable.</span></span> <span data-ttu-id="4c3f8-144">A segunda instrução altera apenas seu valor:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-144">The second statement changes only its value:</span></span>

```powershell
$a = 6
$a = 12
```

<span data-ttu-id="4c3f8-145">As variáveis no PowerShell não têm um tipo de dados específico, a menos que você as converta.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-145">Variables in PowerShell do not have a specific data type unless you cast them.</span></span>
<span data-ttu-id="4c3f8-146">Quando uma variável contém apenas um objeto, a variável usa o tipo de dados desse objeto.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-146">When a variable contains only one object, the variable takes the data type of that object.</span></span> <span data-ttu-id="4c3f8-147">Quando uma variável contém uma coleção de objetos, a variável tem o tipo de dados System. Object.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-147">When a variable contains a collection of objects, the variable has the System.Object data type.</span></span> <span data-ttu-id="4c3f8-148">Portanto, você pode atribuir qualquer tipo de objeto à coleção.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-148">Therefore, you can assign any type of object to the collection.</span></span> <span data-ttu-id="4c3f8-149">O exemplo a seguir mostra que você pode adicionar objetos de processo, objetos de serviço, cadeias de caracteres e inteiros a uma variável sem gerar um erro:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-149">The following example shows that you can add process objects, service objects, strings, and integers to a variable without generating an error:</span></span>

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

<span data-ttu-id="4c3f8-150">Como o operador de atribuição `=` tem uma precedência mais baixa do que o operador de pipeline `|` , não são necessários parênteses para atribuir o resultado de um pipeline de comando a uma variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-150">Because the assignment operator `=` has a lower precedence than the pipeline operator `|`, parentheses are not required to assign the result of a command pipeline to a variable.</span></span> <span data-ttu-id="4c3f8-151">Por exemplo, o comando a seguir classifica os serviços no computador e atribui os serviços classificados à `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-151">For example, the following command sorts the services on the computer and then assigns the sorted services to the `$a` variable:</span></span>

```powershell
$a = Get-Service | Sort-Object -Property name
```

<span data-ttu-id="4c3f8-152">Você também pode atribuir o valor criado por uma instrução a uma variável, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-152">You can also assign the value created by a statement to a variable, as in the following example:</span></span>

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

<span data-ttu-id="4c3f8-153">Este exemplo atribui zero à `$a` variável se o valor de `$b` for menor que zero.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-153">This example assigns zero to the `$a` variable if the value of `$b` is less than zero.</span></span> <span data-ttu-id="4c3f8-154">Ele atribui o valor de `$b` para `$a` se o valor de `$b` não for menor que zero.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-154">It assigns the value of `$b` to `$a` if the value of `$b` is not less than zero.</span></span>

### <a name="the-assignment-operator"></a><span data-ttu-id="4c3f8-155">O operador de atribuição</span><span class="sxs-lookup"><span data-stu-id="4c3f8-155">The assignment operator</span></span>

<span data-ttu-id="4c3f8-156">O operador de atribuição `=` atribui valores a variáveis.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-156">The assignment operator `=` assigns values to variables.</span></span> <span data-ttu-id="4c3f8-157">Se a variável já tiver um valor, o operador de atribuição `=` substituirá o valor sem aviso.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-157">If the variable already has a value, the assignment operator `=` replaces the value without warning.</span></span>

<span data-ttu-id="4c3f8-158">A instrução a seguir atribui o valor inteiro 6 à `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-158">The following statement assigns the integer value 6 to the `$a` variable:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="4c3f8-159">Para atribuir um valor de cadeia de caracteres a uma variável, coloque o valor da cadeia de caracteres entre aspas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-159">To assign a string value to a variable, enclose the string value in quotation marks, as follows:</span></span>

```powershell
$a = "baseball"
```

<span data-ttu-id="4c3f8-160">Para atribuir uma matriz (vários valores) a uma variável, separe os valores com vírgulas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-160">To assign an array (multiple values) to a variable, separate the values with commas, as follows:</span></span>

```powershell
$a = "apple", "orange", "lemon", "grape"
```

<span data-ttu-id="4c3f8-161">Para atribuir uma tabela de hash a uma variável, use a notação de tabela de hash padrão no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-161">To assign a hash table to a variable, use the standard hash table notation in PowerShell.</span></span> <span data-ttu-id="4c3f8-162">Digite um sinal de entrada `@` seguido por pares de chave/valor separados por ponto e vírgula `;` e entre chaves `{ }` .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-162">Type an at sign `@` followed by key/value pairs that are separated by semicolons `;` and enclosed in braces `{ }`.</span></span> <span data-ttu-id="4c3f8-163">Por exemplo, para atribuir uma tabela de hash à `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-163">For example, to assign a hash table to the `$a` variable, type:</span></span>

```powershell
$a = @{one=1; two=2; three=3}
```

<span data-ttu-id="4c3f8-164">Para atribuir valores hexadecimais a uma variável, preceda o valor com `0x` .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-164">To assign hexadecimal values to a variable, precede the value with `0x`.</span></span>
<span data-ttu-id="4c3f8-165">O PowerShell converte o valor hexadecimal (0x10) em um valor decimal (neste caso, 16) e atribui esse valor à `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-165">PowerShell converts the hexadecimal value (0x10) to a decimal value (in this case, 16) and assigns that value to the `$a` variable.</span></span> <span data-ttu-id="4c3f8-166">Por exemplo, para atribuir um valor de 0x10 à `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-166">For example, to assign a value of 0x10 to the `$a` variable, type:</span></span>

```powershell
$a = 0x10
```

<span data-ttu-id="4c3f8-167">Para atribuir um valor exponencial a uma variável, digite o número raiz, a letra `e` e um número que represente um múltiplo de 10.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-167">To assign an exponential value to a variable, type the root number, the letter `e`, and a number that represents a multiple of 10.</span></span> <span data-ttu-id="4c3f8-168">Por exemplo, para atribuir um valor de 3,1415 à potência de 1.000 para a `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-168">For example, to assign a value of 3.1415 to the power of 1,000 to the `$a` variable, type:</span></span>

```powershell
$a = 3.1415e3
```

<span data-ttu-id="4c3f8-169">O PowerShell também pode converter quilobytes `KB` , megabytes `MB` e gigabytes `GB` em bytes.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-169">PowerShell can also convert kilobytes `KB`, megabytes `MB`, and gigabytes `GB` into bytes.</span></span> <span data-ttu-id="4c3f8-170">Por exemplo, para atribuir um valor de 10 kilobytes à `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-170">For example, to assign a value of 10 kilobytes to the `$a` variable, type:</span></span>

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a><span data-ttu-id="4c3f8-171">O operador de atribuição por adição</span><span class="sxs-lookup"><span data-stu-id="4c3f8-171">The assignment by addition operator</span></span>

<span data-ttu-id="4c3f8-172">O operador atribuição por adição `+=` incrementa o valor de uma variável ou acrescenta o valor especificado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-172">The assignment by addition operator `+=` either increments the value of a variable or appends the specified value to the existing value.</span></span> <span data-ttu-id="4c3f8-173">A ação depende de se a variável tem um tipo numérico ou de cadeia de caracteres e se a variável contém um único valor (um escalar) ou vários valores (uma coleção).</span><span class="sxs-lookup"><span data-stu-id="4c3f8-173">The action depends on whether the variable has a numeric or string type and whether the variable contains a single value (a scalar) or multiple values (a collection).</span></span>

<span data-ttu-id="4c3f8-174">O `+=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-174">The `+=` operator combines two operations.</span></span> <span data-ttu-id="4c3f8-175">Primeiro, ele adiciona e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-175">First, it adds, and then it assigns.</span></span>
<span data-ttu-id="4c3f8-176">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-176">Therefore, the following statements are equivalent:</span></span>

```powershell
$a += 2
$a = ($a + 2)
```

<span data-ttu-id="4c3f8-177">Quando a variável contém um único valor numérico, o `+=` operador incrementa o valor existente pelo valor no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-177">When the variable contains a single numeric value, the `+=` operator increments the existing value by the amount on the right side of the operator.</span></span> <span data-ttu-id="4c3f8-178">Em seguida, o operador atribui o valor resultante à variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-178">Then, the operator assigns the resulting value to the variable.</span></span> <span data-ttu-id="4c3f8-179">O exemplo a seguir mostra como usar o `+=` operador para aumentar o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-179">The following example shows how to use the `+=` operator to increase the value of a variable:</span></span>

```powershell
$a = 4
$a += 2
$a
```

```
6
```

<span data-ttu-id="4c3f8-180">Quando o valor da variável é uma cadeia de caracteres, o valor no lado direito do operador é acrescentado à cadeia de caracteres da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-180">When the value of the variable is a string, the value on the right side of the operator is appended to the string, as follows:</span></span>

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

<span data-ttu-id="4c3f8-181">Quando o valor da variável é uma matriz, o `+=` operador acrescenta os valores no lado direito do operador à matriz.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-181">When the value of the variable is an array, the `+=` operator appends the values on the right side of the operator to the array.</span></span> <span data-ttu-id="4c3f8-182">A menos que a matriz seja digitada explicitamente pela conversão, você pode acrescentar qualquer tipo de valor à matriz, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-182">Unless the array is explicitly typed by casting, you can append any type of value to the array, as follows:</span></span>

```powershell
$a = 1,2,3
$a += 2
$a
```

```
1
2
3
2
```

<span data-ttu-id="4c3f8-183">e</span><span class="sxs-lookup"><span data-stu-id="4c3f8-183">and</span></span>

```powershell
$a += "String"
$a
```

```
1
2
3
2
String
```

<span data-ttu-id="4c3f8-184">Quando o valor de uma variável é uma tabela de hash, o `+=` operador acrescenta o valor no lado direito do operador à tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-184">When the value of a variable is a hash table, the `+=` operator appends the value on the right side of the operator to the hash table.</span></span> <span data-ttu-id="4c3f8-185">No entanto, como o único tipo que você pode adicionar a uma tabela de hash é outra tabela de hash, todas as outras atribuições falham.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-185">However, because the only type that you can add to a hash table is another hash table, all other assignments fail.</span></span>

<span data-ttu-id="4c3f8-186">Por exemplo, o comando a seguir atribui uma tabela de hash à `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-186">For example, the following command assigns a hash table to the `$a` variable.</span></span>
<span data-ttu-id="4c3f8-187">Em seguida, ele usa o `+=` operador para acrescentar outra tabela de hash à tabela de hash existente, adicionando efetivamente um novo par de chave/valor à tabela de hash existente.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-187">Then, it uses the `+=` operator to append another hash table to the existing hash table, effectively adding a new key/value pair to the existing hash table.</span></span>
<span data-ttu-id="4c3f8-188">Esse comando é bem sucedido, conforme mostrado na saída:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-188">This command succeeds, as shown in the output:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += @{mode = "write"}
$a
```

```
Name                           Value
----                           -----
a                              1
b                              2
mode                           write
c                              3
```

<span data-ttu-id="4c3f8-189">O comando a seguir tenta acrescentar um inteiro "1" à tabela de hash na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-189">The following command attempts to append an integer "1" to the hash table in the `$a` variable.</span></span> <span data-ttu-id="4c3f8-190">Este comando falha:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-190">This command fails:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a><span data-ttu-id="4c3f8-191">O operador de atribuição por subtração</span><span class="sxs-lookup"><span data-stu-id="4c3f8-191">The assignment by subtraction operator</span></span>

<span data-ttu-id="4c3f8-192">O operador atribuição por subtração `-=` Decrementa o valor de uma variável pelo valor especificado no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-192">The assignment by subtraction operator `-=` decrements the value of a variable by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="4c3f8-193">Esse operador não pode ser usado com variáveis de cadeia de caracteres e não pode ser usado para remover um elemento de uma coleção.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-193">This operator cannot be used with string variables, and it cannot be used to remove an element from a collection.</span></span>

<span data-ttu-id="4c3f8-194">O `-=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-194">The `-=` operator combines two operations.</span></span> <span data-ttu-id="4c3f8-195">Primeiro, ele subtrai e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-195">First, it subtracts, and then it assigns.</span></span> <span data-ttu-id="4c3f8-196">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-196">Therefore, the following statements are equivalent:</span></span>

```powershell
$a -= 2
$a = ($a - 2)
```

<span data-ttu-id="4c3f8-197">O exemplo a seguir mostra como usar o `-=` operador para diminuir o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-197">The following example shows how to use of the `-=` operator to decrease the value of a variable:</span></span>

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

<span data-ttu-id="4c3f8-198">Você também pode usar o `-=` operador de atribuição para diminuir o valor de um membro de uma matriz numérica.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-198">You can also use the `-=` assignment operator to decrease the value of a member of a numeric array.</span></span> <span data-ttu-id="4c3f8-199">Para fazer isso, especifique o índice do elemento da matriz que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-199">To do this, specify the index of the array element that you want to change.</span></span> <span data-ttu-id="4c3f8-200">No exemplo a seguir, o valor do terceiro elemento de uma matriz (elemento 2) é diminuído em 1:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-200">In the following example, the value of the third element of an array (element 2) is decreased by 1:</span></span>

```powershell
$a = 1,2,3
$a[2] -= 1
$a
```

```
1
2
2
```

<span data-ttu-id="4c3f8-201">Você não pode usar o `-=` operador para excluir os valores de uma variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-201">You cannot use the `-=` operator to delete the values of a variable.</span></span> <span data-ttu-id="4c3f8-202">Para excluir todos os valores atribuídos a uma variável, use os cmdlets [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) ou [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) para atribuir um valor de `$null` ou `""` à variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-202">To delete all the values that are assigned to a variable, use the [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) or [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) cmdlets to assign a value of `$null` or `""` to the variable.</span></span>

```powershell
$a = $null
```

<span data-ttu-id="4c3f8-203">Para excluir um valor específico de uma matriz, use a notação de matriz para atribuir um valor de `$null` para o item específico.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-203">To delete a particular value from an array, use array notation to assign a value of `$null` to the particular item.</span></span> <span data-ttu-id="4c3f8-204">Por exemplo, a instrução a seguir exclui o segundo valor (posição de índice 1) de uma matriz:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-204">For example, the following statement deletes the second value (index position 1) from an array:</span></span>

```powershell
$a = 1,2,3
$a
```

```
1
2
3
```

```powershell
$a[1] = $null
$a
```

```
1
3
```

<span data-ttu-id="4c3f8-205">Para excluir uma variável, use o cmdlet [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-205">To delete a variable, use the [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) cmdlet.</span></span> <span data-ttu-id="4c3f8-206">Esse método é útil quando a variável é convertida explicitamente em um tipo de dados específico e você deseja uma variável não tipada.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-206">This method is useful when the variable is explicitly cast to a particular data type, and you want an untyped variable.</span></span> <span data-ttu-id="4c3f8-207">O comando a seguir exclui a `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-207">The following command deletes the `$a` variable:</span></span>

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a><span data-ttu-id="4c3f8-208">A atribuição por operador de multiplicação</span><span class="sxs-lookup"><span data-stu-id="4c3f8-208">The assignment by multiplication operator</span></span>

<span data-ttu-id="4c3f8-209">A atribuição por operador de multiplicação `*=` multiplica um valor numérico ou acrescenta o número especificado de cópias do valor da cadeia de caracteres de uma variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-209">The assignment by multiplication operator `*=` multiplies a numeric value or appends the specified number of copies of the string value of a variable.</span></span>

<span data-ttu-id="4c3f8-210">Quando uma variável contém um único valor numérico, esse valor é multiplicado pelo valor no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-210">When a variable contains a single numeric value, that value is multiplied by the value on the right side of the operator.</span></span> <span data-ttu-id="4c3f8-211">Por exemplo, o exemplo a seguir mostra como usar o `*=` operador para multiplicar o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-211">For example, the following example shows how to use the `*=` operator to multiply the value of a variable:</span></span>

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

<span data-ttu-id="4c3f8-212">Nesse caso, o `*=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-212">In this case, the `*=` operator combines two operations.</span></span> <span data-ttu-id="4c3f8-213">Primeiro, ele multiplica e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-213">First, it multiplies, and then it assigns.</span></span> <span data-ttu-id="4c3f8-214">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-214">Therefore, the following statements are equivalent:</span></span>

```powershell
$a *= 2
$a = ($a * 2)
```

<span data-ttu-id="4c3f8-215">Quando uma variável contém um valor de cadeia de caracteres, o PowerShell anexa o número de cadeias de caracteres especificado ao valor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-215">When a variable contains a string value, PowerShell appends the specified number of strings to the value, as follows:</span></span>

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

<span data-ttu-id="4c3f8-216">Para multiplicar um elemento de uma matriz, use um índice para identificar o elemento que você deseja multiplicar.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-216">To multiply an element of an array, use an index to identify the element that you want to multiply.</span></span> <span data-ttu-id="4c3f8-217">Por exemplo, o comando a seguir multiplica o primeiro elemento na matriz (posição do índice 0) por 2:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-217">For example, the following command multiplies the first element in the array (index position 0) by 2:</span></span>

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a><span data-ttu-id="4c3f8-218">A atribuição por operador de divisão</span><span class="sxs-lookup"><span data-stu-id="4c3f8-218">The assignment by division operator</span></span>

<span data-ttu-id="4c3f8-219">O operador atribuição por divisão `/=` divide um valor numérico pelo valor especificado no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-219">The assignment by division operator `/=` divides a numeric value by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="4c3f8-220">O operador não pode ser usado com variáveis de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-220">The operator cannot be used with string variables.</span></span>

<span data-ttu-id="4c3f8-221">O `/=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-221">The `/=` operator combines two operations.</span></span> <span data-ttu-id="4c3f8-222">Primeiro, ele divide e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-222">First, it divides, and then it assigns.</span></span> <span data-ttu-id="4c3f8-223">Portanto, as duas instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-223">Therefore, the following two statements are equivalent:</span></span>

```powershell
$a /= 2
$a = ($a / 2)
```

<span data-ttu-id="4c3f8-224">Por exemplo, o comando a seguir usa o `/=` operador para dividir o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-224">For example, the following command uses the `/=` operator to divide the value of a variable:</span></span>

```powershell
$a = 8
$a /=2
$a
```

```
4
```

<span data-ttu-id="4c3f8-225">Para dividir um elemento de uma matriz, use um índice para identificar o elemento que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-225">To divide an element of an array, use an index to identify the element that you want to change.</span></span> <span data-ttu-id="4c3f8-226">Por exemplo, o comando a seguir divide o segundo elemento na matriz (posição de índice 1) por 2:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-226">For example, the following command divides the second element in the array (index position 1) by 2:</span></span>

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a><span data-ttu-id="4c3f8-227">O operador de atribuição por módulo</span><span class="sxs-lookup"><span data-stu-id="4c3f8-227">The assignment by modulus operator</span></span>

<span data-ttu-id="4c3f8-228">A atribuição por operador de módulo `%=` divide o valor de uma variável pelo valor no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-228">The assignment by modulus operator `%=` divides the value of a variable by the value on the right side of the operator.</span></span> <span data-ttu-id="4c3f8-229">Em seguida, o `%=` operador atribui o resto (conhecido como módulo) à variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-229">Then, the `%=` operator assigns the remainder (known as the modulus) to the variable.</span></span> <span data-ttu-id="4c3f8-230">Você pode usar esse operador somente quando uma variável contiver um único valor numérico.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-230">You can use this operator only when a variable contains a single numeric value.</span></span> <span data-ttu-id="4c3f8-231">Você não pode usar esse operador quando uma variável contém uma variável de cadeia de caracteres ou uma matriz.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-231">You cannot use this operator when a variable contains a string variable or an array.</span></span>

<span data-ttu-id="4c3f8-232">O `%=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-232">The `%=` operator combines two operations.</span></span> <span data-ttu-id="4c3f8-233">Primeiro, ele divide e determina o restante e, em seguida, atribui o resto à variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-233">First, it divides and determines the remainder, and then it assigns the remainder to the variable.</span></span> <span data-ttu-id="4c3f8-234">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-234">Therefore, the following statements are equivalent:</span></span>

```powershell
$a %= 2
$a = ($a % 2)
```

<span data-ttu-id="4c3f8-235">O exemplo a seguir mostra como usar o `%=` operador para salvar o módulo de um quociente:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-235">The following example shows how to use the `%=` operator to save the modulus of a quotient:</span></span>

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a><span data-ttu-id="4c3f8-236">Os operadores de incremento e decremento</span><span class="sxs-lookup"><span data-stu-id="4c3f8-236">The increment and decrement operators</span></span>

<span data-ttu-id="4c3f8-237">O operador de incremento `++` aumenta o valor de uma variável em 1.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-237">The increment operator `++` increases the value of a variable by 1.</span></span> <span data-ttu-id="4c3f8-238">Quando você usa o operador de incremento em uma instrução simples, nenhum valor é retornado.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-238">When you use the increment operator in a simple statement, no value is returned.</span></span> <span data-ttu-id="4c3f8-239">Para exibir o resultado, exiba o valor da variável, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-239">To view the result, display the value of the variable, as follows:</span></span>

```powershell
$a = 7
++$a
$a
```

```
8
```

<span data-ttu-id="4c3f8-240">Para forçar um valor a ser retornado, coloque a variável e o operador entre parênteses, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-240">To force a value to be returned, enclose the variable and the operator in parentheses, as follows:</span></span>

```powershell
$a = 7
(++$a)
```

```
8
```

<span data-ttu-id="4c3f8-241">O operador de incremento pode ser colocado antes (prefixo) ou após (sufixo) uma variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-241">The increment operator can be placed before (prefix) or after (postfix) a variable.</span></span> <span data-ttu-id="4c3f8-242">A versão de prefixo do operador incrementa uma variável antes de seu valor ser usado na instrução, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-242">The prefix version of the operator increments a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = ++$a
$a
```

```
8
```

```powershell
$c
```

```
8
```

<span data-ttu-id="4c3f8-243">A versão do sufixo do operador incrementa uma variável depois que seu valor é usado na instrução.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-243">The postfix version of the operator increments a variable after its value is used in the statement.</span></span> <span data-ttu-id="4c3f8-244">No exemplo a seguir, as `$c` `$a` variáveis e têm valores diferentes porque o valor é atribuído `$c` antes `$a` das alterações:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-244">In the following example, the `$c` and `$a` variables have different values because the value is assigned to `$c` before `$a` changes:</span></span>

```powershell
$a = 7
$c = $a++
$a
```

```
8
```

```powershell
$c
```

```
7
```

<span data-ttu-id="4c3f8-245">O operador decremento `--` diminui o valor de uma variável em 1.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-245">The decrement operator `--` decreases the value of a variable by 1.</span></span> <span data-ttu-id="4c3f8-246">Assim como com o operador de incremento, nenhum valor é retornado quando você usa o operador em uma instrução simples.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-246">As with the increment operator, no value is returned when you use the operator in a simple statement.</span></span> <span data-ttu-id="4c3f8-247">Use parênteses para retornar um valor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-247">Use parentheses to return a value, as follows:</span></span>

```powershell
$a = 7
--$a
$a
```

```
6
```

```powershell
(--$a)
```

```
5
```

<span data-ttu-id="4c3f8-248">A versão de prefixo do operador decrementa uma variável antes de seu valor ser usado na instrução, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-248">The prefix version of the operator decrements a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = --$a
$a
```

```
6
```

```powershell
$c
```

```
6
```

<span data-ttu-id="4c3f8-249">A versão do sufixo do operador decrementa uma variável depois que seu valor é usado na instrução.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-249">The postfix version of the operator decrements a variable after its value is used in the statement.</span></span> <span data-ttu-id="4c3f8-250">No exemplo a seguir, as `$d` `$a` variáveis e têm valores diferentes porque o valor é atribuído `$d` antes `$a` das alterações:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-250">In the following example, the `$d` and `$a` variables have different values because the value is assigned to `$d` before `$a` changes:</span></span>

```powershell
$a = 7
$d = $a--
$a
```

```
6
```

```powershell
$d
```

```
7
```

## <a name="microsoft-net-framework-types"></a><span data-ttu-id="4c3f8-251">Tipos de estrutura de Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="4c3f8-251">Microsoft .NET Framework types</span></span>

<span data-ttu-id="4c3f8-252">Por padrão, quando uma variável tem apenas um valor, o valor atribuído à variável determina o tipo de dados da variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-252">By default, when a variable has only one value, the value that is assigned to the variable determines the data type of the variable.</span></span> <span data-ttu-id="4c3f8-253">Por exemplo, o comando a seguir cria uma variável que tem o tipo "inteiro" (System. Int32):</span><span class="sxs-lookup"><span data-stu-id="4c3f8-253">For example, the following command creates a variable that has the "Integer" (System.Int32) type:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="4c3f8-254">Para localizar o tipo de .NET Framework de uma variável, use o método **GetType** e sua propriedade **FullName** , da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-254">To find the .NET Framework type of a variable, use the **GetType** method and its **FullName** property, as follows.</span></span> <span data-ttu-id="4c3f8-255">Certifique-se de incluir os parênteses após o nome do método **GetType** , mesmo que a chamada do método não tenha argumentos:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-255">Be sure to include the parentheses after the **GetType** method name, even though the method call has no arguments:</span></span>

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

<span data-ttu-id="4c3f8-256">Para criar uma variável que contém uma cadeia de caracteres, atribua um valor de cadeia de caracteres à variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-256">To create a variable that contains a string, assign a string value to the variable.</span></span> <span data-ttu-id="4c3f8-257">Para indicar que o valor é uma cadeia de caracteres, coloque-o entre aspas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-257">To indicate that the value is a string, enclose it in quotation marks, as follows:</span></span>

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

<span data-ttu-id="4c3f8-258">Se o primeiro valor que é atribuído à variável for uma cadeia de caracteres, o PowerShell tratará todas as operações como operações de cadeia de caracteres e converterá novos valores em cadeias.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-258">If the first value that is assigned to the variable is a string, PowerShell treats all operations as string operations and casts new values to strings.</span></span>
<span data-ttu-id="4c3f8-259">Isso ocorre no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-259">This occurs in the following example:</span></span>

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

<span data-ttu-id="4c3f8-260">Se o primeiro valor for um inteiro, o PowerShell tratará todas as operações como operações de inteiros e converterá novos valores em inteiros.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-260">If the first value is an integer, PowerShell treats all operations as integer operations and casts new values to integers.</span></span> <span data-ttu-id="4c3f8-261">Isso ocorre no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-261">This occurs in the following example:</span></span>

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

<span data-ttu-id="4c3f8-262">Você pode converter uma nova variável escalar como qualquer .NET Framework tipo colocando o nome do tipo entre colchetes que precedem o nome da variável ou o primeiro valor de atribuição.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-262">You can cast a new scalar variable as any .NET Framework type by placing the type name in brackets that precede either the variable name or the first assignment value.</span></span> <span data-ttu-id="4c3f8-263">Ao converter uma variável, você pode determinar os tipos de dados que podem ser armazenados na variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-263">When you cast a variable, you can determine the types of data that can be stored in the variable.</span></span> <span data-ttu-id="4c3f8-264">E você pode determinar como a variável se comporta quando você a manipula.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-264">And, you can determine how the variable behaves when you manipulate it.</span></span>

<span data-ttu-id="4c3f8-265">Por exemplo, o comando a seguir converte a variável como um tipo de cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-265">For example, the following command casts the variable as a string type:</span></span>

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

<span data-ttu-id="4c3f8-266">O exemplo a seguir converte o primeiro valor, em vez de converter a variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-266">The following example casts the first value, instead of casting the variable:</span></span>

```powershell
$a = [string]27
```

<span data-ttu-id="4c3f8-267">Quando você converte uma variável para um tipo específico, a Convenção comum é converter a variável, não o valor.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-267">When you cast a variable to a specific type, the common convention is to cast the variable, not the value.</span></span> <span data-ttu-id="4c3f8-268">No entanto, você não pode reconverter o tipo de dados de uma variável existente se seu valor não puder ser convertido para o novo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-268">However, you cannot recast the data type of an existing variable if its value cannot be converted to the new data type.</span></span> <span data-ttu-id="4c3f8-269">Para alterar o tipo de dados, você deve substituir seu valor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-269">To change the data type, you must replace its value, as follows:</span></span>

```powershell
$a = "string"
[int]$a
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input string was
not in a correct format." At line:1 char:8 + [int]$a <<<<
```

```powershell
[int]$a = 3
```

<span data-ttu-id="4c3f8-270">Além disso, quando você precede um nome de variável com um tipo de dados, o tipo dessa variável é bloqueado, a menos que você substitua explicitamente o tipo especificando outro tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-270">In addition, when you precede a variable name with a data type, the type of that variable is locked unless you explicitly override the type by specifying another data type.</span></span> <span data-ttu-id="4c3f8-271">Se você tentar atribuir um valor incompatível com o tipo existente e não substituir explicitamente o tipo, o PowerShell exibirá um erro, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-271">If you try to assign a value that is incompatible with the existing type, and you do not explicitly override the type, PowerShell displays an error, as shown in the following example:</span></span>

```powershell
$a = 3
$a = "string"
[int]$a = 3
$a = "string"
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input
string was not in a correct format."
At line:1 char:3
+ $a <<<<  = "string"
```

```powershell
[string]$a = "string"
```

<span data-ttu-id="4c3f8-272">No PowerShell, os tipos de dados de variáveis que contêm vários itens em uma matriz são tratados de forma diferente dos tipos de dados de variáveis que contêm um único item.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-272">In PowerShell, the data types of variables that contain multiple items in an array are handled differently from the data types of variables that contain a single item.</span></span> <span data-ttu-id="4c3f8-273">A menos que um tipo de dados seja especificamente atribuído a uma variável de matriz, o tipo de dados é sempre `System.Object []` .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-273">Unless a data type is specifically assigned to an array variable, the data type is always `System.Object []`.</span></span> <span data-ttu-id="4c3f8-274">Esse tipo de dados é específico para matrizes.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-274">This data type is specific to arrays.</span></span>

<span data-ttu-id="4c3f8-275">Às vezes, você pode substituir o tipo padrão especificando outro tipo.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-275">Sometimes, you can override the default type by specifying another type.</span></span> <span data-ttu-id="4c3f8-276">Por exemplo, o comando a seguir converte a variável como um `string []` tipo de matriz:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-276">For example, the following command casts the variable as a `string []` array type:</span></span>

```powershell
[string []] $a = "one", "two", "three"
```

<span data-ttu-id="4c3f8-277">As variáveis do PowerShell podem ser qualquer tipo de dados .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-277">PowerShell variables can be any .NET Framework data type.</span></span> <span data-ttu-id="4c3f8-278">Além disso, você pode atribuir qualquer tipo de dados .NET Framework totalmente qualificado que esteja disponível no processo atual.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-278">In addition, you can assign any fully qualified .NET Framework data type that is available in the current process.</span></span> <span data-ttu-id="4c3f8-279">Por exemplo, o comando a seguir especifica um `System.DateTime` tipo de dados:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-279">For example, the following command specifies a `System.DateTime` data type:</span></span>

```powershell
[System.DateTime]$a = "5/31/2005"
```

<span data-ttu-id="4c3f8-280">A variável será atribuída a um valor que esteja de acordo com o `System.DateTime` tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-280">The variable will be assigned a value that conforms to the `System.DateTime` data type.</span></span> <span data-ttu-id="4c3f8-281">O valor da `$a` variável seria o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-281">The value of the `$a` variable would be the following:</span></span>

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a><span data-ttu-id="4c3f8-282">Atribuindo várias variáveis</span><span class="sxs-lookup"><span data-stu-id="4c3f8-282">Assigning multiple variables</span></span>

<span data-ttu-id="4c3f8-283">No PowerShell, você pode atribuir valores a várias variáveis usando um único comando.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-283">In PowerShell, you can assign values to multiple variables by using a single command.</span></span> <span data-ttu-id="4c3f8-284">O primeiro elemento do valor de atribuição é atribuído à primeira variável, o segundo elemento é atribuído à segunda variável, o terceiro elemento à terceira variável e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-284">The first element of the assignment value is assigned to the first variable, the second element is assigned to the second variable, the third element to the third variable, and so on.</span></span> <span data-ttu-id="4c3f8-285">Por exemplo, o comando a seguir atribui o valor 1 à `$a` variável, o valor 2 à `$b` variável e o valor 3 à `$c` variável:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-285">For example, the following command assigns the value 1 to the `$a` variable, the value 2 to the `$b` variable, and the value 3 to the `$c` variable:</span></span>

```powershell
$a, $b, $c = 1, 2, 3
```

<span data-ttu-id="4c3f8-286">Se o valor de atribuição contiver mais elementos que variáveis, todos os valores restantes serão atribuídos à última variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-286">If the assignment value contains more elements than variables, all the remaining values are assigned to the last variable.</span></span> <span data-ttu-id="4c3f8-287">Por exemplo, o comando a seguir contém três variáveis e cinco valores:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-287">For example, the following command contains three variables and five values:</span></span>

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

<span data-ttu-id="4c3f8-288">Portanto, o PowerShell atribui o valor 1 à `$a` variável e o valor 2 à `$b` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-288">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="4c3f8-289">Ele atribui os valores 3, 4 e 5 à `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-289">It assigns the values 3, 4, and 5 to the `$c` variable.</span></span>
<span data-ttu-id="4c3f8-290">Para atribuir os valores na `$c` variável a três outras variáveis, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-290">To assign the values in the `$c` variable to three other variables, use the following format:</span></span>

```powershell
$d, $e, $f = $c
```

<span data-ttu-id="4c3f8-291">Esse comando atribui o valor 3 à `$d` variável, o valor 4 à `$e` variável e o valor 5 à `$f` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-291">This command assigns the value 3 to the `$d` variable, the value 4 to the `$e` variable, and the value 5 to the `$f` variable.</span></span>

<span data-ttu-id="4c3f8-292">Se o valor de atribuição contiver menos elementos que variáveis, todas as variáveis restantes no final não serão atribuídas a nenhum valor.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-292">If the assignment value contains less elements than variables, all the remaining variables at the end are not assigned any values.</span></span> <span data-ttu-id="4c3f8-293">Por exemplo, o comando a seguir contém três variáveis e dois valores:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-293">For example, the following command contains three variables and two values:</span></span>

```powershell
$a, $b, $c = 1, 2
```

<span data-ttu-id="4c3f8-294">Portanto, o PowerShell atribui o valor 1 à `$a` variável e o valor 2 à `$b` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-294">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="4c3f8-295">Ele não atribuirá nenhum valor à `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-295">It will not assign any value to the `$c` variable.</span></span>

<span data-ttu-id="4c3f8-296">Você também pode atribuir um único valor a várias variáveis encadeando as variáveis.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-296">You can also assign a single value to multiple variables by chaining the variables.</span></span> <span data-ttu-id="4c3f8-297">Por exemplo, o comando a seguir atribui um valor de "três" a todas as quatro variáveis:</span><span class="sxs-lookup"><span data-stu-id="4c3f8-297">For example, the following command assigns a value of "three" to all four variables:</span></span>

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a><span data-ttu-id="4c3f8-298">Cmdlets relacionados a variáveis</span><span class="sxs-lookup"><span data-stu-id="4c3f8-298">Variable-related cmdlets</span></span>

<span data-ttu-id="4c3f8-299">Além de usar uma operação de atribuição para definir um valor de variável, você também pode usar o cmdlet [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) .</span><span class="sxs-lookup"><span data-stu-id="4c3f8-299">In addition to using an assignment operation to set a variable value, you can also use the [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) cmdlet.</span></span> <span data-ttu-id="4c3f8-300">Por exemplo, o comando a seguir usa `Set-Variable` para atribuir uma matriz de 1, 2, 3 à `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="4c3f8-300">For example, the following command uses `Set-Variable` to assign an array of 1, 2, 3 to the `$a` variable.</span></span>

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a><span data-ttu-id="4c3f8-301">Confira também</span><span class="sxs-lookup"><span data-stu-id="4c3f8-301">See also</span></span>

[<span data-ttu-id="4c3f8-302">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="4c3f8-302">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="4c3f8-303">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="4c3f8-303">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="4c3f8-304">about_Variables</span><span class="sxs-lookup"><span data-stu-id="4c3f8-304">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="4c3f8-305">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="4c3f8-305">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[<span data-ttu-id="4c3f8-306">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="4c3f8-306">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[<span data-ttu-id="4c3f8-307">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="4c3f8-307">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
