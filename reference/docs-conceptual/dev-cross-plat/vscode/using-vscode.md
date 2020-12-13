---
title: Uso do Visual Studio Code para desenvolvimento do PowerShell
description: Uso do Visual Studio Code para desenvolvimento do PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 8a4ceb3da669716915449af2d211aaf2ae61bb4f
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390280"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>Uso do Visual Studio Code para desenvolvimento do PowerShell

O [Visual Studio Code][vscode] é um editor de scripts multiplataforma da Microsoft. Junto com a [extensão do PowerShell][psext], ele fornece uma experiência rica e interativa de edição de scripts, facilitando a criação de scripts confiáveis do PowerShell. O Visual Studio Code com a extensão do PowerShell é o editor recomendado para escrever scripts do PowerShell.

Ele dá suporte às seguintes versões do PowerShell:

- PowerShell 7 e posterior (Windows, macOS e Linux)
- PowerShell Core 6 (Windows, macOS e Linux)
- Windows PowerShell 5.1 (apenas Windows)

> [!NOTE]
> Visual Studio Code não é o mesmo que [Visual Studio][].

## <a name="getting-started"></a>Introdução

Antes de começar, verifique se o PowerShell existe no seu sistema. Para cargas de trabalho modernas no Windows, macOS e Linux, confira os seguintes links:

- [Instalar o PowerShell no Linux][install-pscore-linux]
- [Instalar o PowerShell no macOS][install-pscore-macos]
- [Instalar o PowerShell no Windows][install-pscore-windows]

Para cargas de trabalho tradicionais do Windows PowerShell, confira [Como instalar o Windows PowerShell][install-winps].

> [!IMPORTANT]
> O [ISE do Windows PowerShell][ise] ainda está disponível para o Windows. No entanto, não está mais no desenvolvimento ativo de recursos. O ISE não funciona com o PowerShell 6 e posterior. Como componente do Windows, ele continua com suporte oficial para correções de segurança e serviços de alta prioridade.
> Não há planos de remover o ISE do Windows.

## <a name="editing-with-visual-studio-code"></a>Edição com o Visual Studio Code

1. Instale o Visual Studio Code. Para obter mais informações, confira a visão geral [Configurar o Visual Studio Code][vsc-setup].

   Há instruções de instalação para cada plataforma:

   - **Windows**: siga as instruções de instalação na página [Executar o Visual Studio Code no Windows][vsc-setup-win].
   - **macOS**: siga as instruções de instalação na página [Executar o Visual Studio Code no macOS][vsc-setup-macOS].
   - **Linux**: siga as instruções de instalação na página [Executar o Visual Studio Code no Linux][vsc-setup-linux].

1. Instale a extensão do PowerShell.

   1. Inicie o aplicativo do Visual Studio Code digitando `code` em um console ou `code-insiders` se você instalou o Visual Studio Code Insiders.
   1. Inicie o **Abertura rápida** no Windows ou no Linux pressionando <kbd>Ctrl</kbd>+<kbd>P</kbd>. No macOS, pressione <kbd>Cmd</kbd>+<kbd>P</kbd>.
   1. Em Abertura rápida, digite `ext install powershell` e pressione **Enter**.
   1. A exibição **Extensões** será aberta na barra lateral. Selecione a extensão do PowerShell da Microsoft.
      Você deverá ver uma tela do Visual Studio Code semelhante à seguinte imagem:

      ![Visual Studio Code – Exibição da extensão do PowerShell](media/using-vscode/vscode.png)

   1. Clique no botão **Instalar** na extensão do PowerShell da Microsoft.
   1. Após a instalação, se o botão **Instalar** mudar para **Recarregar**, clique em **Recarregar**.
   1. Depois que o Visual Studio Code for recarregado, você estará pronto para a edição.

Por exemplo, para criar um novo arquivo, clique em **Arquivo > Novo**. Para salvá-lo, clique em **Arquivo > Salvar** e forneça um nome de arquivo, como `HelloWorld.ps1`. Para fechar o arquivo, clique no `X` ao lado do nome de arquivo. Para sair do Visual Studio Code, **Arquivo > Sair**.

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>Instalando a extensão do PowerShell em sistemas restritos

Alguns sistemas são configurados para exigir a validação de todas as assinaturas de código. Você poderá receber o seguinte erro:

```
Language server startup failed.
```

Esse problema pode ocorrer quando a política de execução do PowerShell é definida pela Política de Grupo do Windows. Para aprovar manualmente os Serviços do Editor do PowerShell e a extensão do PowerShell para o Visual Studio Code, abra um prompt do PowerShell e execute o seguinte comando:

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

O sistema mostrará a mensagem **Você deseja executar o software desse editor não confiável?** Digite `A` para executar o arquivo. Em seguida, abra o Visual Studio Code e verifique se a extensão do PowerShell está funcionando corretamente. Se você ainda tiver problemas para começar, fale conosco sobre [problemas do GitHub][].

> [!NOTE]
> A extensão do PowerShell para o Visual Studio Code não dá suporte à execução no modo de linguagem restrita. Para obter mais informações, confira [problema 606 do GitHub][i606].

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>Escolha de uma versão do PowerShell para ser usada com a extensão

Com o PowerShell Core instalado com o Windows PowerShell, agora é possível usar uma versão específica do PowerShell com a extensão do PowerShell. Esse recurso analisa alguns caminhos conhecidos em diferentes sistemas operacionais para descobrir locais de instalação do PowerShell.

Siga as etapas a seguir para escolher a versão:

1. Abra a **Paleta de comandos** no Windows ou Linux com <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>. No macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
1. Pesquise por **Sessão**.
1. Clique em **PowerShell: mostrar menu de sessão**.
1. Na lista, escolha a versão do PowerShell que deseja usar, por exemplo: **PowerShell Core**.

Se você instalou o PowerShell em um local não típico, talvez ele não apareça inicialmente no menu de sessão. Você pode estender o menu de sessão [adicionando seus próprios caminhos personalizados](#adding-your-own-powershell-paths-to-the-session-menu) conforme descrito abaixo.

> [!NOTE]
> O menu de sessão do PowerShell também pode ser acessado pelo número de versão verde no canto inferior direito da barra de status. Clicar nesse número de versão abrirá o menu de sessão.

## <a name="configuration-settings-for-visual-studio-code"></a>Definições de configuração para o Visual Studio Code

Primeiro, caso você não esteja familiarizado com a maneira de alterar as configurações no Visual Studio Code, recomendamos ler a [documentação de configurações do Visual Studio Code][vsc-settings].

Depois de ler a documentação, você pode adicionar definições de configuração no `settings.json`.

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

Caso você não queira que essas configurações afetem todos os tipos de arquivos, o Visual Studio Code também permite configurações por idioma. Crie uma configuração específica a um idioma colocando as configurações em um campo `[<language-name>]`. Por exemplo:

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> Para saber mais sobre a codificação de arquivo no Visual Studio Code, confira [Noções básicas sobre codificação de arquivo][file-encoding].
>
> Confira também [Como replicar a experiência do ISE no Visual Studio Code][vsc-ise] para obter outras dicas sobre como configurar o Visual Studio Code para edição no PowerShell.

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a>Adição dos seus caminhos do PowerShell ao menu de sessão

É possível adicionar outros caminhos executáveis do PowerShell ao menu de sessão por meio de uma [configuração do Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.

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

- `exePath`: o caminho para o executável `pwsh` ou `powershell`.
- `versionName`: o texto que aparece no menu de sessão.

Para configurar a versão padrão do PowerShell, defina o valor `powershell.powerShellDefaultVersion` para o texto exibido no menu de sessão (também conhecido como `versionName`):

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

Depois de definir essa configuração, reinicie o Visual Studio Code ou, para recarregar a janela atual do Visual Studio Code na **Paleta de Comandos**, digite **Developer: Reload Window**.

Se você abrir o menu de sessão, agora verá versões adicionais do PowerShell.

> [!NOTE]
> Compilar o PowerShell na origem é uma ótima maneira de testar sua compilação local do PowerShell.

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a>Usar uma versão mais antiga da extensão do PowerShell para Windows PowerShell v3 e v4

A extensão atual do PowerShell não dá suporte ao [PowerShell v3 e v4][i1310]. No entanto, você pode usar a última versão da extensão que dá suporte ao PowerShell v3 e v4.

> [!CAUTION]
> Não haverá correções adicionais para essa versão mais antiga da extensão. Ela é fornecida "no estado em que se encontra", mas estará disponível para você caso ainda esteja usando o Windows PowerShell v3 e v4.

Primeiro, abra o painel Extensão e pesquise por `PowerShell`. Em seguida, clique na engrenagem e selecione **Instalar outra versão...** .

![Item de menu – Instalar outra versão…](media/using-vscode/install-another-version.png)

Selecione a versão **2020.1.0**. Essa versão da extensão foi a última com suporte ao v3 e v4. Adicione a seguinte configuração para que a versão da extensão não seja atualizada automaticamente:

```json
{
    "extensions.autoUpdate": false
}
```

A versão **2020.1.0** funcionará por um futuro próximo. No entanto, o Visual Studio Code pode implementar uma alteração que interrompa essa versão da extensão. Devido a isso e à falta de suporte, recomendamos:

- Atualizar para o Windows PowerShell 5.1
- Instalar o PowerShell 7, que é uma instalação lado a lado do Windows PowerShell e funciona melhor com a extensão do PowerShell

## <a name="debugging-with-visual-studio-code"></a>Depuração com o Visual Studio Code

### <a name="no-workspace-debugging"></a>Depuração sem espaço de trabalho

No Visual Studio Code versão 1.9 (ou posterior), é possível depurar scripts do PowerShell sem abrir a pasta que contém o script do PowerShell.

1. Abra o arquivo de script do PowerShell com **Arquivo > Abrir Arquivo...**
1. Defina um ponto de interrupção – selecione uma linha e pressione <kbd>F9</kbd>
1. Pressione <kbd>F5</kbd> para iniciar a depuração

Será exibido o painel de ações de depuração, que permite que você interrompa o depurador, execute em etapas, retome e pare a depuração.

### <a name="workspace-debugging"></a>Depuração do workspace

A depuração do workspace refere-se à depuração no contexto de uma pasta que você abriu no menu **Arquivo** usando **Abrir Pasta...** . A pasta que você abrir normalmente é a pasta do projeto do PowerShell ou a raiz do repositório Git. A depuração do workspace permite definir várias configurações de depuração diferentes de depurar apenas o arquivo aberto no momento.

Siga estas etapas para criar um arquivo de configuração de depuração:

1. Abra a exibição **Depurar** no Windows ou Linux pressionando <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>. No macOS, pressione <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.
1. Clique no link **criar um arquivo launch.json**.
1. No prompt **Selecionar Ambiente**, escolha **PowerShell**.
1. Escolha o tipo de depuração que você deseja usar:

   - **Iniciar o Arquivo Atual** – inicie e depure o arquivo na janela do editor atualmente ativa
   - **Iniciar Script** – inicie e depure o arquivo ou comando especificado
   - **Sessão Interativa** – depure os comandos executados no Console Integrado
   - **Anexar** – anexe o depurador a um processo de host do PowerShell em execução

O Visual Studio Code cria um diretório e um arquivo `.vscode\launch.json` na raiz da sua pasta do workspace para armazenar a configuração de depuração. Se os arquivos estiverem em um repositório Git, normalmente você desejará confirmar o arquivo `launch.json`. O conteúdo do arquivo `launch.json` e:

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

Esse arquivo representa os cenários comuns de depuração. Ao abrir este arquivo no editor, você vê um botão **Adicionar configuração...** . É possível clicar nesse botão para adicionar mais configurações de depuração do PowerShell. Uma configuração útil a adicionar é **PowerShell: Iniciar Script**. Com essa configuração, é possível especificar um arquivo contendo os argumentos opcionais usados sempre que você pressiona <kbd>F5</kbd>, não importa qual arquivo está ativo no editor.

Depois que a configuração de depuração for estabelecida, você poderá selecionar qual configuração deseja usar durante uma sessão de depuração. Selecione uma configuração na lista suspensa de configuração de depuração, na barra de ferramentas da exibição **Depurar**.

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a>Solucionar problemas na extensão do PowerShell para Visual Studio Code

Se você tiver problemas ao usar o Visual Studio Code para desenvolver scripts do PowerShell, confira o [guia de solução de problemas][troubleshooting] no GitHub.

## <a name="useful-resources"></a>Recursos úteis

Há alguns vídeos e postagens no blog que podem ser úteis para você começar a usar a extensão do PowerShell para o Visual Studio Code:

### <a name="videos"></a>vídeos

- [Usar o Visual Studio Code como seu editor padrão do PowerShell](https://youtu.be/bGn45vIeAMM)
- [Visual Studio Code: análise aprofundada sobre a depuração de scripts do PowerShell](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a>Postagens no blog

- [Extensão do PowerShell][pscdn]
- [Gravar e depurar scripts do PowerShell no Visual Studio Code][debug]
- [Diretrizes sobre depuração no Visual Studio Code][psdbgblog]
- [Depuração do PowerShell no Visual Studio Code][psdbg-gh]
- [Introdução ao desenvolvimento do PowerShell no Visual Studio Code][getting-started]
- [Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 1][editing-part1]
- [Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 2][editing-part2]
- [Depuração de script do PowerShell no Visual Studio Code– parte 1][debugging-part1]
- [Depuração de script do PowerShell no Visual Studio Code– parte 2][debugging-part2]

## <a name="powershell-extension-project-source-code"></a>Código-fonte do projeto de extensão do PowerShell

O código-fonte da extensão do PowerShell pode ser encontrado no [GitHub][psext-src].

Se você tem interesse em contribuir, as solicitações de pull são uma ótima opção. Siga a [documentação de desenvolvedor][dev-docs] no GitHub para começar.

<!-- related articles -->
[ise]:                    ../../windows-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:   ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:   ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]:          ../../install/Installing-Windows-PowerShell.md
[file-encoding]:          understanding-file-encoding.md
[vsc-ise]:                How-To-Replicate-the-ISE-Experience-In-VSCode.md

<!-- blogs -->
[debug]:                  https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[debugging-part1]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/
[editing-part1]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[getting-started]:        https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[psdbgblog]:              https://johnpapa.net/debugging-with-visual-studio-code/
[psdbg-gh]:               https://github.com/PowerShell/vscode-powershell/tree/master/examples
[pscdn]:                  https://docs.microsoft.com/archive/blogs/cdndevs/visual-studio-code-powershell-extension

<!-- issues -->
[Problemas do GitHub]:          https://github.com/PowerShell/vscode-powershell/issues
[i1310]:                  https://github.com/PowerShell/vscode-powershell/issues/1310
[i606]:                   https://github.com/PowerShell/vscode-powershell/issues/606

<!-- product links -->
[Visual Studio]:          https://visualstudio.microsoft.com/
[vscode]:                 https://code.visualstudio.com/
[psext]:                  https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[vsc-settings]:           https://code.visualstudio.com/docs/getstarted/settings
[vsc-setup]:              https://code.visualstudio.com/Docs/setup/setup-overview
[vsc-setup-win]:          https://code.visualstudio.com/docs/setup/windows
[vsc-setup-macos]:        https://code.visualstudio.com/docs/setup/mac
[vsc-setup-linux]:        https://code.visualstudio.com/docs/setup/linux
[psext-src]:              https://github.com/PowerShell/vscode-powershell
[troubleshooting]:        https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md
[dev-docs]:               https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md
