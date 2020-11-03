---
description: Descreve os operadores com suporte do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/28/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: a917afc1499af96f834496c22e5634826c5aeb73
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "93196657"
---
# <a name="about-operators"></a><span data-ttu-id="9be17-104">Sobre operadores</span><span class="sxs-lookup"><span data-stu-id="9be17-104">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="9be17-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="9be17-105">Short description</span></span>
<span data-ttu-id="9be17-106">Descreve os operadores com suporte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9be17-106">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9be17-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="9be17-107">Long description</span></span>

<span data-ttu-id="9be17-108">Um operador é um elemento de linguagem que você pode usar em um comando ou expressão.</span><span class="sxs-lookup"><span data-stu-id="9be17-108">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="9be17-109">O PowerShell dá suporte a vários tipos de operadores para ajudá-lo a manipular valores.</span><span class="sxs-lookup"><span data-stu-id="9be17-109">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="9be17-110">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="9be17-110">Arithmetic Operators</span></span>

<span data-ttu-id="9be17-111">Use operadores aritméticos (,,, `+` `-` `*` `/` , `%` ) para calcular valores em um comando ou expressão.</span><span class="sxs-lookup"><span data-stu-id="9be17-111">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="9be17-112">Com esses operadores, você pode adicionar, subtrair, multiplicar ou dividir valores e calcular o resto (módulo) de uma operação de divisão.</span><span class="sxs-lookup"><span data-stu-id="9be17-112">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="9be17-113">O operador de adição concatena os elementos.</span><span class="sxs-lookup"><span data-stu-id="9be17-113">The addition operator concatenates elements.</span></span> <span data-ttu-id="9be17-114">O operador de multiplicação retorna o número especificado de cópias de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="9be17-114">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="9be17-115">Você pode usar operadores aritméticos em qualquer tipo .NET que os implemente, como: `Int` ,, `String` `DateTime` , `Hashtable` e matrizes.</span><span class="sxs-lookup"><span data-stu-id="9be17-115">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="9be17-116">Os operadores bit `-band` a bit (, `-bor` , `-bxor` ,, `-bnot` `-shl` , `-shr` ) manipulam os padrões de bits em valores.</span><span class="sxs-lookup"><span data-stu-id="9be17-116">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="9be17-117">Para obter mais informações, consulte [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-117">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="9be17-118">Operadores de atribuição</span><span class="sxs-lookup"><span data-stu-id="9be17-118">Assignment Operators</span></span>

<span data-ttu-id="9be17-119">Use operadores de atribuição ( `=` ,, `+=` ,, `-=` `*=` `/=` , `%=` ) para atribuir, alterar ou acrescentar valores a variáveis.</span><span class="sxs-lookup"><span data-stu-id="9be17-119">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="9be17-120">Você pode combinar operadores aritméticos com atribuição para atribuir o resultado da operação aritmética a uma variável.</span><span class="sxs-lookup"><span data-stu-id="9be17-120">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="9be17-121">Para obter mais informações, consulte [about_assignment_operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-121">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="9be17-122">Operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="9be17-122">Comparison Operators</span></span>

<span data-ttu-id="9be17-123">Use operadores de comparação ( `-eq` ,, `-ne` ,, `-gt` `-lt` `-le` , `-ge` ) para comparar valores e condições de teste.</span><span class="sxs-lookup"><span data-stu-id="9be17-123">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="9be17-124">Por exemplo, você pode comparar dois valores de cadeia de caracteres para determinar se eles são iguais.</span><span class="sxs-lookup"><span data-stu-id="9be17-124">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="9be17-125">Os operadores de comparação também incluem operadores que localizam ou substituem padrões no texto.</span><span class="sxs-lookup"><span data-stu-id="9be17-125">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="9be17-126">Os `-match` operadores (, `-notmatch` , `-replace` ) usam expressões regulares e ( `-like` , `-notlike` ) usam Curingas `*` .</span><span class="sxs-lookup"><span data-stu-id="9be17-126">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="9be17-127">Os operadores de comparação de confinamento determinam se um valor de teste aparece em um conjunto de referência (,,, `-in` `-notin` `-contains` `-notcontains` ).</span><span class="sxs-lookup"><span data-stu-id="9be17-127">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="9be17-128">Operadores de comparação de tipo ( `-is` , `-isnot` ) determinam se um objeto é de um tipo específico.</span><span class="sxs-lookup"><span data-stu-id="9be17-128">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="9be17-129">Para obter mais informações, consulte [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="9be17-130">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="9be17-130">Logical Operators</span></span>

<span data-ttu-id="9be17-131">Use operadores lógicos (,,, `-and` `-or` `-xor` `-not` , `!` ) para conectar instruções condicionais em um único condicional complexo.</span><span class="sxs-lookup"><span data-stu-id="9be17-131">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="9be17-132">Por exemplo, você pode usar um `-and` operador lógico para criar um filtro de objeto com duas condições diferentes.</span><span class="sxs-lookup"><span data-stu-id="9be17-132">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="9be17-133">Para obter mais informações, consulte [about_Logical_Operators](about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-133">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="9be17-134">Operadores de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="9be17-134">Redirection Operators</span></span>

<span data-ttu-id="9be17-135">Use operadores de redirecionamento ( `>` ,, `>>` `2>` , `2>>` e `2>&1` ) para enviar a saída de um comando ou expressão para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="9be17-135">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="9be17-136">Os operadores de redirecionamento funcionam como o `Out-File` cmdlet (sem parâmetros), mas também permitem redirecionar a saída de erro para os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="9be17-136">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="9be17-137">Você também pode usar o `Tee-Object` cmdlet para redirecionar a saída.</span><span class="sxs-lookup"><span data-stu-id="9be17-137">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="9be17-138">Para obter mais informações, consulte [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="9be17-138">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="9be17-139">Operadores de divisão e junção</span><span class="sxs-lookup"><span data-stu-id="9be17-139">Split and Join Operators</span></span>

<span data-ttu-id="9be17-140">Os `-split` `-join` operadores e dividem e combinam subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9be17-140">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="9be17-141">O `-split` operador divide uma cadeia de caracteres em subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9be17-141">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="9be17-142">O `-join` operador concatena várias cadeias de caracteres em uma única cadeia.</span><span class="sxs-lookup"><span data-stu-id="9be17-142">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="9be17-143">Para obter mais informações, consulte [about_Split](about_Split.md) e [about_join](about_Join.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-143">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="9be17-144">Operadores de tipo</span><span class="sxs-lookup"><span data-stu-id="9be17-144">Type Operators</span></span>

<span data-ttu-id="9be17-145">Use os operadores de tipo ( `-is` , `-isnot` , `-as` ) para localizar ou alterar o tipo de .NET Framework de um objeto.</span><span class="sxs-lookup"><span data-stu-id="9be17-145">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="9be17-146">Para obter mais informações, consulte [about_Type_Operators](about_Type_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-146">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="9be17-147">Operadores unários</span><span class="sxs-lookup"><span data-stu-id="9be17-147">Unary Operators</span></span>

<span data-ttu-id="9be17-148">Use operadores unários para incrementar ou decrementar variáveis ou propriedades de objeto e para definir inteiros como números positivos ou negativos.</span><span class="sxs-lookup"><span data-stu-id="9be17-148">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="9be17-149">Por exemplo, para incrementar a variável `$a` de `9` para `10` , digite `$a++` .</span><span class="sxs-lookup"><span data-stu-id="9be17-149">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="9be17-150">Operadores especiais</span><span class="sxs-lookup"><span data-stu-id="9be17-150">Special Operators</span></span>

<span data-ttu-id="9be17-151">Operadores especiais têm casos de uso específicos que não se ajustam a nenhum outro grupo de operadores.</span><span class="sxs-lookup"><span data-stu-id="9be17-151">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="9be17-152">Por exemplo, operadores especiais permitem que você execute comandos, altere o tipo de dados de um valor ou recupere elementos de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="9be17-152">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="9be17-153">Operador de agrupamento `( )`</span><span class="sxs-lookup"><span data-stu-id="9be17-153">Grouping operator `( )`</span></span>

<span data-ttu-id="9be17-154">Como em outras linguagens, `(...)` serve para substituir a precedência de operador em expressões.</span><span class="sxs-lookup"><span data-stu-id="9be17-154">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="9be17-155">Por exemplo: `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="9be17-155">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="9be17-156">No entanto, no PowerShell, há comportamentos adicionais.</span><span class="sxs-lookup"><span data-stu-id="9be17-156">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="9be17-157">`(...)` permite que você permita que a saída de um _comando_ participe de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="9be17-157">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="9be17-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9be17-158">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="9be17-159">Quando usado como o primeiro segmento de um pipeline, o encapsulamento de um comando ou uma expressão em parênteses invariavelmente causa a _Enumeração_ do resultado da expressão.</span><span class="sxs-lookup"><span data-stu-id="9be17-159">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="9be17-160">Se os parênteses encapsularem um _comando_ , ele será executado para conclusão com todas as saídas _coletadas na memória_ antes que os resultados sejam enviados por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9be17-160">If the parentheses wrap a _command_ , it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="9be17-161">Operador de subexpressão `$( )`</span><span class="sxs-lookup"><span data-stu-id="9be17-161">Subexpression operator `$( )`</span></span>

<span data-ttu-id="9be17-162">Retorna o resultado de uma ou mais instruções.</span><span class="sxs-lookup"><span data-stu-id="9be17-162">Returns the result of one or more statements.</span></span> <span data-ttu-id="9be17-163">Para um único resultado, retorna um escalar.</span><span class="sxs-lookup"><span data-stu-id="9be17-163">For a single result, returns a scalar.</span></span> <span data-ttu-id="9be17-164">Para vários resultados, retorna uma matriz.</span><span class="sxs-lookup"><span data-stu-id="9be17-164">For multiple results, returns an array.</span></span> <span data-ttu-id="9be17-165">Use isso quando desejar usar uma expressão dentro de outra expressão.</span><span class="sxs-lookup"><span data-stu-id="9be17-165">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="9be17-166">Por exemplo, para inserir os resultados do comando em uma expressão de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9be17-166">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="9be17-167">Operador de subexpressão de matriz `@( )`</span><span class="sxs-lookup"><span data-stu-id="9be17-167">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="9be17-168">Retorna o resultado de uma ou mais instruções como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="9be17-168">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="9be17-169">Se houver apenas um item, a matriz terá apenas um membro.</span><span class="sxs-lookup"><span data-stu-id="9be17-169">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="call-operator-"></a><span data-ttu-id="9be17-170">Operador de chamada `&`</span><span class="sxs-lookup"><span data-stu-id="9be17-170">Call operator `&`</span></span>

<span data-ttu-id="9be17-171">Executa um comando, script ou bloco de script.</span><span class="sxs-lookup"><span data-stu-id="9be17-171">Runs a command, script, or script block.</span></span> <span data-ttu-id="9be17-172">O operador Call, também conhecido como "operador de invocação", permite executar comandos que são armazenados em variáveis e representados por cadeias de caracteres ou blocos de script.</span><span class="sxs-lookup"><span data-stu-id="9be17-172">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="9be17-173">O operador de chamada é executado em um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="9be17-173">The call operator executes in a child scope.</span></span> <span data-ttu-id="9be17-174">Para obter mais informações sobre escopos, consulte [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-174">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="9be17-175">Este exemplo armazena um comando em uma cadeia de caracteres e executa-o usando o operador Call.</span><span class="sxs-lookup"><span data-stu-id="9be17-175">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="9be17-176">O operador de chamada não analisa cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9be17-176">The call operator does not parse strings.</span></span> <span data-ttu-id="9be17-177">Isso significa que você não pode usar parâmetros de comando em uma cadeia de caracteres ao usar o operador de chamada.</span><span class="sxs-lookup"><span data-stu-id="9be17-177">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
```

<span data-ttu-id="9be17-178">O cmdlet [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) pode executar código que causa erros de análise ao usar o operador Call.</span><span class="sxs-lookup"><span data-stu-id="9be17-178">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

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

<span data-ttu-id="9be17-179">Você pode usar o operador de chamada para executar scripts usando seus nomes de File.</span><span class="sxs-lookup"><span data-stu-id="9be17-179">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="9be17-180">O exemplo a seguir mostra um nome de arquivo de script que contém espaços.</span><span class="sxs-lookup"><span data-stu-id="9be17-180">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="9be17-181">Quando você tenta executar o script, o PowerShell exibe o conteúdo da cadeia de caracteres entre aspas que contém o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="9be17-181">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="9be17-182">O operador Call permite que você execute o conteúdo da cadeia de caracteres que contém o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="9be17-182">The call operator allows you to execute the contents of the string containing the filename.</span></span>

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

<span data-ttu-id="9be17-183">Para obter mais informações sobre blocos de script, consulte [about_Script_Blocks](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-183">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="background-operator-"></a><span data-ttu-id="9be17-184">Operador de segundo plano `&`</span><span class="sxs-lookup"><span data-stu-id="9be17-184">Background operator `&`</span></span>

<span data-ttu-id="9be17-185">Executa o pipeline antes dele em segundo plano, em um trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9be17-185">Runs the pipeline before it in the background, in a PowerShell job.</span></span> <span data-ttu-id="9be17-186">Esse operador funciona de forma semelhante ao e comercial do operador de controle do UNIX ( `&` ), que executa o comando antes dele de forma assíncrona no subshell como um trabalho.</span><span class="sxs-lookup"><span data-stu-id="9be17-186">This operator acts similarly to the UNIX control operator ampersand (`&`), which runs the command before it asynchronously in subshell as a job.</span></span>

<span data-ttu-id="9be17-187">Esse operador é funcionalmente equivalente a `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="9be17-187">This operator is functionally equivalent to `Start-Job`.</span></span> <span data-ttu-id="9be17-188">Por padrão, o operador background inicia os trabalhos no diretório de trabalho atual do chamador que iniciou as tarefas paralelas.</span><span class="sxs-lookup"><span data-stu-id="9be17-188">By default, the background operator starts the jobs in the current working directory of the caller that started the parallel tasks.</span></span> <span data-ttu-id="9be17-189">O exemplo a seguir demonstra o uso básico do operador de trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9be17-189">The following example demonstrates basic usage of the background job operator.</span></span>

```powershell
Get-Process -Name pwsh &
```

<span data-ttu-id="9be17-190">Esse comando é funcionalmente equivalente ao seguinte uso de `Start-Job` :</span><span class="sxs-lookup"><span data-stu-id="9be17-190">That command is functionally equivalent to the following usage of `Start-Job`:</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process -Name pwsh}
```

<span data-ttu-id="9be17-191">Assim como `Start-Job` , o `&` operador background retorna um `Job` objeto.</span><span class="sxs-lookup"><span data-stu-id="9be17-191">Just like `Start-Job`, the `&` background operator returns a `Job` object.</span></span> <span data-ttu-id="9be17-192">Esse objeto pode ser usado com `Receive-Job` e `Remove-Job` , assim como se você tivesse usado `Start-Job` para iniciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9be17-192">This object can be used with `Receive-Job` and `Remove-Job`, just as if you had used `Start-Job` to start the job.</span></span>

```powershell
$job = Get-Process -Name pwsh &
Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

```powershell
Remove-Job $job
```

<span data-ttu-id="9be17-193">O `&` operador background também é um terminador de instrução, assim como o e comercial do operador de controle do UNIX ( `&` ).</span><span class="sxs-lookup"><span data-stu-id="9be17-193">The `&` background operator is also a statement terminator, just like the UNIX control operator ampersand (`&`).</span></span> <span data-ttu-id="9be17-194">Isso permite que você invoque comandos adicionais após o `&` operador de segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9be17-194">This allows you to invoke additional commands after the `&` background operator.</span></span> <span data-ttu-id="9be17-195">O exemplo a seguir demonstra a invocação de comandos adicionais após o `&` operador de segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9be17-195">The following example demonstrates the invocation of additional commands after the `&` background operator.</span></span>

```powershell
$job = Get-Process -Name pwsh & Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

<span data-ttu-id="9be17-196">Isso é equivalente ao seguinte script:</span><span class="sxs-lookup"><span data-stu-id="9be17-196">This is equivalent to the following script:</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process -Name pwsh}
Receive-Job $job -Wait
```

<span data-ttu-id="9be17-197">Se você quiser executar vários comandos, cada um em seu próprio processo em segundo plano, mas tudo em uma linha, simplesmente coloque `&` entre e depois de cada um dos comandos.</span><span class="sxs-lookup"><span data-stu-id="9be17-197">If you want to run multiple commands, each in their own background process but all on one line, simply place `&` between and after each of the commands.</span></span>

```powershell
Get-Process -Name pwsh & Get-Service -Name BITS & Get-CimInstance -ClassName Win32_ComputerSystem &
```

<span data-ttu-id="9be17-198">Para obter mais informações sobre trabalhos do PowerShell, consulte [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-198">For more information on PowerShell jobs, see [about_Jobs](about_Jobs.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="9be17-199">Operador cast `[ ]`</span><span class="sxs-lookup"><span data-stu-id="9be17-199">Cast operator `[ ]`</span></span>

<span data-ttu-id="9be17-200">Converte ou limita objetos no tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="9be17-200">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="9be17-201">Se os objetos não puderem ser convertidos, o PowerShell gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="9be17-201">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="9be17-202">Uma conversão também pode ser executada quando uma variável é atribuída ao uso de [notação de conversão](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-202">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="9be17-203">Operador de vírgula `,`</span><span class="sxs-lookup"><span data-stu-id="9be17-203">Comma operator `,`</span></span>

<span data-ttu-id="9be17-204">Como um operador binário, a vírgula cria uma matriz ou acrescenta à matriz que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="9be17-204">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="9be17-205">No modo de expressão, como um operador unário, a vírgula cria uma matriz com apenas um membro.</span><span class="sxs-lookup"><span data-stu-id="9be17-205">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="9be17-206">Coloque a vírgula antes do membro.</span><span class="sxs-lookup"><span data-stu-id="9be17-206">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="9be17-207">Como `Write-Object` o espera um argumento, você deve colocar a expressão entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="9be17-207">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="9be17-208">Operador de fornecimento de ponto `.`</span><span class="sxs-lookup"><span data-stu-id="9be17-208">Dot sourcing operator `.`</span></span>

<span data-ttu-id="9be17-209">Executa um script no escopo atual para que quaisquer funções, aliases e variáveis que o script cria sejam adicionados ao escopo atual, substituindo os existentes.</span><span class="sxs-lookup"><span data-stu-id="9be17-209">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="9be17-210">Os parâmetros declarados pelo script se tornam variáveis.</span><span class="sxs-lookup"><span data-stu-id="9be17-210">Parameters declared by the script become variables.</span></span> <span data-ttu-id="9be17-211">Parâmetros para os quais nenhum valor foi fornecido se tornam variáveis sem valor.</span><span class="sxs-lookup"><span data-stu-id="9be17-211">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="9be17-212">No entanto, a variável automática `$args` é preservada.</span><span class="sxs-lookup"><span data-stu-id="9be17-212">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="9be17-213">O operador ponto de fornecimento é seguido por um espaço.</span><span class="sxs-lookup"><span data-stu-id="9be17-213">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="9be17-214">Use o espaço para distinguir o ponto do símbolo de ponto ( `.` ) que representa o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="9be17-214">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="9be17-215">No exemplo a seguir, o script Sample.ps1 no diretório atual é executado no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="9be17-215">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="9be17-216">Operador de formato `-f`</span><span class="sxs-lookup"><span data-stu-id="9be17-216">Format operator `-f`</span></span>

<span data-ttu-id="9be17-217">Formata cadeias de caracteres usando o método Format de objetos String.</span><span class="sxs-lookup"><span data-stu-id="9be17-217">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="9be17-218">Insira a cadeia de caracteres de formato no lado esquerdo do operador e os objetos a serem formatados no lado direito do operador.</span><span class="sxs-lookup"><span data-stu-id="9be17-218">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="9be17-219">Se você precisar manter as chaves ( `{}` ) na cadeia de caracteres formatada, poderá escapar delas dobrando as chaves.</span><span class="sxs-lookup"><span data-stu-id="9be17-219">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="9be17-220">Para obter mais informações, consulte o método [String. Format](/dotnet/api/system.string.format) e a [formatação composta](/dotnet/standard/base-types/composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="9be17-220">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="9be17-221">Operador de índice `[ ]`</span><span class="sxs-lookup"><span data-stu-id="9be17-221">Index operator `[ ]`</span></span>

<span data-ttu-id="9be17-222">Seleciona objetos de coleções indexadas, como matrizes e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="9be17-222">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="9be17-223">Os índices de matriz são baseados em zero, portanto, o primeiro objeto é indexado como `[0]` .</span><span class="sxs-lookup"><span data-stu-id="9be17-223">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="9be17-224">Para matrizes (somente), você também pode usar índices negativos para obter os últimos valores.</span><span class="sxs-lookup"><span data-stu-id="9be17-224">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="9be17-225">As tabelas de hash são indexadas por valor de chave.</span><span class="sxs-lookup"><span data-stu-id="9be17-225">Hash tables are indexed by key value.</span></span>

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

#### <a name="pipeline-operator-"></a><span data-ttu-id="9be17-226">Operador de pipeline `|`</span><span class="sxs-lookup"><span data-stu-id="9be17-226">Pipeline operator `|`</span></span>

<span data-ttu-id="9be17-227">Envia ("pipes") a saída do comando que o precede para o comando que o segue.</span><span class="sxs-lookup"><span data-stu-id="9be17-227">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="9be17-228">Quando a saída inclui mais de um objeto (uma "coleção"), o operador de pipeline envia os objetos um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9be17-228">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="pipeline-chain-operators--and-"></a><span data-ttu-id="9be17-229">Operadores de cadeia `&&` de pipeline e `||`</span><span class="sxs-lookup"><span data-stu-id="9be17-229">Pipeline chain operators `&&` and `||`</span></span>

<span data-ttu-id="9be17-230">Execute condicionalmente o pipeline do lado direito com base no sucesso do pipeline do lado esquerdo.</span><span class="sxs-lookup"><span data-stu-id="9be17-230">Conditionally execute the right-hand side pipeline based on the success of the left-hand side pipeline.</span></span>

```powershell
# If Get-Process successfully finds a process called notepad,
# Stop-Process -Name notepad is called
Get-Process notepad && Stop-Process -Name notepad
```

```powershell
# If npm install fails, the node_modules directory is removed
npm install || Remove-Item -Recurse ./node_modules
```

<span data-ttu-id="9be17-231">Para obter mais informações, consulte [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-231">For more information, see [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md).</span></span>

#### <a name="range-operator-"></a><span data-ttu-id="9be17-232">Operador de intervalo `..`</span><span class="sxs-lookup"><span data-stu-id="9be17-232">Range operator `..`</span></span>

<span data-ttu-id="9be17-233">Representa os inteiros sequenciais em uma matriz de inteiros, de acordo com um limite superior e inferior.</span><span class="sxs-lookup"><span data-stu-id="9be17-233">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="9be17-234">Você também pode criar intervalos na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="9be17-234">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

<span data-ttu-id="9be17-235">A partir do PowerShell 6, o operador Range funciona com **caracteres** , bem como **inteiros** .</span><span class="sxs-lookup"><span data-stu-id="9be17-235">Beginning in PowerShell 6, the range operator works with **Characters** as well as **Integers** .</span></span>

<span data-ttu-id="9be17-236">Para criar um intervalo de caracteres, coloque os caracteres de limite entre aspas.</span><span class="sxs-lookup"><span data-stu-id="9be17-236">To create a range of characters, enclose the boundary characters in quotes.</span></span>

```powershell
PS> 'a'..'f'
a
b
c
d
e
f
```

```powershell
PS> 'F'..'A'
F
E
D
C
B
A
```

#### <a name="member-access-operator-"></a><span data-ttu-id="9be17-237">Operador de acesso de membro `.`</span><span class="sxs-lookup"><span data-stu-id="9be17-237">Member access operator `.`</span></span>

<span data-ttu-id="9be17-238">Acessa as propriedades e os métodos de um objeto.</span><span class="sxs-lookup"><span data-stu-id="9be17-238">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="9be17-239">O nome do membro pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="9be17-239">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="9be17-240">Operador de membro estático `::`</span><span class="sxs-lookup"><span data-stu-id="9be17-240">Static member operator `::`</span></span>

<span data-ttu-id="9be17-241">Chama as propriedades e os métodos estáticos de uma classe .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9be17-241">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="9be17-242">Para localizar as propriedades e os métodos estáticos de um objeto, use o parâmetro static do `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9be17-242">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="9be17-243">O nome do membro pode ser uma expressão.</span><span class="sxs-lookup"><span data-stu-id="9be17-243">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

#### <a name="ternary-operator--if-true--if-false"></a><span data-ttu-id="9be17-244">Operador ternário `? <if-true> : <if-false>`</span><span class="sxs-lookup"><span data-stu-id="9be17-244">Ternary operator `? <if-true> : <if-false>`</span></span>

<span data-ttu-id="9be17-245">Você pode usar o operador ternário como uma substituição para a `if-else` instrução em casos condicionais simples.</span><span class="sxs-lookup"><span data-stu-id="9be17-245">You can use the ternary operator as a replacement for the `if-else` statement in simple conditional cases.</span></span>

<span data-ttu-id="9be17-246">Para obter mais informações, consulte [about_If](about_If.md).</span><span class="sxs-lookup"><span data-stu-id="9be17-246">For more information, see [about_If](about_If.md).</span></span>

#### <a name="null-coalescing-operator-"></a><span data-ttu-id="9be17-247">Operador de União nula `??`</span><span class="sxs-lookup"><span data-stu-id="9be17-247">Null-coalescing operator `??`</span></span>

<span data-ttu-id="9be17-248">O operador de avaliação de nulo `??` retorna o valor do seu operando esquerdo caso não seja nulo.</span><span class="sxs-lookup"><span data-stu-id="9be17-248">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null.</span></span> <span data-ttu-id="9be17-249">Caso contrário, ele avalia o operando do lado direito e retorna seu resultado.</span><span class="sxs-lookup"><span data-stu-id="9be17-249">Otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="9be17-250">O operador `??` não avaliará o operando do lado direito se o operando esquerdo for avaliado como não nulo.</span><span class="sxs-lookup"><span data-stu-id="9be17-250">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ?? 100
```

```Output
100
```

<span data-ttu-id="9be17-251">No exemplo a seguir, o operando à direita não será avaliado.</span><span class="sxs-lookup"><span data-stu-id="9be17-251">In the following example, the right-hand operand won't be evaluated.</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-coalescing-assignment-operator-"></a><span data-ttu-id="9be17-252">Operador de atribuição de União nula `??=`</span><span class="sxs-lookup"><span data-stu-id="9be17-252">Null-coalescing assignment operator `??=`</span></span>

<span data-ttu-id="9be17-253">O operador de atribuição de União nula `??=` atribui o valor do seu operando à direita para seu operando à esquerda somente se o operando esquerdo for avaliado como nulo.</span><span class="sxs-lookup"><span data-stu-id="9be17-253">The null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null.</span></span> <span data-ttu-id="9be17-254">O operador `??=` não avaliará o operando do lado direito se o operando esquerdo for avaliado como não nulo.</span><span class="sxs-lookup"><span data-stu-id="9be17-254">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ??= 100
$x
```

```Output
100
```

<span data-ttu-id="9be17-255">No exemplo a seguir, o operando à direita não será avaliado.</span><span class="sxs-lookup"><span data-stu-id="9be17-255">In the following example, the right-hand operand won't be evaluated.</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-conditional-operators--and-"></a><span data-ttu-id="9be17-256">Operadores condicionais nulos `?.` e `?[]`</span><span class="sxs-lookup"><span data-stu-id="9be17-256">Null-conditional operators `?.` and `?[]`</span></span>

> [!NOTE]
> <span data-ttu-id="9be17-257">Esse recurso foi movido do experimental para o básico no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="9be17-257">This feature was moved from experimental to mainstream in PowerShell 7.1.</span></span>

<span data-ttu-id="9be17-258">Um operador NULL-Conditional aplica um acesso de membro, `?.` , ou acesso de elemento, `?[]` , operação para seu operando somente se esse operando for avaliado como não nulo; caso contrário, retornará NULL.</span><span class="sxs-lookup"><span data-stu-id="9be17-258">A null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns null.</span></span>

<span data-ttu-id="9be17-259">Como o PowerShell permite que `?` faça parte do nome da variável, é necessária uma especificação formal do nome da variável para usar esses operadores.</span><span class="sxs-lookup"><span data-stu-id="9be17-259">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="9be17-260">Portanto, é necessário usar `{}` em torno dos nomes de variáveis, como `${a}` ou quando `?` faz parte do nome da variável `${a?}`.</span><span class="sxs-lookup"><span data-stu-id="9be17-260">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>

<span data-ttu-id="9be17-261">No exemplo a seguir, o valor de **propName** é retornado.</span><span class="sxs-lookup"><span data-stu-id="9be17-261">In the following example, the value of **PropName** is returned.</span></span>

```powershell
$a = @{ PropName = 100 }
${a}?.PropName
```

```Output
100
```

<span data-ttu-id="9be17-262">O exemplo a seguir retornará NULL, sem tentar acessar o nome do membro **propName** .</span><span class="sxs-lookup"><span data-stu-id="9be17-262">The following example will return null, without trying to access the member name **PropName** .</span></span>

```powershell
$a = $null
${a}?.PropName
```

<span data-ttu-id="9be17-263">Da mesma forma, o valor do elemento será retornado.</span><span class="sxs-lookup"><span data-stu-id="9be17-263">Similarly, the value of the element will be returned.</span></span>

```powershell
$a = 1..10
${a}?[0]
```

```Output
1
```

<span data-ttu-id="9be17-264">E quando o operando é nulo, o elemento não é acessado e nulo é retornado.</span><span class="sxs-lookup"><span data-stu-id="9be17-264">And when the operand is null, the element isn't accessed and null is returned.</span></span>

```PowerShell
$a = $null
${a}?[0]
```

## <a name="see-also"></a><span data-ttu-id="9be17-265">Confira também</span><span class="sxs-lookup"><span data-stu-id="9be17-265">See also</span></span>

[<span data-ttu-id="9be17-266">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="9be17-266">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="9be17-267">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="9be17-267">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="9be17-268">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="9be17-268">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="9be17-269">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="9be17-269">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="9be17-270">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="9be17-270">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="9be17-271">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="9be17-271">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="9be17-272">about_Pipeline_Chain_Operators</span><span class="sxs-lookup"><span data-stu-id="9be17-272">about_Pipeline_Chain_Operators</span></span>](about_Pipeline_Chain_Operators.md)

[<span data-ttu-id="9be17-273">about_Split</span><span class="sxs-lookup"><span data-stu-id="9be17-273">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="9be17-274">about_Join</span><span class="sxs-lookup"><span data-stu-id="9be17-274">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="9be17-275">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="9be17-275">about_Redirection</span></span>](about_Redirection.md)
