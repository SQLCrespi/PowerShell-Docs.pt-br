---
title: Uso do Visual Studio Code para desenvolvimento do PowerShell
description: Uso do Visual Studio Code para desenvolvimento do PowerShell
ms.date: 08/06/2018
ms.openlocfilehash: 0e082b74f99d214749f10224fb5aaf41e2ef8951
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71325244"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>Uso do Visual Studio Code para desenvolvimento do PowerShell

Além do [ISE do PowerShell][ise], o PowerShell também tem um bom suporte no VSCode (Visual Studio Code). Além disso, o ISE não é compatível com o PowerShell Core, embora haja suporte do VSCode para o PowerShell Core em todas as plataformas (Windows, macOS e Linux)

É possível usar o VSCode no Windows com o PowerShell versão 5 usando o Windows 10 ou instalando o [Windows Management Framework 5.0 RTM](https://devblogs.microsoft.com/powershell/windows-management-framework-wmf-5-0-rtm-is-now-available-via-the-microsoft-update-catalog/) para sistemas operacionais do Windows de nível baixo (por exemplo, Windows 8.1 etc.).

Antes de iniciá-lo, verifique se o PowerShell existe no sistema. Para cargas de trabalho modernas no Windows, macOS e Linux, consulte:

- [Instalar o PowerShell Core no Linux][install-pscore-linux]
- [Instalar o PowerShell Core no macOS][install-pscore-macos]
- [Instalação do PowerShell Core no Windows][install-pscore-windows]

Para cargas de trabalho tradicionais do Windows PowerShell, confira [Como instalar o Windows PowerShell][install-winps].

## <a name="editing-with-vscode"></a>Editar com VSCode

1. [Instalar o VSCode](https://code.visualstudio.com/Docs/setup/setup-overview)

   - **Linux**: siga as instruções de instalação na página [Executar o VSCode no Linux](https://code.visualstudio.com/docs/setup/linux)
   - **macOS**: siga as instruções de instalação na página [Executar o VSCode no macOS](https://code.visualstudio.com/docs/setup/mac)

     > [!IMPORTANT]
     > No macOS, você deve instalar o OpenSSL para que a extensão do PowerShell funcione corretamente. A maneira mais fácil de fazer isso é instalar o [Homebrew](https://brew.sh/) e, em seguida, executar `brew install openssl`. Agora, o VS Code pode carregar a extensão do PowerShell com êxito.

   - **Windows**: siga as instruções de instalação na página [Executar o VSCode no Windows](https://code.visualstudio.com/docs/setup/windows)

2. Instalação da extensão do PowerShell

   - Inicie o aplicativo VSCode das seguintes formas:
     - **Windows**: digitando `code` na sua sessão do PowerShell
     - **Linux**: digitando `code` em seu terminal
     - **macOS**: digitando `code` em seu terminal
   - Inicie **Abertura rápida** pressionando <kbd>Ctrl</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>P</kbd> no Mac).
   - Na Abertura rápida, digite `ext install powershell` e clique em **Enter**.
   - A exibição **Extensões** será aberta na barra lateral. Selecione a extensão do PowerShell da Microsoft.
     Você deve ver algo como:

     ![VSCode](../../images/using-vscode/vscode.png)

   - Clique no botão **Instalar** na extensão do PowerShell da Microsoft.
   - Após a instalação, você verá que o botão **Instalar** mudará para **Recarregar**. Clique em **Recarregar**.
   - Depois de recarregar o VSCode, você está pronto para edição.

Por exemplo, para criar um novo arquivo, clique em **Arquivo -> Novo**. Para salvá-lo, clique em **Arquivo -> Salvar** e, em seguida, forneça um nome de arquivo. Digamos `HelloWorld.ps1`. Para fechar o arquivo, clique no "x" ao lado do nome de arquivo. Para sair do VSCode, **Arquivo -> Sair**.

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>Instalando a extensão do PowerShell em sistemas restritos

Alguns sistemas são configurados de forma a exigir que todas as assinaturas de código sejam verificadas e, portanto, exigem que os Serviços do Editor do PowerShell sejam aprovados manualmente para serem executados no sistema. Uma atualização da Política de Grupo que altera a política de execução é uma causa provável caso tenha instalado a extensão do PowerShell, mas veja um erro como:

```
Language server startup failed.
```

Para aprovar manualmente os Serviços do Editor do PowerShell e, portanto, a extensão do PowerShell para VSCode, abra um prompt do PowerShell e execute:

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

O sistema mostrará a mensagem "Você deseja executar o software desse editor não confiável?" Digite `R` para executar o arquivo. Em seguida, abra o VSCode e verifique se a extensão do PowerShell está funcionando corretamente. Se você ainda tiver problemas para começar, fale conosco no [GitHub](https://github.com/PowerShell/vscode-powershell/issues).

#### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>Escolha de uma versão do PowerShell para ser usada com a extensão

Com o PowerShell Core instalado com o Windows PowerShell, agora é possível usar uma versão específica do PowerShell com a extensão do PowerShell. Siga estas etapas para escolher a versão:

1. Abra a paleta de comando (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no Windows e Linux, ou <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS).
1. Pesquise "Sessão".
1. Clique em "PowerShell: mostrar menu de sessão".
1. Na lista, escolha a versão do PowerShell que deseja usar; por exemplo, "PowerShell Core".

> [!IMPORTANT]
> Esse recurso analisa alguns caminhos conhecidos em diferentes sistemas operacionais para descobrir locais de instalação do PowerShell. Se você instalou o PowerShell em um local não típico, talvez ele não apareça inicialmente no menu de sessão. Você pode estender o menu de sessão [adicionando seus próprios caminhos personalizados](#adding-your-own-powershell-paths-to-the-session-menu) conforme descrito abaixo.

>[!NOTE]
> Há outra maneira de acessar o menu de sessão. Quando um arquivo do PowerShell é aberto no editor, um número de versão em verde aparece no canto inferior direito. Clicar nesse número de versão levará ao menu de sessão.

##### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a>Adição dos seus caminhos do PowerShell ao menu de sessão

É possível adicionar outros caminhos executáveis do PowerShell ao menu de sessão por meio de uma configuração do VSCode.

Adicione um item à lista `powershell.powerShellAdditionalExePaths` ou crie a lista se ela não estiver em `settings.json`:

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    // other settings...
}
```

Cada item precisa ter:

* `exePath`: o caminho para o executável `pwsh` ou `powershell`.
* `versionName`: o texto que aparece no menu de sessão.

É possível definir a versão padrão do PowerShell a ser usada. Para isso, utilize a configuração `powershell.powerShellDefaultVersion` definindo-a como o texto exibido no menu de sessão (também conhecido como `versionName` na última configuração):

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    "powershell.powerShellDefaultVersion": "Downloaded PowerShell",

    // other settings...
}
```

Depois de definir essa configuração, reinicie o VSCode ou use a ação "Desenvolvedor: recarregar janela" da paleta de comando para atualizar a janela atual do VSCode.

Se você abrir o menu de sessão, agora verá versões adicionais do PowerShell.

> [!NOTE]
> Compilar o PowerShell na origem é uma ótima maneira de testar sua compilação local do PowerShell.

#### <a name="configuration-settings-for-vscode"></a>Definições de configuração do VSCode

Usando as etapas no parágrafo anterior, você pode adicionar configurações no `settings.json`.

Recomendamos as seguintes definições de configuração para o VSCode:

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

Caso não queira que essas configurações afetem todos os tipos de arquivos, o VSCode também permite configurações por idioma. Crie uma configuração específica para um idioma colocando as configurações em um campo `[<language-name>]`. Por exemplo:

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

Para saber mais sobre a codificação do arquivo no VS Code, confira [Entendendo a codificação do arquivo](understanding-file-encoding.md).

## <a name="debugging-with-vscode"></a>Depurar com o VSCode

### <a name="no-workspace-debugging"></a>Depuração sem espaço de trabalho

A partir da versão 1.9 do VSCode, é possível depurar scripts do PowerShell sem a necessidade de abrir a pasta que contém o script do PowerShell. Abra o arquivo de script do PowerShell usando **Arquivo -> Abrir Arquivo…** , defina um ponto de interrupção em uma linha (pressione <kbd>F9</kbd>) e, em seguida, pressione <kbd>F5</kbd> para iniciar a depuração. Será exibido o painel de ações de depuração, que permite que você interrompa o depurador, execute em etapas, retome e pare a depuração.

### <a name="workspace-debugging"></a>Depuração do workspace

A depuração do workspace refere-se a depuração no contexto de uma pasta que você abriu no Visual Studio Code usando **Abrir Pasta...**  do menu **Arquivo**. A pasta que você abrir normalmente é a pasta do projeto do PowerShell e/ou a raiz do repositório Git.

Mesmo nesse modo, é possível iniciar a depuração de script do PowerShell selecionado no momento pressionando <kbd>F5</kbd>. No entanto, a depuração do workspace permite definir várias configurações de depuração diferentes de depurar apenas o arquivo aberto no momento. Por exemplo, você pode adicionar configurações para:

- Iniciar testes Pester no depurador
- Abrir um arquivo específico com argumentos no depurador
- Inicie uma sessão interativa no depurador
- Anexar o depurador a um processo de host do PowerShell

Siga estas etapas para criar o arquivo de configuração de depuração:

  1. Abra a exibição **Depurar** pressionando <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> no Mac).
  2. Clique no ícone de engrenagem **Configurar** na barra de ferramentas.
  3. O VSCode solicitará que você **Selecionar o Ambiente**. Escolha **PowerShell**.

  Quando você fizer isso, o VSCode criará um diretório e um arquivo ".vscode\launch.json" na raiz da sua pasta de workspace. A configuração de depuração é armazena nesse local. Quando os arquivos estão em um repositório Git, normalmente deseja-se confirmar o arquivo launch.json. O conteúdo do arquivo launch.json é:

  ```json
  {
    "version": "0.2.0",
    "configurations": [
        {
            "type": "PowerShell",
            "request": "launch",
            "name": "PowerShell Launch (current file)",
            "script": "${file}",
            "args": [],
            "cwd": "${file}"
        },
        {
            "type": "PowerShell",
            "request": "attach",
            "name": "PowerShell Attach to Host Process",
            "processId": "${command.PickPSHostProcess}",
            "runspaceId": 1
        },
        {
            "type": "PowerShell",
            "request": "launch",
            "name": "PowerShell Interactive Session",
            "cwd": "${workspaceRoot}"
        }
    ]
  }
  ```

  Isso representa os cenários comuns de depuração. No entanto, ao abrir este arquivo no editor, você vê um botão **Adicionar Configuração...** . É possível clicar nesse botão para adicionar mais configurações de depuração do PowerShell. Uma configuração útil a adicionar é **PowerShell: Iniciar Script**. Com essa configuração, é possível especificar um arquivo específico com argumentos opcionais que devem ser iniciados sempre que você pressionar <kbd>F5</kbd>, não importa qual arquivo está ativo no momento no editor.

  Quando a configuração de depuração é estabelecida, selecione qual configuração você deseja usar durante uma sessão de depuração, selecionando uma no menu suspenso de configuração de depuração na barra de ferramentas da exibição **Depurar**.

Há alguns blogs que podem ser úteis para você começar a usar a extensão do PowerShell para o Visual Studio Code:

- [Extensão do PowerShell][ps-extension]
- [Gravar e depurar scripts do PowerShell no Visual Studio Code][debug]
- [Diretrizes sobre depuração no Visual Studio Code][vscode-guide]
- [Depuração do PowerShell no Visual Studio Code][ps-vscode]
- [Introdução ao desenvolvimento do PowerShell no Visual Studio Code][getting-started]
- [Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 1][editing-part1]
- [Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 2][editing-part2]
- [Depuração de script do PowerShell no Visual Studio Code– parte 1][debugging-part1]
- [Depuração de script do PowerShell no Visual Studio Code– parte 2][debugging-part2]

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../setup/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../setup/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../setup/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../setup/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://blogs.msdn.microsoft.com/powershell/2015/11/16/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://blogs.technet.microsoft.com/heyscriptingguy/2016/12/05/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/11/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/12/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/06/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/13/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-vscode"></a>Extensão do PowerShell para VSCode

O código-fonte da extensão do PowerShell pode ser encontrado no [GitHub](https://github.com/PowerShell/vscode-powershell).
