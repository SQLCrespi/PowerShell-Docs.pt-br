---
description: Descreve os operadores com suporte do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: b783d2cb76fe8a0a66ec77b67ef915f3b78def04
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94482985"
---
# <a name="about-operators"></a><span data-ttu-id="81828-104">Sobre operadores</span><span class="sxs-lookup"><span data-stu-id="81828-104">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="81828-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="81828-105">Short description</span></span>
<span data-ttu-id="81828-106">Descreve os operadores com suporte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81828-106">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="81828-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="81828-107">Long description</span></span>

<span data-ttu-id="81828-108">Um operador é um elemento de linguagem que você pode usar em um comando ou expressão.</span><span class="sxs-lookup"><span data-stu-id="81828-108">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="81828-109">O PowerShell dá suporte a vários tipos de operadores para ajudá-lo a manipular valores.</span><span class="sxs-lookup"><span data-stu-id="81828-109">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="81828-110">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="81828-110">Arithmetic Operators</span></span>

<span data-ttu-id="81828-111">Use operadores aritméticos (,,, `+` `-` `*` `/` , `%` ) para calcular valores em um comando ou expressão.</span><span class="sxs-lookup"><span data-stu-id="81828-111">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="81828-112">Com esses operadores, você pode adicionar, subtrair, multiplicar ou dividir valores e calcular o resto (módulo) de uma operação de divisão.</span><span class="sxs-lookup"><span data-stu-id="81828-112">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="81828-113">O operador de adição concatena os elementos.</span><span class="sxs-lookup"><span data-stu-id="81828-113">The addition operator concatenates elements.</span></span> <span data-ttu-id="81828-114">O operador de multiplicação retorna o número especificado de cópias de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="81828-114">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="81828-115">Você pode usar operadores aritméticos em qualquer tipo .NET que os implemente, como: `Int` ,, `String` `DateTime` , `Hashtable` e matrizes.</span><span class="sxs-lookup"><span data-stu-id="81828-115">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="81828-116">Os operadores bit `-band` a bit (, `-bor` , `-bxor` ,, `-bnot` `-shl` , `-shr` ) manipulam os padrões de bits em valores.</span><span class="sxs-lookup"><span data-stu-id="81828-116">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="81828-117">Para obter mais informações, consulte [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="81828-117">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="81828-118">Operadores de atribuição</span><span class="sxs-lookup"><span data-stu-id="81828-118">Assignment Operators</span></span>

<span data-ttu-id="81828-119">Use operadores de atribuição ( `=` ,, `+=` ,, `-=` `*=` `/=` , `%=` ) para atribuir, alterar ou acrescentar valores a variáveis.</span><span class="sxs-lookup"><span data-stu-id="81828-119">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="81828-120">Você pode combinar operadores aritméticos com atribuição para atribuir o resultado da operação aritmética a uma variável.</span><span class="sxs-lookup"><span data-stu-id="81828-120">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="81828-121">Para obter mais informações, consulte [about_assignment_operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="81828-121">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="81828-122">Operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="81828-122">Comparison Operators</span></span>

<span data-ttu-id="81828-123">Use operadores de comparação ( `-eq` ,, `-ne` ,, `-gt` `-lt` `-le` , `-ge` ) para comparar valores e condições de teste.</span><span class="sxs-lookup"><span data-stu-id="81828-123">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="81828-124">Por exemplo, você pode comparar dois valores de cadeia de caracteres para determinar se eles são iguais.</span><span class="sxs-lookup"><span data-stu-id="81828-124">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="81828-125">Os operadores de comparação também incluem operadores que localizam ou substituem padrões no texto.</span><span class="sxs-lookup"><span data-stu-id="81828-125">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="81828-126">Os `-match` operadores (, `-notmatch` , `-replace` ) usam expressões regulares e ( `-like` , `-notlike` ) usam Curingas `*` .</span><span class="sxs-lookup"><span data-stu-id="81828-126">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="81828-127">Os operadores de comparação de confinamento determinam se um valor de teste aparece em um conjunto de referência (,,, `-in` `-notin` `-contains` `-notcontains` ).</span><span class="sxs-lookup"><span data-stu-id="81828-127">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="81828-128">Operadores de comparação de tipo ( `-is` , `-isnot` ) determinam se um objeto é de um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="81828-128">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="81828-129">Para obter mais informações, consulte [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="81828-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="81828-130">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="81828-130">Logical Operators</span></span>

<span data-ttu-id="81828-131">Use operadores lógicos (,,, `-and` `-or` `-xor` `-not` , `!` ) para conectar instruções condicionais em um único condicional complexo.</span><span class="sxs-lookup"><span data-stu-id="81828-131">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="81828-132">Por exemplo, você pode usar um `-and` operador lógico para criar um filtro de objeto com duas condições diferentes.</span><span class="sxs-lookup"><span data-stu-id="81828-132">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="81828-133">Para obter mais informações, consulte [about_Logical_Operators](about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="81828-133">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="81828-134">Operadores de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="81828-134">Redirection Operators</span></span>

<span data-ttu-id="81828-135">Use operadores de redirecionamento ( `>` ,, `>>` `2>` , `2>>` e `2>&1` ) para enviar a saída de um comando ou expressão para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="81828-135">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="81828-136">Os operadores de redirecionamento funcionam como o `Out-File` cmdlet (sem parâmetros), mas também permitem redirecionar a saída de erro para os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="81828-136">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="81828-137">Você também pode usar o `Tee-Object` cmdlet para redirecionar a saída.</span><span class="sxs-lookup"><span data-stu-id="81828-137">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="81828-138">Para obter mais informações, consulte [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="81828-138">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="81828-139">Operadores de divisão e junção</span><span class="sxs-lookup"><span data-stu-id="81828-139">Split and Join Operators</span></span>

<span data-ttu-id="81828-140">Os `-split` `-join` operadores e dividem e combinam subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="81828-140">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="81828-141">O `-split` operador divide uma cadeia de caracteres em subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="81828-141">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="81828-142">O `-join` operador concatena várias cadeias de caracteres em uma única cadeia.</span><span class="sxs-lookup"><span data-stu-id="81828-142">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="81828-143">Para obter mais informações, consulte [about_Split](about_Split.md) e [about_join](about_Join.md).</span><span class="sxs-lookup"><span data-stu-id="81828-143">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="81828-144">Operadores de tipo</span><span class="sxs-lookup"><span data-stu-id="81828-144">Type Operators</span></span>

<span data-ttu-id="81828-145">Use os operadores de tipo ( `-is` , `-isnot` , `-as` ) para localizar ou alterar o tipo de .NET Framework de um objeto.</span><span class="sxs-lookup"><span data-stu-id="81828-145">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="81828-146">Para obter mais informações, consulte [about_Type_Operators](about_Type_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="81828-146">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="81828-147">Operadores unários</span><span class="sxs-lookup"><span data-stu-id="81828-147">Unary Operators</span></span>

<span data-ttu-id="81828-148">Use operadores unários para incrementar ou decrementar variáveis ou propriedades de objeto e para definir inteiros como números positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="81828-148">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="81828-149">Por exemplo, para incrementar a variável `$a` de `9` para `10` , digite `$a++` .</span><span class="sxs-lookup"><span data-stu-id="81828-149">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="81828-150">Operadores especiais</span><span class="sxs-lookup"><span data-stu-id="81828-150">Special Operators</span></span>

<span data-ttu-id="81828-151">Operadores especiais têm casos de uso específicos que não se ajustam a nenhum outro grupo de operadores.</span><span class="sxs-lookup"><span data-stu-id="81828-151">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="81828-152">Por exemplo, operadores especiais permitem que você execute comandos, altere o tipo de dados de um valor ou recupere elementos de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="81828-152">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="81828-153">Operador de agrupamento `( )`</span><span class="sxs-lookup"><span data-stu-id="81828-153">Grouping operator `( )`</span></span>

<span data-ttu-id="81828-154">Como em outras linguagens, `(...)` serve para substituir a precedência de operador em expressões.</span><span class="sxs-lookup"><span data-stu-id="81828-154">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="81828-155">Por exemplo: `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="81828-155">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="81828-156">No entanto, no PowerShell, há comportamentos adicionais.</span><span class="sxs-lookup"><span data-stu-id="81828-156">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="81828-157">`(...)` permite que você permita que a saída de um _comando_ participe de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="81828-157">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="81828-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="81828-158">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="81828-159">Quando usado como o primeiro segmento de um pipeline, o encapsulamento de um comando ou uma expressão em parênteses invariavelmente causa a _Enumeração_ do resultado da expressão.</span><span class="sxs-lookup"><span data-stu-id="81828-159">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="81828-160">Se os parênteses encapsularem um _comando_ , ele será executado para conclusão com todas as saídas _coletadas na memória_ antes que os resultados sejam enviados por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="81828-160">If the parentheses wrap a _command_ , it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="81828-161">O encapsulamento de um comando entre parênteses faz com que a variável automática `$?` seja definida como `$true` , mesmo quando o próprio comando incluído é definido `$?` como `$false` .</span><span class="sxs-lookup"><span data-stu-id="81828-161">Wrapping a command in parentheses causes the automatic variable `$?` to be set to `$true`, even when the enclosed command itself set `$?` to `$false`.</span></span>
> <span data-ttu-id="81828-162">Por exemplo, o `(Get-Item /Nosuch); $?` resultado é **verdadeiro** inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="81828-162">For example, `(Get-Item /Nosuch); $?` unexpectedly yields **True**.</span></span> <span data-ttu-id="81828-163">Para obter mais informações sobre o `$?` , consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="81828-163">For more information about `$?`, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="81828-164">Operador de subexpressão `$( )`</span><span class="sxs-lookup"><span data-stu-id="81828-164">Subexpression operator `$( )`</span></span>

<span data-ttu-id="81828-165">Retorna o resultado de uma ou mais instruções.</span><span class="sxs-lookup"><span data-stu-id="81828-165">Returns the result of one or more statements.</span></span> <span data-ttu-id="81828-166">Para um único resultado, retorna um escalar.</span><span class="sxs-lookup"><span data-stu-id="81828-166">For a single result, returns a scalar.</span></span> <span data-ttu-id="81828-167">Para vários resultados, retorna uma matriz.</span><span class="sxs-lookup"><span data-stu-id="81828-167">For multiple results, returns an array.</span></span> <span data-ttu-id="81828-168">Use isso quando desejar usar uma expressão dentro de outra expressão.</span><span class="sxs-lookup"><span data-stu-id="81828-168">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="81828-169">Por exemplo, para inserir os resultados do comando em uma expressão de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="81828-169">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="81828-170">Operador de subexpressão de matriz `@( )`</span><span class="sxs-lookup"><span data-stu-id="81828-170">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="81828-171">Retorna o resultado de uma ou mais instruções como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="81828-171">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="81828-172">Se houver apenas um item, a matriz terá apenas um membro.</span><span class="sxs-lookup"><span data-stu-id="81828-172">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="hash-table-literal-syntax-"></a><span data-ttu-id="81828-173">Sintaxe literal da tabela de hash `@{}`</span><span class="sxs-lookup"><span data-stu-id="81828-173">Hash table literal syntax `@{}`</span></span>

<span data-ttu-id="81828-174">Semelhante à subexpressão de matriz, essa sintaxe é usada para declarar uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="81828-174">Similar to the array subexpression, this syntax is used to declare a hash table.</span></span>
<span data-ttu-id="81828-175">Para obter mais informações, consulte [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="81828-175">For more information, see [about_Hash_Tables](about_Hash_Tables.md).</span></span>

#### <a name="call-operator-"></a><span data-ttu-id="81828-176">Operador de chamada `&`</span><span class="sxs-lookup"><span data-stu-id="81828-176">Call operator `&`</span></span>

<span data-ttu-id="81828-177">Executa um comando, script ou bloco de script.</span><span class="sxs-lookup"><span data-stu-id="81828-177">Runs a command, script, or script block.</span></span> <span data-ttu-id="81828-178">O operador Call, também conhecido como "operador de invocação", permite executar comandos que são armazenados em variáveis e representados por cadeias de caracteres ou blocos de script.</span><span class="sxs-lookup"><span data-stu-id="81828-178">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="81828-179">O operador de chamada é executado em um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="81828-179">The call operator executes in a child scope.</span></span> <span data-ttu-id="81828-180">Para obter mais informações sobre escopos, consulte [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="81828-180">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="81828-181">Este exemplo armazena um comando em uma cadeia de caracteres e executa-o usando o operador Call.</span><span class="sxs-lookup"><span data-stu-id="81828-181">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="81828-182">O operador de chamada não analisa cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="81828-182">The call operator does not parse strings.</span></span> <span data-ttu-id="81828-183">Isso significa que você não pode usar parâmetros de comando em uma cadeia de caracteres ao usar o operador de chamada.</span><span class="sxs-lookup"><span data-stu-id="81828-183">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
At line:1 char:2
+ & $c
+  ~~
    + CategoryInfo          : ObjectNotFound: (Get-Service -Name Spooler:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="81828-184">O cmdlet [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) pode executar código que causa erros de análise ao usar o operador Call.</span><span class="sxs-lookup"><span data-stu-id="81828-184">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

<span data-ttu-id="81828-185">Você pode usar o operador de chamada para executar scripts usando seus nomes de File.</span><span class="sxs-lookup"><span data-stu-id="81828-185">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="81828-186">O exemplo a seguir mostra um nome de arquivo de script que contém espaços.</span><span class="sxs-lookup"><span data-stu-id="81828-186">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="81828-187">Quando você tenta executar o script, o PowerShell exibe o conteúdo da cadeia de caracteres entre aspas que contém o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="81828-187">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="81828-188">O operador Call permite que você execute o conteúdo da cadeia de caracteres que contém o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="81828-188">The call operator allows you to execute the contents of the string containing the filename.</span></span>

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

<span data-ttu-id="81828-189">Para obter mais informações sobre blocos de script, consulte [about_Script_Blocks](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="81828-189">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="81828-190">Operador cast `[ ]`</span><span class="sxs-lookup"><span data-stu-id="81828-190">Cast operator `[ ]`</span></span>

<span data-ttu-id="81828-191">Converte ou limita objetos no tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="81828-191">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="81828-192">Se os objetos não puderem ser convertidos, o PowerShell gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="81828-192">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="81828-193">Uma conversão também pode ser executada quando uma variável é atribuída ao uso de [notação de conversão](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="81828-193">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="81828-194">Operador de vírgula `,`</span><span class="sxs-lookup"><span data-stu-id="81828-194">Comma operator `,`</span></span>

<span data-ttu-id="81828-195">Como um operador binário, a vírgula cria uma matriz ou acrescenta à matriz que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="81828-195">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="81828-196">No modo de expressão, como um operador unário, a vírgula cria uma matriz com apenas um membro.</span><span class="sxs-lookup"><span data-stu-id="81828-196">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="81828-197">Coloque a vírgula antes do membro.</span><span class="sxs-lookup"><span data-stu-id="81828-197">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="81828-198">Como `Write-Object` o espera um argumento, você deve colocar a expressão entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="81828-198">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="81828-199">Operador de fornecimento de ponto `.`</span><span class="sxs-lookup"><span data-stu-id="81828-199">Dot sourcing operator `.`</span></span>

<span data-ttu-id="81828-200">Executa um script no escopo atual para que quaisquer funções, aliases e variáveis que o script cria sejam adicionados ao escopo atual, substituindo os existentes.</span><span class="sxs-lookup"><span data-stu-id="81828-200">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="81828-201">Os parâmetros declarados pelo script se tornam variáveis.</span><span class="sxs-lookup"><span data-stu-id="81828-201">Parameters declared by the script become variables.</span></span> <span data-ttu-id="81828-202">Parâmetros para os quais nenhum valor foi fornecido se tornam variáveis sem valor.</span><span class="sxs-lookup"><span data-stu-id="81828-202">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="81828-203">No entanto, a variável automática `$args` é preservada.</span><span class="sxs-lookup"><span data-stu-id="81828-203">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="81828-204">O operador ponto de fornecimento é seguido por um espaço.</span><span class="sxs-lookup"><span data-stu-id="81828-204">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="81828-205">Use o espaço para distinguir o ponto do símbolo de ponto ( `.` ) que representa o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="81828-205">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="81828-206">No exemplo a seguir, o script Sample.ps1 no diretório atual é executado no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="81828-206">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="81828-207">Operador de formato `-f`</span><span class="sxs-lookup"><span data-stu-id="81828-207">Format operator `-f`</span></span>

<span data-ttu-id="81828-208">Formata cadeias de caracteres usando o método Format de objetos String.</span><span class="sxs-lookup"><span data-stu-id="81828-208">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="81828-209">Insira a cadeia de caracteres de formato no lado esquerdo do operador e os objetos a serem formatados no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="81828-209">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="81828-210">Se você precisar manter as chaves ( `{}` ) na cadeia de caracteres formatada, poderá escapar delas dobrando as chaves.</span><span class="sxs-lookup"><span data-stu-id="81828-210">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="81828-211">Para obter mais informações, consulte o método [String. Format](/dotnet/api/system.string.format) e a [formatação composta](/dotnet/standard/base-types/composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="81828-211">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="81828-212">Operador de índice `[ ]`</span><span class="sxs-lookup"><span data-stu-id="81828-212">Index operator `[ ]`</span></span>

<span data-ttu-id="81828-213">Seleciona objetos de coleções indexadas, como matrizes e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="81828-213">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="81828-214">Os índices de matriz são baseados em zero, portanto, o primeiro objeto é indexado como `[0]` .</span><span class="sxs-lookup"><span data-stu-id="81828-214">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="81828-215">Para matrizes (somente), você também pode usar índices negativos para obter os últimos valores.</span><span class="sxs-lookup"><span data-stu-id="81828-215">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="81828-216">As tabelas de hash são indexadas por valor de chave.</span><span class="sxs-lookup"><span data-stu-id="81828-216">Hash tables are indexed by key value.</span></span>

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a><span data-ttu-id="81828-217">Operador de pipeline `|`</span><span class="sxs-lookup"><span data-stu-id="81828-217">Pipeline operator `|`</span></span>

<span data-ttu-id="81828-218">Envia ("pipes") a saída do comando que o precede para o comando que o segue.</span><span class="sxs-lookup"><span data-stu-id="81828-218">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="81828-219">Quando a saída inclui mais de um objeto (uma "coleção"), o operador de pipeline envia os objetos um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="81828-219">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="range-operator-"></a><span data-ttu-id="81828-220">Operador de intervalo `..`</span><span class="sxs-lookup"><span data-stu-id="81828-220">Range operator `..`</span></span>

<span data-ttu-id="81828-221">Representa os inteiros sequenciais em uma matriz de inteiros, de acordo com um limite superior e inferior.</span><span class="sxs-lookup"><span data-stu-id="81828-221">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="81828-222">Você também pode criar intervalos na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="81828-222">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

#### <a name="member-access-operator-"></a><span data-ttu-id="81828-223">Operador de acesso de membro `.`</span><span class="sxs-lookup"><span data-stu-id="81828-223">Member access operator `.`</span></span>

<span data-ttu-id="81828-224">Acessa as propriedades e os métodos de um objeto.</span><span class="sxs-lookup"><span data-stu-id="81828-224">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="81828-225">O nome do membro pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="81828-225">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="81828-226">Operador de membro estático `::`</span><span class="sxs-lookup"><span data-stu-id="81828-226">Static member operator `::`</span></span>

<span data-ttu-id="81828-227">Chama as propriedades e os métodos estáticos de uma classe .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="81828-227">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="81828-228">Para localizar as propriedades e os métodos estáticos de um objeto, use o parâmetro static do `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="81828-228">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="81828-229">O nome do membro pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="81828-229">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

## <a name="see-also"></a><span data-ttu-id="81828-230">Confira também</span><span class="sxs-lookup"><span data-stu-id="81828-230">See also</span></span>

[<span data-ttu-id="81828-231">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="81828-231">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="81828-232">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="81828-232">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="81828-233">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="81828-233">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="81828-234">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="81828-234">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="81828-235">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="81828-235">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="81828-236">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="81828-236">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="81828-237">about_Split</span><span class="sxs-lookup"><span data-stu-id="81828-237">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="81828-238">about_Join</span><span class="sxs-lookup"><span data-stu-id="81828-238">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="81828-239">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="81828-239">about_Redirection</span></span>](about_Redirection.md)
