---
description: Explica como usar a `powershell.exe` interface de linha de comando. Exibe os parâmetros de linha de comando e descreve a sintaxe.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: 4025630ebb3abe4c0598c85940cfce383e9c7890
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726648"
---
# <a name="about-powershellexe"></a><span data-ttu-id="80a95-105">Sobre PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="80a95-105">About PowerShell.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="80a95-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="80a95-106">Short Description</span></span>
<span data-ttu-id="80a95-107">Explica como usar a `powershell.exe` interface de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="80a95-107">Explains how to use the `powershell.exe` command-line interface.</span></span> <span data-ttu-id="80a95-108">Exibe os parâmetros de linha de comando e descreve a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="80a95-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="80a95-109">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="80a95-109">Long Description</span></span>

### <a name="syntax"></a><span data-ttu-id="80a95-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80a95-110">SYNTAX</span></span>

```
PowerShell[.exe]
    [-PSConsoleFile <file> | -Version <version>]
    [-NoLogo]
    [-NoExit]
    [-Sta]
    [-Mta]
    [-NoProfile]
    [-NonInteractive]
    [-InputFormat {Text | XML}]
    [-OutputFormat {Text | XML}]
    [-WindowStyle <style>]
    [-EncodedCommand <Base64EncodedCommand>]
    [-ConfigurationName <string>]
    [-File - | <filePath> <args>]
    [-ExecutionPolicy <ExecutionPolicy>]
    [-Command - | { <script-block> [-args <arg-array>] }
                | { <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

### <a name="parameters"></a><span data-ttu-id="80a95-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="80a95-111">Parameters</span></span>

#### <a name="-psconsolefile-filepath"></a><span data-ttu-id="80a95-112">-PSConsoleFile \<FilePath\></span><span class="sxs-lookup"><span data-stu-id="80a95-112">-PSConsoleFile \<FilePath\></span></span>

<span data-ttu-id="80a95-113">Carrega o arquivo de console do PowerShell especificado.</span><span class="sxs-lookup"><span data-stu-id="80a95-113">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="80a95-114">Insira o caminho e o nome do arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="80a95-114">Enter the path and name of the console file.</span></span> <span data-ttu-id="80a95-115">Para criar um arquivo de console, use o cmdlet Export-Console no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80a95-115">To create a console file, use the Export-Console cmdlet in PowerShell.</span></span>

#### <a name="-version-powershell-version"></a><span data-ttu-id="80a95-116">-Version \<PowerShell Version\></span><span class="sxs-lookup"><span data-stu-id="80a95-116">-Version \<PowerShell Version\></span></span>

<span data-ttu-id="80a95-117">Inicia a versão especificada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80a95-117">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="80a95-118">Os valores válidos são 2.0 e 3.0.</span><span class="sxs-lookup"><span data-stu-id="80a95-118">Valid values are 2.0 and 3.0.</span></span> <span data-ttu-id="80a95-119">A versão que você especificar deve estar instalada no sistema.</span><span class="sxs-lookup"><span data-stu-id="80a95-119">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="80a95-120">Se o Windows PowerShell 3,0 estiver instalado no computador, "3,0" será a versão padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-120">If Windows PowerShell 3.0 is installed on the computer, "3.0" is the default version.</span></span>
<span data-ttu-id="80a95-121">Caso contrário, "2,0" é a versão padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-121">Otherwise, "2.0" is the default version.</span></span> <span data-ttu-id="80a95-122">Para obter mais informações, consulte [instalando o PowerShell](/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="80a95-122">For more information, see [Installing PowerShell](/powershell/scripting/install/installing-windows-powershell).</span></span>

#### <a name="-nologo"></a><span data-ttu-id="80a95-123">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="80a95-123">-NoLogo</span></span>

<span data-ttu-id="80a95-124">Oculta a faixa de direitos autorais na inicialização.</span><span class="sxs-lookup"><span data-stu-id="80a95-124">Hides the copyright banner at startup.</span></span>

#### <a name="-noexit"></a><span data-ttu-id="80a95-125">-NoExit</span><span class="sxs-lookup"><span data-stu-id="80a95-125">-NoExit</span></span>

<span data-ttu-id="80a95-126">Não é encerrado depois de executar comandos de inicialização.</span><span class="sxs-lookup"><span data-stu-id="80a95-126">Does not exit after running startup commands.</span></span>

#### <a name="-sta"></a><span data-ttu-id="80a95-127">-Sta</span><span class="sxs-lookup"><span data-stu-id="80a95-127">-Sta</span></span>

<span data-ttu-id="80a95-128">Inicia o PowerShell usando um single-threaded apartment.</span><span class="sxs-lookup"><span data-stu-id="80a95-128">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="80a95-129">No Windows PowerShell 2.0, o MTA (Multi-Threaded Apartment) é o padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-129">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="80a95-130">No Windows PowerShell 3.0, o STA (Single-Threaded Apartment) é o padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-130">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-mta"></a><span data-ttu-id="80a95-131">-Mta</span><span class="sxs-lookup"><span data-stu-id="80a95-131">-Mta</span></span>

<span data-ttu-id="80a95-132">Inicia o PowerShell usando um multi-threaded apartment.</span><span class="sxs-lookup"><span data-stu-id="80a95-132">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="80a95-133">Este parâmetro é introduzido no PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="80a95-133">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="80a95-134">No PowerShell 2.0, o MTA (Multi-Threaded Apartment) é o padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-134">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="80a95-135">No PowerShell 3.0, o STA (Single-Threaded Apartment) é o padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-135">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-noprofile"></a><span data-ttu-id="80a95-136">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="80a95-136">-NoProfile</span></span>

<span data-ttu-id="80a95-137">Não carrega o perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80a95-137">Does not load the PowerShell profile.</span></span>

#### <a name="-noninteractive"></a><span data-ttu-id="80a95-138">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="80a95-138">-NonInteractive</span></span>

<span data-ttu-id="80a95-139">Não exibe um prompt interativo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="80a95-139">Does not present an interactive prompt to the user.</span></span>

#### <a name="-inputformat-text--xml"></a><span data-ttu-id="80a95-140">-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="80a95-140">-InputFormat {Text | XML}</span></span>

<span data-ttu-id="80a95-141">Descreve o formato dos dados enviados ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80a95-141">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="80a95-142">Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).</span><span class="sxs-lookup"><span data-stu-id="80a95-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-outputformat-text--xml"></a><span data-ttu-id="80a95-143">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="80a95-143">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="80a95-144">Determina como a saída do PowerShell é formatada.</span><span class="sxs-lookup"><span data-stu-id="80a95-144">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="80a95-145">Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).</span><span class="sxs-lookup"><span data-stu-id="80a95-145">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-windowstyle-window-style"></a><span data-ttu-id="80a95-146">-WindowStyle \<Window style\></span><span class="sxs-lookup"><span data-stu-id="80a95-146">-WindowStyle \<Window style\></span></span>

<span data-ttu-id="80a95-147">Define o estilo da janela da sessão.</span><span class="sxs-lookup"><span data-stu-id="80a95-147">Sets the window style for the session.</span></span> <span data-ttu-id="80a95-148">Os valores válidos são Normal, Minimized, Maximized e Hidden.</span><span class="sxs-lookup"><span data-stu-id="80a95-148">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

#### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="80a95-149">-EncodedCommand \<Base64EncodedCommand\></span><span class="sxs-lookup"><span data-stu-id="80a95-149">-EncodedCommand \<Base64EncodedCommand\></span></span>

<span data-ttu-id="80a95-150">Aceita uma versão de cadeia de caracteres com codificação de base 64 de um comando.</span><span class="sxs-lookup"><span data-stu-id="80a95-150">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="80a95-151">Use esse parâmetro para enviar comandos ao PowerShell que exigem aspas ou chaves complexas.</span><span class="sxs-lookup"><span data-stu-id="80a95-151">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span> <span data-ttu-id="80a95-152">A cadeia de caracteres deve ser formatada usando a codificação de caracteres UTF-16LE.</span><span class="sxs-lookup"><span data-stu-id="80a95-152">The string must be formatted using UTF-16LE character encoding.</span></span>

#### <a name="-configurationname-string"></a><span data-ttu-id="80a95-153">-ConfigurationName \<string\></span><span class="sxs-lookup"><span data-stu-id="80a95-153">-ConfigurationName \<string\></span></span>

<span data-ttu-id="80a95-154">Especifica um ponto de extremidade de configuração no qual o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="80a95-154">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="80a95-155">Pode ser qualquer ponto de extremidade registrado no computador local, incluindo os pontos de extremidade remotos de comunicação remota do PowerShell ou um ponto de extremidades personalizado com recursos de função de usuário específicos.</span><span class="sxs-lookup"><span data-stu-id="80a95-155">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

#### <a name="-file----filepath-args"></a><span data-ttu-id="80a95-156">-Arquivo-| \<filePath\>\<args\></span><span class="sxs-lookup"><span data-stu-id="80a95-156">-File - | \<filePath\> \<args\></span></span>

<span data-ttu-id="80a95-157">Se o valor do **arquivo** for "-", o texto do comando será lido da entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-157">If the value of **File** is "-", the command text is read from standard input.</span></span>
<span data-ttu-id="80a95-158">`powershell -File -`A execução sem entrada padrão redirecionada inicia uma sessão normal.</span><span class="sxs-lookup"><span data-stu-id="80a95-158">Running `powershell -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="80a95-159">Isso é o mesmo que não especificar o parâmetro **File** .</span><span class="sxs-lookup"><span data-stu-id="80a95-159">This is the same as not specifying the **File** parameter at all.</span></span>

<span data-ttu-id="80a95-160">Se o valor de **File** for um caminho de arquivo, o script será executado no escopo local ("dot-sourceed"), para que as funções e variáveis que o script cria estejam disponíveis na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="80a95-160">If the value of **File** is a file path, the script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="80a95-161">Insira o caminho do arquivo de script e quaisquer parâmetros.</span><span class="sxs-lookup"><span data-stu-id="80a95-161">Enter the script file path and any parameters.</span></span> <span data-ttu-id="80a95-162">**File** deve ser o último parâmetro no comando.</span><span class="sxs-lookup"><span data-stu-id="80a95-162">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="80a95-163">Todos os valores digitados após o parâmetro **File** são interpretados como o caminho do arquivo de script e os parâmetros passados para esse script.</span><span class="sxs-lookup"><span data-stu-id="80a95-163">All values typed after the **File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="80a95-164">Os parâmetros passados para o script são passados como cadeias de caracteres literais (após a interpretação do shell atual).</span><span class="sxs-lookup"><span data-stu-id="80a95-164">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="80a95-165">Por exemplo, se você estiver em **cmd.exe** e quiser passar um valor de variável de ambiente, use a sintaxe **cmd.exe** : `powershell.exe -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="80a95-165">For example, if you are in **cmd.exe** and want to pass an environment variable value, you would use the **cmd.exe** syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="80a95-166">Por outro lado, `powershell.exe -File .\test.ps1 -TestParam $env:windir` a execução em **cmd.exe** resulta no script que recebe a cadeia de caracteres literal `$env:windir` porque não tem nenhum significado especial para o Shell **cmd.exe** atual.</span><span class="sxs-lookup"><span data-stu-id="80a95-166">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in **cmd.exe** results in the script receiving the literal string `$env:windir` because it has no special meaning to the current **cmd.exe** shell.</span></span> <span data-ttu-id="80a95-167">O `$env:windir` estilo da referência de variável de ambiente _pode_ ser usado dentro de um parâmetro de **comando** , já que ele será interpretado como código do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80a95-167">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it will be interpreted as PowerShell code.</span></span>

<span data-ttu-id="80a95-168">Da mesma forma, se você quiser executar o mesmo comando de um **script em lotes**, você usaria `%~dp0` em vez de `.\` ou `$PSScriptRoot` para representar o diretório de execução atual: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` .</span><span class="sxs-lookup"><span data-stu-id="80a95-168">Similarly, if you want to execute the same command from a **Batch script**, you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%`.</span></span>
<span data-ttu-id="80a95-169">Se você, em vez disso `.\test.ps1` , o PowerShell geraria um erro porque ele não consegue encontrar o caminho literal `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="80a95-169">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="80a95-170">Quando o valor do **arquivo** for um caminho de arquivo, o **arquivo** _deverá_ ser o último parâmetro no comando, pois os caracteres digitados após o nome do parâmetro de **arquivo** serão interpretados como o caminho do arquivo de script seguido pelos parâmetros do script.</span><span class="sxs-lookup"><span data-stu-id="80a95-170">When the value of **File** is a file path, **File** _must_ be the last parameter in the command because any characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="80a95-171">Você pode incluir os parâmetros e os valores do script no valor do parâmetro **File** .</span><span class="sxs-lookup"><span data-stu-id="80a95-171">You can include the script parameters and values in the value of the **File** parameter.</span></span> <span data-ttu-id="80a95-172">Por exemplo: `-File .\Get-Script.ps1 -Domain Central`</span><span class="sxs-lookup"><span data-stu-id="80a95-172">For example: `-File .\Get-Script.ps1 -Domain Central`</span></span>

<span data-ttu-id="80a95-173">Normalmente, os parâmetros de opção de um script são incluídos ou omitidos.</span><span class="sxs-lookup"><span data-stu-id="80a95-173">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="80a95-174">Por exemplo, o comando a seguir usa o parâmetro **All** do `Get-Script.ps1` arquivo de script: `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="80a95-174">For example, the following command uses the **All** parameter of the `Get-Script.ps1` script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="80a95-175">Em casos raros, talvez seja necessário fornecer um valor **booliano** para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="80a95-175">In rare cases, you might need to provide a **Boolean** value for a parameter.</span></span>
<span data-ttu-id="80a95-176">Não é possível passar um valor booliano explícito para um parâmetro de opção ao executar um script dessa forma.</span><span class="sxs-lookup"><span data-stu-id="80a95-176">It is not possible to pass an explicit boolean value for a switch parameter when running a script in this way.</span></span> <span data-ttu-id="80a95-177">Essa limitação foi removida no PowerShell 6 ( `pwsh.exe` ).</span><span class="sxs-lookup"><span data-stu-id="80a95-177">This limitation was removed in PowerShell 6 (`pwsh.exe`).</span></span>

#### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="80a95-178">-ExecutionPolicy \<ExecutionPolicy\></span><span class="sxs-lookup"><span data-stu-id="80a95-178">-ExecutionPolicy \<ExecutionPolicy\></span></span>

<span data-ttu-id="80a95-179">Define a política de execução padrão para a sessão atual e salva-a na `$env:PSExecutionPolicyPreference` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="80a95-179">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="80a95-180">Esse parâmetro não altera a política de execução do PowerShell definida no Registro.</span><span class="sxs-lookup"><span data-stu-id="80a95-180">This parameter does not change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="80a95-181">Para saber mais sobre as políticas de execução do PowerShell, inclusive uma lista de valores válidos, confira [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="80a95-181">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

#### <a name="-command"></a><span data-ttu-id="80a95-182">-Command</span><span class="sxs-lookup"><span data-stu-id="80a95-182">-Command</span></span>

<span data-ttu-id="80a95-183">Executa os comandos especificados (e quaisquer parâmetros) como se eles fossem digitados no prompt de comando do PowerShell e, em seguida, são encerrados, a menos que o `NoExit` parâmetro seja especificado.</span><span class="sxs-lookup"><span data-stu-id="80a95-183">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="80a95-184">O valor do **comando** pode ser `-` , um bloco de script ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="80a95-184">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="80a95-185">Se o valor do **comando** for `-` , o texto do comando será lido da entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-185">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="80a95-186">O parâmetro **Command** aceita apenas um bloco de script para execução quando ele pode reconhecer o valor passado para **Command** como um tipo de **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="80a95-186">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="80a95-187">Isso _só_ é possível durante a execução `powershell.exe` de outro host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80a95-187">This is _only_ possible when running `powershell.exe` from another PowerShell host.</span></span> <span data-ttu-id="80a95-188">O tipo de **scriptblock** pode estar contido em uma variável existente, retornada de uma expressão ou analisado pelo host do PowerShell como um bloco de script literal entre chaves ( `{}` ), antes de ser passado para `powershell.exe` .</span><span class="sxs-lookup"><span data-stu-id="80a95-188">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `powershell.exe`.</span></span>

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="80a95-189">No `cmd.exe` , não há tal coisa como um bloco de script (ou tipo **scriptblock** ), portanto, o valor passado para **Command** _sempre_ será uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="80a95-189">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="80a95-190">Você pode escrever um bloco de script dentro da cadeia de caracteres, mas em vez de ser executado, ele se comportará exatamente como se tivesse sido digitado em um prompt comum do PowerShell, imprimindo o conteúdo do bloco de script para você.</span><span class="sxs-lookup"><span data-stu-id="80a95-190">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="80a95-191">Uma cadeia de caracteres passada para o **comando** ainda é executada como código do PowerShell, portanto, as chaves de bloco de script geralmente não são necessárias em primeiro lugar durante a execução do `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="80a95-191">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="80a95-192">Para executar um bloco de script embutido definido em uma cadeia de caracteres, o [operador de chamada](about_operators.md#special-operators) `&` pode ser usado:</span><span class="sxs-lookup"><span data-stu-id="80a95-192">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```cmd
powershell.exe -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="80a95-193">Se o valor do **comando** for uma cadeia de caracteres, **Command** deverá ser o último parâmetro para pwsh, pois todos os argumentos após ele serão interpretados como parte do comando a ser executado.</span><span class="sxs-lookup"><span data-stu-id="80a95-193">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="80a95-194">Quando chamado de dentro de uma sessão existente do PowerShell, os resultados são retornados para o Shell pai como objetos XML desserializados, não objetos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="80a95-194">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="80a95-195">Para outros shells, os resultados são retornados como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="80a95-195">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="80a95-196">Se o valor do **comando** for `-` , o texto do comando será lido da entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-196">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="80a95-197">Você deve redirecionar a entrada padrão ao usar o parâmetro de **comando** com entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="80a95-197">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="80a95-198">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="80a95-198">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="80a95-199">Esse exemplo gera a saída a seguir:</span><span class="sxs-lookup"><span data-stu-id="80a95-199">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="80a95-200">O código de saída do processo é determinado pelo status do último comando (executado) dentro do bloco de script.</span><span class="sxs-lookup"><span data-stu-id="80a95-200">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="80a95-201">O código de saída é `0` quando `$?` é `$true` ou `1` quando `$?` é `$false` .</span><span class="sxs-lookup"><span data-stu-id="80a95-201">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="80a95-202">Se o último comando for um programa externo ou um script do PowerShell que define explicitamente um código de saída diferente de `0` ou `1` , esse código de saída será convertido em `1` para o código de saída do processo.</span><span class="sxs-lookup"><span data-stu-id="80a95-202">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="80a95-203">Para preservar o código de saída específico, adicione `exit $LASTEXITCODE` à cadeia de caracteres de comando ou ao bloco de script.</span><span class="sxs-lookup"><span data-stu-id="80a95-203">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="80a95-204">Da mesma forma, o valor 1 é retornado quando um erro de encerramento de script (encerramento de runspace), como um `throw` ou `-ErrorAction Stop` , ocorre ou quando a execução é interrompida com <kbd>Ctrl</kbd> - <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="80a95-204">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

#### <a name="-help---"></a><span data-ttu-id="80a95-205">-Help, -?, /?</span><span class="sxs-lookup"><span data-stu-id="80a95-205">-Help, -?, /?</span></span>

<span data-ttu-id="80a95-206">Exibe a ajuda para **PowerShell.exe**.</span><span class="sxs-lookup"><span data-stu-id="80a95-206">Displays help for **PowerShell.exe**.</span></span> <span data-ttu-id="80a95-207">Se você estiver digitando um comando **PowerShell.exe** em uma sessão do PowerShell, preceda os parâmetros de comando com um hífen (-), não uma barra (/).</span><span class="sxs-lookup"><span data-stu-id="80a95-207">If you are typing a **PowerShell.exe** command in a PowerShell session, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="80a95-208">Você pode usar um hífen ou uma barra em **cmd.exe**.</span><span class="sxs-lookup"><span data-stu-id="80a95-208">You can use either a hyphen or forward slash in **cmd.exe**.</span></span>

### <a name="remarks"></a><span data-ttu-id="80a95-209">COMENTÁRIOS</span><span class="sxs-lookup"><span data-stu-id="80a95-209">REMARKS</span></span>

<span data-ttu-id="80a95-210">Observação de solução de problemas: no PowerShell 2,0, iniciar alguns programas do console do PowerShell falha com um **LastExitCode** de 0xc0000142.</span><span class="sxs-lookup"><span data-stu-id="80a95-210">Troubleshooting note: In PowerShell 2.0, starting some programs from the PowerShell console fails with a **LastExitCode** of 0xc0000142.</span></span>

### <a name="examples"></a><span data-ttu-id="80a95-211">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="80a95-211">EXAMPLES</span></span>

```powershell
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a PowerShell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate way to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
