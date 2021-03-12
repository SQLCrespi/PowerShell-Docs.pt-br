---
description: Explica como usar a `pwsh` interface de linha de comando. Exibe os parâmetros de linha de comando e descreve a sintaxe.
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pwsh
ms.openlocfilehash: eae22efa9302826d3e1303dd933d8ea114123ab9
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195996"
---
# <a name="about-pwsh"></a><span data-ttu-id="3b036-104">Sobre o pwsh</span><span class="sxs-lookup"><span data-stu-id="3b036-104">About pwsh</span></span>

## <a name="short-description"></a><span data-ttu-id="3b036-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="3b036-105">Short Description</span></span>
<span data-ttu-id="3b036-106">Explica como usar a `pwsh` interface de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3b036-106">Explains how to use the `pwsh` command-line interface.</span></span> <span data-ttu-id="3b036-107">Exibe os parâmetros de linha de comando e descreve a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="3b036-107">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="3b036-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="3b036-108">Long Description</span></span>

## <a name="syntax"></a><span data-ttu-id="3b036-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3b036-109">Syntax</span></span>

```
pwsh[.exe]
   [[-File] <filePath> [args]]
   [-Command { - | <script-block> [-args <arg-array>]
                 | <string> [<CommandParameters>] } ]
   [-ConfigurationName <string>]
   [-CustomPipeName <string>]
   [-EncodedCommand <Base64EncodedCommand>]
   [-ExecutionPolicy <ExecutionPolicy>]
   [-InputFormat {Text | XML}]
   [-Interactive]
   [-Login]
   [-MTA]
   [-NoExit]
   [-NoLogo]
   [-NonInteractive]
   [-NoProfile]
   [-OutputFormat {Text | XML}]
   [-SettingsFile <SettingsFilePath>]
   [-SSHServerMode]
   [-STA]
   [-Version]
   [-WindowStyle <style>]
   [-WorkingDirectory <directoryPath>]

pwsh[.exe] -h | -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="3b036-110">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3b036-110">Parameters</span></span>

<span data-ttu-id="3b036-111">Todos os parâmetros não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3b036-111">All parameters are case-insensitive.</span></span>

### <a name="-file---f"></a><span data-ttu-id="3b036-112">-Arquivo | -f</span><span class="sxs-lookup"><span data-stu-id="3b036-112">-File | -f</span></span>

<span data-ttu-id="3b036-113">Se o valor de `File` for `-` , o texto do comando será lido da entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="3b036-113">If the value of `File` is `-`, the command text is read from standard input.</span></span>
<span data-ttu-id="3b036-114">`pwsh -File -`A execução sem entrada padrão redirecionada inicia uma sessão normal.</span><span class="sxs-lookup"><span data-stu-id="3b036-114">Running `pwsh -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="3b036-115">Isso é o mesmo que não especificar o `File` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3b036-115">This is the same as not specifying the `File` parameter at all.</span></span>

<span data-ttu-id="3b036-116">Esse será o parâmetro padrão se nenhum parâmetro estiver presente, mas os valores estiverem presentes na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3b036-116">This is the default parameter if no parameters are present but values are present in the command line.</span></span> <span data-ttu-id="3b036-117">O script especificado é executado no escopo local ("dot-sourceed"), de modo que as funções e variáveis que o script cria estão disponíveis na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3b036-117">The specified script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="3b036-118">Insira o caminho do arquivo de script e quaisquer parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3b036-118">Enter the script file path and any parameters.</span></span> <span data-ttu-id="3b036-119">O arquivo deve ser o último parâmetro no comando, pois todos os caracteres digitados após o nome do parâmetro de arquivo são interpretados como o caminho do arquivo de script seguido pelos parâmetros do script.</span><span class="sxs-lookup"><span data-stu-id="3b036-119">File must be the last parameter in the command, because all characters typed after the File parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="3b036-120">Normalmente, os parâmetros de opção de um script são incluídos ou omitidos.</span><span class="sxs-lookup"><span data-stu-id="3b036-120">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="3b036-121">Por exemplo, o comando a seguir usa o parâmetro All do arquivo de script Get-Script.ps1: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="3b036-121">For example, the following command uses the All parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="3b036-122">Em casos raros, talvez seja necessário fornecer um valor **booliano** para um parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="3b036-122">In rare cases, you might need to provide a **Boolean** value for a switch parameter.</span></span> <span data-ttu-id="3b036-123">Para fornecer um valor **booliano** para um parâmetro de opção no valor do parâmetro **File** , use o parâmetro normalmente seguido imediatamente por dois-pontos e o valor booliano, como o seguinte: `-File .\Get-Script.ps1 -All:$False` .</span><span class="sxs-lookup"><span data-stu-id="3b036-123">To provide a **Boolean** value for a switch parameter in the value of the **File** parameter, Use the parameter normally followed immediately by a colon and the boolean value, such as the following: `-File .\Get-Script.ps1 -All:$False`.</span></span>

<span data-ttu-id="3b036-124">Os parâmetros passados para o script são passados como cadeias de caracteres literais (após a interpretação do shell atual).</span><span class="sxs-lookup"><span data-stu-id="3b036-124">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="3b036-125">Por exemplo, se você estiver no `cmd.exe` e desejar passar um valor de variável de ambiente, use a `cmd.exe` sintaxe: `pwsh -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="3b036-125">For example, if you are in `cmd.exe` and want to pass an environment variable value, you would use the `cmd.exe` syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="3b036-126">Por outro lado, `pwsh -File .\test.ps1 -TestParam $env:windir` a execução nos `cmd.exe` resultados no script recebe a cadeia de caracteres literal `$env:windir` porque não tem significado especial para o `cmd.exe` shell atual.</span><span class="sxs-lookup"><span data-stu-id="3b036-126">In contrast, running `pwsh -File .\test.ps1 -TestParam $env:windir` in `cmd.exe` results in the script receiving the literal string `$env:windir` because it has no special meaning to the current `cmd.exe` shell.</span></span> <span data-ttu-id="3b036-127">O `$env:windir` estilo da referência de variável de ambiente _pode_ ser usado dentro de um parâmetro de **comando** , já que ele é interpretado como código do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b036-127">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it is interpreted as PowerShell code.</span></span>

<span data-ttu-id="3b036-128">Da mesma forma, se você quiser executar o mesmo comando de um _script em lotes_, você usaria `%~dp0` em vez de `.\` ou `$PSScriptRoot` para representar o diretório de execução atual: `pwsh -File %~dp0test.ps1 -TestParam %windir%` .</span><span class="sxs-lookup"><span data-stu-id="3b036-128">Similarly, if you want to execute the same command from a _Batch script_, you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `pwsh -File %~dp0test.ps1 -TestParam %windir%`.</span></span> <span data-ttu-id="3b036-129">Se você, em vez disso `.\test.ps1` , o PowerShell geraria um erro porque ele não consegue encontrar o caminho literal `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="3b036-129">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="3b036-130">Quando o arquivo de script termina com um `exit` comando, o código de saída do processo é definido como o argumento numérico usado com o `exit` comando.</span><span class="sxs-lookup"><span data-stu-id="3b036-130">When the script file terminates with an `exit` command, the process exit code is set to the numeric argument used with the `exit` command.</span></span> <span data-ttu-id="3b036-131">Com o encerramento normal, o código de saída é sempre `0` .</span><span class="sxs-lookup"><span data-stu-id="3b036-131">With normal termination, the exit code is always `0`.</span></span>

<span data-ttu-id="3b036-132">Semelhante a `-Command` , quando ocorre um erro de terminação de script, o código de saída é definido como `1` .</span><span class="sxs-lookup"><span data-stu-id="3b036-132">Similar to `-Command`, when a script-terminating error occurs, the exit code is set to `1`.</span></span> <span data-ttu-id="3b036-133">No entanto, ao contrário de with `-Command` , quando a execução é interrompida com <kbd>Ctrl</kbd> - <kbd>C</kbd> , o código de saída é `0` .</span><span class="sxs-lookup"><span data-stu-id="3b036-133">However, unlike with `-Command`, when the execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd> the exit code is `0`.</span></span>

### <a name="-command---c"></a><span data-ttu-id="3b036-134">-Comando | -c</span><span class="sxs-lookup"><span data-stu-id="3b036-134">-Command | -c</span></span>

<span data-ttu-id="3b036-135">Executa os comandos especificados (e quaisquer parâmetros) como se eles fossem digitados no prompt de comando do PowerShell e, em seguida, são encerrados, a menos que o `NoExit` parâmetro seja especificado.</span><span class="sxs-lookup"><span data-stu-id="3b036-135">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="3b036-136">O valor do **comando** pode ser `-` , um bloco de script ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3b036-136">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="3b036-137">Se o valor do **comando** for `-` , o texto do comando será lido da entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="3b036-137">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="3b036-138">O parâmetro **Command** aceita apenas um bloco de script para execução quando ele pode reconhecer o valor passado para **Command** como um tipo de **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="3b036-138">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="3b036-139">Isso _só_ é possível durante a execução `pwsh` de outro host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b036-139">This is _only_ possible when running `pwsh` from another PowerShell host.</span></span> <span data-ttu-id="3b036-140">O tipo de **scriptblock** pode estar contido em uma variável existente, retornada de uma expressão ou analisado pelo host do PowerShell como um bloco de script literal entre chaves ( `{}` ), antes de ser passado para `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="3b036-140">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `pwsh`.</span></span>

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="3b036-141">No `cmd.exe` , não há tal coisa como um bloco de script (ou tipo **scriptblock** ), portanto, o valor passado para **Command** _sempre_ será uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3b036-141">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="3b036-142">Você pode escrever um bloco de script dentro da cadeia de caracteres, mas em vez de ser executado, ele se comportará exatamente como se tivesse sido digitado em um prompt comum do PowerShell, imprimindo o conteúdo do bloco de script para você.</span><span class="sxs-lookup"><span data-stu-id="3b036-142">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="3b036-143">Uma cadeia de caracteres passada para o **comando** ainda é executada como código do PowerShell, portanto, as chaves de bloco de script geralmente não são necessárias em primeiro lugar durante a execução do `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="3b036-143">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="3b036-144">Para executar um bloco de script embutido definido em uma cadeia de caracteres, o [operador de chamada](about_operators.md#special-operators) `&` pode ser usado:</span><span class="sxs-lookup"><span data-stu-id="3b036-144">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="3b036-145">Se o valor do **comando** for uma cadeia de caracteres, **Command** deverá ser o último parâmetro para pwsh, pois todos os argumentos após ele serão interpretados como parte do comando a ser executado.</span><span class="sxs-lookup"><span data-stu-id="3b036-145">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="3b036-146">Quando chamado de dentro de uma sessão existente do PowerShell, os resultados são retornados para o Shell pai como objetos XML desserializados, não objetos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="3b036-146">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="3b036-147">Para outros shells, os resultados são retornados como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3b036-147">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="3b036-148">Se o valor do **comando** for `-` , o texto do comando será lido da entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="3b036-148">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="3b036-149">Você deve redirecionar a entrada padrão ao usar o parâmetro de **comando** com entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="3b036-149">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="3b036-150">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3b036-150">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="3b036-151">Esse exemplo gera a saída a seguir:</span><span class="sxs-lookup"><span data-stu-id="3b036-151">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="3b036-152">O código de saída do processo é determinado pelo status do último comando (executado) dentro do bloco de script.</span><span class="sxs-lookup"><span data-stu-id="3b036-152">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="3b036-153">O código de saída é `0` quando `$?` é `$true` ou `1` quando `$?` é `$false` .</span><span class="sxs-lookup"><span data-stu-id="3b036-153">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="3b036-154">Se o último comando for um programa externo ou um script do PowerShell que define explicitamente um código de saída diferente de `0` ou `1` , esse código de saída será convertido em `1` para o código de saída do processo.</span><span class="sxs-lookup"><span data-stu-id="3b036-154">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="3b036-155">Para preservar o código de saída específico, adicione `exit $LASTEXITCODE` à cadeia de caracteres de comando ou ao bloco de script.</span><span class="sxs-lookup"><span data-stu-id="3b036-155">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="3b036-156">Da mesma forma, o valor 1 é retornado quando um erro de encerramento de script (encerramento de runspace), como um `throw` ou `-ErrorAction Stop` , ocorre ou quando a execução é interrompida com <kbd>Ctrl</kbd> - <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3b036-156">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

### <a name="-configurationname---config"></a><span data-ttu-id="3b036-157">-ConfigurationName | -configuração</span><span class="sxs-lookup"><span data-stu-id="3b036-157">-ConfigurationName | -config</span></span>

<span data-ttu-id="3b036-158">Especifica um ponto de extremidade de configuração no qual o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="3b036-158">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="3b036-159">Pode ser qualquer ponto de extremidade registrado no computador local, incluindo os pontos de extremidade remotos de comunicação remota do PowerShell ou um ponto de extremidades personalizado com recursos de função de usuário específicos.</span><span class="sxs-lookup"><span data-stu-id="3b036-159">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

<span data-ttu-id="3b036-160">Exemplo: `pwsh -ConfigurationName AdminRoles`</span><span class="sxs-lookup"><span data-stu-id="3b036-160">Example: `pwsh -ConfigurationName AdminRoles`</span></span>

### <a name="-custompipename"></a><span data-ttu-id="3b036-161">-CustomPipeName</span><span class="sxs-lookup"><span data-stu-id="3b036-161">-CustomPipeName</span></span>

<span data-ttu-id="3b036-162">Especifica o nome a ser usado para um servidor IPC adicional (pipe nomeado) usado para depuração e outra comunicação entre processos.</span><span class="sxs-lookup"><span data-stu-id="3b036-162">Specifies the name to use for an additional IPC server (named pipe) used for debugging and other cross-process communication.</span></span> <span data-ttu-id="3b036-163">Isso oferece um mecanismo previsível para se conectar a outras instâncias do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b036-163">This offers a predictable mechanism for connecting to other PowerShell instances.</span></span> <span data-ttu-id="3b036-164">Normalmente usado com o parâmetro **CustomPipeName** em `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="3b036-164">Typically used with the **CustomPipeName** parameter on `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="3b036-165">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="3b036-165">This parameter was introduced in PowerShell 6.2.</span></span>

<span data-ttu-id="3b036-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3b036-166">For example:</span></span>

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a><span data-ttu-id="3b036-167">-EncodedCommand | -e | -EC</span><span class="sxs-lookup"><span data-stu-id="3b036-167">-EncodedCommand | -e | -ec</span></span>

<span data-ttu-id="3b036-168">Aceita uma versão de cadeia de caracteres codificada em Base64 de um comando.</span><span class="sxs-lookup"><span data-stu-id="3b036-168">Accepts a Base64-encoded string version of a command.</span></span> <span data-ttu-id="3b036-169">Use esse parâmetro para enviar comandos ao PowerShell que exigem cotas aninhadas complexas.</span><span class="sxs-lookup"><span data-stu-id="3b036-169">Use this parameter to submit commands to PowerShell that require complex, nested quoting.</span></span> <span data-ttu-id="3b036-170">A representação Base64 deve ser uma cadeia de caracteres codificada em UTF-16LE.</span><span class="sxs-lookup"><span data-stu-id="3b036-170">The Base64 representation must be a UTF-16LE encoded string.</span></span>

<span data-ttu-id="3b036-171">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3b036-171">For example:</span></span>

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a><span data-ttu-id="3b036-172">-ExecutionPolicy | -ex | -EP</span><span class="sxs-lookup"><span data-stu-id="3b036-172">-ExecutionPolicy | -ex | -ep</span></span>

<span data-ttu-id="3b036-173">Define a política de execução padrão para a sessão atual e salva-a na `$env:PSExecutionPolicyPreference` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="3b036-173">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="3b036-174">Esse parâmetro não altera as políticas de execução configuradas de forma persistente.</span><span class="sxs-lookup"><span data-stu-id="3b036-174">This parameter does not change the persistently configured execution policies.</span></span>

<span data-ttu-id="3b036-175">Esse parâmetro se aplica somente a computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="3b036-175">This parameter only applies to Windows computers.</span></span> <span data-ttu-id="3b036-176">A `$env:PSExecutionPolicyPreference` variável de ambiente não existe em plataformas que não sejam do Windows.</span><span class="sxs-lookup"><span data-stu-id="3b036-176">The `$env:PSExecutionPolicyPreference` environment variable does not exist on non-Windows platforms.</span></span>

### <a name="-inputformat---inp---if"></a><span data-ttu-id="3b036-177">-InputFormat | -inp | -se</span><span class="sxs-lookup"><span data-stu-id="3b036-177">-InputFormat | -inp | -if</span></span>

<span data-ttu-id="3b036-178">Descreve o formato dos dados enviados ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b036-178">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="3b036-179">Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).</span><span class="sxs-lookup"><span data-stu-id="3b036-179">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-interactive---i"></a><span data-ttu-id="3b036-180">-Interativo | -i</span><span class="sxs-lookup"><span data-stu-id="3b036-180">-Interactive | -i</span></span>

<span data-ttu-id="3b036-181">Apresente um prompt interativo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="3b036-181">Present an interactive prompt to the user.</span></span> <span data-ttu-id="3b036-182">Inverso para parâmetro não interativo.</span><span class="sxs-lookup"><span data-stu-id="3b036-182">Inverse for NonInteractive parameter.</span></span>

### <a name="-login---l"></a><span data-ttu-id="3b036-183">-Logon | -l</span><span class="sxs-lookup"><span data-stu-id="3b036-183">-Login | -l</span></span>

<span data-ttu-id="3b036-184">No Linux e no macOS, o inicia o PowerShell como um shell de logon, usando/bin/sh para executar perfis de logon, como/etc/profile e ~/.Profile.</span><span class="sxs-lookup"><span data-stu-id="3b036-184">On Linux and macOS, starts PowerShell as a login shell, using /bin/sh to execute login profiles such as /etc/profile and ~/.profile.</span></span>
<span data-ttu-id="3b036-185">No Windows, essa opção não faz nada.</span><span class="sxs-lookup"><span data-stu-id="3b036-185">On Windows, this switch does nothing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b036-186">Esse parâmetro deve ser primeiro para iniciar o PowerShell como um shell de logon.</span><span class="sxs-lookup"><span data-stu-id="3b036-186">This parameter must come first to start PowerShell as a login shell.</span></span>
> <span data-ttu-id="3b036-187">Passar esse parâmetro em outra posição será ignorado.</span><span class="sxs-lookup"><span data-stu-id="3b036-187">Passing this parameter in another position will be ignored.</span></span>

<span data-ttu-id="3b036-188">Para configurar `pwsh` o Shell de logon em sistemas operacionais semelhantes ao Unix:</span><span class="sxs-lookup"><span data-stu-id="3b036-188">To set up `pwsh` as the login shell on UNIX-like operating systems:</span></span>

- <span data-ttu-id="3b036-189">Verifique se o caminho absoluto completo para `pwsh` está listado em `/etc/shells`</span><span class="sxs-lookup"><span data-stu-id="3b036-189">Verify that the full absolute path to `pwsh` is listed under `/etc/shells`</span></span>
  - <span data-ttu-id="3b036-190">Esse caminho geralmente é algo como `/usr/bin/pwsh` no Linux ou `/usr/local/bin/pwsh` no MacOS</span><span class="sxs-lookup"><span data-stu-id="3b036-190">This path is usually something like `/usr/bin/pwsh` on Linux or `/usr/local/bin/pwsh` on macOS</span></span>
  - <span data-ttu-id="3b036-191">Com alguns métodos de instalação, essa entrada será adicionada automaticamente no momento da instalação</span><span class="sxs-lookup"><span data-stu-id="3b036-191">With some installation methods, this entry will be added automatically at installation time</span></span>
  - <span data-ttu-id="3b036-192">Se `pwsh` não estiver presente no `/etc/shells` , use um editor para acrescentar o caminho à `pwsh` última linha.</span><span class="sxs-lookup"><span data-stu-id="3b036-192">If `pwsh` is not present in `/etc/shells`, use an editor to append the path to `pwsh` on the last line.</span></span> <span data-ttu-id="3b036-193">Isso requer privilégios elevados para editar.</span><span class="sxs-lookup"><span data-stu-id="3b036-193">This requires elevated privileges to edit.</span></span>
- <span data-ttu-id="3b036-194">Use o utilitário [chsh](https://linux.die.net/man/1/chsh) para definir o Shell do usuário atual para `pwsh` :</span><span class="sxs-lookup"><span data-stu-id="3b036-194">Use the [chsh](https://linux.die.net/man/1/chsh) utility to set your current user's shell to `pwsh`:</span></span>

  ```sh
  chsh -s /usr/bin/pwsh
  ```

> [!WARNING]
> <span data-ttu-id="3b036-195">`pwsh`A configuração como o Shell de logon atualmente não tem suporte no subsistema do Windows para Linux (WSL) e a tentativa de definir `pwsh` como o Shell de logon pode levar a não conseguir iniciar o WSL interativamente.</span><span class="sxs-lookup"><span data-stu-id="3b036-195">Setting `pwsh` as the login shell is currently not supported on Windows Subsystem for Linux (WSL), and attempting to set `pwsh` as the login shell there may lead to being unable to start WSL interactively.</span></span>

### <a name="-mta"></a><span data-ttu-id="3b036-196">-MTA</span><span class="sxs-lookup"><span data-stu-id="3b036-196">-MTA</span></span>

<span data-ttu-id="3b036-197">Inicie o PowerShell usando um apartamento multi-threaded.</span><span class="sxs-lookup"><span data-stu-id="3b036-197">Start PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="3b036-198">Essa opção só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="3b036-198">This switch is only available on Windows.</span></span>

### <a name="-noexit---noe"></a><span data-ttu-id="3b036-199">-NoExit | -noe</span><span class="sxs-lookup"><span data-stu-id="3b036-199">-NoExit | -noe</span></span>

<span data-ttu-id="3b036-200">Não é encerrado depois de executar comandos de inicialização.</span><span class="sxs-lookup"><span data-stu-id="3b036-200">Does not exit after running startup commands.</span></span>

<span data-ttu-id="3b036-201">Exemplo: `pwsh -NoExit -Command Get-Date`</span><span class="sxs-lookup"><span data-stu-id="3b036-201">Example: `pwsh -NoExit -Command Get-Date`</span></span>

### <a name="-nologo---nol"></a><span data-ttu-id="3b036-202">-Nologo | -nol</span><span class="sxs-lookup"><span data-stu-id="3b036-202">-NoLogo | -nol</span></span>

<span data-ttu-id="3b036-203">Oculta a faixa de direitos autorais na inicialização de sessões interativas.</span><span class="sxs-lookup"><span data-stu-id="3b036-203">Hides the copyright banner at startup of interactive sessions.</span></span>

### <a name="-noninteractive---noni"></a><span data-ttu-id="3b036-204">-Não interativo | -noni</span><span class="sxs-lookup"><span data-stu-id="3b036-204">-NonInteractive | -noni</span></span>

<span data-ttu-id="3b036-205">Não exibe um prompt interativo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="3b036-205">Does not present an interactive prompt to the user.</span></span> <span data-ttu-id="3b036-206">Quaisquer tentativas de usar recursos interativos, como `Read-Host` ou prompts de confirmação, resultam em erros de encerramento de instrução.</span><span class="sxs-lookup"><span data-stu-id="3b036-206">Any attempts to use interactive features, like `Read-Host` or confirmation prompts, result in statement-terminating errors.</span></span>

### <a name="-noprofile---nop"></a><span data-ttu-id="3b036-207">-NoProfile | -Nop</span><span class="sxs-lookup"><span data-stu-id="3b036-207">-NoProfile | -nop</span></span>

<span data-ttu-id="3b036-208">Não carrega os perfis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b036-208">Does not load the PowerShell profiles.</span></span>

### <a name="-outputformat---o---of"></a><span data-ttu-id="3b036-209">-OutputFormat | -o | -de</span><span class="sxs-lookup"><span data-stu-id="3b036-209">-OutputFormat | -o | -of</span></span>

<span data-ttu-id="3b036-210">Determina como a saída do PowerShell é formatada.</span><span class="sxs-lookup"><span data-stu-id="3b036-210">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="3b036-211">Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).</span><span class="sxs-lookup"><span data-stu-id="3b036-211">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

<span data-ttu-id="3b036-212">Exemplo: `pwsh -o XML -c Get-Date`</span><span class="sxs-lookup"><span data-stu-id="3b036-212">Example: `pwsh -o XML -c Get-Date`</span></span>

<span data-ttu-id="3b036-213">Quando chamado com uma sessão do PowerShell, você obtém objetos desserializados como cadeias de caracteres de saída, e não simples.</span><span class="sxs-lookup"><span data-stu-id="3b036-213">When called withing a PowerShell session, you get deserialized objects as output rather plain strings.</span></span> <span data-ttu-id="3b036-214">Quando chamado de outros shells, a saída é dados de cadeia de caracteres formatados como texto CLIXML.</span><span class="sxs-lookup"><span data-stu-id="3b036-214">When called from other shells, the output is string data formatted as CLIXML text.</span></span>

### <a name="-settingsfile---settings"></a><span data-ttu-id="3b036-215">-SettingsFile | -configurações</span><span class="sxs-lookup"><span data-stu-id="3b036-215">-SettingsFile | -settings</span></span>

<span data-ttu-id="3b036-216">Substitui o arquivo de configurações de todo o sistema da `powershell.config.json` sessão.</span><span class="sxs-lookup"><span data-stu-id="3b036-216">Overrides the system-wide `powershell.config.json` settings file for the session.</span></span> <span data-ttu-id="3b036-217">Por padrão, as configurações de todo o sistema são lidas do `powershell.config.json` no `$PSHOME` diretório.</span><span class="sxs-lookup"><span data-stu-id="3b036-217">By default, system-wide settings are read from the `powershell.config.json` in the `$PSHOME` directory.</span></span>

<span data-ttu-id="3b036-218">Observe que essas configurações não são usadas pelo ponto de extremidade especificado pelo `-ConfigurationName` argumento.</span><span class="sxs-lookup"><span data-stu-id="3b036-218">Note that these settings are not used by the endpoint specified by the `-ConfigurationName` argument.</span></span>

<span data-ttu-id="3b036-219">Exemplo: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span><span class="sxs-lookup"><span data-stu-id="3b036-219">Example: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span></span>

### <a name="-sshservermode---sshs"></a><span data-ttu-id="3b036-220">-SSHServerMode | -sshs</span><span class="sxs-lookup"><span data-stu-id="3b036-220">-SSHServerMode | -sshs</span></span>

<span data-ttu-id="3b036-221">Usado em sshd_config para executar o PowerShell como um subsistema SSH.</span><span class="sxs-lookup"><span data-stu-id="3b036-221">Used in sshd_config for running PowerShell as an SSH subsystem.</span></span> <span data-ttu-id="3b036-222">Ela não é destinada nem tem suporte para nenhum outro uso.</span><span class="sxs-lookup"><span data-stu-id="3b036-222">It is not intended or supported for any other use.</span></span>

### <a name="-sta"></a><span data-ttu-id="3b036-223">-STA</span><span class="sxs-lookup"><span data-stu-id="3b036-223">-STA</span></span>

<span data-ttu-id="3b036-224">Inicie o PowerShell usando um apartamento de thread único.</span><span class="sxs-lookup"><span data-stu-id="3b036-224">Start PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="3b036-225">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="3b036-225">This is the default.</span></span> <span data-ttu-id="3b036-226">Essa opção só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="3b036-226">This switch is only available on Windows.</span></span>

### <a name="-version---v"></a><span data-ttu-id="3b036-227">-Versão | -v</span><span class="sxs-lookup"><span data-stu-id="3b036-227">-Version | -v</span></span>

<span data-ttu-id="3b036-228">Exibe a versão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b036-228">Displays the version of PowerShell.</span></span> <span data-ttu-id="3b036-229">Parâmetros adicionais são ignorados.</span><span class="sxs-lookup"><span data-stu-id="3b036-229">Additional parameters are ignored.</span></span>

### <a name="-windowstyle---w"></a><span data-ttu-id="3b036-230">-WindowStyle | -w</span><span class="sxs-lookup"><span data-stu-id="3b036-230">-WindowStyle | -w</span></span>

<span data-ttu-id="3b036-231">Define o estilo da janela da sessão.</span><span class="sxs-lookup"><span data-stu-id="3b036-231">Sets the window style for the session.</span></span> <span data-ttu-id="3b036-232">Os valores válidos são Normal, Minimized, Maximized e Hidden.</span><span class="sxs-lookup"><span data-stu-id="3b036-232">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-workingdirectory---wd"></a><span data-ttu-id="3b036-233">-WorkingDirectory | -WD</span><span class="sxs-lookup"><span data-stu-id="3b036-233">-WorkingDirectory | -wd</span></span>

<span data-ttu-id="3b036-234">Define o diretório de trabalho inicial executando na inicialização.</span><span class="sxs-lookup"><span data-stu-id="3b036-234">Sets the initial working directory by executing at startup.</span></span> <span data-ttu-id="3b036-235">Há suporte para qualquer caminho de arquivo válido do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b036-235">Any valid PowerShell file path is supported.</span></span>

<span data-ttu-id="3b036-236">Para iniciar o PowerShell em seu diretório base, use: `pwsh -WorkingDirectory ~`</span><span class="sxs-lookup"><span data-stu-id="3b036-236">To start PowerShell in your home directory, use: `pwsh -WorkingDirectory ~`</span></span>

### <a name="-help---"></a><span data-ttu-id="3b036-237">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="3b036-237">-Help, -?, /?</span></span>

<span data-ttu-id="3b036-238">Exibe a ajuda para `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="3b036-238">Displays help for `pwsh`.</span></span> <span data-ttu-id="3b036-239">Se você estiver digitando um comando pwsh no PowerShell, preceda os parâmetros de comando com um hífen ( `-` ), não uma barra "/" ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="3b036-239">If you are typing a pwsh command in PowerShell, prepend the command parameters with a hyphen (`-`), not a forward slash (`/`).</span></span>
