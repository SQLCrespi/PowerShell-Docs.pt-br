---
description: Descreve os pipelines de encadeamento com `&&` os `||` operadores e no PowerShell.
Locale: en-US
ms.date: 09/30/2019
schema: 2.0.0
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: ece84ec061126401e53bf58112cd79a07a816e8d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598655"
---
# <a name="about-pipeline-chain-operators"></a><span data-ttu-id="04bff-103">Sobre operadores de cadeia de pipeline</span><span class="sxs-lookup"><span data-stu-id="04bff-103">About Pipeline Chain Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="04bff-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="04bff-104">Short description</span></span>

<span data-ttu-id="04bff-105">Descreve os pipelines de encadeamento com `&&` os `||` operadores e no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04bff-105">Describes chaining pipelines with the `&&` and `||` operators in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="04bff-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="04bff-106">Long description</span></span>

<span data-ttu-id="04bff-107">A partir do PowerShell 7, o PowerShell implementa os `&&` `||` operadores e para encadear pipelines condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="04bff-107">Beginning in PowerShell 7, PowerShell implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="04bff-108">Esses operadores são conhecidos no PowerShell como *operadores de cadeia de pipeline* e são semelhantes às [listas e-ou](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) em shells POSIX, como bash, zsh e sh, bem como [símbolos de processamento condicional](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) no Shell de comando do Windows (cmd.exe).</span><span class="sxs-lookup"><span data-stu-id="04bff-108">These operators are known in PowerShell as *pipeline chain operators*, and are similar to [AND-OR lists](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) in POSIX shells like bash, zsh and sh, as well as [conditional processing symbols](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) in the Windows Command Shell (cmd.exe).</span></span>

<span data-ttu-id="04bff-109">O operador `&&` executa o pipeline à direita, se o pipeline à esquerda foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="04bff-109">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="04bff-110">Por outro lado, o operador `||` executa o pipeline à direita, se o pipeline à esquerda falhou.</span><span class="sxs-lookup"><span data-stu-id="04bff-110">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

<span data-ttu-id="04bff-111">Esses operadores usam as variáveis `$?` e `$LASTEXITCODE` para determinar se um pipeline falhou.</span><span class="sxs-lookup"><span data-stu-id="04bff-111">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="04bff-112">Isso permite que você os utilize com comandos nativos, e não apenas com cmdlets ou funções.</span><span class="sxs-lookup"><span data-stu-id="04bff-112">This allows you to use them with native commands and not just with cmdlets or functions.</span></span> <span data-ttu-id="04bff-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="04bff-113">For example:</span></span>

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a><span data-ttu-id="04bff-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="04bff-114">Examples</span></span>

#### <a name="two-successful-commands"></a><span data-ttu-id="04bff-115">Dois comandos bem-sucedidos</span><span class="sxs-lookup"><span data-stu-id="04bff-115">Two successful commands</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a><span data-ttu-id="04bff-116">O primeiro comando falha, fazendo com que o segundo não seja executado</span><span class="sxs-lookup"><span data-stu-id="04bff-116">First command fails, causing second not to be executed</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a><span data-ttu-id="04bff-117">O primeiro comando é bem sucedido; portanto, o segundo comando não é executado</span><span class="sxs-lookup"><span data-stu-id="04bff-117">First command succeeds, so the second command is not executed</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a><span data-ttu-id="04bff-118">O primeiro comando falha, portanto, o segundo comando é executado</span><span class="sxs-lookup"><span data-stu-id="04bff-118">First command fails, so the second command is executed</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

<span data-ttu-id="04bff-119">O êxito do pipeline é definido pelo valor da `$?` variável, que o PowerShell define automaticamente após a execução de um pipeline com base em seu status de execução.</span><span class="sxs-lookup"><span data-stu-id="04bff-119">Pipeline success is defined by the value of the `$?` variable, which PowerShell automatically sets after executing a pipeline based on its execution status.</span></span>
<span data-ttu-id="04bff-120">Isso significa que os operadores de cadeia de pipeline têm a seguinte equivalência:</span><span class="sxs-lookup"><span data-stu-id="04bff-120">This means that pipeline chain operators have the following equivalence:</span></span>

```powershell
Test-Command '1' && Test-Command '2'
```

<span data-ttu-id="04bff-121">funciona da mesma forma que</span><span class="sxs-lookup"><span data-stu-id="04bff-121">works the same as</span></span>

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

<span data-ttu-id="04bff-122">e</span><span class="sxs-lookup"><span data-stu-id="04bff-122">and</span></span>

```powershell
Test-Command '1' || Test-Command '2'
```

<span data-ttu-id="04bff-123">funciona da mesma forma que</span><span class="sxs-lookup"><span data-stu-id="04bff-123">works the same as</span></span>

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a><span data-ttu-id="04bff-124">Atribuição de cadeias de pipeline</span><span class="sxs-lookup"><span data-stu-id="04bff-124">Assignment from pipeline chains</span></span>

<span data-ttu-id="04bff-125">A atribuição de uma variável de uma cadeia de pipeline usa a concatenação de todos os pipelines na cadeia:</span><span class="sxs-lookup"><span data-stu-id="04bff-125">Assigning a variable from a pipeline chain takes the concatenation of all the pipelines in the chain:</span></span>

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

<span data-ttu-id="04bff-126">Se ocorrer um erro de encerramento de script durante a atribuição de uma cadeia de pipeline, a atribuição não terá sucesso:</span><span class="sxs-lookup"><span data-stu-id="04bff-126">If a script-terminating error occurs during assignment from a pipeline chain, the assignment does not succeed:</span></span>

```powershell
try
{
    $result = Write-Output 'Value' && $(throw 'Bad')
}
catch
{
    # Do nothing, just squash the error
}

"Result: $result"
```

```Output
Result:
```

### <a name="operator-syntax-and-precedence"></a><span data-ttu-id="04bff-127">Sintaxe e precedência do operador</span><span class="sxs-lookup"><span data-stu-id="04bff-127">Operator syntax and precedence</span></span>

<span data-ttu-id="04bff-128">Ao contrário de outros operadores, `&&` e `||` operam em pipelines, em vez de expressões como `+` ou `-and` , por exemplo.</span><span class="sxs-lookup"><span data-stu-id="04bff-128">Unlike other operators, `&&` and `||` operate on pipelines, rather than on expressions like `+` or `-and`, for example.</span></span>

<span data-ttu-id="04bff-129">`&&` e `||` têm uma precedência mais baixa do que o de tubulação () `|` ou redirecionamento ( `>` ), mas uma precedência mais alta do que os operadores de trabalho ( `&` ), atribuição ( `=` ) ou ponto-e-vírgula ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="04bff-129">`&&` and `||` have a lower precedence than piping (`|`) or redirection (`>`), but a higher precedence than job operators (`&`), assignment (`=`) or semicolons (`;`).</span></span> <span data-ttu-id="04bff-130">Isso significa que os pipelines em uma cadeia de pipeline podem ser redirecionados individualmente e que todas as cadeias de pipeline podem ser em segundo plano, atribuídas a variáveis ou separadas como instruções.</span><span class="sxs-lookup"><span data-stu-id="04bff-130">This means that pipelines within a pipeline chain can be individually redirected, and that entire pipeline chains can be backgrounded, assigned to variables, or separated as statements.</span></span>

<span data-ttu-id="04bff-131">Para usar a sintaxe de precedência inferior em uma cadeia de pipeline, considere o uso de parênteses `(...)` .</span><span class="sxs-lookup"><span data-stu-id="04bff-131">To use lower precedence syntax within a pipeline chain, consider the use of parentheses `(...)`.</span></span>
<span data-ttu-id="04bff-132">Da mesma forma, para inserir uma instrução em uma cadeia de pipeline, uma subexpressão `$(...)` pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="04bff-132">Similarly, to embed a statement within a pipeline chain, a subexpression `$(...)` can be used.</span></span>
<span data-ttu-id="04bff-133">Isso pode ser útil para combinar comandos nativos com o fluxo de controle:</span><span class="sxs-lookup"><span data-stu-id="04bff-133">This can be useful for combining native commands with control flow:</span></span>

```powershell
foreach ($file in 'file1','file2','file3')
{
    # When find succeeds, the loop breaks
    find $file && Write-Output "Found $file" && $(break)
}
```

```Output
find: file1: No such file or directory
file2
Found file2
```

<span data-ttu-id="04bff-134">A partir do PowerShell 7, o comportamento dessas sintaxes foi alterado para que `$?` seja definido como esperado quando um comando é executado com êxito ou falha entre parênteses ou uma subexpressão.</span><span class="sxs-lookup"><span data-stu-id="04bff-134">As of PowerShell 7, the behaviour of these syntaxes has been changed so that `$?` is set as expected when a command succeeds or fails within parentheses or a subexpression.</span></span>

<span data-ttu-id="04bff-135">Como a maioria dos outros operadores no PowerShell `&&` e `||` também são *associativas à esquerda*, o que significa que eles são agrupados da esquerda.</span><span class="sxs-lookup"><span data-stu-id="04bff-135">Like most other operators in PowerShell, `&&` and `||` are also *left-associative*, meaning they group from the left.</span></span> <span data-ttu-id="04bff-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="04bff-136">For example:</span></span>

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

<span data-ttu-id="04bff-137">será agrupado como:</span><span class="sxs-lookup"><span data-stu-id="04bff-137">will group as:</span></span>

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

<span data-ttu-id="04bff-138">sendo equivalente a:</span><span class="sxs-lookup"><span data-stu-id="04bff-138">being equivalent to:</span></span>

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a><span data-ttu-id="04bff-139">Interação de erro</span><span class="sxs-lookup"><span data-stu-id="04bff-139">Error interaction</span></span>

<span data-ttu-id="04bff-140">Os operadores de cadeia de pipeline não absorvem erros.</span><span class="sxs-lookup"><span data-stu-id="04bff-140">Pipeline chain operators do not absorb errors.</span></span> <span data-ttu-id="04bff-141">Quando uma instrução em uma cadeia de pipeline gera um erro de encerramento de script, a cadeia de pipeline é encerrada.</span><span class="sxs-lookup"><span data-stu-id="04bff-141">When a statement in a pipeline chain throws a script-terminating error, the pipeline chain is terminated.</span></span>

<span data-ttu-id="04bff-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="04bff-142">For example:</span></span>

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

<span data-ttu-id="04bff-143">Mesmo quando o erro é capturado, a cadeia de pipeline ainda é encerrada:</span><span class="sxs-lookup"><span data-stu-id="04bff-143">Even when the error is caught, the pipeline chain is still terminated:</span></span>

```powershell
try
{
    $(throw 'Bad') || Write-Output '2'
}
catch
{
    Write-Output "Caught: $_"
}
Write-Output 'Done'
```

```Output
Caught: Bad
Done
```

<span data-ttu-id="04bff-144">Se um erro não estiver sendo encerrado ou apenas terminar um pipeline, a cadeia de pipeline continuará, respeitando o valor de `$?` :</span><span class="sxs-lookup"><span data-stu-id="04bff-144">If an error is non-terminating, or only terminates a pipeline, the pipeline chain continues, respecting the value of `$?`:</span></span>

```powershell
function Test-NonTerminatingError
{
    [CmdletBinding()]
    param()

    $exception = [System.Exception]::new('BAD')
    $errorId = 'BAD'
    $errorCategory = 'NotSpecified'

    $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

    $PSCmdlet.WriteError($errorRecord)
}

Test-NonTerminatingError || Write-Output 'Second'
```

```Output
Test-NonTerminatingError: BAD
Second
```

### <a name="chaining-pipelines-rather-than-commands"></a><span data-ttu-id="04bff-145">Encadeando pipelines em vez de comandos</span><span class="sxs-lookup"><span data-stu-id="04bff-145">Chaining pipelines rather than commands</span></span>

<span data-ttu-id="04bff-146">Os operadores de cadeia de pipeline, por seu nome, podem ser usados para encadear pipelines, em vez de apenas comandos.</span><span class="sxs-lookup"><span data-stu-id="04bff-146">Pipeline chain operators, by their name, can be used to chain pipelines, rather than just commands.</span></span> <span data-ttu-id="04bff-147">Isso corresponde ao comportamento de outros shells, mas pode dificultar o *sucesso* de determinar:</span><span class="sxs-lookup"><span data-stu-id="04bff-147">This matches the behavior of other shells, but can make *success* harder to determine:</span></span>

```powershell
function Test-NotTwo
{
    [CmdletBinding()]
    param(
      [Parameter(ValueFromPipeline)]
      $Input
    )

    process
    {
        if ($Input -ne 2)
        {
            return $Input
        }

        $exception = [System.Exception]::new('Input is 2')
        $errorId = 'InputTwo'
        $errorCategory = 'InvalidData'

        $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

        $PSCmdlet.WriteError($errorRecord)
    }
}

1,2,3 | Test-NotTwo && Write-Output 'All done!'
```

```Output
1
Test-NotTwo : Input is 2
3
```

<span data-ttu-id="04bff-148">Observe que `Write-Output 'All done!'` não é executado, uma vez que `Test-NotTwo` é considerado com falha após gerar o erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="04bff-148">Note that `Write-Output 'All done!'` is not executed, since `Test-NotTwo` is deemed to have failed after generating the non-terminating error.</span></span>

## <a name="see-also"></a><span data-ttu-id="04bff-149">Consulte também</span><span class="sxs-lookup"><span data-stu-id="04bff-149">See also</span></span>

- [<span data-ttu-id="04bff-150">about_Operators</span><span class="sxs-lookup"><span data-stu-id="04bff-150">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="04bff-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="04bff-151">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="04bff-152">about_pipelines</span><span class="sxs-lookup"><span data-stu-id="04bff-152">about_pipelines</span></span>](about_pipelines.md)

