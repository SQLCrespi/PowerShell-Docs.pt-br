---
title: Como replicar a experiência do ISE no Visual Studio Code
description: Como replicar a experiência do ISE no Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: d5542e9a3a48b1ae64356309be669418edf6c79e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74117498"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Como replicar a experiência do ISE no Visual Studio Code

Embora a extensão do PowerShell para VSCode não exija paridade de recursos perfeita com o ISE do PowerShell, há recursos definidos para tornar a experiência do VSCode mais natural aos usuários do ISE.

Este documento tenta listar configurações que você pode definir no VSCode para tornar a experiência do usuário um pouco mais familiar em comparação com o ISE.

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

Isso ocultará as seções "Barra de Atividades" e "Barra Lateral de Depuração" abaixo na caixa vermelha:

![a seção realçada inclui a Barra de Atividades e a Barra Lateral de Depuração](images/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

O resultado final se parece com o seguinte:

![Exibição simplificada do VS Code](images/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a>Preenchimento de guias

Para habilitar um preenchimento com Tab mais semelhante ao ISE, adicione esta configuração:

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> Essa configuração foi adicionada diretamente ao VSCode (não à extensão). Seu comportamento é determinado diretamente pelo VSCode e não pode ser alterado pela extensão.

## <a name="no-focus-on-console-when-executing"></a>Sem destaque no console durante a execução

Para manter o destaque no editor ao executar com <kbd>F8</kbd>:

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

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

## <a name="color-scheme"></a>Esquema de cores

Há vários temas do ISE disponíveis para VSCode para tornar a aparência do editor muito mais parecida com a do ISE.

Na [Paleta de Comandos], digite `theme` para obter `Preferences: Color Theme` e pressione <kbd>Enter</kbd>.
Na lista suspensa, selecione `PowerShell ISE`.

Você pode definir esse tema nas configurações com:

```json
"workbench.colorTheme": "PowerShell ISE",
```

## <a name="powershell-command-explorer"></a>Gerenciador de comandos do PowerShell

Graças ao trabalho de [@corbob](https://github.com/corbob), a extensão do PowerShell tem os princípios de seu próprio gerenciador de comandos.

Na [Paleta de Comandos], digite `PowerShell Command Explorer` e pressione <kbd>Enter</kbd>.

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

### <a name="command-palette"></a>Paleta de comandos

<kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS)

Uma maneira útil de executar comandos no VSCode.
Para saber mais, confira [os documentos do VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).

[Paleta de comandos]: #command-palette
