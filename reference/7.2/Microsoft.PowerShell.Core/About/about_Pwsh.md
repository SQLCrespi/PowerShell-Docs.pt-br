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
# <a name="about-pwsh"></a>Sobre o pwsh

## <a name="short-description"></a>Descrição breve
Explica como usar a `pwsh` interface de linha de comando. Exibe os parâmetros de linha de comando e descreve a sintaxe.

## <a name="long-description"></a>Descrição longa

## <a name="syntax"></a>Sintaxe

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

## <a name="parameters"></a>Parâmetros

Todos os parâmetros não diferenciam maiúsculas de minúsculas.

### <a name="-file---f"></a>-Arquivo | -f

Se o valor de `File` for `-` , o texto do comando será lido da entrada padrão.
`pwsh -File -`A execução sem entrada padrão redirecionada inicia uma sessão normal. Isso é o mesmo que não especificar o `File` parâmetro.

Esse será o parâmetro padrão se nenhum parâmetro estiver presente, mas os valores estiverem presentes na linha de comando. O script especificado é executado no escopo local ("dot-sourceed"), de modo que as funções e variáveis que o script cria estão disponíveis na sessão atual. Insira o caminho do arquivo de script e quaisquer parâmetros. O arquivo deve ser o último parâmetro no comando, pois todos os caracteres digitados após o nome do parâmetro de arquivo são interpretados como o caminho do arquivo de script seguido pelos parâmetros do script.

Normalmente, os parâmetros de opção de um script são incluídos ou omitidos.
Por exemplo, o comando a seguir usa o parâmetro All do arquivo de script Get-Script.ps1: `-File .\Get-Script.ps1 -All`

Em casos raros, talvez seja necessário fornecer um valor **booliano** para um parâmetro de opção. Para fornecer um valor **booliano** para um parâmetro de opção no valor do parâmetro **File** , use o parâmetro normalmente seguido imediatamente por dois-pontos e o valor booliano, como o seguinte: `-File .\Get-Script.ps1 -All:$False` .

Os parâmetros passados para o script são passados como cadeias de caracteres literais (após a interpretação do shell atual). Por exemplo, se você estiver no `cmd.exe` e desejar passar um valor de variável de ambiente, use a `cmd.exe` sintaxe: `pwsh -File .\test.ps1 -TestParam %windir%`

Por outro lado, `pwsh -File .\test.ps1 -TestParam $env:windir` a execução nos `cmd.exe` resultados no script recebe a cadeia de caracteres literal `$env:windir` porque não tem significado especial para o `cmd.exe` shell atual. O `$env:windir` estilo da referência de variável de ambiente _pode_ ser usado dentro de um parâmetro de **comando** , já que ele é interpretado como código do PowerShell.

Da mesma forma, se você quiser executar o mesmo comando de um _script em lotes_, você usaria `%~dp0` em vez de `.\` ou `$PSScriptRoot` para representar o diretório de execução atual: `pwsh -File %~dp0test.ps1 -TestParam %windir%` . Se você, em vez disso `.\test.ps1` , o PowerShell geraria um erro porque ele não consegue encontrar o caminho literal `.\test.ps1`

Quando o arquivo de script termina com um `exit` comando, o código de saída do processo é definido como o argumento numérico usado com o `exit` comando. Com o encerramento normal, o código de saída é sempre `0` .

Semelhante a `-Command` , quando ocorre um erro de terminação de script, o código de saída é definido como `1` . No entanto, ao contrário de with `-Command` , quando a execução é interrompida com <kbd>Ctrl</kbd> - <kbd>C</kbd> , o código de saída é `0` .

### <a name="-command---c"></a>-Comando | -c

Executa os comandos especificados (e quaisquer parâmetros) como se eles fossem digitados no prompt de comando do PowerShell e, em seguida, são encerrados, a menos que o `NoExit` parâmetro seja especificado.

O valor do **comando** pode ser `-` , um bloco de script ou uma cadeia de caracteres. Se o valor do **comando** for `-` , o texto do comando será lido da entrada padrão.

O parâmetro **Command** aceita apenas um bloco de script para execução quando ele pode reconhecer o valor passado para **Command** como um tipo de **scriptblock** . Isso _só_ é possível durante a execução `pwsh` de outro host do PowerShell. O tipo de **scriptblock** pode estar contido em uma variável existente, retornada de uma expressão ou analisado pelo host do PowerShell como um bloco de script literal entre chaves ( `{}` ), antes de ser passado para `pwsh` .

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

No `cmd.exe` , não há tal coisa como um bloco de script (ou tipo **scriptblock** ), portanto, o valor passado para **Command** _sempre_ será uma cadeia de caracteres. Você pode escrever um bloco de script dentro da cadeia de caracteres, mas em vez de ser executado, ele se comportará exatamente como se tivesse sido digitado em um prompt comum do PowerShell, imprimindo o conteúdo do bloco de script para você.

Uma cadeia de caracteres passada para o **comando** ainda é executada como código do PowerShell, portanto, as chaves de bloco de script geralmente não são necessárias em primeiro lugar durante a execução do `cmd.exe` . Para executar um bloco de script embutido definido em uma cadeia de caracteres, o [operador de chamada](about_operators.md#special-operators) `&` pode ser usado:

```
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

### <a name="-configurationname---config"></a>-ConfigurationName | -configuração

Especifica um ponto de extremidade de configuração no qual o PowerShell é executado. Pode ser qualquer ponto de extremidade registrado no computador local, incluindo os pontos de extremidade remotos de comunicação remota do PowerShell ou um ponto de extremidades personalizado com recursos de função de usuário específicos.

Exemplo: `pwsh -ConfigurationName AdminRoles`

### <a name="-custompipename"></a>-CustomPipeName

Especifica o nome a ser usado para um servidor IPC adicional (pipe nomeado) usado para depuração e outra comunicação entre processos. Isso oferece um mecanismo previsível para se conectar a outras instâncias do PowerShell. Normalmente usado com o parâmetro **CustomPipeName** em `Enter-PSHostProcess` .

Esse parâmetro foi introduzido no PowerShell 6,2.

Por exemplo:

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a>-EncodedCommand | -e | -EC

Aceita uma versão de cadeia de caracteres codificada em Base64 de um comando. Use esse parâmetro para enviar comandos ao PowerShell que exigem cotas aninhadas complexas. A representação Base64 deve ser uma cadeia de caracteres codificada em UTF-16LE.

Por exemplo:

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a>-ExecutionPolicy | -ex | -EP

Define a política de execução padrão para a sessão atual e salva-a na `$env:PSExecutionPolicyPreference` variável de ambiente. Esse parâmetro não altera as políticas de execução configuradas de forma persistente.

Esse parâmetro se aplica somente a computadores Windows. A `$env:PSExecutionPolicyPreference` variável de ambiente não existe em plataformas que não sejam do Windows.

### <a name="-inputformat---inp---if"></a>-InputFormat | -inp | -se

Descreve o formato dos dados enviados ao PowerShell. Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).

### <a name="-interactive---i"></a>-Interativo | -i

Apresente um prompt interativo para o usuário. Inverso para parâmetro não interativo.

### <a name="-login---l"></a>-Logon | -l

No Linux e no macOS, o inicia o PowerShell como um shell de logon, usando/bin/sh para executar perfis de logon, como/etc/profile e ~/.Profile.
No Windows, essa opção não faz nada.

> [!IMPORTANT]
> Esse parâmetro deve ser primeiro para iniciar o PowerShell como um shell de logon.
> Passar esse parâmetro em outra posição será ignorado.

Para configurar `pwsh` o Shell de logon em sistemas operacionais semelhantes ao Unix:

- Verifique se o caminho absoluto completo para `pwsh` está listado em `/etc/shells`
  - Esse caminho geralmente é algo como `/usr/bin/pwsh` no Linux ou `/usr/local/bin/pwsh` no MacOS
  - Com alguns métodos de instalação, essa entrada será adicionada automaticamente no momento da instalação
  - Se `pwsh` não estiver presente no `/etc/shells` , use um editor para acrescentar o caminho à `pwsh` última linha. Isso requer privilégios elevados para editar.
- Use o utilitário [chsh](https://linux.die.net/man/1/chsh) para definir o Shell do usuário atual para `pwsh` :

  ```sh
  chsh -s /usr/bin/pwsh
  ```

> [!WARNING]
> `pwsh`A configuração como o Shell de logon atualmente não tem suporte no subsistema do Windows para Linux (WSL) e a tentativa de definir `pwsh` como o Shell de logon pode levar a não conseguir iniciar o WSL interativamente.

### <a name="-mta"></a>-MTA

Inicie o PowerShell usando um apartamento multi-threaded. Essa opção só está disponível no Windows.

### <a name="-noexit---noe"></a>-NoExit | -noe

Não é encerrado depois de executar comandos de inicialização.

Exemplo: `pwsh -NoExit -Command Get-Date`

### <a name="-nologo---nol"></a>-Nologo | -nol

Oculta a faixa de direitos autorais na inicialização de sessões interativas.

### <a name="-noninteractive---noni"></a>-Não interativo | -noni

Não exibe um prompt interativo para o usuário. Quaisquer tentativas de usar recursos interativos, como `Read-Host` ou prompts de confirmação, resultam em erros de encerramento de instrução.

### <a name="-noprofile---nop"></a>-NoProfile | -Nop

Não carrega os perfis do PowerShell.

### <a name="-outputformat---o---of"></a>-OutputFormat | -o | -de

Determina como a saída do PowerShell é formatada. Os valores válidos são "Text" (cadeias de caracteres de texto) ou "XML" (formato CLIXML serializado).

Exemplo: `pwsh -o XML -c Get-Date`

Quando chamado com uma sessão do PowerShell, você obtém objetos desserializados como cadeias de caracteres de saída, e não simples. Quando chamado de outros shells, a saída é dados de cadeia de caracteres formatados como texto CLIXML.

### <a name="-settingsfile---settings"></a>-SettingsFile | -configurações

Substitui o arquivo de configurações de todo o sistema da `powershell.config.json` sessão. Por padrão, as configurações de todo o sistema são lidas do `powershell.config.json` no `$PSHOME` diretório.

Observe que essas configurações não são usadas pelo ponto de extremidade especificado pelo `-ConfigurationName` argumento.

Exemplo: `pwsh -SettingsFile c:\myproject\powershell.config.json`

### <a name="-sshservermode---sshs"></a>-SSHServerMode | -sshs

Usado em sshd_config para executar o PowerShell como um subsistema SSH. Ela não é destinada nem tem suporte para nenhum outro uso.

### <a name="-sta"></a>-STA

Inicie o PowerShell usando um apartamento de thread único. Este é o padrão. Essa opção só está disponível no Windows.

### <a name="-version---v"></a>-Versão | -v

Exibe a versão do PowerShell. Parâmetros adicionais são ignorados.

### <a name="-windowstyle---w"></a>-WindowStyle | -w

Define o estilo da janela da sessão. Os valores válidos são Normal, Minimized, Maximized e Hidden.

### <a name="-workingdirectory---wd"></a>-WorkingDirectory | -WD

Define o diretório de trabalho inicial executando na inicialização. Há suporte para qualquer caminho de arquivo válido do PowerShell.

Para iniciar o PowerShell em seu diretório base, use: `pwsh -WorkingDirectory ~`

### <a name="-help---"></a>-Help, -?, /?

Exibe a ajuda para `pwsh` . Se você estiver digitando um comando pwsh no PowerShell, preceda os parâmetros de comando com um hífen ( `-` ), não uma barra "/" ( `/` ).
