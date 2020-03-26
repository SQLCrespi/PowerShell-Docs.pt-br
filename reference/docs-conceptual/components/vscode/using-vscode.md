---
title: Uso do Visual Studio Code para desenvolvimento do PowerShell
description: Uso do Visual Studio Code para desenvolvimento do PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 86739970b58460bef9686a75bf0604d0605d4888
ms.sourcegitcommit: d36db3a1bc44aee6bc97422b557041c3aece4c67
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80082424"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>Uso do Visual Studio Code para desenvolvimento do PowerShell

O [Visual Studio Code](https://code.visualstudio.com/) é um editor de scripts multiplataforma (Windows, macOS e Linux) da Microsoft. Junto com a [extensão do PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell), ele fornece uma experiência rica e interativa de edição de scripts, facilitando a criação de scripts confiáveis do PowerShell.

O Visual Studio Code com a extensão do PowerShell é o editor recomendado para escrever scripts do PowerShell.
Ele dá suporte às seguintes versões do PowerShell:

- PowerShell 7 e posterior
- PowerShell Core 6
- Windows PowerShell 5.1

Antes de começar, verifique se o PowerShell existe no seu sistema. Para cargas de trabalho modernas no Windows, macOS e Linux, confira os seguintes links:

- [Instalar o PowerShell Core no Linux][install-pscore-linux]
- [Instalar o PowerShell Core no macOS][install-pscore-macos]
- [Instalar o PowerShell Core no Windows][install-pscore-windows]

Para cargas de trabalho tradicionais do Windows PowerShell, confira [Como instalar o Windows PowerShell][install-winps].

> [!NOTE]
> Visual Studio Code não é o mesmo que [Visual Studio](https://visualstudio.microsoft.com/).

> [!IMPORTANT]
> O [ISE do Windows PowerShell][ise] ainda está disponível para o Windows, no entanto, ele não está mais no desenvolvimento ativo de recursos e não funciona com o PowerShell 7 e posteriores ou com o PowerShell Core 6.
> Como componente de remessa do Windows, ele continua com suporte oficial para correções de segurança e serviços de alta prioridade. No momento, não há planos de remover o ISE do Windows.

## <a name="editing-with-visual-studio-code"></a>Edição com o Visual Studio Code

1. Instale o Visual Studio Code. Para obter mais informações, confira a visão geral [Configurar o Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).

    Há instruções de instalação para cada plataforma:

    - **Windows**: siga as instruções de instalação na página [Executar o Visual Studio Code no Windows](https://code.visualstudio.com/docs/setup/windows).
    - **macOS**: siga as instruções de instalação na página [Executar o Visual Studio Code no macOS](https://code.visualstudio.com/docs/setup/mac).
    - **Linux**: siga as instruções de instalação na página [Executar o Visual Studio Code no Linux](https://code.visualstudio.com/docs/setup/linux).

1. Instale a extensão do PowerShell.

   1. Inicie o aplicativo do Visual Studio Code digitando `code` em um console ou `code-insiders` se você instalou o Visual Studio Code Insiders.
   1. Inicie o **Abertura rápida** no Windows ou no Linux pressionando <kbd>Ctrl</kbd>+<kbd>P</kbd>. No macOS, pressione <kbd>Cmd</kbd>+<kbd>P</kbd>.
   1. Em Abertura rápida, digite `ext install powershell` e pressione **Enter**.
   1. A exibição **Extensões** será aberta na barra lateral. Selecione a extensão do PowerShell da Microsoft.
      Você deverá ver uma tela do Visual Studio Code semelhante à seguinte imagem:

      ![Visual Studio Code](media/using-vscode/vscode.png)

   1. Clique no botão **Instalar** na extensão do PowerShell da Microsoft.
   1. Após a instalação, se o botão **Instalar** mudar para **Recarregar**, clique em **Recarregar**.
   1. Depois que o Visual Studio Code for recarregado, você estará pronto para a edição.

Por exemplo, para criar um novo arquivo, clique em **Arquivo > Novo**. Para salvá-lo, clique em **Arquivo > Salvar** e forneça um nome de arquivo, como `HelloWorld.ps1`. Para fechar o arquivo, clique no `X` ao lado do nome de arquivo. Para sair do Visual Studio Code, **Arquivo > Sair**.

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>Instalando a extensão do PowerShell em sistemas restritos

Alguns sistemas são configurados de forma a exigir que todas as assinaturas de código sejam verificadas e exigem que os Serviços do Editor do PowerShell sejam aprovados manualmente para serem executados no sistema. Uma atualização da Política de Grupo que altera a política de execução é uma causa provável caso tenha instalado a extensão do PowerShell, mas está recebendo um erro como:

```
Language server startup failed.
```

Para aprovar manualmente os Serviços do Editor do PowerShell e a extensão do PowerShell para o Visual Studio Code, abra um prompt do PowerShell e execute o seguinte comando:

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

O sistema mostrará a mensagem **Você deseja executar o software desse editor não confiável?**
Digite `A` para executar o arquivo. Em seguida, abra o Visual Studio Code e verifique se a extensão do PowerShell está funcionando corretamente. Se você ainda tiver problemas para começar, fale conosco no [GitHub](https://github.com/PowerShell/vscode-powershell/issues).

> [!NOTE]
> A extensão do PowerShell para o Visual Studio Code não dá suporte à execução no modo de linguagem restrita. Para obter mais informações, confira o [problema do GitHub que acompanha esse suporte](https://github.com/PowerShell/vscode-powershell/issues/606).

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a>Usar uma versão mais antiga da extensão do PowerShell para Windows PowerShell v3 e v4

Embora a extensão atual do PowerShell [tenha interrompido o suporte ao v3 e v4](https://github.com/PowerShell/vscode-powershell/issues/1310), você ainda pode usar a última versão da extensão que oferecia suporte.

> [!NOTE]
> Não haverá correções adicionais para essa versão mais antiga da extensão. Ela é fornecida "no estado em que se encontra", mas estará disponível para você caso ainda esteja usando o Windows PowerShell v3 e v4.

Primeiro, abra o painel Extensão e pesquise por `PowerShell`. Em seguida, clique na engrenagem e selecione **Instalar outra versão...** .

![Instalar outra versão...](media/using-vscode/install-another-version.png)

Depois, selecione a versão **`2020.1.0`** . Essa versão da extensão foi a última com suporte ao v3 e v4.

Além disso, adicione a seguinte configuração para que a versão da extensão não seja atualizada automaticamente:

```json
{
    "extensions.autoUpdate": false
}
```

Isso funcionará no futuro próximo, mas o Visual Studio Code pode implementar uma alteração que interrompa essa versão da extensão.
Devido a isso e à falta de suporte, nós recomendamos:

- Baixar o PowerShell 7 – que é uma instalação lado a lado do Windows PowerShell e funciona melhor com a extensão do PowerShell
- Atualizar para o Windows PowerShell 5.1

A seção [Editar com o Visual Studio Code](#editing-with-visual-studio-code) neste artigo contém links sobre onde instalá-lo.

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>Escolha de uma versão do PowerShell para ser usada com a extensão

Com o PowerShell Core instalado com o Windows PowerShell, agora é possível usar uma versão específica do PowerShell com a extensão do PowerShell. Siga as etapas a seguir para escolher a versão:

1. Abra a **Paleta de comandos** no Windows ou Linux com <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>. No macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.
1. Pesquise por **Sessão**.
1. Clique em **PowerShell: mostrar menu de sessão**.
1. Na lista, escolha a versão do PowerShell que deseja usar, por exemplo: **PowerShell Core**.

> [!IMPORTANT]
> Esse recurso analisa alguns caminhos conhecidos em diferentes sistemas operacionais para descobrir locais de instalação do PowerShell. Se você instalou o PowerShell em um local não típico, talvez ele não apareça inicialmente no menu de sessão. Você pode estender o menu de sessão [adicionando seus próprios caminhos personalizados](#adding-your-own-powershell-paths-to-the-session-menu) conforme descrito abaixo.

>[!NOTE]
> Há outra maneira de acessar o menu de sessão. Quando um arquivo do PowerShell é aberto no editor, um número de versão em verde aparece no canto inferior direito. Clicar nesse número de versão levará ao menu de sessão.

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

É possível definir a versão padrão do PowerShell para usar a configuração `powershell.powerShellDefaultVersion` definindo-a como o texto exibido no menu de sessão (também conhecido como `versionName` na última configuração):

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

### <a name="configuration-settings-for-visual-studio-code"></a>Definições de configuração para o Visual Studio Code

Primeiro, se você não estiver familiarizado com a maneira de alterar as configurações no Visual Studio Code, recomendamos ler a [documentação de configurações do Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings).

Usando as etapas no parágrafo anterior, você pode adicionar configurações no `settings.json`.

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
> Para saber mais sobre a codificação de arquivo no Visual Studio Code, confira [Noções básicas sobre codificação de arquivo](understanding-file-encoding.md).
>
> Confira também [Como replicar a experiência do ISE no Visual Studio Code](How-To-Replicate-the-ISE-Experience-In-VSCode.md) para obter outras dicas sobre como configurar o Visual Studio Code para edição no PowerShell.

## <a name="debugging-with-visual-studio-code"></a>Depuração com o Visual Studio Code

### <a name="no-workspace-debugging"></a>Depuração sem espaço de trabalho

A partir da versão 1.9 do Visual Studio Code, é possível depurar scripts do PowerShell sem abrir a pasta que contém o script do PowerShell. Abra o arquivo de script do PowerShell usando **Arquivo > Abrir Arquivo…** , defina um ponto de interrupção em uma linha, pressione <kbd>F9</kbd> e <kbd>F5</kbd> para iniciar a depuração. Será exibido o painel de ações de depuração, que permite que você interrompa o depurador, execute em etapas, retome e pare a depuração.

### <a name="workspace-debugging"></a>Depuração do workspace

A depuração do workspace refere-se a depuração no contexto de uma pasta que você abriu no Visual Studio Code a partir do menu **Arquivo** usando **Abrir Pasta...** . A pasta que você abrir normalmente é a pasta do projeto do PowerShell e/ou a raiz do repositório Git.

Mesmo nesse modo, é possível iniciar a depuração de script do PowerShell selecionado no momento pressionando <kbd>F5</kbd>. No entanto, a depuração do workspace permite definir várias configurações de depuração diferentes de depurar apenas o arquivo aberto no momento. Abordaremos isso em um momento.

Siga estas etapas para criar o arquivo de configuração de depuração:

  1. Abra a exibição **Depurar** no Windows ou Linux pressionando <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>. No macOS, pressione <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.
  1. Clique no link "criar um arquivo launch.json".
  1. O Visual Studio Code solicitará que você **Selecione o Ambiente**. Escolha **PowerShell**.
  1. Por fim, escolha o tipo de depuração que deseja usar:

- **Iniciar o Arquivo Atual** – inicie e depure o arquivo na janela do editor atualmente ativa
- **Iniciar Script** – inicie e depure o arquivo ou comando especificado
- **Sessão Interativa** – depure os comandos executados no Console Integrado
- **Anexar** – anexe o depurador a um processo de host do PowerShell em execução

O resultado é que o Visual Studio Code cria um diretório e um arquivo `.vscode\launch.json` na raiz da sua pasta do espaço de trabalho. A configuração de depuração é armazenada nesse local. Se os arquivos estiverem em um repositório Git, normalmente você desejará confirmar o arquivo `launch.json`. O conteúdo do arquivo `launch.json` e:

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

Esse arquivo representa os cenários comuns de depuração. Ao abrir este arquivo no editor, você vê um botão **Adicionar configuração...** . É possível clicar nesse botão para adicionar mais configurações de depuração do PowerShell. Uma configuração útil a adicionar é **PowerShell: Iniciar Script**. Com essa configuração, é possível especificar um arquivo com argumentos opcionais que devem ser iniciados sempre que você pressionar <kbd>F5</kbd>, não importa qual arquivo está ativo no momento no editor.

Depois que a configuração de depuração for estabelecida, você poderá selecionar qual configuração deseja usar durante uma sessão de depuração. Selecione uma configuração na lista suspensa de configuração de depuração, na barra de ferramentas da exibição **Depurar**.

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
[install-pscore-linux]:  ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../install/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-visual-studio-code"></a>Extensão do PowerShell para Visual Studio Code

O código-fonte da extensão do PowerShell pode ser encontrado no [GitHub](https://github.com/PowerShell/vscode-powershell).

Se você tem interesse em contribuir, a solicitação de pull é uma ótima opção. Siga a [documentação de desenvolvedor no GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md) para começar.

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a>Solucionar problemas na extensão do PowerShell para Visual Studio Code

Se você tiver problemas ao usar o Visual Studio Code para desenvolver scripts do PowerShell, confira o [guia de solução de problemas no GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)
