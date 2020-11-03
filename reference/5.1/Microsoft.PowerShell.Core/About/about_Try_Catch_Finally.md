---
description: Descreve como usar os `Try` blocos, `Catch` e `Finally` para lidar com erros de encerramento.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_try_catch_finally?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Try_Catch_Finally
ms.openlocfilehash: 4cb392df950184feeee1fe2e3567004b94d14b36
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195953"
---
# <a name="about-try-catch-finally"></a><span data-ttu-id="a1172-104">Sobre try catch finalmente</span><span class="sxs-lookup"><span data-stu-id="a1172-104">About Try Catch Finally</span></span>

## <a name="short-description"></a><span data-ttu-id="a1172-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="a1172-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="a1172-106">Descreve como usar os `Try` blocos, `Catch` e `Finally` para lidar com erros de encerramento.</span><span class="sxs-lookup"><span data-stu-id="a1172-106">Describes how to use the `Try`, `Catch`, and `Finally` blocks to handle terminating errors.</span></span>

## <a name="long-description"></a><span data-ttu-id="a1172-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="a1172-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="a1172-108">Use `Try` os `Catch` blocos, e `Finally` para responder ou manipular erros de encerramento em scripts.</span><span class="sxs-lookup"><span data-stu-id="a1172-108">Use `Try`, `Catch`, and `Finally` blocks to respond to or handle terminating errors in scripts.</span></span> <span data-ttu-id="a1172-109">A `Trap` instrução também pode ser usada para lidar com erros de encerramento em scripts.</span><span class="sxs-lookup"><span data-stu-id="a1172-109">The `Trap` statement can also be used to handle terminating errors in scripts.</span></span> <span data-ttu-id="a1172-110">Para obter mais informações, consulte [about_Trap](about_Trap.md).</span><span class="sxs-lookup"><span data-stu-id="a1172-110">For more information, see [about_Trap](about_Trap.md).</span></span>

<span data-ttu-id="a1172-111">Um erro de encerramento interrompe a execução de uma instrução.</span><span class="sxs-lookup"><span data-stu-id="a1172-111">A terminating error stops a statement from running.</span></span> <span data-ttu-id="a1172-112">Se o PowerShell não tratar um erro de encerramento de alguma forma, o PowerShell também interromperá a execução da função ou do script usando o pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="a1172-112">If PowerShell does not handle a terminating error in some way, PowerShell also stops running the function or script using the current pipeline.</span></span> <span data-ttu-id="a1172-113">Em outras linguagens, como C \# , os erros de encerramento são chamados de exceções.</span><span class="sxs-lookup"><span data-stu-id="a1172-113">In other languages, such as C\#, terminating errors are referred to as exceptions.</span></span>

<span data-ttu-id="a1172-114">Use o `Try` bloco para definir uma seção de um script no qual você deseja que o PowerShell monitore os erros.</span><span class="sxs-lookup"><span data-stu-id="a1172-114">Use the `Try` block to define a section of a script in which you want PowerShell to monitor for errors.</span></span> <span data-ttu-id="a1172-115">Quando ocorre um erro dentro do `Try` bloco, o erro é salvo primeiro na `$Error` variável automática.</span><span class="sxs-lookup"><span data-stu-id="a1172-115">When an error occurs within the `Try` block, the error is first saved to the `$Error` automatic variable.</span></span> <span data-ttu-id="a1172-116">Em seguida, o PowerShell procura um `Catch` bloco para manipular o erro.</span><span class="sxs-lookup"><span data-stu-id="a1172-116">PowerShell then searches for a `Catch` block to handle the error.</span></span> <span data-ttu-id="a1172-117">Se a `Try` instrução não tiver um bloco correspondente `Catch` , o PowerShell continuará procurando um `Catch` bloco ou uma `Trap` instrução apropriada nos escopos pai.</span><span class="sxs-lookup"><span data-stu-id="a1172-117">If the `Try` statement does not have a matching `Catch` block, PowerShell continues to search for an appropriate `Catch` block or `Trap` statement in the parent scopes.</span></span> <span data-ttu-id="a1172-118">Depois `Catch` que um bloco for concluído ou se nenhum `Catch` bloco ou `Trap` instrução apropriado for encontrado, o `Finally` bloco será executado.</span><span class="sxs-lookup"><span data-stu-id="a1172-118">After a `Catch` block is completed or if no appropriate `Catch` block or `Trap` statement is found, the `Finally` block is run.</span></span> <span data-ttu-id="a1172-119">Se o erro não puder ser tratado, o erro será gravado no fluxo de erro.</span><span class="sxs-lookup"><span data-stu-id="a1172-119">If the error cannot be handled, the error is written to the error stream.</span></span>

<span data-ttu-id="a1172-120">Um `Catch` bloco pode incluir comandos para acompanhar o erro ou para recuperar o fluxo esperado do script.</span><span class="sxs-lookup"><span data-stu-id="a1172-120">A `Catch` block can include commands for tracking the error or for recovering the expected flow of the script.</span></span> <span data-ttu-id="a1172-121">Um `Catch` bloco pode especificar quais tipos de erro ele captura.</span><span class="sxs-lookup"><span data-stu-id="a1172-121">A `Catch` block can specify which error types it catches.</span></span> <span data-ttu-id="a1172-122">Uma `Try` instrução pode incluir vários `Catch` blocos para diferentes tipos de erros.</span><span class="sxs-lookup"><span data-stu-id="a1172-122">A `Try` statement can include multiple `Catch` blocks for different kinds of errors.</span></span>

<span data-ttu-id="a1172-123">Um `Finally` bloco pode ser usado para liberar todos os recursos que não são mais necessários para o seu script.</span><span class="sxs-lookup"><span data-stu-id="a1172-123">A `Finally` block can be used to free any resources that are no longer needed by your script.</span></span>

<span data-ttu-id="a1172-124">`Try`, `Catch` e se `Finally` assemelham às `Try` `Catch` `Finally` palavras-chave, e usadas na \# linguagem de programação C.</span><span class="sxs-lookup"><span data-stu-id="a1172-124">`Try`, `Catch`, and `Finally` resemble the `Try`, `Catch`, and `Finally` keywords used in the C\# programming language.</span></span>

### <a name="syntax"></a><span data-ttu-id="a1172-125">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1172-125">SYNTAX</span></span>

<span data-ttu-id="a1172-126">Uma `Try` instrução contém um `Try` bloco, zero ou mais `Catch` blocos e zero ou um `Finally` bloco.</span><span class="sxs-lookup"><span data-stu-id="a1172-126">A `Try` statement contains a `Try` block, zero or more `Catch` blocks, and zero or one `Finally` block.</span></span> <span data-ttu-id="a1172-127">Uma `Try` instrução deve ter pelo menos um `Catch` bloco ou um `Finally` bloco.</span><span class="sxs-lookup"><span data-stu-id="a1172-127">A `Try` statement must have at least one `Catch` block or one `Finally` block.</span></span>

<span data-ttu-id="a1172-128">O seguinte mostra a `Try` sintaxe de bloco:</span><span class="sxs-lookup"><span data-stu-id="a1172-128">The following shows the `Try` block syntax:</span></span>

```powershell
try {<statement list>}
```

<span data-ttu-id="a1172-129">A `Try` palavra-chave é seguida por uma lista de instruções entre chaves.</span><span class="sxs-lookup"><span data-stu-id="a1172-129">The `Try` keyword is followed by a statement list in braces.</span></span> <span data-ttu-id="a1172-130">Se ocorrer um erro de encerramento enquanto as instruções na lista de instruções estiverem sendo executadas, o script passará o objeto de erro do `Try` bloco para um `Catch` bloco apropriado.</span><span class="sxs-lookup"><span data-stu-id="a1172-130">If a terminating error occurs while the statements in the statement list are being run, the script passes the error object from the `Try` block to an appropriate `Catch` block.</span></span>

<span data-ttu-id="a1172-131">O seguinte mostra a `Catch` sintaxe de bloco:</span><span class="sxs-lookup"><span data-stu-id="a1172-131">The following shows the `Catch` block syntax:</span></span>

```powershell
catch [[<error type>][',' <error type>]*] {<statement list>}
```

<span data-ttu-id="a1172-132">Os tipos de erro aparecem entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="a1172-132">Error types appear in brackets.</span></span> <span data-ttu-id="a1172-133">Os colchetes mais externos indicam que o elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="a1172-133">The outermost brackets indicate the element is optional.</span></span>

<span data-ttu-id="a1172-134">A `Catch` palavra-chave é seguida por uma lista opcional de especificações de tipo de erro e uma lista de instruções.</span><span class="sxs-lookup"><span data-stu-id="a1172-134">The `Catch` keyword is followed by an optional list of error type specifications and a statement list.</span></span> <span data-ttu-id="a1172-135">Se ocorrer um erro de encerramento no `Try` bloco, o PowerShell procurará um `Catch` bloco apropriado.</span><span class="sxs-lookup"><span data-stu-id="a1172-135">If a terminating error occurs in the `Try` block, PowerShell searches for an appropriate `Catch` block.</span></span> <span data-ttu-id="a1172-136">Se um for encontrado, as instruções no `Catch` bloco serão executadas.</span><span class="sxs-lookup"><span data-stu-id="a1172-136">If one is found, the statements in the `Catch` block are executed.</span></span>

<span data-ttu-id="a1172-137">O `Catch` bloco pode especificar um ou mais tipos de erro.</span><span class="sxs-lookup"><span data-stu-id="a1172-137">The `Catch` block can specify one or more error types.</span></span> <span data-ttu-id="a1172-138">Um tipo de erro é uma exceção de estrutura Microsoft .NET ou uma exceção que é derivada de uma exceção de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a1172-138">An error type is a Microsoft .NET Framework exception or an exception that is derived from a .NET Framework exception.</span></span> <span data-ttu-id="a1172-139">Um `Catch` bloco manipula erros da classe de exceção de .NET Framework especificada ou de qualquer classe derivada da classe especificada.</span><span class="sxs-lookup"><span data-stu-id="a1172-139">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span>

<span data-ttu-id="a1172-140">Se um `Catch` bloco especificar um tipo de erro, esse `Catch` bloco tratará desse tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="a1172-140">If a `Catch` block specifies an error type, that `Catch` block handles that type of error.</span></span> <span data-ttu-id="a1172-141">Se um `Catch` bloco não especificar um tipo de erro, esse `Catch` bloco tratará qualquer erro encontrado no `Try` bloco.</span><span class="sxs-lookup"><span data-stu-id="a1172-141">If a `Catch` block does not specify an error type, that `Catch` block handles any error encountered in the `Try` block.</span></span> <span data-ttu-id="a1172-142">Uma `Try` instrução pode incluir vários `Catch` blocos para os diferentes tipos de erro especificados.</span><span class="sxs-lookup"><span data-stu-id="a1172-142">A `Try` statement can include multiple `Catch` blocks for the different specified error types.</span></span>

<span data-ttu-id="a1172-143">O seguinte mostra a `Finally` sintaxe de bloco:</span><span class="sxs-lookup"><span data-stu-id="a1172-143">The following shows the `Finally` block syntax:</span></span>

```powershell
finally {<statement list>}
```

<span data-ttu-id="a1172-144">A `Finally` palavra-chave é seguida por uma lista de instruções que é executada toda vez que o script é executado, mesmo que a `Try` instrução tenha sido executada sem erro ou um erro tenha sido detectado em uma `Catch` instrução.</span><span class="sxs-lookup"><span data-stu-id="a1172-144">The `Finally` keyword is followed by a statement list that runs every time the script is run, even if the `Try` statement ran without error or an error was caught in a `Catch` statement.</span></span>

<span data-ttu-id="a1172-145">Observe que pressionar <kbd>Ctrl</kbd> + <kbd>C</kbd> para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="a1172-145">Note that pressing <kbd>CTRL</kbd>+<kbd>C</kbd> stops the pipeline.</span></span> <span data-ttu-id="a1172-146">Os objetos que são enviados para o pipeline não serão exibidos como saída.</span><span class="sxs-lookup"><span data-stu-id="a1172-146">Objects that are sent to the pipeline will not be displayed as output.</span></span> <span data-ttu-id="a1172-147">Portanto, se você incluir uma instrução a ser exibida, como "finally block tenha executado", ela não será exibida depois que você pressionar <kbd>Ctrl</kbd> + <kbd>C</kbd>, mesmo que o `Finally` bloco seja executado.</span><span class="sxs-lookup"><span data-stu-id="a1172-147">Therefore, if you include a statement to be displayed, such as "Finally block has run", it will not be displayed after you press <kbd>CTRL</kbd>+<kbd>C</kbd>, even if the `Finally` block ran.</span></span>

### <a name="catching-errors"></a><span data-ttu-id="a1172-148">ERROS DE CAPTURA</span><span class="sxs-lookup"><span data-stu-id="a1172-148">CATCHING ERRORS</span></span>

<span data-ttu-id="a1172-149">O script de exemplo a seguir mostra um `Try` bloco com um `Catch` bloco:</span><span class="sxs-lookup"><span data-stu-id="a1172-149">The following sample script shows a `Try` block with a `Catch` block:</span></span>

```powershell
try { NonsenseString }
catch { "An error occurred." }
```

<span data-ttu-id="a1172-150">A `Catch` palavra-chave deve seguir imediatamente o `Try` bloco ou outro `Catch` bloco.</span><span class="sxs-lookup"><span data-stu-id="a1172-150">The `Catch` keyword must immediately follow the `Try` block or another `Catch` block.</span></span>

<span data-ttu-id="a1172-151">O PowerShell não reconhece "não-Sense" como um cmdlet ou outro item.</span><span class="sxs-lookup"><span data-stu-id="a1172-151">PowerShell does not recognize "NonsenseString" as a cmdlet or other item.</span></span>
<span data-ttu-id="a1172-152">A execução desse script retorna o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="a1172-152">Running this script returns the following result:</span></span>

```powershell
An error occurred.
```

<span data-ttu-id="a1172-153">Quando o script encontra "não sensorstring", ele causa um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="a1172-153">When the script encounters "NonsenseString", it causes a terminating error.</span></span> <span data-ttu-id="a1172-154">O `Catch` bloco trata o erro executando a lista de instruções dentro do bloco.</span><span class="sxs-lookup"><span data-stu-id="a1172-154">The `Catch` block handles the error by running the statement list inside the block.</span></span>

### <a name="using-multiple-catch-statements"></a><span data-ttu-id="a1172-155">USANDO VÁRIAS INSTRUÇÕES CATCH</span><span class="sxs-lookup"><span data-stu-id="a1172-155">USING MULTIPLE CATCH STATEMENTS</span></span>

<span data-ttu-id="a1172-156">Uma `Try` instrução pode ter qualquer número de `Catch` blocos.</span><span class="sxs-lookup"><span data-stu-id="a1172-156">A `Try` statement can have any number of `Catch` blocks.</span></span> <span data-ttu-id="a1172-157">Por exemplo, o script a seguir tem um `Try` bloco que `MyDoc.doc` é baixado e contém dois `Catch` blocos:</span><span class="sxs-lookup"><span data-stu-id="a1172-157">For example, the following script has a `Try` block that downloads `MyDoc.doc`, and it contains two `Catch` blocks:</span></span>

```powershell
try {
   $wc = new-object System.Net.WebClient
   $wc.DownloadFile("http://www.contoso.com/MyDoc.doc","c:\temp\MyDoc.doc")
}
catch [System.Net.WebException],[System.IO.IOException] {
    "Unable to download MyDoc.doc from http://www.contoso.com."
}
catch {
    "An error occurred that could not be resolved."
}

```

<span data-ttu-id="a1172-158">O primeiro `Catch` bloco manipula erros dos tipos **System .net. WebException** e **System. IO. IOException** .</span><span class="sxs-lookup"><span data-stu-id="a1172-158">The first `Catch` block handles errors of the **System.Net.WebException** and **System.IO.IOException** types.</span></span> <span data-ttu-id="a1172-159">O segundo `Catch` bloco não especifica um tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="a1172-159">The second `Catch` block does not specify an error type.</span></span> <span data-ttu-id="a1172-160">O segundo `Catch` bloco manipula quaisquer outros erros de encerramento que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="a1172-160">The second `Catch` block handles any other terminating errors that occur.</span></span>

<span data-ttu-id="a1172-161">O PowerShell corresponde aos tipos de erro por herança.</span><span class="sxs-lookup"><span data-stu-id="a1172-161">PowerShell matches error types by inheritance.</span></span> <span data-ttu-id="a1172-162">Um `Catch` bloco manipula erros da classe de exceção de .NET Framework especificada ou de qualquer classe derivada da classe especificada.</span><span class="sxs-lookup"><span data-stu-id="a1172-162">A `Catch` block handles errors of the specified .NET Framework exception class or of any class that derives from the specified class.</span></span> <span data-ttu-id="a1172-163">O exemplo a seguir contém um `Catch` bloco que captura um erro "comando não encontrado":</span><span class="sxs-lookup"><span data-stu-id="a1172-163">The following example contains a `Catch` block that catches a "Command Not Found" error:</span></span>

```powershell
catch [System.Management.Automation.CommandNotFoundException]
{"Inherited Exception" }
```

<span data-ttu-id="a1172-164">O tipo de erro especificado, **CommandNotFoundException** , é herdado do tipo de **System.SystemException** .</span><span class="sxs-lookup"><span data-stu-id="a1172-164">The specified error type, **CommandNotFoundException** , inherits from the **System.SystemException** type.</span></span> <span data-ttu-id="a1172-165">O exemplo a seguir também captura um erro de comando não encontrado:</span><span class="sxs-lookup"><span data-stu-id="a1172-165">The following example also catches a Command Not Found error:</span></span>

```powershell
catch [System.SystemException] {"Base Exception" }
```

<span data-ttu-id="a1172-166">Esse `Catch` bloco manipula o erro "comando não encontrado" e outros erros que herdam do tipo **SystemException** .</span><span class="sxs-lookup"><span data-stu-id="a1172-166">This `Catch` block handles the "Command Not Found" error and other errors that inherit from the **SystemException** type.</span></span>

<span data-ttu-id="a1172-167">Se você especificar uma classe de erro e uma de suas classes derivadas, coloque o `Catch` bloco para a classe derivada antes do `Catch` bloco da classe geral.</span><span class="sxs-lookup"><span data-stu-id="a1172-167">If you specify an error class and one of its derived classes, place the `Catch` block for the derived class before the `Catch` block for the general class.</span></span>

### <a name="using-traps-in-a-try-catch"></a><span data-ttu-id="a1172-168">Usando interceptações em uma tentativa catch</span><span class="sxs-lookup"><span data-stu-id="a1172-168">Using Traps in a Try Catch</span></span>

<span data-ttu-id="a1172-169">Quando ocorre um erro de encerramento em um `Try` bloco com um `Trap` definido dentro do `Try` bloco, mesmo que haja um bloco correspondente `Catch` , a `Trap` instrução assume o controle.</span><span class="sxs-lookup"><span data-stu-id="a1172-169">When a terminating error occurs in a `Try` block with a `Trap` defined within the `Try` block, even if there is a matching `Catch` block, the `Trap` statement takes control.</span></span>

<span data-ttu-id="a1172-170">Se `Trap` existir um em um bloco maior do que o `Try` , e não houver nenhum `Catch` bloco correspondente no escopo atual, o `Trap` assumirá o controle, mesmo que qualquer escopo pai tenha um `Catch` bloco correspondente.</span><span class="sxs-lookup"><span data-stu-id="a1172-170">If a `Trap` exists at a higher block than the `Try`, and there is no matching `Catch` block within the current scope, the `Trap` will take control, even if any parent scope has a matching `Catch` block.</span></span>

### <a name="accessing-exception-information"></a><span data-ttu-id="a1172-171">ACESSANDO INFORMAÇÕES DE EXCEÇÃO</span><span class="sxs-lookup"><span data-stu-id="a1172-171">ACCESSING EXCEPTION INFORMATION</span></span>

<span data-ttu-id="a1172-172">Em um `Catch` bloco, o erro atual pode ser acessado usando `$_` , que também é conhecido como `$PSItem` .</span><span class="sxs-lookup"><span data-stu-id="a1172-172">Within a `Catch` block, the current error can be accessed using `$_`, which is also known as `$PSItem`.</span></span> <span data-ttu-id="a1172-173">O objeto é do tipo **ErrorRecord** .</span><span class="sxs-lookup"><span data-stu-id="a1172-173">The object is of type **ErrorRecord** .</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_
}
```

<span data-ttu-id="a1172-174">A execução desse script retorna o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="a1172-174">Running this script returns the following result:</span></span>

```Output
An Error occurred:
The term 'NonsenseString' is not recognized as the name of a cmdlet, function,
script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
```

<span data-ttu-id="a1172-175">Há propriedades adicionais que podem ser acessadas, como **ScriptStackTrace** , **Exception** e **ErrorDetails** .</span><span class="sxs-lookup"><span data-stu-id="a1172-175">There are additional properties that can be accessed, such as **ScriptStackTrace** , **Exception** , and **ErrorDetails** .</span></span>  <span data-ttu-id="a1172-176">Por exemplo, se alterarmos o script para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a1172-176">For example, if we change the script to the following:</span></span>

```powershell
try { NonsenseString }
catch {
  Write-Host "An error occurred:"
  Write-Host $_.ScriptStackTrace
}
```

<span data-ttu-id="a1172-177">O resultado será semelhante a:</span><span class="sxs-lookup"><span data-stu-id="a1172-177">The result will be similar to:</span></span>

```
An Error occurred:
at <ScriptBlock>, <No file>: line 2
```

### <a name="freeing-resources-by-using-finally"></a><span data-ttu-id="a1172-178">LIBERANDO RECURSOS USANDO FINALLY</span><span class="sxs-lookup"><span data-stu-id="a1172-178">FREEING RESOURCES BY USING FINALLY</span></span>

<span data-ttu-id="a1172-179">Para liberar recursos usados por um script, adicione um `Finally` bloco após os `Try` `Catch` blocos e.</span><span class="sxs-lookup"><span data-stu-id="a1172-179">To free resources used by a script, add a `Finally` block after the `Try` and `Catch` blocks.</span></span> <span data-ttu-id="a1172-180">As `Finally` instruções de bloco são executadas independentemente de o `Try` bloco encontrar um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="a1172-180">The `Finally` block statements run regardless of whether the `Try` block encounters a terminating error.</span></span> <span data-ttu-id="a1172-181">O PowerShell executa o `Finally` bloco antes que o script seja encerrado ou antes que o bloco atual saia do escopo.</span><span class="sxs-lookup"><span data-stu-id="a1172-181">PowerShell runs the `Finally` block before the script terminates or before the current block goes out of scope.</span></span>

<span data-ttu-id="a1172-182">Um `Finally` bloco é executado mesmo se você usar <kbd>Ctrl</kbd> + <kbd>C</kbd> para interromper o script.</span><span class="sxs-lookup"><span data-stu-id="a1172-182">A `Finally` block runs even if you use <kbd>CTRL</kbd>+<kbd>C</kbd> to stop the script.</span></span> <span data-ttu-id="a1172-183">Um `Finally` bloco também será executado se uma palavra-chave Exit parar o script dentro de um `Catch` bloco.</span><span class="sxs-lookup"><span data-stu-id="a1172-183">A `Finally` block also runs if an Exit keyword stops the script from within a `Catch` block.</span></span>

### <a name="see-also"></a><span data-ttu-id="a1172-184">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="a1172-184">SEE ALSO</span></span>

[<span data-ttu-id="a1172-185">about_Break</span><span class="sxs-lookup"><span data-stu-id="a1172-185">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="a1172-186">about_Continue</span><span class="sxs-lookup"><span data-stu-id="a1172-186">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="a1172-187">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="a1172-187">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="a1172-188">about_Throw</span><span class="sxs-lookup"><span data-stu-id="a1172-188">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="a1172-189">about_Trap</span><span class="sxs-lookup"><span data-stu-id="a1172-189">about_Trap</span></span>](about_Trap.md)
