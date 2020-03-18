---
title: Como replicar a experiência do ISE no Visual Studio Code
description: Como replicar a experiência do ISE no Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 193243dc2e3e921b22a6ee068370200ae84ce4ac
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279224"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Como replicar a experiência do ISE no Visual Studio Code

Embora a extensão do PowerShell para VSCode não exija paridade de recursos perfeita com o ISE do PowerShell, há recursos definidos para tornar a experiência do VSCode mais natural aos usuários do ISE.

Este documento tenta listar configurações que você pode definir no VSCode para tornar a experiência do usuário um pouco mais familiar em comparação com o ISE.

## <a name="ise-mode"></a>Modo ISE

> [!NOTE]
> Esse recurso está disponível na extensão do da Versão Prévia do PowerShell desde a versão 2019.12.0 e na extensão do PowerShell desde a versão 2020.3.0.

A maneira mais fácil de replicar a experiência do ISE no Visual Studio Code é ativar o "Modo ISE".
Para fazer isso, abra a paleta de comandos (<kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OU <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS) e digite "Modo ISE".
Selecione "PowerShell: Habilitar modo ISE" na lista.

Este comando aplicará muitas das configurações encontradas neste documento automaticamente.
O resultado será semelhante a este:

![Modo ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

O restante deste artigo inclui informações mais detalhadas sobre configurações no modo ISE e algumas configurações adicionais.

## <a name="key-bindings"></a>Associações de teclas

| Função                              | Associação do ISE                  | Associação do VSCode                              |
| ----------------                      | -----------                  | --------------                              |
| Interromper o depurador          | <kbd>Ctrl</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
| Executar texto destacado/linha atual | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
| Listar snippets disponíveis               | <kbd>Ctrl</kbd>+<kbd>J</kbd> | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

### <a name="custom-key-bindings"></a>Associações de teclas personalizadas

Você também pode [configurar suas próprias associações de teclas](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) no VSCode.

## <a name="simplified-ise-like-ui"></a>Interface do usuário simplificada semelhante à do ISE

Se você estiver procurando simplificar a interface do usuário do Visual Studio Code para ter uma aparência mais próxima da interface do usuário do ISE, aplique estas duas configurações:

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

> [!NOTE]
> Essas configurações estão incluídas no ["Modo ISE"](#ise-mode).

Isso ocultará as seções "Barra de Atividades" e "Barra Lateral de Depuração" abaixo na caixa vermelha:

![a seção realçada inclui a Barra de Atividades e a Barra Lateral de Depuração](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

O resultado final se parece com o seguinte:

![Exibição simplificada do VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a>Preenchimento de guias

Para habilitar um preenchimento com Tab mais semelhante ao ISE, adicione esta configuração:

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> Essa configuração foi adicionada diretamente ao VSCode (não à extensão). Seu comportamento é determinado diretamente pelo VSCode e não pode ser alterado pela extensão.

> [!NOTE]
> Essa configuração está incluída no ["Modo ISE"](#ise-mode).

## <a name="no-focus-on-console-when-executing"></a>Sem foco no console ao executar

Para manter o destaque no editor ao executar com <kbd>F8</kbd>:

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

> [!NOTE]
> Essa configuração está incluída no ["Modo ISE"](#ise-mode).

O padrão é `true` para fins de acessibilidade.

## <a name="dont-start-integrated-console-on-startup"></a>Não inicie o console integrado na inicialização

Para interromper o console integrado na inicialização, defina:

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> O processo do PowerShell em segundo plano ainda será iniciado, uma vez que isso proporciona análise de script, navegação de símbolo, IntelliSense, etc. Porém o console não será mostrado.

## <a name="assume-files-are-powershell-by-default"></a>Pressupor que os arquivos sejam do PowerShell por padrão

Para tornar os arquivos novos/sem título, registre-os como PowerShell por padrão:

```json
"files.defaultLanguage": "powershell",
```

> [!NOTE]
> Essa configuração está incluída no ["Modo ISE"](#ise-mode).

## <a name="color-scheme"></a>Esquema de cores

Há vários temas do ISE disponíveis para VSCode para tornar a aparência do editor muito mais parecida com a do ISE.

Na [Paleta de Comandos], digite `theme` para obter `Preferences: Color Theme` e pressione <kbd>Enter</kbd>.
Na lista suspensa, selecione `PowerShell ISE`.

Você pode definir esse tema nas configurações com:

```json
"workbench.colorTheme": "PowerShell ISE",
```

> [!NOTE]
> Essa configuração está incluída no ["Modo ISE"](#ise-mode).

## <a name="powershell-command-explorer"></a>Gerenciador de comandos do PowerShell

Graças ao trabalho de [@corbob](https://github.com/corbob), a extensão do PowerShell tem os princípios de seu próprio gerenciador de comandos.

Na [Paleta de Comandos], digite `PowerShell Command Explorer` e pressione <kbd>Enter</kbd>.

> [!NOTE]
> Isto é mostrado automaticamente no ["Modo ISE"](#ise-mode).

## <a name="open-in-the-ise"></a>Abrir no ISE

Caso queira abrir um arquivo no ISE mesmo assim, use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.

## <a name="other-resources"></a>Outros recursos

- O blog 4sysops tem [um excelente artigo](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) sobre como configurar o VSCode para ser mais parecido com o ISE.
- Mike F. Robbins tem [uma excelente postagem](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) sobre como configurar o VSCode.
- Saiba que o PowerShell conta com [um excelente manual detalhado](https://www.learnpwsh.com/setup-vs-code-for-powershell/) sobre a configuração do VSCode para PowerShell.

## <a name="more-settings"></a>Mais configurações

Se você conhece outras maneiras de tornar o VSCode mais familiar aos usuários do ISE, contribua com esse documento. Se você está procurando por uma configuração de compatibilidade, mas não consegue encontrar onde habilitá-la, [abra uma ocorrência](https://github.com/PowerShell/vscode-powershell/issues/new/choose) e pergunte!

Também gostamos de receber PRs e contribuições!

## <a name="vscode-tips"></a>Dicas do VSCode

### <a name="command-palette"></a>Paleta de Comandos

<kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS)

Uma maneira útil de executar comandos no VSCode.
Para saber mais, confira [os documentos do VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).

[Paleta de comandos]: #command-palette
