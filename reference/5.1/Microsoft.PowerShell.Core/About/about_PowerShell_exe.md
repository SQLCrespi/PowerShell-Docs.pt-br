---
description: Explica como usar a `powershell.exe` interface de linha de comando. Exibe os parâmetros de linha de comando e descreve a sintaxe.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: ef03558a6b58868b98c9da488934b0bfbbce9fe7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196167"
---
# <a name="about-powershellexe"></a>Sobre PowerShell.exe

## <a name="short-description"></a>Descrição breve
Explica como usar a `powershell.exe` interface de linha de comando. Exibe os parâmetros de linha de comando e descreve a sintaxe.

## <a name="long-description"></a>Descrição longa

### <a name="syntax"></a>SYNTAX

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

### <a name="parameters"></a>Parâmetros

#### <a name="-psconsolefile-filepath"></a>-PSConsoleFile \<FilePath\>

Carrega o arquivo de console do PowerShell especificado. Insira o caminho e o nome do arquivo de console. Para criar um arquivo de console, use o cmdlet Export-Console no PowerShell.

#### <a name="-version-powershell-version"></a>-Version \<PowerShell Version\>

Inicia a versão especificada do PowerShell. Os valores válidos são 2.0 e 3.0. A versão que você especificar deve estar instalada no sistema. Se o Windows PowerShell 3,0 estiver instalado no computador, "3,0" será a versão padrão.
Caso contrário, "2,0" é a versão padrão. Para obter mais informações, consulte [instalando o PowerShell](/powershell/scripting/install/installing-windows-powershell).

#### <a name="-nologo"></a>-NoLogo

Oculta a faixa de direitos autorais na inicialização.

#### <a name="-noexit"></a>-NoExit

Não é encerrado depois de executar comandos de inicialização.

#### <a name="-sta"></a>-Sta

Inicia o PowerShell usando um single-threaded apartment. No Windows PowerShell 2.0, o MTA (Multi-Threaded Apartment) é o padrão. No Windows PowerShell 3.0, o STA (Single-Threaded Apartment) é o padrão.

#### <a name="-mta"></a>-Mta

Inicia o PowerShell usando um multi-threaded apartment. Este parâmetro é introduzido no PowerShell 3.0. No PowerShell 2.0, o MTA (Multi-Threaded Apartment) é o padrão. No PowerShell 3.0, o STA (Single-Threaded Apartment) é o padrão.

#### <a name="-noprofile"></a>-NoProfile

Não carrega o perfil do PowerShell.

#### <a name="-noninteractive"></a>-NonInteractive

Não exibe um prompt interativo para o usuário.

#### <a name="-inputformat-text--xml"></a>-InputFormat {Text | XML}

Descreve o formato dos dados enviados ao PowerShell. Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).

#### <a name="-outputformat-text--xml"></a>-OutputFormat {Text | XML}

Determina como a saída do PowerShell é formatada. Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).

#### <a name="-windowstyle-window-style"></a>-WindowStyle \<Window style\>

Define o estilo da janela da sessão. Os valores válidos são Normal, Minimized, Maximized e Hidden.

#### <a name="-encodedcommand-base64encodedcommand"></a>-EncodedCommand \<Base64EncodedCommand\>

Aceita uma versão de cadeia de caracteres com codificação de base 64 de um comando. Use esse parâmetro para enviar comandos ao PowerShell que exigem aspas ou chaves complexas. A cadeia de caracteres deve ser formatada usando a codificação de caracteres UTF-16LE.

#### <a name="-configurationname-string"></a>-ConfigurationName \<string\>

Especifica um ponto de extremidade de configuração no qual o PowerShell é executado. Pode ser qualquer ponto de extremidade registrado no computador local, incluindo os pontos de extremidade remotos de comunicação remota do PowerShell ou um ponto de extremidades personalizado com recursos de função de usuário específicos.

#### <a name="-file----filepath-args"></a>-Arquivo-| \<filePath\>\<args\>

Se o valor do **arquivo** for "-", o texto do comando será lido da entrada padrão.
`powershell -File -`A execução sem entrada padrão redirecionada inicia uma sessão normal. Isso é o mesmo que não especificar o parâmetro **File** .

Se o valor de **File** for um caminho de arquivo, o script será executado no escopo local ("dot-sourceed"), para que as funções e variáveis que o script cria estejam disponíveis na sessão atual. Insira o caminho do arquivo de script e quaisquer parâmetros. **File** deve ser o último parâmetro no comando. Todos os valores digitados após o parâmetro **File** são interpretados como o caminho do arquivo de script e os parâmetros passados para esse script.

Os parâmetros passados para o script são passados como cadeias de caracteres literais (após a interpretação do shell atual). Por exemplo, se você estiver em **cmd.exe** e quiser passar um valor de variável de ambiente, use a sintaxe **cmd.exe** : `powershell.exe -File .\test.ps1 -TestParam %windir%`

Por outro lado, `powershell.exe -File .\test.ps1 -TestParam $env:windir` a execução em **cmd.exe** resulta no script que recebe a cadeia de caracteres literal `$env:windir` porque não tem nenhum significado especial para o Shell **cmd.exe** atual. O `$env:windir` estilo da referência de variável de ambiente _pode_ ser usado dentro de um parâmetro de **comando** , já que ele será interpretado como código do PowerShell.

Da mesma forma, se você quiser executar o mesmo comando de um **script em lotes** , você usaria `%~dp0` em vez de `.\` ou `$PSScriptRoot` para representar o diretório de execução atual: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` .
Se você, em vez disso `.\test.ps1` , o PowerShell geraria um erro porque ele não consegue encontrar o caminho literal `.\test.ps1`

Quando o valor do **arquivo** for um caminho de arquivo, o **arquivo** _deverá_ ser o último parâmetro no comando, pois os caracteres digitados após o nome do parâmetro de **arquivo** serão interpretados como o caminho do arquivo de script seguido pelos parâmetros do script.

Você pode incluir os parâmetros e os valores do script no valor do parâmetro **File** . Por exemplo: `-File .\Get-Script.ps1 -Domain Central`

Normalmente, os parâmetros de opção de um script são incluídos ou omitidos.
Por exemplo, o comando a seguir usa o parâmetro **All** do `Get-Script.ps1` arquivo de script: `-File .\Get-Script.ps1 -All`

Em casos raros, talvez seja necessário fornecer um valor **booliano** para um parâmetro.
Não é possível passar um valor booliano explícito para um parâmetro de opção ao executar um script dessa forma. Essa limitação foi removida no PowerShell 6 ( `pwsh.exe` ).

#### <a name="-executionpolicy-executionpolicy"></a>-ExecutionPolicy \<ExecutionPolicy\>

Define a política de execução padrão para a sessão atual e salva-a na `$env:PSExecutionPolicyPreference` variável de ambiente. Esse parâmetro não altera a política de execução do PowerShell definida no Registro. Para saber mais sobre as políticas de execução do PowerShell, inclusive uma lista de valores válidos, confira [about_Execution_Policies](about_Execution_Policies.md).

#### <a name="-command"></a>-Command

Executa os comandos especificados (e quaisquer parâmetros) como se eles fossem digitados no prompt de comando do PowerShell e, em seguida, são encerrados, a menos que o `NoExit` parâmetro seja especificado.

O valor do **comando** pode ser `-` , um bloco de script ou uma cadeia de caracteres. Se o valor do **comando** for `-` , o texto do comando será lido da entrada padrão.

O parâmetro **Command** aceita apenas um bloco de script para execução quando ele pode reconhecer o valor passado para **Command** como um tipo de **scriptblock** . Isso _só_ é possível durante a execução `powershell.exe` de outro host do PowerShell. O tipo de **scriptblock** pode estar contido em uma variável existente, retornada de uma expressão ou analisado pelo host do PowerShell como um bloco de script literal entre chaves ( `{}` ), antes de ser passado para `powershell.exe` .

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

No `cmd.exe` , não há tal coisa como um bloco de script (ou tipo **scriptblock** ), portanto, o valor passado para **Command** _sempre_ será uma cadeia de caracteres. Você pode escrever um bloco de script dentro da cadeia de caracteres, mas em vez de ser executado, ele se comportará exatamente como se tivesse sido digitado em um prompt comum do PowerShell, imprimindo o conteúdo do bloco de script para você.

Uma cadeia de caracteres passada para o **comando** ainda é executada como código do PowerShell, portanto, as chaves de bloco de script geralmente não são necessárias em primeiro lugar durante a execução do `cmd.exe` . Para executar um bloco de script embutido definido em uma cadeia de caracteres, o [operador de chamada](about_operators.md#special-operators) `&` pode ser usado:

```cmd
pwsh -Command "& {Get-WinEvent -LogName security}"
```

Se o valor do **comando** for uma cadeia de caracteres, **Command** deverá ser o último parâmetro para pwsh, pois todos os argumentos após ele serão interpretados como parte do comando a ser executado.

Quando chamado de dentro de uma sessão existente do PowerShell, os resultados são retornados para o Shell pai como objetos XML desserializados, não objetos dinâmicos. Para outros shells, os resultados são retornados como cadeias de caracteres.

Se o valor do **comando** for `-` , o texto do comando será lido da entrada padrão. Você deve redirecionar a entrada padrão ao usar o parâmetro de **comando** com entrada padrão. Por exemplo:

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

Esse exemplo gera a saída a seguir:

```Output
in
hi there
out
```

O código de saída do processo é determinado pelo status do último comando (executado) dentro do bloco de script. O código de saída é `0` quando `$?` é `$true` ou `1` quando `$?` é `$false` . Se o último comando for um programa externo ou um script do PowerShell que define explicitamente um código de saída diferente de `0` ou `1` , esse código de saída será convertido em `1` para o código de saída do processo. Para preservar o código de saída específico, adicione `exit $LASTEXITCODE` à cadeia de caracteres de comando ou ao bloco de script.

Da mesma forma, o valor 1 é retornado quando um erro de encerramento de script (encerramento de runspace), como um `throw` ou `-ErrorAction Stop` , ocorre ou quando a execução é interrompida com <kbd>Ctrl</kbd> - <kbd>C</kbd>.

possível _somente_ ao executar **PowerShell.exe** de outro host do PowerShell.
O tipo **scriptblock** pode estar contido em uma variável existente, retornada de uma expressão ou analisado pelo host do PowerShell como um bloco de script literal entre chaves `{}` , antes de ser passado para **PowerShell.exe** .

Em **cmd.exe** , não há nada como um bloco de script (ou tipo **scriptblock** ), portanto, o valor passado para **Command** _sempre_ será uma cadeia de caracteres. Você pode escrever um bloco de script dentro da cadeia de caracteres, mas em vez de ser executado, ele se comportará exatamente como se tivesse sido digitado em um prompt comum do PowerShell, imprimindo o conteúdo do bloco de script para você.

Uma cadeia de caracteres passada para o **comando** ainda será executada como PowerShell, portanto, as chaves de bloco de script geralmente não são necessárias em primeiro lugar durante a execução de **cmd.exe** . Para executar um bloco de script embutido definido dentro de uma cadeia de caracteres, o [operador de chamada](about_operators.md#special-operators) 
 `&` pode ser usado:

```console
"& {<command>}"
```

#### <a name="-help---"></a>-Help, -?, /?

Exibe a ajuda para **PowerShell.exe** . Se você estiver digitando um comando **PowerShell.exe** em uma sessão do PowerShell, preceda os parâmetros de comando com um hífen (-), não uma barra (/). Você pode usar um hífen ou uma barra em **cmd.exe** .

### <a name="remarks"></a>COMENTÁRIOS

Observação de solução de problemas: no PowerShell 2,0, iniciar alguns programas do console do PowerShell falha com um **LastExitCode** de 0xc0000142.

### <a name="examples"></a>EXEMPLOS

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
