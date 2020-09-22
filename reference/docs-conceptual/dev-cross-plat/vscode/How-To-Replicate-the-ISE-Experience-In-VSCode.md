---
title: Como replicar a experiência do ISE no Visual Studio Code
description: Como replicar a experiência do ISE no Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 6b0b8ce054695d6cc0fc578290c554e2dc1472bc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784615"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Como replicar a experiência do ISE no Visual Studio Code

Embora a extensão do PowerShell para VS Code não exija paridade de recursos perfeita com o ISE do PowerShell, há recursos definidos para tornar a experiência do VS Code mais natural aos usuários do ISE.

Este documento tenta listar configurações que você pode definir no VS Code para tornar a experiência do usuário um pouco mais familiar em comparação com o ISE.

## <a name="ise-mode"></a>Modo ISE

> [!NOTE]
> Esse recurso está disponível na extensão do da Versão Prévia do PowerShell desde a versão 2019.12.0 e na extensão do PowerShell desde a versão 2020.3.0.

A maneira mais fácil de replicar a experiência do ISE no Visual Studio Code é ativar o "Modo ISE".
Para fazer isso, abra a paleta de comandos (<kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OU <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS) e digite "Modo ISE". Selecione "PowerShell: Habilitar modo ISE" na lista.

Esse comando aplica automaticamente as configurações descritas abaixo. O resultado é semelhante a este:

![Visual Studio Code no modo ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a>Definições de configuração do modo ISE

O modo ISE faz as alterações a seguir nas configurações do VS Code.

- Associações de teclas

  |               Função                |         Associação do ISE          |              Associação do VS Code                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | Interromper o depurador          | <kbd>Ctrl</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
  | Executar texto destacado/linha atual | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
  | Listar snippets disponíveis               | <kbd>Ctrl</kbd>+<kbd>J</kbd> | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

  > [!NOTE]
  > Você também pode [configurar suas próprias associações de teclas](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) no VS Code.

- Interface do usuário simplificada semelhante à do ISE

  Se você estiver procurando simplificar a interface do usuário do Visual Studio Code para ter uma aparência mais próxima da interface do usuário do ISE, aplique estas duas configurações:

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  Essas configurações ocultam as seções "Barra de Atividades" e "Barra Lateral de Depuração" mostradas na caixa vermelha abaixo:

  ![A seção realçada inclui a Barra de Atividades e a Barra Lateral de Depuração](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  O resultado final se parece com o seguinte:

  ![Exibição simplificada do VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- Preenchimento de guias

  Para habilitar um preenchimento com Tab mais semelhante ao ISE, adicione esta configuração:

  ```json
  "editor.tabCompletion": "on",
  ```

- Sem foco no console ao executar

  Para manter o destaque no editor ao executar com <kbd>F8</kbd>:

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  O padrão é `true` para fins de acessibilidade.

- Não inicie o console integrado na inicialização

  Para interromper o console integrado na inicialização, defina:

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > O processo em segundo plano do PowerShell ainda começa a fornecer IntelliSense, análise de script, navegação de símbolos, entre outros, mas o console não será mostrado.

- Pressupor que os arquivos sejam do PowerShell por padrão

  Para tornar os arquivos novos/sem título, registre-os como PowerShell por padrão:

  ```json
  "files.defaultLanguage": "powershell",
  ```

- Esquema de cores

  Há vários temas do ISE disponíveis para VS Code a fim de tornar a aparência do editor muito mais parecida com a do ISE.

  Na [Paleta de Comandos][], digite `theme` para obter `Preferences: Color Theme` e pressione <kbd>Enter</kbd>. Na lista suspensa, selecione `PowerShell ISE`.

  Você pode definir esse tema nas configurações com:

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- Gerenciador de comandos do PowerShell

  Graças ao trabalho de [@corbob](https://github.com/corbob), a extensão do PowerShell tem os princípios de seu próprio gerenciador de comandos.

  Na [Paleta de Comandos][], digite `PowerShell Command Explorer` e pressione <kbd>Enter</kbd>.

- Abrir no ISE

  Se você, ainda assim, deseja abrir um arquivo no Windows PowerShell ISE, abra a [Paleta de Comandos][], procure "abrir no ise" e selecione **PowerShell: abrir o arquivo atual no ISE do PowerShell**.

## <a name="other-resources"></a>Outros recursos

- O blog 4sysops tem [um excelente artigo][4sysops] sobre como configurar o VS Code para que ele fique mais parecido com o ISE.
- Mike F. Robbins tem [uma excelente postagem][mikefrobbins] sobre como configurar o VS Code.
<!-- - Learn PowerShell has [an excellent write up][learnpwsh] setup for PowerShell. -->

## <a name="vs-code-tips"></a>Dicas de VS Code

- Paleta de Comandos

  A Paleta de Comandos é um recurso prático que permite executar comandos no VS Code. Abra a paleta de comandos clicando em <kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OU <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS.

  Para saber mais, confira [a documentação VS Code][vsc-docs].

- Desabilitar o console de depuração

  Se você planeja usar o VS Code apenas para scripts do PowerShell, é possível ocultar o **Console de Depuração**, pois ele não é usado pela extensão do PowerShell. Para fazer isso, clique com o botão direito do mouse em **Console de Depuração** e clique na marca de seleção para ocultá-lo.

## <a name="more-settings"></a>Mais configurações

Se você souber mais maneiras de fazer o VS Code parecer mais familiar para os usuários do ISE, colabore com este documento. Se você está procurando por uma configuração de compatibilidade, mas não consegue encontrar onde habilitá-la, [abra uma ocorrência][] e pergunte!

Também gostamos de receber PRs e contribuições!

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[Paleta de comandos]: #vs-code-tips
[abrir um problema]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
