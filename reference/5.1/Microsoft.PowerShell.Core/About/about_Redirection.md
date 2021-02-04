---
description: Explica como redirecionar a saída do PowerShell para arquivos de texto.
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: 2f2081bbfcc2cfc97eaa5a3c2c527cdd9cd61d2c
ms.sourcegitcommit: b9826dcf402db8a2b6d3eab37edb82c6af113343
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98040866"
---
# <a name="about-redirection"></a><span data-ttu-id="2b213-103">Sobre o redirecionamento</span><span class="sxs-lookup"><span data-stu-id="2b213-103">About Redirection</span></span>

## <a name="short-description"></a><span data-ttu-id="2b213-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="2b213-104">Short description</span></span>
<span data-ttu-id="2b213-105">Explica como redirecionar a saída do PowerShell para arquivos de texto.</span><span class="sxs-lookup"><span data-stu-id="2b213-105">Explains how to redirect output from PowerShell to text files.</span></span>

## <a name="long-description"></a><span data-ttu-id="2b213-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="2b213-106">Long description</span></span>

<span data-ttu-id="2b213-107">Por padrão, o PowerShell envia a saída para o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b213-107">By default, PowerShell sends output to the PowerShell host.</span></span> <span data-ttu-id="2b213-108">Geralmente, esse é o aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="2b213-108">Usually this is the console application.</span></span> <span data-ttu-id="2b213-109">No entanto, você pode direcionar a saída para um arquivo de texto e pode redirecionar a saída de erro para o fluxo de saída regular.</span><span class="sxs-lookup"><span data-stu-id="2b213-109">However, you can direct the output to a text file, and you can redirect error output to the regular output stream.</span></span>

<span data-ttu-id="2b213-110">Você pode usar os seguintes métodos para redirecionar a saída:</span><span class="sxs-lookup"><span data-stu-id="2b213-110">You can use the following methods to redirect output:</span></span>

- <span data-ttu-id="2b213-111">Use o `Out-File` cmdlet, que envia a saída de comando para um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2b213-111">Use the `Out-File` cmdlet, which sends command output to a text file.</span></span>
  <span data-ttu-id="2b213-112">Normalmente, você usa o `Out-File` cmdlet quando precisa usar seus parâmetros, como os `Encoding` `Force` parâmetros,, `Width` ou `NoClobber` .</span><span class="sxs-lookup"><span data-stu-id="2b213-112">Typically, you use the `Out-File` cmdlet when you need to use its parameters, such as the `Encoding`, `Force`, `Width`, or `NoClobber` parameters.</span></span>

- <span data-ttu-id="2b213-113">Use o `Tee-Object` cmdlet, que envia a saída do comando para um arquivo de texto e, em seguida, o envia para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="2b213-113">Use the `Tee-Object` cmdlet, which sends command output to a text file and then sends it to the pipeline.</span></span>

- <span data-ttu-id="2b213-114">Use os operadores de redirecionamento do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b213-114">Use the PowerShell redirection operators.</span></span> <span data-ttu-id="2b213-115">Usar o operador de redirecionamento com um destino de arquivo é funcionalmente equivalente a direcionar para o sem `Out-File` Parâmetros extras.</span><span class="sxs-lookup"><span data-stu-id="2b213-115">Using the redirection operator with a file target is functionally equivalent to piping to `Out-File` with no extra parameters.</span></span>

<span data-ttu-id="2b213-116">Para obter mais informações sobre fluxos, consulte [about_Output_Streams](about_Output_Streams.md).</span><span class="sxs-lookup"><span data-stu-id="2b213-116">For more information about streams, see [about_Output_Streams](about_Output_Streams.md).</span></span>

### <a name="redirectable-output-streams"></a><span data-ttu-id="2b213-117">Fluxos de saída redirecionáveis</span><span class="sxs-lookup"><span data-stu-id="2b213-117">Redirectable output streams</span></span>

<span data-ttu-id="2b213-118">O PowerShell dá suporte ao redirecionamento dos fluxos de saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="2b213-118">PowerShell supports redirection of the following output streams.</span></span>

| <span data-ttu-id="2b213-119">Fluxo #</span><span class="sxs-lookup"><span data-stu-id="2b213-119">Stream #</span></span> |      <span data-ttu-id="2b213-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b213-120">Description</span></span>       | <span data-ttu-id="2b213-121">Introduzido em</span><span class="sxs-lookup"><span data-stu-id="2b213-121">Introduced in</span></span>  |    <span data-ttu-id="2b213-122">Cmdlet de gravação</span><span class="sxs-lookup"><span data-stu-id="2b213-122">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="2b213-123">1</span><span class="sxs-lookup"><span data-stu-id="2b213-123">1</span></span>        | <span data-ttu-id="2b213-124">**Êxito** Fluxo</span><span class="sxs-lookup"><span data-stu-id="2b213-124">**Success** Stream</span></span>     | <span data-ttu-id="2b213-125">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="2b213-125">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="2b213-126">2</span><span class="sxs-lookup"><span data-stu-id="2b213-126">2</span></span>        | <span data-ttu-id="2b213-127">**Erro** do Fluxo</span><span class="sxs-lookup"><span data-stu-id="2b213-127">**Error** Stream</span></span>       | <span data-ttu-id="2b213-128">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="2b213-128">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="2b213-129">3</span><span class="sxs-lookup"><span data-stu-id="2b213-129">3</span></span>        | <span data-ttu-id="2b213-130">**Aviso** Fluxo</span><span class="sxs-lookup"><span data-stu-id="2b213-130">**Warning** Stream</span></span>     | <span data-ttu-id="2b213-131">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="2b213-131">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="2b213-132">4</span><span class="sxs-lookup"><span data-stu-id="2b213-132">4</span></span>        | <span data-ttu-id="2b213-133">**Modo detalhado** Fluxo</span><span class="sxs-lookup"><span data-stu-id="2b213-133">**Verbose** Stream</span></span>     | <span data-ttu-id="2b213-134">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="2b213-134">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="2b213-135">5</span><span class="sxs-lookup"><span data-stu-id="2b213-135">5</span></span>        | <span data-ttu-id="2b213-136">**Depurar** Fluxo</span><span class="sxs-lookup"><span data-stu-id="2b213-136">**Debug** Stream</span></span>       | <span data-ttu-id="2b213-137">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="2b213-137">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="2b213-138">6</span><span class="sxs-lookup"><span data-stu-id="2b213-138">6</span></span>        | <span data-ttu-id="2b213-139">**Informações** do Fluxo</span><span class="sxs-lookup"><span data-stu-id="2b213-139">**Information** Stream</span></span> | <span data-ttu-id="2b213-140">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2b213-140">PowerShell 5.0</span></span> | `Write-Information` |
| *        | <span data-ttu-id="2b213-141">Todos os fluxos</span><span class="sxs-lookup"><span data-stu-id="2b213-141">All Streams</span></span>            | <span data-ttu-id="2b213-142">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="2b213-142">PowerShell 3.0</span></span> |                     |

> [!NOTE]
> <span data-ttu-id="2b213-143">Também há um fluxo de **progresso** no PowerShell, mas ele não dá suporte ao redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="2b213-143">There is also a **Progress** stream in PowerShell, but it does not support redirection.</span></span>

### <a name="powershell-redirection-operators"></a><span data-ttu-id="2b213-144">Operadores de redirecionamento do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b213-144">PowerShell redirection operators</span></span>

<span data-ttu-id="2b213-145">Os operadores de redirecionamento do PowerShell são os seguintes, onde `n` representa o número do fluxo.</span><span class="sxs-lookup"><span data-stu-id="2b213-145">The PowerShell redirection operators are as follows, where `n` represents the stream number.</span></span> <span data-ttu-id="2b213-146">O fluxo de **êxito** ( `1` ) será o padrão se nenhum fluxo for especificado.</span><span class="sxs-lookup"><span data-stu-id="2b213-146">The **Success** stream ( `1` ) is the default if no stream is specified.</span></span>

| <span data-ttu-id="2b213-147">Operador</span><span class="sxs-lookup"><span data-stu-id="2b213-147">Operator</span></span> |                         <span data-ttu-id="2b213-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b213-148">Description</span></span>                         | <span data-ttu-id="2b213-149">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b213-149">Syntax</span></span> |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | <span data-ttu-id="2b213-150">Enviar o fluxo especificado para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b213-150">Send specified stream to a file.</span></span>                            | `n>`   |
| `>>`     | <span data-ttu-id="2b213-151">**Acrescentar** o fluxo especificado a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b213-151">**Append** specified stream to a file.</span></span>                      | `n>>`  |
| `>&1`    | <span data-ttu-id="2b213-152">_Redireciona_ o fluxo especificado para o fluxo de **êxito** .</span><span class="sxs-lookup"><span data-stu-id="2b213-152">_Redirects_ the specified stream to the **Success** stream.</span></span> | `n>&1` |

> [!NOTE]
> <span data-ttu-id="2b213-153">Ao contrário de alguns shells do UNIX, você só pode redirecionar outros fluxos para o fluxo de **êxito** .</span><span class="sxs-lookup"><span data-stu-id="2b213-153">Unlike some Unix shells, you can only redirect other streams to the **Success** stream.</span></span>

## <a name="examples"></a><span data-ttu-id="2b213-154">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2b213-154">Examples</span></span>

### <a name="example-1-redirect-errors-and-output-to-a-file"></a><span data-ttu-id="2b213-155">Exemplo 1: redirecionar erros e saída para um arquivo</span><span class="sxs-lookup"><span data-stu-id="2b213-155">Example 1: Redirect errors and output to a file</span></span>

<span data-ttu-id="2b213-156">Este exemplo é executado `dir` em um item que terá sucesso e um que será um erro.</span><span class="sxs-lookup"><span data-stu-id="2b213-156">This example runs `dir` on one item that will succeed, and one that will error.</span></span>

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

<span data-ttu-id="2b213-157">Ele usa `2>&1` para redirecionar o fluxo de **erros** para o fluxo de **êxito** e `>` para enviar o fluxo de **êxito** resultante para um arquivo chamado `dir.log`</span><span class="sxs-lookup"><span data-stu-id="2b213-157">It uses `2>&1` to redirect the **Error** stream to the **Success** stream, and `>` to send the resultant **Success** stream to a file called `dir.log`</span></span>

### <a name="example-2-send-all-success-stream-data-to-a-file"></a><span data-ttu-id="2b213-158">Exemplo 2: enviar todos os dados de fluxo de êxito para um arquivo</span><span class="sxs-lookup"><span data-stu-id="2b213-158">Example 2: Send all Success stream data to a file</span></span>

<span data-ttu-id="2b213-159">Este exemplo envia todos os dados de fluxo de **êxito** para um arquivo chamado `script.log` .</span><span class="sxs-lookup"><span data-stu-id="2b213-159">This example sends all **Success** stream data to a file called `script.log`.</span></span>

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a><span data-ttu-id="2b213-160">Exemplo 3: enviar fluxos de êxito, de aviso e de erro para um arquivo</span><span class="sxs-lookup"><span data-stu-id="2b213-160">Example 3: Send Success, Warning, and Error streams to a file</span></span>

<span data-ttu-id="2b213-161">Este exemplo mostra como você pode combinar operadores de redirecionamento para obter um resultado desejado.</span><span class="sxs-lookup"><span data-stu-id="2b213-161">This example shows how you can combine redirection operators to achieve a desired result.</span></span>

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > C:\Temp\redirection.log
```

- <span data-ttu-id="2b213-162">`3>&1` redireciona o fluxo de **aviso** para o fluxo de **êxito** .</span><span class="sxs-lookup"><span data-stu-id="2b213-162">`3>&1` redirects the **Warning** stream to the **Success** stream.</span></span>
- <span data-ttu-id="2b213-163">`2>&1` redireciona o fluxo de **erro** para o fluxo de **êxito** (que também inclui todos os dados de fluxo de **aviso** )</span><span class="sxs-lookup"><span data-stu-id="2b213-163">`2>&1` redirects the **Error** stream to the **Success** stream (which also now includes all **Warning** stream data)</span></span>
- <span data-ttu-id="2b213-164">`>` redireciona o fluxo de **êxito** (que agora contém os fluxos de **aviso** e de **erro** ) para um arquivo chamado `C:\temp\redirection.log` )</span><span class="sxs-lookup"><span data-stu-id="2b213-164">`>` redirects the **Success** stream (which now contains both **Warning** and **Error** streams) to a file called `C:\temp\redirection.log`)</span></span>

### <a name="example-4-redirect-all-streams-to-a-file"></a><span data-ttu-id="2b213-165">Exemplo 4: redirecionar todos os fluxos para um arquivo</span><span class="sxs-lookup"><span data-stu-id="2b213-165">Example 4: Redirect all streams to a file</span></span>

<span data-ttu-id="2b213-166">Este exemplo envia a saída de todos os fluxos de um script chamado `script.ps1` para um arquivo chamado `script.log`</span><span class="sxs-lookup"><span data-stu-id="2b213-166">This example sends all streams output from a script called `script.ps1` to a file called `script.log`</span></span>

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a><span data-ttu-id="2b213-167">Exemplo 5: suprimir todos os Write-Host e dados de fluxo de informações</span><span class="sxs-lookup"><span data-stu-id="2b213-167">Example 5: Suppress all Write-Host and Information stream data</span></span>

<span data-ttu-id="2b213-168">Este exemplo suprime todos os dados de fluxo de informações.</span><span class="sxs-lookup"><span data-stu-id="2b213-168">This example suppresses all information stream data.</span></span> <span data-ttu-id="2b213-169">Para ler mais sobre os cmdlets de fluxo de **informações** , consulte [write-host](xref:Microsoft.PowerShell.Utility.Write-Host) e [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)</span><span class="sxs-lookup"><span data-stu-id="2b213-169">To read more about **Information** stream cmdlets, see [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) and [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)</span></span>

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a><span data-ttu-id="2b213-170">Exemplo 6: mostrar o efeito das preferências de ação</span><span class="sxs-lookup"><span data-stu-id="2b213-170">Example 6: Show the effect of Action Preferences</span></span>

<span data-ttu-id="2b213-171">Variáveis de preferência de ação e parâmetros podem alterar o que é gravado em um fluxo específico.</span><span class="sxs-lookup"><span data-stu-id="2b213-171">Action Preference variables and parameters can change what gets written to a particular stream.</span></span> <span data-ttu-id="2b213-172">O script neste exemplo mostra como o valor de `$ErrorActionPreference` afeta o que é gravado no fluxo de **erro** .</span><span class="sxs-lookup"><span data-stu-id="2b213-172">The script in this example shows how the value of `$ErrorActionPreference` affects what gets written to the **Error** stream.</span></span>

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

<span data-ttu-id="2b213-173">Quando executamos esse script, recebemos uma solicitação quando `$ErrorActionPreference` é definido como `Inquire` .</span><span class="sxs-lookup"><span data-stu-id="2b213-173">When we run this script we get prompted when `$ErrorActionPreference` is set to `Inquire`.</span></span>

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

<span data-ttu-id="2b213-174">Quando examinamos o arquivo de log, vemos o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2b213-174">When we examine the log file we see the following:</span></span>

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a><span data-ttu-id="2b213-175">Anotações</span><span class="sxs-lookup"><span data-stu-id="2b213-175">Notes</span></span>

<span data-ttu-id="2b213-176">Os operadores de redirecionamento que não acrescentam dados ( `>` e `n>` ) substituem o conteúdo atual do arquivo especificado sem aviso.</span><span class="sxs-lookup"><span data-stu-id="2b213-176">The redirection operators that do not append data (`>` and `n>`) overwrite the current contents of the specified file without warning.</span></span>

<span data-ttu-id="2b213-177">No entanto, se o arquivo for somente leitura, oculto ou arquivo do sistema, o redirecionamento **falhará**.</span><span class="sxs-lookup"><span data-stu-id="2b213-177">However, if the file is a read-only, hidden, or system file, the redirection **fails**.</span></span> <span data-ttu-id="2b213-178">Os operadores de redirecionamento de acréscimo ( `>>` e `n>>` ) não gravam em um arquivo somente leitura, mas acrescentam conteúdo a um sistema ou arquivo oculto.</span><span class="sxs-lookup"><span data-stu-id="2b213-178">The append redirection operators (`>>` and `n>>`) do not write to a read-only file, but they append content to a system or hidden file.</span></span>

<span data-ttu-id="2b213-179">Para forçar o redirecionamento de conteúdo para um arquivo somente leitura, oculto ou de sistema, use o `Out-File` cmdlet com seu `Force` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2b213-179">To force the redirection of content to a read-only, hidden, or system file, use the `Out-File` cmdlet with its `Force` parameter.</span></span>

<span data-ttu-id="2b213-180">Quando você está gravando em arquivos, os operadores de redirecionamento usam `UTF8NoBOM` codificação.</span><span class="sxs-lookup"><span data-stu-id="2b213-180">When you are writing to files, the redirection operators use `UTF8NoBOM` encoding.</span></span> <span data-ttu-id="2b213-181">Se o arquivo tiver uma codificação diferente, a saída poderá não ser formatada corretamente.</span><span class="sxs-lookup"><span data-stu-id="2b213-181">If the file has a different encoding, the output might not be formatted correctly.</span></span> <span data-ttu-id="2b213-182">Para gravar em arquivos com uma codificação diferente, use o `Out-File` cmdlet com seu `Encoding` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2b213-182">To write to files with a different encoding, use the `Out-File` cmdlet with its `Encoding` parameter.</span></span>

### <a name="potential-confusion-with-comparison-operators"></a><span data-ttu-id="2b213-183">Possível confusão com operadores de comparação</span><span class="sxs-lookup"><span data-stu-id="2b213-183">Potential confusion with comparison operators</span></span>

<span data-ttu-id="2b213-184">O `>` operador não deve ser confundido com o operador de comparação [maior que](about_Comparison_Operators.md#-gt--ge--lt-and--le) (geralmente indicado como `>` em outras linguagens de programação).</span><span class="sxs-lookup"><span data-stu-id="2b213-184">The `>` operator is not to be confused with the [Greater-than](about_Comparison_Operators.md#-gt--ge--lt-and--le) comparison operator (often denoted as `>` in other programming languages).</span></span>

<span data-ttu-id="2b213-185">Dependendo dos objetos que estão sendo comparados, a saída usando `>` pode parecer correta (porque 36 não é maior que 42).</span><span class="sxs-lookup"><span data-stu-id="2b213-185">Depending on the objects being compared, the output using `>` can appear to be correct (because 36 is not greater than 42).</span></span>

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

<span data-ttu-id="2b213-186">No entanto, uma verificação do sistema de arquivos local pode ver que um arquivo chamado `42` foi gravado, com o conteúdo `36` .</span><span class="sxs-lookup"><span data-stu-id="2b213-186">However, a check of the local filesystem can see that a file called `42` was written, with the contents `36`.</span></span>

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

<span data-ttu-id="2b213-187">A tentativa de usar a comparação inversa `<` (menor que) produz um erro do sistema:</span><span class="sxs-lookup"><span data-stu-id="2b213-187">Attempting to use the reverse comparison `<` (less than), yields a system error:</span></span>

```powershell
PS> if (36 < 42) { "true" } else { "false" }
At line:1 char:8
+ if (36 < 42) { "true" } else { "false" }
+        ~
The '<' operator is reserved for future use.
    + CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : RedirectionNotSupported
```

<span data-ttu-id="2b213-188">Se a comparação numérica for a operação necessária `-lt` e `-gt` deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="2b213-188">If numeric comparison is the required operation, `-lt` and `-gt` should be used.</span></span> <span data-ttu-id="2b213-189">Para obter mais informações, consulte o `-gt` operador em [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).</span><span class="sxs-lookup"><span data-stu-id="2b213-189">For more information, see the `-gt` operator in [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b213-190">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b213-190">See also</span></span>

- [<span data-ttu-id="2b213-191">Out-File</span><span class="sxs-lookup"><span data-stu-id="2b213-191">Out-File</span></span>](xref:Microsoft.PowerShell.Utility.Out-File)
- [<span data-ttu-id="2b213-192">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="2b213-192">Tee-Object</span></span>](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [<span data-ttu-id="2b213-193">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="2b213-193">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="2b213-194">Write-Error</span><span class="sxs-lookup"><span data-stu-id="2b213-194">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="2b213-195">Write-Host</span><span class="sxs-lookup"><span data-stu-id="2b213-195">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="2b213-196">Write-Information</span><span class="sxs-lookup"><span data-stu-id="2b213-196">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="2b213-197">Write-Output</span><span class="sxs-lookup"><span data-stu-id="2b213-197">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="2b213-198">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="2b213-198">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="2b213-199">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="2b213-199">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="2b213-200">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="2b213-200">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="2b213-201">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="2b213-201">about_Output_Streams</span></span>](about_Output_Streams.md)
- [<span data-ttu-id="2b213-202">about_Operators</span><span class="sxs-lookup"><span data-stu-id="2b213-202">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="2b213-203">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="2b213-203">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="2b213-204">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="2b213-204">about_Path_Syntax</span></span>](about_Path_Syntax.md)
