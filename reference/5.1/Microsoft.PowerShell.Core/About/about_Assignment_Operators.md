---
description: Descreve como usar operadores para atribuir valores a variáveis.
Locale: en-US
ms.date: 04/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: 469c482ea8dbf2af315ed64129b8e790b66840e4
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194546"
---
# <a name="about-assignment-operators"></a><span data-ttu-id="f3345-103">Sobre operadores de atribuição</span><span class="sxs-lookup"><span data-stu-id="f3345-103">About Assignment Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="f3345-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f3345-104">Short description</span></span>
<span data-ttu-id="f3345-105">Descreve como usar operadores para atribuir valores a variáveis.</span><span class="sxs-lookup"><span data-stu-id="f3345-105">Describes how to use operators to assign values to variables.</span></span>

## <a name="long-description"></a><span data-ttu-id="f3345-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f3345-106">Long description</span></span>

<span data-ttu-id="f3345-107">Os operadores de atribuição atribuem um ou mais valores a uma variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-107">Assignment operators assign one or more values to a variable.</span></span> <span data-ttu-id="f3345-108">Eles podem executar operações numéricas nos valores antes da atribuição.</span><span class="sxs-lookup"><span data-stu-id="f3345-108">They can perform numeric operations on the values before the assignment.</span></span>

<span data-ttu-id="f3345-109">O PowerShell dá suporte aos seguintes operadores de atribuição.</span><span class="sxs-lookup"><span data-stu-id="f3345-109">PowerShell supports the following assignment operators.</span></span>

|<span data-ttu-id="f3345-110">Operador</span><span class="sxs-lookup"><span data-stu-id="f3345-110">Operator</span></span>|<span data-ttu-id="f3345-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3345-111">Description</span></span>                                                  |
|--------|-------------------------------------------------------------|
|=       |<span data-ttu-id="f3345-112">Define o valor de uma variável para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="f3345-112">Sets the value of a variable to the specified value.</span></span>         |
|+=      |<span data-ttu-id="f3345-113">Aumenta o valor de uma variável pelo valor especificado ou</span><span class="sxs-lookup"><span data-stu-id="f3345-113">Increases the value of a variable by the specified value, or</span></span> |
|        |<span data-ttu-id="f3345-114">acrescenta o valor especificado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="f3345-114">appends the specified value to the existing value.</span></span>           |
|-=      |<span data-ttu-id="f3345-115">Diminui o valor de uma variável pelo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="f3345-115">Decreases the value of a variable by the specified value.</span></span>    |
|*=      |<span data-ttu-id="f3345-116">Multiplica o valor de uma variável pelo valor especificado ou</span><span class="sxs-lookup"><span data-stu-id="f3345-116">Multiplies the value of a variable by the specified value, or</span></span>|
|        |<span data-ttu-id="f3345-117">acrescenta o valor especificado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="f3345-117">appends the specified value to the existing value.</span></span>           |
|/=      |<span data-ttu-id="f3345-118">Divide o valor de uma variável pelo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="f3345-118">Divides the value of a variable by the specified value.</span></span>      |
|%=      |<span data-ttu-id="f3345-119">Divide o valor de uma variável pelo valor especificado e</span><span class="sxs-lookup"><span data-stu-id="f3345-119">Divides the value of a variable by the specified value and</span></span>   |
|        |<span data-ttu-id="f3345-120">em seguida, atribui o resto (módulo) à variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-120">then assigns the remainder (modulus) to the variable.</span></span>        |
|++      |<span data-ttu-id="f3345-121">Aumenta o valor de uma variável, Propriedade atribuível ou</span><span class="sxs-lookup"><span data-stu-id="f3345-121">Increases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="f3345-122">elemento de matriz em 1.</span><span class="sxs-lookup"><span data-stu-id="f3345-122">array element by 1.</span></span>                                          |
|--      |<span data-ttu-id="f3345-123">Diminui o valor de uma variável, Propriedade atribuível ou</span><span class="sxs-lookup"><span data-stu-id="f3345-123">Decreases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="f3345-124">elemento de matriz em 1.</span><span class="sxs-lookup"><span data-stu-id="f3345-124">array element by 1.</span></span>                                          |

## <a name="syntax"></a><span data-ttu-id="f3345-125">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f3345-125">Syntax</span></span>

<span data-ttu-id="f3345-126">A sintaxe dos operadores de atribuição é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3345-126">The syntax of the assignment operators is as follows:</span></span>

<span data-ttu-id="f3345-127">`<assignable-expression>` `<assignment-operator>` `<value>`</span><span class="sxs-lookup"><span data-stu-id="f3345-127">`<assignable-expression>` `<assignment-operator>` `<value>`</span></span>

<span data-ttu-id="f3345-128">As expressões atribuíveis incluem variáveis e propriedades.</span><span class="sxs-lookup"><span data-stu-id="f3345-128">Assignable expressions include variables and properties.</span></span> <span data-ttu-id="f3345-129">O valor pode ser um único valor, uma matriz de valores ou um comando, expressão ou instrução.</span><span class="sxs-lookup"><span data-stu-id="f3345-129">The value can be a single value, an array of values, or a command, expression, or statement.</span></span>

<span data-ttu-id="f3345-130">Os operadores de incremento e decremento são operadores unários.</span><span class="sxs-lookup"><span data-stu-id="f3345-130">The increment and decrement operators are unary operators.</span></span> <span data-ttu-id="f3345-131">Cada uma tem versões de prefixo e sufixo.</span><span class="sxs-lookup"><span data-stu-id="f3345-131">Each has prefix and postfix versions.</span></span>

`<assignable-expression><operator>`
`<operator><assignable-expression>`

<span data-ttu-id="f3345-132">A expressão atribuível deve ser um número ou deve ser conversível em um número.</span><span class="sxs-lookup"><span data-stu-id="f3345-132">The assignable expression must be a number or it must be convertible to a number.</span></span>

## <a name="assigning-values"></a><span data-ttu-id="f3345-133">Atribuindo valores</span><span class="sxs-lookup"><span data-stu-id="f3345-133">Assigning values</span></span>

<span data-ttu-id="f3345-134">Variáveis são nomes de espaços de memória que armazenam valores.</span><span class="sxs-lookup"><span data-stu-id="f3345-134">Variables are named memory spaces that store values.</span></span> <span data-ttu-id="f3345-135">Você armazena os valores em variáveis usando o operador de atribuição `=` .</span><span class="sxs-lookup"><span data-stu-id="f3345-135">You store the values in variables by using the assignment operator `=`.</span></span> <span data-ttu-id="f3345-136">O novo valor pode substituir o valor existente da variável ou você pode acrescentar um novo valor ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="f3345-136">The new value can replace the existing value of the variable, or you can append a new value to the existing value.</span></span>

<span data-ttu-id="f3345-137">O operador de atribuição básica é o sinal de igual `=` `(ASCII 61)` .</span><span class="sxs-lookup"><span data-stu-id="f3345-137">The basic assignment operator is the equal sign `=` `(ASCII 61)`.</span></span> <span data-ttu-id="f3345-138">Por exemplo, a instrução a seguir atribui o valor PowerShell à `$MyShell` variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-138">For example, the following statement assigns the value PowerShell to the `$MyShell` variable:</span></span>

```powershell
$MyShell = "PowerShell"
```

<span data-ttu-id="f3345-139">Quando você atribui um valor a uma variável no PowerShell, a variável é criada, caso ainda não exista.</span><span class="sxs-lookup"><span data-stu-id="f3345-139">When you assign a value to a variable in PowerShell, the variable is created if it did not already exist.</span></span> <span data-ttu-id="f3345-140">Por exemplo, a primeira das duas instruções de atribuição a seguir cria a `$a` variável e atribui um valor de 6 a `$a` .</span><span class="sxs-lookup"><span data-stu-id="f3345-140">For example, the first of the following two assignment statements creates the `$a` variable and assigns a value of 6 to `$a`.</span></span> <span data-ttu-id="f3345-141">A segunda instrução de atribuição atribui um valor de 12 a `$a` .</span><span class="sxs-lookup"><span data-stu-id="f3345-141">The second assignment statement assigns a value of 12 to `$a`.</span></span> <span data-ttu-id="f3345-142">A primeira instrução cria uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-142">The first statement creates a new variable.</span></span> <span data-ttu-id="f3345-143">A segunda instrução altera apenas seu valor:</span><span class="sxs-lookup"><span data-stu-id="f3345-143">The second statement changes only its value:</span></span>

```powershell
$a = 6
$a = 12
```

<span data-ttu-id="f3345-144">As variáveis no PowerShell não têm um tipo de dados específico, a menos que você as converta.</span><span class="sxs-lookup"><span data-stu-id="f3345-144">Variables in PowerShell do not have a specific data type unless you cast them.</span></span>
<span data-ttu-id="f3345-145">Quando uma variável contém apenas um objeto, a variável usa o tipo de dados desse objeto.</span><span class="sxs-lookup"><span data-stu-id="f3345-145">When a variable contains only one object, the variable takes the data type of that object.</span></span> <span data-ttu-id="f3345-146">Quando uma variável contém uma coleção de objetos, a variável tem o tipo de dados System. Object.</span><span class="sxs-lookup"><span data-stu-id="f3345-146">When a variable contains a collection of objects, the variable has the System.Object data type.</span></span> <span data-ttu-id="f3345-147">Portanto, você pode atribuir qualquer tipo de objeto à coleção.</span><span class="sxs-lookup"><span data-stu-id="f3345-147">Therefore, you can assign any type of object to the collection.</span></span> <span data-ttu-id="f3345-148">O exemplo a seguir mostra que você pode adicionar objetos de processo, objetos de serviço, cadeias de caracteres e inteiros a uma variável sem gerar um erro:</span><span class="sxs-lookup"><span data-stu-id="f3345-148">The following example shows that you can add process objects, service objects, strings, and integers to a variable without generating an error:</span></span>

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

<span data-ttu-id="f3345-149">Como o operador de atribuição `=` tem uma precedência mais baixa do que o operador de pipeline `|` , não são necessários parênteses para atribuir o resultado de um pipeline de comando a uma variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-149">Because the assignment operator `=` has a lower precedence than the pipeline operator `|`, parentheses are not required to assign the result of a command pipeline to a variable.</span></span> <span data-ttu-id="f3345-150">Por exemplo, o comando a seguir classifica os serviços no computador e atribui os serviços classificados à `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-150">For example, the following command sorts the services on the computer and then assigns the sorted services to the `$a` variable:</span></span>

```powershell
$a = Get-Service | Sort-Object -Property name
```

<span data-ttu-id="f3345-151">Você também pode atribuir o valor criado por uma instrução a uma variável, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f3345-151">You can also assign the value created by a statement to a variable, as in the following example:</span></span>

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

<span data-ttu-id="f3345-152">Este exemplo atribui zero à `$a` variável se o valor de `$b` for menor que zero.</span><span class="sxs-lookup"><span data-stu-id="f3345-152">This example assigns zero to the `$a` variable if the value of `$b` is less than zero.</span></span> <span data-ttu-id="f3345-153">Ele atribui o valor de `$b` para `$a` se o valor de `$b` não for menor que zero.</span><span class="sxs-lookup"><span data-stu-id="f3345-153">It assigns the value of `$b` to `$a` if the value of `$b` is not less than zero.</span></span>

### <a name="the-assignment-operator"></a><span data-ttu-id="f3345-154">O operador de atribuição</span><span class="sxs-lookup"><span data-stu-id="f3345-154">The assignment operator</span></span>

<span data-ttu-id="f3345-155">O operador de atribuição `=` atribui valores a variáveis.</span><span class="sxs-lookup"><span data-stu-id="f3345-155">The assignment operator `=` assigns values to variables.</span></span> <span data-ttu-id="f3345-156">Se a variável já tiver um valor, o operador de atribuição `=` substituirá o valor sem aviso.</span><span class="sxs-lookup"><span data-stu-id="f3345-156">If the variable already has a value, the assignment operator `=` replaces the value without warning.</span></span>

<span data-ttu-id="f3345-157">A instrução a seguir atribui o valor inteiro 6 à `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-157">The following statement assigns the integer value 6 to the `$a` variable:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="f3345-158">Para atribuir um valor de cadeia de caracteres a uma variável, coloque o valor da cadeia de caracteres entre aspas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-158">To assign a string value to a variable, enclose the string value in quotation marks, as follows:</span></span>

```powershell
$a = "baseball"
```

<span data-ttu-id="f3345-159">Para atribuir uma matriz (vários valores) a uma variável, separe os valores com vírgulas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-159">To assign an array (multiple values) to a variable, separate the values with commas, as follows:</span></span>

```powershell
$a = "apple", "orange", "lemon", "grape"
```

<span data-ttu-id="f3345-160">Para atribuir uma tabela de hash a uma variável, use a notação de tabela de hash padrão no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3345-160">To assign a hash table to a variable, use the standard hash table notation in PowerShell.</span></span> <span data-ttu-id="f3345-161">Digite um sinal de entrada `@` seguido por pares de chave/valor separados por ponto e vírgula `;` e entre chaves `{ }` .</span><span class="sxs-lookup"><span data-stu-id="f3345-161">Type an at sign `@` followed by key/value pairs that are separated by semicolons `;` and enclosed in braces `{ }`.</span></span> <span data-ttu-id="f3345-162">Por exemplo, para atribuir uma tabela de hash à `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="f3345-162">For example, to assign a hash table to the `$a` variable, type:</span></span>

```powershell
$a = @{one=1; two=2; three=3}
```

<span data-ttu-id="f3345-163">Para atribuir valores hexadecimais a uma variável, preceda o valor com `0x` .</span><span class="sxs-lookup"><span data-stu-id="f3345-163">To assign hexadecimal values to a variable, precede the value with `0x`.</span></span>
<span data-ttu-id="f3345-164">O PowerShell converte o valor hexadecimal (0x10) em um valor decimal (neste caso, 16) e atribui esse valor à `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-164">PowerShell converts the hexadecimal value (0x10) to a decimal value (in this case, 16) and assigns that value to the `$a` variable.</span></span> <span data-ttu-id="f3345-165">Por exemplo, para atribuir um valor de 0x10 à `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="f3345-165">For example, to assign a value of 0x10 to the `$a` variable, type:</span></span>

```powershell
$a = 0x10
```

<span data-ttu-id="f3345-166">Para atribuir um valor exponencial a uma variável, digite o número raiz, a letra `e` e um número que represente um múltiplo de 10.</span><span class="sxs-lookup"><span data-stu-id="f3345-166">To assign an exponential value to a variable, type the root number, the letter `e`, and a number that represents a multiple of 10.</span></span> <span data-ttu-id="f3345-167">Por exemplo, para atribuir um valor de 3,1415 à potência de 1.000 para a `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="f3345-167">For example, to assign a value of 3.1415 to the power of 1,000 to the `$a` variable, type:</span></span>

```powershell
$a = 3.1415e3
```

<span data-ttu-id="f3345-168">O PowerShell também pode converter quilobytes `KB` , megabytes `MB` e gigabytes `GB` em bytes.</span><span class="sxs-lookup"><span data-stu-id="f3345-168">PowerShell can also convert kilobytes `KB`, megabytes `MB`, and gigabytes `GB` into bytes.</span></span> <span data-ttu-id="f3345-169">Por exemplo, para atribuir um valor de 10 kilobytes à `$a` variável, digite:</span><span class="sxs-lookup"><span data-stu-id="f3345-169">For example, to assign a value of 10 kilobytes to the `$a` variable, type:</span></span>

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a><span data-ttu-id="f3345-170">O operador de atribuição por adição</span><span class="sxs-lookup"><span data-stu-id="f3345-170">The assignment by addition operator</span></span>

<span data-ttu-id="f3345-171">O operador atribuição por adição `+=` incrementa o valor de uma variável ou acrescenta o valor especificado ao valor existente.</span><span class="sxs-lookup"><span data-stu-id="f3345-171">The assignment by addition operator `+=` either increments the value of a variable or appends the specified value to the existing value.</span></span> <span data-ttu-id="f3345-172">A ação depende de se a variável tem um tipo numérico ou de cadeia de caracteres e se a variável contém um único valor (um escalar) ou vários valores (uma coleção).</span><span class="sxs-lookup"><span data-stu-id="f3345-172">The action depends on whether the variable has a numeric or string type and whether the variable contains a single value (a scalar) or multiple values (a collection).</span></span>

<span data-ttu-id="f3345-173">O `+=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="f3345-173">The `+=` operator combines two operations.</span></span> <span data-ttu-id="f3345-174">Primeiro, ele adiciona e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="f3345-174">First, it adds, and then it assigns.</span></span>
<span data-ttu-id="f3345-175">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f3345-175">Therefore, the following statements are equivalent:</span></span>

```powershell
$a += 2
$a = ($a + 2)
```

<span data-ttu-id="f3345-176">Quando a variável contém um único valor numérico, o `+=` operador incrementa o valor existente pelo valor no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="f3345-176">When the variable contains a single numeric value, the `+=` operator increments the existing value by the amount on the right side of the operator.</span></span> <span data-ttu-id="f3345-177">Em seguida, o operador atribui o valor resultante à variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-177">Then, the operator assigns the resulting value to the variable.</span></span> <span data-ttu-id="f3345-178">O exemplo a seguir mostra como usar o `+=` operador para aumentar o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-178">The following example shows how to use the `+=` operator to increase the value of a variable:</span></span>

```powershell
$a = 4
$a += 2
$a
```

```
6
```

<span data-ttu-id="f3345-179">Quando o valor da variável é uma cadeia de caracteres, o valor no lado direito do operador é acrescentado à cadeia de caracteres da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-179">When the value of the variable is a string, the value on the right side of the operator is appended to the string, as follows:</span></span>

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

<span data-ttu-id="f3345-180">Quando o valor da variável é uma matriz, o `+=` operador acrescenta os valores no lado direito do operador à matriz.</span><span class="sxs-lookup"><span data-stu-id="f3345-180">When the value of the variable is an array, the `+=` operator appends the values on the right side of the operator to the array.</span></span> <span data-ttu-id="f3345-181">A menos que a matriz seja digitada explicitamente pela conversão, você pode acrescentar qualquer tipo de valor à matriz, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-181">Unless the array is explicitly typed by casting, you can append any type of value to the array, as follows:</span></span>

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

<span data-ttu-id="f3345-182">e</span><span class="sxs-lookup"><span data-stu-id="f3345-182">and</span></span>

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

<span data-ttu-id="f3345-183">Quando o valor de uma variável é uma tabela de hash, o `+=` operador acrescenta o valor no lado direito do operador à tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="f3345-183">When the value of a variable is a hash table, the `+=` operator appends the value on the right side of the operator to the hash table.</span></span> <span data-ttu-id="f3345-184">No entanto, como o único tipo que você pode adicionar a uma tabela de hash é outra tabela de hash, todas as outras atribuições falham.</span><span class="sxs-lookup"><span data-stu-id="f3345-184">However, because the only type that you can add to a hash table is another hash table, all other assignments fail.</span></span>

<span data-ttu-id="f3345-185">Por exemplo, o comando a seguir atribui uma tabela de hash à `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-185">For example, the following command assigns a hash table to the `$a` variable.</span></span>
<span data-ttu-id="f3345-186">Em seguida, ele usa o `+=` operador para acrescentar outra tabela de hash à tabela de hash existente, adicionando efetivamente um novo par de chave/valor à tabela de hash existente.</span><span class="sxs-lookup"><span data-stu-id="f3345-186">Then, it uses the `+=` operator to append another hash table to the existing hash table, effectively adding a new key/value pair to the existing hash table.</span></span>
<span data-ttu-id="f3345-187">Esse comando é bem sucedido, conforme mostrado na saída:</span><span class="sxs-lookup"><span data-stu-id="f3345-187">This command succeeds, as shown in the output:</span></span>

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

<span data-ttu-id="f3345-188">O comando a seguir tenta acrescentar um inteiro "1" à tabela de hash na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-188">The following command attempts to append an integer "1" to the hash table in the `$a` variable.</span></span> <span data-ttu-id="f3345-189">Este comando falha:</span><span class="sxs-lookup"><span data-stu-id="f3345-189">This command fails:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a><span data-ttu-id="f3345-190">O operador de atribuição por subtração</span><span class="sxs-lookup"><span data-stu-id="f3345-190">The assignment by subtraction operator</span></span>

<span data-ttu-id="f3345-191">O operador atribuição por subtração `-=` Decrementa o valor de uma variável pelo valor especificado no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="f3345-191">The assignment by subtraction operator `-=` decrements the value of a variable by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="f3345-192">Esse operador não pode ser usado com variáveis de cadeia de caracteres e não pode ser usado para remover um elemento de uma coleção.</span><span class="sxs-lookup"><span data-stu-id="f3345-192">This operator cannot be used with string variables, and it cannot be used to remove an element from a collection.</span></span>

<span data-ttu-id="f3345-193">O `-=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="f3345-193">The `-=` operator combines two operations.</span></span> <span data-ttu-id="f3345-194">Primeiro, ele subtrai e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="f3345-194">First, it subtracts, and then it assigns.</span></span> <span data-ttu-id="f3345-195">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f3345-195">Therefore, the following statements are equivalent:</span></span>

```powershell
$a -= 2
$a = ($a - 2)
```

<span data-ttu-id="f3345-196">O exemplo a seguir mostra como usar o `-=` operador para diminuir o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-196">The following example shows how to use of the `-=` operator to decrease the value of a variable:</span></span>

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

<span data-ttu-id="f3345-197">Você também pode usar o `-=` operador de atribuição para diminuir o valor de um membro de uma matriz numérica.</span><span class="sxs-lookup"><span data-stu-id="f3345-197">You can also use the `-=` assignment operator to decrease the value of a member of a numeric array.</span></span> <span data-ttu-id="f3345-198">Para fazer isso, especifique o índice do elemento da matriz que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="f3345-198">To do this, specify the index of the array element that you want to change.</span></span> <span data-ttu-id="f3345-199">No exemplo a seguir, o valor do terceiro elemento de uma matriz (elemento 2) é diminuído em 1:</span><span class="sxs-lookup"><span data-stu-id="f3345-199">In the following example, the value of the third element of an array (element 2) is decreased by 1:</span></span>

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

<span data-ttu-id="f3345-200">Você não pode usar o `-=` operador para excluir os valores de uma variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-200">You cannot use the `-=` operator to delete the values of a variable.</span></span> <span data-ttu-id="f3345-201">Para excluir todos os valores atribuídos a uma variável, use os cmdlets [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) ou [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) para atribuir um valor de `$null` ou `""` à variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-201">To delete all the values that are assigned to a variable, use the [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) or [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) cmdlets to assign a value of `$null` or `""` to the variable.</span></span>

```powershell
$a = $null
```

<span data-ttu-id="f3345-202">Para excluir um valor específico de uma matriz, use a notação de matriz para atribuir um valor de `$null` para o item específico.</span><span class="sxs-lookup"><span data-stu-id="f3345-202">To delete a particular value from an array, use array notation to assign a value of `$null` to the particular item.</span></span> <span data-ttu-id="f3345-203">Por exemplo, a instrução a seguir exclui o segundo valor (posição de índice 1) de uma matriz:</span><span class="sxs-lookup"><span data-stu-id="f3345-203">For example, the following statement deletes the second value (index position 1) from an array:</span></span>

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

<span data-ttu-id="f3345-204">Para excluir uma variável, use o cmdlet [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) .</span><span class="sxs-lookup"><span data-stu-id="f3345-204">To delete a variable, use the [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) cmdlet.</span></span> <span data-ttu-id="f3345-205">Esse método é útil quando a variável é convertida explicitamente em um tipo de dados específico e você deseja uma variável não tipada.</span><span class="sxs-lookup"><span data-stu-id="f3345-205">This method is useful when the variable is explicitly cast to a particular data type, and you want an untyped variable.</span></span> <span data-ttu-id="f3345-206">O comando a seguir exclui a `$a` variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-206">The following command deletes the `$a` variable:</span></span>

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a><span data-ttu-id="f3345-207">A atribuição por operador de multiplicação</span><span class="sxs-lookup"><span data-stu-id="f3345-207">The assignment by multiplication operator</span></span>

<span data-ttu-id="f3345-208">A atribuição por operador de multiplicação `*=` multiplica um valor numérico ou acrescenta o número especificado de cópias do valor da cadeia de caracteres de uma variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-208">The assignment by multiplication operator `*=` multiplies a numeric value or appends the specified number of copies of the string value of a variable.</span></span>

<span data-ttu-id="f3345-209">Quando uma variável contém um único valor numérico, esse valor é multiplicado pelo valor no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="f3345-209">When a variable contains a single numeric value, that value is multiplied by the value on the right side of the operator.</span></span> <span data-ttu-id="f3345-210">Por exemplo, o exemplo a seguir mostra como usar o `*=` operador para multiplicar o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-210">For example, the following example shows how to use the `*=` operator to multiply the value of a variable:</span></span>

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

<span data-ttu-id="f3345-211">Nesse caso, o `*=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="f3345-211">In this case, the `*=` operator combines two operations.</span></span> <span data-ttu-id="f3345-212">Primeiro, ele multiplica e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="f3345-212">First, it multiplies, and then it assigns.</span></span> <span data-ttu-id="f3345-213">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f3345-213">Therefore, the following statements are equivalent:</span></span>

```powershell
$a *= 2
$a = ($a * 2)
```

<span data-ttu-id="f3345-214">Quando uma variável contém um valor de cadeia de caracteres, o PowerShell anexa o número de cadeias de caracteres especificado ao valor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-214">When a variable contains a string value, PowerShell appends the specified number of strings to the value, as follows:</span></span>

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

<span data-ttu-id="f3345-215">Para multiplicar um elemento de uma matriz, use um índice para identificar o elemento que você deseja multiplicar.</span><span class="sxs-lookup"><span data-stu-id="f3345-215">To multiply an element of an array, use an index to identify the element that you want to multiply.</span></span> <span data-ttu-id="f3345-216">Por exemplo, o comando a seguir multiplica o primeiro elemento na matriz (posição do índice 0) por 2:</span><span class="sxs-lookup"><span data-stu-id="f3345-216">For example, the following command multiplies the first element in the array (index position 0) by 2:</span></span>

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a><span data-ttu-id="f3345-217">A atribuição por operador de divisão</span><span class="sxs-lookup"><span data-stu-id="f3345-217">The assignment by division operator</span></span>

<span data-ttu-id="f3345-218">O operador atribuição por divisão `/=` divide um valor numérico pelo valor especificado no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="f3345-218">The assignment by division operator `/=` divides a numeric value by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="f3345-219">O operador não pode ser usado com variáveis de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f3345-219">The operator cannot be used with string variables.</span></span>

<span data-ttu-id="f3345-220">O `/=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="f3345-220">The `/=` operator combines two operations.</span></span> <span data-ttu-id="f3345-221">Primeiro, ele divide e, em seguida, atribui.</span><span class="sxs-lookup"><span data-stu-id="f3345-221">First, it divides, and then it assigns.</span></span> <span data-ttu-id="f3345-222">Portanto, as duas instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f3345-222">Therefore, the following two statements are equivalent:</span></span>

```powershell
$a /= 2
$a = ($a / 2)
```

<span data-ttu-id="f3345-223">Por exemplo, o comando a seguir usa o `/=` operador para dividir o valor de uma variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-223">For example, the following command uses the `/=` operator to divide the value of a variable:</span></span>

```powershell
$a = 8
$a /=2
$a
```

```
4
```

<span data-ttu-id="f3345-224">Para dividir um elemento de uma matriz, use um índice para identificar o elemento que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="f3345-224">To divide an element of an array, use an index to identify the element that you want to change.</span></span> <span data-ttu-id="f3345-225">Por exemplo, o comando a seguir divide o segundo elemento na matriz (posição de índice 1) por 2:</span><span class="sxs-lookup"><span data-stu-id="f3345-225">For example, the following command divides the second element in the array (index position 1) by 2:</span></span>

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a><span data-ttu-id="f3345-226">O operador de atribuição por módulo</span><span class="sxs-lookup"><span data-stu-id="f3345-226">The assignment by modulus operator</span></span>

<span data-ttu-id="f3345-227">A atribuição por operador de módulo `%=` divide o valor de uma variável pelo valor no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="f3345-227">The assignment by modulus operator `%=` divides the value of a variable by the value on the right side of the operator.</span></span> <span data-ttu-id="f3345-228">Em seguida, o `%=` operador atribui o resto (conhecido como módulo) à variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-228">Then, the `%=` operator assigns the remainder (known as the modulus) to the variable.</span></span> <span data-ttu-id="f3345-229">Você pode usar esse operador somente quando uma variável contiver um único valor numérico.</span><span class="sxs-lookup"><span data-stu-id="f3345-229">You can use this operator only when a variable contains a single numeric value.</span></span> <span data-ttu-id="f3345-230">Você não pode usar esse operador quando uma variável contém uma variável de cadeia de caracteres ou uma matriz.</span><span class="sxs-lookup"><span data-stu-id="f3345-230">You cannot use this operator when a variable contains a string variable or an array.</span></span>

<span data-ttu-id="f3345-231">O `%=` operador combina duas operações.</span><span class="sxs-lookup"><span data-stu-id="f3345-231">The `%=` operator combines two operations.</span></span> <span data-ttu-id="f3345-232">Primeiro, ele divide e determina o restante e, em seguida, atribui o resto à variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-232">First, it divides and determines the remainder, and then it assigns the remainder to the variable.</span></span> <span data-ttu-id="f3345-233">Portanto, as instruções a seguir são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f3345-233">Therefore, the following statements are equivalent:</span></span>

```powershell
$a %= 2
$a = ($a % 2)
```

<span data-ttu-id="f3345-234">O exemplo a seguir mostra como usar o `%=` operador para salvar o módulo de um quociente:</span><span class="sxs-lookup"><span data-stu-id="f3345-234">The following example shows how to use the `%=` operator to save the modulus of a quotient:</span></span>

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a><span data-ttu-id="f3345-235">Os operadores de incremento e decremento</span><span class="sxs-lookup"><span data-stu-id="f3345-235">The increment and decrement operators</span></span>

<span data-ttu-id="f3345-236">O operador de incremento `++` aumenta o valor de uma variável em 1.</span><span class="sxs-lookup"><span data-stu-id="f3345-236">The increment operator `++` increases the value of a variable by 1.</span></span> <span data-ttu-id="f3345-237">Quando você usa o operador de incremento em uma instrução simples, nenhum valor é retornado.</span><span class="sxs-lookup"><span data-stu-id="f3345-237">When you use the increment operator in a simple statement, no value is returned.</span></span> <span data-ttu-id="f3345-238">Para exibir o resultado, exiba o valor da variável, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-238">To view the result, display the value of the variable, as follows:</span></span>

```powershell
$a = 7
++$a
$a
```

```
8
```

<span data-ttu-id="f3345-239">Para forçar um valor a ser retornado, coloque a variável e o operador entre parênteses, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-239">To force a value to be returned, enclose the variable and the operator in parentheses, as follows:</span></span>

```powershell
$a = 7
(++$a)
```

```
8
```

<span data-ttu-id="f3345-240">O operador de incremento pode ser colocado antes (prefixo) ou após (sufixo) uma variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-240">The increment operator can be placed before (prefix) or after (postfix) a variable.</span></span> <span data-ttu-id="f3345-241">A versão de prefixo do operador incrementa uma variável antes de seu valor ser usado na instrução, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-241">The prefix version of the operator increments a variable before its value is used in the statement, as follows:</span></span>

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

<span data-ttu-id="f3345-242">A versão do sufixo do operador incrementa uma variável depois que seu valor é usado na instrução.</span><span class="sxs-lookup"><span data-stu-id="f3345-242">The postfix version of the operator increments a variable after its value is used in the statement.</span></span> <span data-ttu-id="f3345-243">No exemplo a seguir, as `$c` `$a` variáveis e têm valores diferentes porque o valor é atribuído `$c` antes `$a` das alterações:</span><span class="sxs-lookup"><span data-stu-id="f3345-243">In the following example, the `$c` and `$a` variables have different values because the value is assigned to `$c` before `$a` changes:</span></span>

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

<span data-ttu-id="f3345-244">O operador decremento `--` diminui o valor de uma variável em 1.</span><span class="sxs-lookup"><span data-stu-id="f3345-244">The decrement operator `--` decreases the value of a variable by 1.</span></span> <span data-ttu-id="f3345-245">Assim como com o operador de incremento, nenhum valor é retornado quando você usa o operador em uma instrução simples.</span><span class="sxs-lookup"><span data-stu-id="f3345-245">As with the increment operator, no value is returned when you use the operator in a simple statement.</span></span> <span data-ttu-id="f3345-246">Use parênteses para retornar um valor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-246">Use parentheses to return a value, as follows:</span></span>

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

<span data-ttu-id="f3345-247">A versão de prefixo do operador decrementa uma variável antes de seu valor ser usado na instrução, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-247">The prefix version of the operator decrements a variable before its value is used in the statement, as follows:</span></span>

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

<span data-ttu-id="f3345-248">A versão do sufixo do operador decrementa uma variável depois que seu valor é usado na instrução.</span><span class="sxs-lookup"><span data-stu-id="f3345-248">The postfix version of the operator decrements a variable after its value is used in the statement.</span></span> <span data-ttu-id="f3345-249">No exemplo a seguir, as `$d` `$a` variáveis e têm valores diferentes porque o valor é atribuído `$d` antes `$a` das alterações:</span><span class="sxs-lookup"><span data-stu-id="f3345-249">In the following example, the `$d` and `$a` variables have different values because the value is assigned to `$d` before `$a` changes:</span></span>

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

## <a name="microsoft-net-framework-types"></a><span data-ttu-id="f3345-250">Tipos de estrutura de Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="f3345-250">Microsoft .NET Framework types</span></span>

<span data-ttu-id="f3345-251">Por padrão, quando uma variável tem apenas um valor, o valor atribuído à variável determina o tipo de dados da variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-251">By default, when a variable has only one value, the value that is assigned to the variable determines the data type of the variable.</span></span> <span data-ttu-id="f3345-252">Por exemplo, o comando a seguir cria uma variável que tem o tipo "inteiro" (System. Int32):</span><span class="sxs-lookup"><span data-stu-id="f3345-252">For example, the following command creates a variable that has the "Integer" (System.Int32) type:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="f3345-253">Para localizar o tipo de .NET Framework de uma variável, use o método **GetType** e sua propriedade **FullName** , da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="f3345-253">To find the .NET Framework type of a variable, use the **GetType** method and its **FullName** property, as follows.</span></span> <span data-ttu-id="f3345-254">Certifique-se de incluir os parênteses após o nome do método **GetType** , mesmo que a chamada do método não tenha argumentos:</span><span class="sxs-lookup"><span data-stu-id="f3345-254">Be sure to include the parentheses after the **GetType** method name, even though the method call has no arguments:</span></span>

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

<span data-ttu-id="f3345-255">Para criar uma variável que contém uma cadeia de caracteres, atribua um valor de cadeia de caracteres à variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-255">To create a variable that contains a string, assign a string value to the variable.</span></span> <span data-ttu-id="f3345-256">Para indicar que o valor é uma cadeia de caracteres, coloque-o entre aspas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-256">To indicate that the value is a string, enclose it in quotation marks, as follows:</span></span>

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

<span data-ttu-id="f3345-257">Se o primeiro valor que é atribuído à variável for uma cadeia de caracteres, o PowerShell tratará todas as operações como operações de cadeia de caracteres e converterá novos valores em cadeias.</span><span class="sxs-lookup"><span data-stu-id="f3345-257">If the first value that is assigned to the variable is a string, PowerShell treats all operations as string operations and casts new values to strings.</span></span>
<span data-ttu-id="f3345-258">Isso ocorre no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f3345-258">This occurs in the following example:</span></span>

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

<span data-ttu-id="f3345-259">Se o primeiro valor for um inteiro, o PowerShell tratará todas as operações como operações de inteiros e converterá novos valores em inteiros.</span><span class="sxs-lookup"><span data-stu-id="f3345-259">If the first value is an integer, PowerShell treats all operations as integer operations and casts new values to integers.</span></span> <span data-ttu-id="f3345-260">Isso ocorre no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f3345-260">This occurs in the following example:</span></span>

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

<span data-ttu-id="f3345-261">Você pode converter uma nova variável escalar como qualquer .NET Framework tipo colocando o nome do tipo entre colchetes que precedem o nome da variável ou o primeiro valor de atribuição.</span><span class="sxs-lookup"><span data-stu-id="f3345-261">You can cast a new scalar variable as any .NET Framework type by placing the type name in brackets that precede either the variable name or the first assignment value.</span></span> <span data-ttu-id="f3345-262">Ao converter uma variável, você pode determinar os tipos de dados que podem ser armazenados na variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-262">When you cast a variable, you can determine the types of data that can be stored in the variable.</span></span> <span data-ttu-id="f3345-263">E você pode determinar como a variável se comporta quando você a manipula.</span><span class="sxs-lookup"><span data-stu-id="f3345-263">And, you can determine how the variable behaves when you manipulate it.</span></span>

<span data-ttu-id="f3345-264">Por exemplo, o comando a seguir converte a variável como um tipo de cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="f3345-264">For example, the following command casts the variable as a string type:</span></span>

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

<span data-ttu-id="f3345-265">O exemplo a seguir converte o primeiro valor, em vez de converter a variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-265">The following example casts the first value, instead of casting the variable:</span></span>

```powershell
$a = [string]27
```

<span data-ttu-id="f3345-266">Quando você converte uma variável para um tipo específico, a Convenção comum é converter a variável, não o valor.</span><span class="sxs-lookup"><span data-stu-id="f3345-266">When you cast a variable to a specific type, the common convention is to cast the variable, not the value.</span></span> <span data-ttu-id="f3345-267">No entanto, você não pode reconverter o tipo de dados de uma variável existente se seu valor não puder ser convertido para o novo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="f3345-267">However, you cannot recast the data type of an existing variable if its value cannot be converted to the new data type.</span></span> <span data-ttu-id="f3345-268">Para alterar o tipo de dados, você deve substituir seu valor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3345-268">To change the data type, you must replace its value, as follows:</span></span>

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

<span data-ttu-id="f3345-269">Além disso, quando você precede um nome de variável com um tipo de dados, o tipo dessa variável é bloqueado, a menos que você substitua explicitamente o tipo especificando outro tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="f3345-269">In addition, when you precede a variable name with a data type, the type of that variable is locked unless you explicitly override the type by specifying another data type.</span></span> <span data-ttu-id="f3345-270">Se você tentar atribuir um valor incompatível com o tipo existente e não substituir explicitamente o tipo, o PowerShell exibirá um erro, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f3345-270">If you try to assign a value that is incompatible with the existing type, and you do not explicitly override the type, PowerShell displays an error, as shown in the following example:</span></span>

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

<span data-ttu-id="f3345-271">No PowerShell, os tipos de dados de variáveis que contêm vários itens em uma matriz são tratados de forma diferente dos tipos de dados de variáveis que contêm um único item.</span><span class="sxs-lookup"><span data-stu-id="f3345-271">In PowerShell, the data types of variables that contain multiple items in an array are handled differently from the data types of variables that contain a single item.</span></span> <span data-ttu-id="f3345-272">A menos que um tipo de dados seja especificamente atribuído a uma variável de matriz, o tipo de dados é sempre `System.Object []` .</span><span class="sxs-lookup"><span data-stu-id="f3345-272">Unless a data type is specifically assigned to an array variable, the data type is always `System.Object []`.</span></span> <span data-ttu-id="f3345-273">Esse tipo de dados é específico para matrizes.</span><span class="sxs-lookup"><span data-stu-id="f3345-273">This data type is specific to arrays.</span></span>

<span data-ttu-id="f3345-274">Às vezes, você pode substituir o tipo padrão especificando outro tipo.</span><span class="sxs-lookup"><span data-stu-id="f3345-274">Sometimes, you can override the default type by specifying another type.</span></span> <span data-ttu-id="f3345-275">Por exemplo, o comando a seguir converte a variável como um `string []` tipo de matriz:</span><span class="sxs-lookup"><span data-stu-id="f3345-275">For example, the following command casts the variable as a `string []` array type:</span></span>

```powershell
[string []] $a = "one", "two", "three"
```

<span data-ttu-id="f3345-276">As variáveis do PowerShell podem ser qualquer tipo de dados .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3345-276">PowerShell variables can be any .NET Framework data type.</span></span> <span data-ttu-id="f3345-277">Além disso, você pode atribuir qualquer tipo de dados .NET Framework totalmente qualificado que esteja disponível no processo atual.</span><span class="sxs-lookup"><span data-stu-id="f3345-277">In addition, you can assign any fully qualified .NET Framework data type that is available in the current process.</span></span> <span data-ttu-id="f3345-278">Por exemplo, o comando a seguir especifica um `System.DateTime` tipo de dados:</span><span class="sxs-lookup"><span data-stu-id="f3345-278">For example, the following command specifies a `System.DateTime` data type:</span></span>

```powershell
[System.DateTime]$a = "5/31/2005"
```

<span data-ttu-id="f3345-279">A variável será atribuída a um valor que esteja de acordo com o `System.DateTime` tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="f3345-279">The variable will be assigned a value that conforms to the `System.DateTime` data type.</span></span> <span data-ttu-id="f3345-280">O valor da `$a` variável seria o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3345-280">The value of the `$a` variable would be the following:</span></span>

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a><span data-ttu-id="f3345-281">Atribuindo várias variáveis</span><span class="sxs-lookup"><span data-stu-id="f3345-281">Assigning multiple variables</span></span>

<span data-ttu-id="f3345-282">No PowerShell, você pode atribuir valores a várias variáveis usando um único comando.</span><span class="sxs-lookup"><span data-stu-id="f3345-282">In PowerShell, you can assign values to multiple variables by using a single command.</span></span> <span data-ttu-id="f3345-283">O primeiro elemento do valor de atribuição é atribuído à primeira variável, o segundo elemento é atribuído à segunda variável, o terceiro elemento à terceira variável e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f3345-283">The first element of the assignment value is assigned to the first variable, the second element is assigned to the second variable, the third element to the third variable, and so on.</span></span> <span data-ttu-id="f3345-284">Por exemplo, o comando a seguir atribui o valor 1 à `$a` variável, o valor 2 à `$b` variável e o valor 3 à `$c` variável:</span><span class="sxs-lookup"><span data-stu-id="f3345-284">For example, the following command assigns the value 1 to the `$a` variable, the value 2 to the `$b` variable, and the value 3 to the `$c` variable:</span></span>

```powershell
$a, $b, $c = 1, 2, 3
```

<span data-ttu-id="f3345-285">Se o valor de atribuição contiver mais elementos que variáveis, todos os valores restantes serão atribuídos à última variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-285">If the assignment value contains more elements than variables, all the remaining values are assigned to the last variable.</span></span> <span data-ttu-id="f3345-286">Por exemplo, o comando a seguir contém três variáveis e cinco valores:</span><span class="sxs-lookup"><span data-stu-id="f3345-286">For example, the following command contains three variables and five values:</span></span>

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

<span data-ttu-id="f3345-287">Portanto, o PowerShell atribui o valor 1 à `$a` variável e o valor 2 à `$b` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-287">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="f3345-288">Ele atribui os valores 3, 4 e 5 à `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-288">It assigns the values 3, 4, and 5 to the `$c` variable.</span></span>
<span data-ttu-id="f3345-289">Para atribuir os valores na `$c` variável a três outras variáveis, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="f3345-289">To assign the values in the `$c` variable to three other variables, use the following format:</span></span>

```powershell
$d, $e, $f = $c
```

<span data-ttu-id="f3345-290">Esse comando atribui o valor 3 à `$d` variável, o valor 4 à `$e` variável e o valor 5 à `$f` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-290">This command assigns the value 3 to the `$d` variable, the value 4 to the `$e` variable, and the value 5 to the `$f` variable.</span></span>

<span data-ttu-id="f3345-291">Se o valor de atribuição contiver menos elementos que variáveis, todas as variáveis restantes no final não serão atribuídas a nenhum valor.</span><span class="sxs-lookup"><span data-stu-id="f3345-291">If the assignment value contains less elements than variables, all the remaining variables at the end are not assigned any values.</span></span> <span data-ttu-id="f3345-292">Por exemplo, o comando a seguir contém três variáveis e dois valores:</span><span class="sxs-lookup"><span data-stu-id="f3345-292">For example, the following command contains three variables and two values:</span></span>

```powershell
$a, $b, $c = 1, 2
```

<span data-ttu-id="f3345-293">Portanto, o PowerShell atribui o valor 1 à `$a` variável e o valor 2 à `$b` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-293">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="f3345-294">Ele não atribuirá nenhum valor à `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-294">It will not assign any value to the `$c` variable.</span></span>

<span data-ttu-id="f3345-295">Você também pode atribuir um único valor a várias variáveis encadeando as variáveis.</span><span class="sxs-lookup"><span data-stu-id="f3345-295">You can also assign a single value to multiple variables by chaining the variables.</span></span> <span data-ttu-id="f3345-296">Por exemplo, o comando a seguir atribui um valor de "três" a todas as quatro variáveis:</span><span class="sxs-lookup"><span data-stu-id="f3345-296">For example, the following command assigns a value of "three" to all four variables:</span></span>

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a><span data-ttu-id="f3345-297">Cmdlets relacionados a variáveis</span><span class="sxs-lookup"><span data-stu-id="f3345-297">Variable-related cmdlets</span></span>

<span data-ttu-id="f3345-298">Além de usar uma operação de atribuição para definir um valor de variável, você também pode usar o cmdlet [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) .</span><span class="sxs-lookup"><span data-stu-id="f3345-298">In addition to using an assignment operation to set a variable value, you can also use the [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) cmdlet.</span></span> <span data-ttu-id="f3345-299">Por exemplo, o comando a seguir usa `Set-Variable` para atribuir uma matriz de 1, 2, 3 à `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="f3345-299">For example, the following command uses `Set-Variable` to assign an array of 1, 2, 3 to the `$a` variable.</span></span>

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a><span data-ttu-id="f3345-300">Confira também</span><span class="sxs-lookup"><span data-stu-id="f3345-300">See also</span></span>

[<span data-ttu-id="f3345-301">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="f3345-301">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="f3345-302">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="f3345-302">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="f3345-303">about_Variables</span><span class="sxs-lookup"><span data-stu-id="f3345-303">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="f3345-304">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="f3345-304">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[<span data-ttu-id="f3345-305">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="f3345-305">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[<span data-ttu-id="f3345-306">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="f3345-306">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
