---
description: Descreve uma palavra-chave que manipula um erro de encerramento.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_trap?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Trap
ms.openlocfilehash: 1e5541ce45e4dea8ebe87aa76a984f7d3de8c51f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195464"
---
# <a name="about-trap"></a><span data-ttu-id="055e4-104">Sobre interceptação</span><span class="sxs-lookup"><span data-stu-id="055e4-104">About Trap</span></span>

## <a name="short-description"></a><span data-ttu-id="055e4-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="055e4-105">Short description</span></span>

<span data-ttu-id="055e4-106">Descreve uma palavra-chave que manipula um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="055e4-106">Describes a keyword that handles a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="055e4-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="055e4-107">Long description</span></span>

<span data-ttu-id="055e4-108">Um erro de encerramento interrompe a execução de uma instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-108">A terminating error stops a statement from running.</span></span> <span data-ttu-id="055e4-109">Se o PowerShell não tratar um erro de encerramento de alguma forma, o PowerShell também interromperá a execução da função ou do script no pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="055e4-109">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script in the current pipeline.</span></span> <span data-ttu-id="055e4-110">Em outras linguagens, como C#, os erros de encerramento são conhecidos como exceções.</span><span class="sxs-lookup"><span data-stu-id="055e4-110">In other languages, such as C#, terminating errors are known as exceptions.</span></span>

<span data-ttu-id="055e4-111">A `trap` palavra-chave especifica uma lista de instruções a serem executadas quando ocorre um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="055e4-111">The `trap` keyword specifies a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="055e4-112">`trap` as instruções manipulam os erros de encerramento das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="055e4-112">`trap` statements handle the terminating errors in the following ways:</span></span>

- <span data-ttu-id="055e4-113">Exiba o erro depois de processar o `trap` bloco de instrução e continuar a execução do script ou da função que contém o `trap` .</span><span class="sxs-lookup"><span data-stu-id="055e4-113">Display the error after processing the `trap` statement block and continuing execution of the script or function containing the `trap`.</span></span> <span data-ttu-id="055e4-114">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="055e4-114">This is the default behavior.</span></span>

- <span data-ttu-id="055e4-115">Exiba o erro e anule a execução do script ou da função que contém o `trap` usando `break` na `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-115">Display the error and abort execution of the script or function containing the `trap` using `break` in the `trap` statement.</span></span>

- <span data-ttu-id="055e4-116">Silenciar o erro, mas continuar a execução do script ou da função que contém o usando `trap` `continue` na `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-116">Silence the error, but continue execution of the script or function containing the `trap` by using `continue` in the `trap` statement.</span></span>

<span data-ttu-id="055e4-117">A lista de instruções do `trap` pode incluir várias condições ou chamadas de função.</span><span class="sxs-lookup"><span data-stu-id="055e4-117">The statement list of the `trap` can include multiple conditions or function calls.</span></span> <span data-ttu-id="055e4-118">Um `trap` pode gravar logs, condições de teste ou até mesmo executar outro programa.</span><span class="sxs-lookup"><span data-stu-id="055e4-118">A `trap` can write logs, test conditions, or even run another program.</span></span>

### <a name="syntax"></a><span data-ttu-id="055e4-119">Syntax</span><span class="sxs-lookup"><span data-stu-id="055e4-119">Syntax</span></span>

<span data-ttu-id="055e4-120">A `trap` instrução tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="055e4-120">The `trap` statement has the following syntax:</span></span>

```powershell
trap [[<error type>]] {<statement list>}
```

<span data-ttu-id="055e4-121">A `trap` instrução inclui uma lista de instruções a serem executadas quando ocorre um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="055e4-121">The `trap` statement includes a list of statements to run when a terminating error occurs.</span></span> <span data-ttu-id="055e4-122">Uma `trap` instrução consiste na `trap` palavra-chave, opcionalmente seguida por uma expressão de tipo, e o bloco de instrução que contém a lista de instruções a serem executadas quando um erro é interceptado.</span><span class="sxs-lookup"><span data-stu-id="055e4-122">A `trap` statement consists of the `trap` keyword, optionally followed by a type expression, and the statement block containing the list of statements to run when an error is trapped.</span></span> <span data-ttu-id="055e4-123">A expressão de tipo restringe os tipos de erros que o `trap` captura.</span><span class="sxs-lookup"><span data-stu-id="055e4-123">The type expression refines the types of errors the `trap` catches.</span></span>

<span data-ttu-id="055e4-124">Um script ou comando pode ter várias `trap` instruções.</span><span class="sxs-lookup"><span data-stu-id="055e4-124">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="055e4-125">`trap` as instruções podem aparecer em qualquer lugar no script ou comando.</span><span class="sxs-lookup"><span data-stu-id="055e4-125">`trap` statements can appear anywhere in the script or command.</span></span>

### <a name="trapping-all-terminating-errors"></a><span data-ttu-id="055e4-126">Interceptando todos os erros de encerramento</span><span class="sxs-lookup"><span data-stu-id="055e4-126">Trapping all terminating errors</span></span>

<span data-ttu-id="055e4-127">Quando ocorre um erro de encerramento que não é tratado de outra maneira em um script ou comando, o PowerShell verifica uma `trap` instrução que manipula o erro.</span><span class="sxs-lookup"><span data-stu-id="055e4-127">When a terminating error occurs that is not handled in another way in a script or command, PowerShell checks for a `trap` statement that handles the error.</span></span> <span data-ttu-id="055e4-128">Se uma `trap` instrução estiver presente, o PowerShell continuará executando o script ou o comando na `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-128">If a `trap` statement is present, PowerShell continues running the script or command in the `trap` statement.</span></span>

<span data-ttu-id="055e4-129">O exemplo a seguir é uma instrução muito simples `trap` :</span><span class="sxs-lookup"><span data-stu-id="055e4-129">The following example is a very simple `trap` statement:</span></span>

```powershell
trap {"Error found."}
```

<span data-ttu-id="055e4-130">Essa `trap` instrução intercepta qualquer erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="055e4-130">This `trap` statement traps any terminating error.</span></span>

<span data-ttu-id="055e4-131">No exemplo a seguir, a função inclui uma cadeia de caracteres de sentido que causa um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="055e4-131">In the following example, the function includes a nonsense string that causes a runtime error.</span></span>

```powershell
function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="055e4-132">A execução dessa função retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="055e4-132">Running this function returns the following:</span></span>

```Output
Error found.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="055e4-133">O exemplo a seguir inclui uma `trap` instrução que exibe o erro usando a `$_` variável automática:</span><span class="sxs-lookup"><span data-stu-id="055e4-133">The following example includes a `trap` statement that displays the error by using the `$_` automatic variable:</span></span>

```powershell
function TrapTest {
    trap {"Error found: $_"}
    nonsenseString
}

TrapTest
```

<span data-ttu-id="055e4-134">A execução desta versão da função retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="055e4-134">Running this version of the function returns the following:</span></span>

```Output
Error found: The term 'nonsenseString' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the
name, or if a path was included, verify that the path is correct and try again.
nonsenseString:
Line |
   3 |      nonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

> [!IMPORTANT]
> <span data-ttu-id="055e4-135">`trap` as instruções podem ser definidas em qualquer lugar dentro de um determinado escopo, mas sempre se aplicam a todas as instruções nesse escopo.</span><span class="sxs-lookup"><span data-stu-id="055e4-135">`trap` statements may be defined anywhere within a given scope, but always apply to all statements in that scope.</span></span> <span data-ttu-id="055e4-136">Em tempo de execução, `trap` as instruções em um bloco são definidas antes de qualquer outra instrução ser executada.</span><span class="sxs-lookup"><span data-stu-id="055e4-136">At runtime, `trap` statements in a block are defined before any other statements are executed.</span></span> <span data-ttu-id="055e4-137">No JavaScript, isso é conhecido como [guindaste](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span><span class="sxs-lookup"><span data-stu-id="055e4-137">In JavaScript, this is known as [hoisting](https://wikipedia.org/wiki/JavaScript_syntax#hoisting).</span></span> <span data-ttu-id="055e4-138">Isso significa que `trap` as instruções se aplicam a todas as instruções nesse bloco, mesmo que a execução não tenha sido avançada após o ponto no qual elas são definidas.</span><span class="sxs-lookup"><span data-stu-id="055e4-138">This means that `trap` statements apply to all statements in that block even if execution has not advanced past the point at which they are defined.</span></span> <span data-ttu-id="055e4-139">Por exemplo, definir um `trap` no final de um script e lançar um erro na primeira instrução ainda dispara isso `trap` .</span><span class="sxs-lookup"><span data-stu-id="055e4-139">For example, defining a `trap` at the end of a script and throwing an error in the first statement still triggers that `trap`.</span></span>

### <a name="trapping-specific-errors"></a><span data-ttu-id="055e4-140">Interceptando erros específicos</span><span class="sxs-lookup"><span data-stu-id="055e4-140">Trapping specific errors</span></span>

<span data-ttu-id="055e4-141">Um script ou comando pode ter várias `trap` instruções.</span><span class="sxs-lookup"><span data-stu-id="055e4-141">A script or command can have multiple `trap` statements.</span></span> <span data-ttu-id="055e4-142">Um `trap` pode ser definido para lidar com erros específicos.</span><span class="sxs-lookup"><span data-stu-id="055e4-142">A `trap` can be defined to handle specific errors.</span></span>

<span data-ttu-id="055e4-143">O exemplo a seguir é uma `trap` instrução que intercepta o erro específico **CommandNotFoundException** :</span><span class="sxs-lookup"><span data-stu-id="055e4-143">The following example is a `trap` statement that traps the specific error **CommandNotFoundException** :</span></span>

```powershell
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
```

<span data-ttu-id="055e4-144">Quando uma função ou script encontra uma cadeia de caracteres que não corresponde a um comando conhecido, essa `trap` instrução exibe a cadeia de caracteres "erro de comando interceptado".</span><span class="sxs-lookup"><span data-stu-id="055e4-144">When a function or script encounters a string that does not match a known command, this `trap` statement displays the "Command error trapped" string.</span></span>
<span data-ttu-id="055e4-145">Depois de executar a `trap` lista de instruções, o PowerShell grava o objeto de erro no fluxo de erros e, em seguida, continua o script.</span><span class="sxs-lookup"><span data-stu-id="055e4-145">After running the `trap` statement list, PowerShell writes the error object to the error stream and then continues the script.</span></span>

<span data-ttu-id="055e4-146">O PowerShell usa tipos de exceção .NET.</span><span class="sxs-lookup"><span data-stu-id="055e4-146">PowerShell uses .NET exception types.</span></span> <span data-ttu-id="055e4-147">O exemplo a seguir especifica o tipo de erro **System. Exception** :</span><span class="sxs-lookup"><span data-stu-id="055e4-147">The following example specifies the **System.Exception** error type:</span></span>

```powershell
trap [System.Exception] {"An error trapped"}
```

<span data-ttu-id="055e4-148">O tipo de erro **CommandNotFoundException** herda do tipo **System. Exception** .</span><span class="sxs-lookup"><span data-stu-id="055e4-148">The **CommandNotFoundException** error type inherits from the **System.Exception** type.</span></span> <span data-ttu-id="055e4-149">Essa instrução intercepta um erro que é criado por um comando desconhecido.</span><span class="sxs-lookup"><span data-stu-id="055e4-149">This statement traps an error that is created by an unknown command.</span></span> <span data-ttu-id="055e4-150">Ele também intercepta outros tipos de erro.</span><span class="sxs-lookup"><span data-stu-id="055e4-150">It also traps other error types.</span></span>

<span data-ttu-id="055e4-151">Você pode ter mais de uma `trap` instrução em um script.</span><span class="sxs-lookup"><span data-stu-id="055e4-151">You can have more than one `trap` statement in a script.</span></span> <span data-ttu-id="055e4-152">Cada tipo de erro pode ser interceptado por apenas uma `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-152">Each error type can be trapped by only one `trap` statement.</span></span> <span data-ttu-id="055e4-153">Quando ocorre um erro de encerramento, o PowerShell procura o `trap` com a correspondência mais específica, começando no escopo atual de execução.</span><span class="sxs-lookup"><span data-stu-id="055e4-153">When a terminating error occurs, PowerShell searches for the `trap` with the most specific match, starting in the current scope of execution.</span></span>

<span data-ttu-id="055e4-154">O exemplo de script a seguir contém um erro.</span><span class="sxs-lookup"><span data-stu-id="055e4-154">The following script example contains an error.</span></span> <span data-ttu-id="055e4-155">O script inclui uma `trap` instrução geral que intercepta qualquer erro de encerramento e uma `trap` instrução específica que especifica o tipo **CommandNotFoundException** .</span><span class="sxs-lookup"><span data-stu-id="055e4-155">The script includes a general `trap` statement that traps any terminating error and a specific `trap` statement that specifies the **CommandNotFoundException** type.</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException] {
  "Command error trapped"
}
nonsenseString
```

<span data-ttu-id="055e4-156">A execução desse script produz o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="055e4-156">Running this script produces the following result:</span></span>

```Output
Command error trapped
nonsenseString:
Line |
   5 |  nonsenseString
     |  ~~~~~~~~~~~~~~
     | The term 'nonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="055e4-157">Como o PowerShell não reconhece "não-Sense" como um cmdlet ou outro item, ele retorna um erro **CommandNotFoundException** .</span><span class="sxs-lookup"><span data-stu-id="055e4-157">Because PowerShell does not recognize "nonsenseString" as a cmdlet or other item, it returns a **CommandNotFoundException** error.</span></span> <span data-ttu-id="055e4-158">Esse erro de encerramento é interceptado pela `trap` instrução específica.</span><span class="sxs-lookup"><span data-stu-id="055e4-158">This terminating error is trapped by the specific `trap` statement.</span></span>

<span data-ttu-id="055e4-159">O exemplo de script a seguir contém as mesmas `trap` instruções com um erro diferente:</span><span class="sxs-lookup"><span data-stu-id="055e4-159">The following script example contains the same `trap` statements with a different error:</span></span>

```powershell
trap {"Other terminating error trapped" }
trap [System.Management.Automation.CommandNotFoundException]
    {"Command error trapped"}
1/$null
```

<span data-ttu-id="055e4-160">A execução desse script produz o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="055e4-160">Running this script produces the following result:</span></span>

```Output
Other terminating error trapped
RuntimeException:
Line |
   4 |  1/$null
     |  ~~~~~~~
     | Attempted to divide by zero.
```

<span data-ttu-id="055e4-161">A tentativa de dividir por zero não cria um erro **CommandNotFoundException** .</span><span class="sxs-lookup"><span data-stu-id="055e4-161">The attempt to divide by zero does not create a **CommandNotFoundException** error.</span></span> <span data-ttu-id="055e4-162">Em vez disso, esse erro é interceptado pela outra `trap` instrução, que intercepta qualquer erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="055e4-162">Instead, that error is trapped by the other `trap` statement, which traps any terminating error.</span></span>

### <a name="trapping-errors-and-scope"></a><span data-ttu-id="055e4-163">Interceptando erros e escopo</span><span class="sxs-lookup"><span data-stu-id="055e4-163">Trapping errors and scope</span></span>

<span data-ttu-id="055e4-164">Se um erro de encerramento ocorrer no mesmo escopo que a `trap` instrução, o PowerShell executará a lista de instruções definidas pelo `trap` .</span><span class="sxs-lookup"><span data-stu-id="055e4-164">If a terminating error occurs in the same scope as the `trap` statement, PowerShell runs the list of statements defined by the `trap`.</span></span> <span data-ttu-id="055e4-165">A execução continua na instrução após o erro.</span><span class="sxs-lookup"><span data-stu-id="055e4-165">Execution continues at the statement after the error.</span></span> <span data-ttu-id="055e4-166">Se a `trap` instrução estiver em um escopo diferente do erro, a execução continuará na próxima instrução que está no mesmo escopo que a `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-166">If the `trap` statement is in a different scope from the error, execution continues at the next statement that is in the same scope as the `trap` statement.</span></span>

<span data-ttu-id="055e4-167">Por exemplo, se ocorrer um erro em uma função e a `trap` instrução estiver na função, o script continuará na próxima instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-167">For example, if an error occurs in a function, and the `trap` statement is in the function, the script continues at the next statement.</span></span> <span data-ttu-id="055e4-168">O script a seguir contém um erro e uma `trap` instrução:</span><span class="sxs-lookup"><span data-stu-id="055e4-168">The following script contains an error and a `trap` statement:</span></span>

```powershell
function function1 {
    trap { "An error: " }
    NonsenseString
    "function1 was completed"
}

function1
```

<span data-ttu-id="055e4-169">A execução desse script produz o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="055e4-169">Running this script produces the following result:</span></span>

```Output
An error:
NonsenseString:
Line |
   3 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
function1 was completed
```

<span data-ttu-id="055e4-170">A `trap` instrução na função intercepta o erro.</span><span class="sxs-lookup"><span data-stu-id="055e4-170">The `trap` statement in the function traps the error.</span></span> <span data-ttu-id="055e4-171">Depois de exibir a mensagem, o PowerShell retoma a execução da função.</span><span class="sxs-lookup"><span data-stu-id="055e4-171">After displaying the message, PowerShell resumes running the function.</span></span> <span data-ttu-id="055e4-172">Observe que `Function1` foi concluída.</span><span class="sxs-lookup"><span data-stu-id="055e4-172">Note that `Function1` was completed.</span></span>

<span data-ttu-id="055e4-173">Compare isso com o exemplo a seguir, que tem o mesmo erro e `trap` instrução.</span><span class="sxs-lookup"><span data-stu-id="055e4-173">Compare this with the following example, which has the same error and `trap` statement.</span></span> <span data-ttu-id="055e4-174">Neste exemplo, a `trap` instrução ocorre fora da função:</span><span class="sxs-lookup"><span data-stu-id="055e4-174">In this example, the `trap` statement occurs outside the function:</span></span>

```powershell
function function2 {
    NonsenseString
    "function2 was completed"
}

trap { "An error: " }

function2
```

<span data-ttu-id="055e4-175">A execução da `Function2` função produz o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="055e4-175">Running the `Function2` function produces the following result:</span></span>

```Output
An error:
NonsenseString:
Line |
   2 |      NonsenseString
     |      ~~~~~~~~~~~~~~
     | The term 'NonsenseString' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="055e4-176">Neste exemplo, o comando "function2 foi concluído" não foi executado.</span><span class="sxs-lookup"><span data-stu-id="055e4-176">In this example, the "function2 was completed" command was not run.</span></span> <span data-ttu-id="055e4-177">Em ambos os exemplos, o erro de encerramento ocorre dentro da função.</span><span class="sxs-lookup"><span data-stu-id="055e4-177">In both examples, the terminating error occurs within the function.</span></span> <span data-ttu-id="055e4-178">Neste exemplo, no entanto, a `trap` instrução está fora da função.</span><span class="sxs-lookup"><span data-stu-id="055e4-178">In this example, however, the `trap` statement is outside the function.</span></span> <span data-ttu-id="055e4-179">O PowerShell não volta à função depois que a `trap` instrução é executada.</span><span class="sxs-lookup"><span data-stu-id="055e4-179">PowerShell does not go back into the function after the `trap` statement runs.</span></span>

> [!CAUTION]
> <span data-ttu-id="055e4-180">Quando várias interceptações são definidas para a mesma condição de erro, o primeiro `trap` definido lexicalmente (mais alto no escopo) é usado.</span><span class="sxs-lookup"><span data-stu-id="055e4-180">When multiple traps are defined for the same error condition, the first `trap` defined lexically (highest in the scope) is used.</span></span>

<span data-ttu-id="055e4-181">No exemplo a seguir, somente o `trap` com "Opa 1" é executado.</span><span class="sxs-lookup"><span data-stu-id="055e4-181">In the following example, only the `trap` with "whoops 1" is run.</span></span>

```powershell
Remove-Item -ErrorAction Stop ThisFileDoesNotExist
trap { "whoops 1"; continue }
trap { "whoops 2"; continue }
```

> [!IMPORTANT]
> <span data-ttu-id="055e4-182">Uma instrução de interceptação é delimitada para onde ela é compilada.</span><span class="sxs-lookup"><span data-stu-id="055e4-182">A Trap statement is scoped to where it compiles.</span></span> <span data-ttu-id="055e4-183">Se você tiver uma `trap` instrução dentro de um script de origem de função ou ponto, quando o script de função ou ponto tiver sido encerrado, todas as `trap` instruções dentro serão removidas.</span><span class="sxs-lookup"><span data-stu-id="055e4-183">If you have a `trap` statement inside a function or dot sourced script, when the function or dot sourced script exits, all `trap` statements inside are removed.</span></span>

### <a name="using-the-break-and-continue-keywords"></a><span data-ttu-id="055e4-184">Usando as palavras-chave break e continue</span><span class="sxs-lookup"><span data-stu-id="055e4-184">Using the break and continue keywords</span></span>

<span data-ttu-id="055e4-185">Você pode usar as `break` `continue` palavras-chave e em uma `trap` instrução para determinar se um script ou comando continua a ser executado após um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="055e4-185">You can use the `break` and `continue` keywords in a `trap` statement to determine whether a script or command continues to run after a terminating error.</span></span>

<span data-ttu-id="055e4-186">Se você incluir uma `break` instrução em uma `trap` lista de instruções, o PowerShell interromperá a função ou o script.</span><span class="sxs-lookup"><span data-stu-id="055e4-186">If you include a `break` statement in a `trap` statement list, PowerShell stops the function or script.</span></span> <span data-ttu-id="055e4-187">A seguinte função de exemplo usa a `break` palavra-chave em uma `trap` instrução:</span><span class="sxs-lookup"><span data-stu-id="055e4-187">The following sample function uses the `break` keyword in a `trap` statement:</span></span>

```powershell
function break_example {
    trap {
        "Error trapped"
        break
    }
    1/$null
    "Function completed."
}

break_example
```

```Output
Error trapped
ParentContainsErrorRecordException:
Line |
   6 |      1/$null
     |      ~~~~~~~
     | Attempted to divide by zero.
```

<span data-ttu-id="055e4-188">Como a `trap` instrução incluía a `break` palavra-chave, a função não continua a ser executada e a linha "função concluída" não é executada.</span><span class="sxs-lookup"><span data-stu-id="055e4-188">Because the `trap` statement included the `break` keyword, the function does not continue to run, and the "Function completed" line is not run.</span></span>

<span data-ttu-id="055e4-189">Se você incluir uma `continue` palavra-chave em uma `trap` instrução, o PowerShell será retomado após a instrução que causou o erro, assim como faria sem `break` ou `continue` .</span><span class="sxs-lookup"><span data-stu-id="055e4-189">If you include a `continue` keyword in a `trap` statement, PowerShell resumes after the statement that caused the error, just as it would without `break` or `continue`.</span></span> <span data-ttu-id="055e4-190">Com a `continue` palavra-chave, no entanto, o PowerShell não grava um erro no fluxo de erros.</span><span class="sxs-lookup"><span data-stu-id="055e4-190">With the `continue` keyword, however, PowerShell does not write an error to the error stream.</span></span>

<span data-ttu-id="055e4-191">A seguinte função de exemplo usa a `continue` palavra-chave em uma `trap` instrução:</span><span class="sxs-lookup"><span data-stu-id="055e4-191">The following sample function uses the `continue` keyword in a `trap` statement:</span></span>

```powershell
function continue_example {
    trap {
        "Error trapped"
        continue
    }
    1/$null
    "Function completed."
}

continue_example
```

```Output
Error trapped
Function completed.
```

<span data-ttu-id="055e4-192">A função é retomada depois que o erro é interceptado e a instrução "função concluída" é executada.</span><span class="sxs-lookup"><span data-stu-id="055e4-192">The function resumes after the error is trapped, and the "Function completed" statement runs.</span></span> <span data-ttu-id="055e4-193">Nenhum erro é gravado no fluxo de erro.</span><span class="sxs-lookup"><span data-stu-id="055e4-193">No error is written to the error stream.</span></span>

## <a name="notes"></a><span data-ttu-id="055e4-194">Observações</span><span class="sxs-lookup"><span data-stu-id="055e4-194">Notes</span></span>

<span data-ttu-id="055e4-195">`trap` as instruções fornecem uma maneira simples de garantir amplamente a manipulação de todos os erros de encerramento dentro de um escopo.</span><span class="sxs-lookup"><span data-stu-id="055e4-195">`trap` statements provide a simple way to broadly ensure all terminating errors within a scope are handled.</span></span> <span data-ttu-id="055e4-196">Para tratamento de erros mais refinado, use `try` / `catch` blocos em que as interceptações são definidas usando `catch` instruções.</span><span class="sxs-lookup"><span data-stu-id="055e4-196">For more finer-grained error handling, use `try`/`catch` blocks where traps are defined using `catch` statements.</span></span> <span data-ttu-id="055e4-197">As `catch` instruções se aplicam somente ao código dentro da `try` instrução associada.</span><span class="sxs-lookup"><span data-stu-id="055e4-197">The `catch` statements only apply to the code inside the associated `try` statement.</span></span> <span data-ttu-id="055e4-198">Para obter mais informações, consulte [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span><span class="sxs-lookup"><span data-stu-id="055e4-198">For more information, see [about_Try_Catch_Finally](about_Try_Catch_Finally.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="055e4-199">Confira também</span><span class="sxs-lookup"><span data-stu-id="055e4-199">See also</span></span>

[<span data-ttu-id="055e4-200">about_Break</span><span class="sxs-lookup"><span data-stu-id="055e4-200">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="055e4-201">about_Continue</span><span class="sxs-lookup"><span data-stu-id="055e4-201">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="055e4-202">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="055e4-202">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="055e4-203">about_Throw</span><span class="sxs-lookup"><span data-stu-id="055e4-203">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="055e4-204">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="055e4-204">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
