---
title: Como replicar a experiência do ISE no Visual Studio Code
description: Como replicar a experiência do ISE no Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: d5542e9a3a48b1ae64356309be669418edf6c79e
ms.sourcegitcommit: a6e54a305fdeb6482321c77da8066d2f991c93e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "74117498"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="3a185-103">Como replicar a experiência do ISE no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3a185-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="3a185-104">Embora a extensão do PowerShell para VSCode não exija paridade de recursos perfeita com o ISE do PowerShell, há recursos definidos para tornar a experiência do VSCode mais natural aos usuários do ISE.</span><span class="sxs-lookup"><span data-stu-id="3a185-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="3a185-105">Este documento tenta listar configurações que você pode definir no VSCode para tornar a experiência do usuário um pouco mais familiar em comparação com o ISE.</span><span class="sxs-lookup"><span data-stu-id="3a185-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="3a185-106">Associações de teclas</span><span class="sxs-lookup"><span data-stu-id="3a185-106">Key bindings</span></span>

| <span data-ttu-id="3a185-107">Função</span><span class="sxs-lookup"><span data-stu-id="3a185-107">Function</span></span>                              | <span data-ttu-id="3a185-108">Associação do ISE</span><span class="sxs-lookup"><span data-stu-id="3a185-108">ISE Binding</span></span>                  | <span data-ttu-id="3a185-109">Associação do VSCode</span><span class="sxs-lookup"><span data-stu-id="3a185-109">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="3a185-110">Interromper o depurador</span><span class="sxs-lookup"><span data-stu-id="3a185-110">Interrupt and break debugger</span></span>          | <span data-ttu-id="3a185-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="3a185-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="3a185-112"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="3a185-112"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="3a185-113">Executar texto destacado/linha atual</span><span class="sxs-lookup"><span data-stu-id="3a185-113">Execute current line/highlighted text</span></span> | <span data-ttu-id="3a185-114"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="3a185-114"><kbd>F8</kbd></span></span>                | <span data-ttu-id="3a185-115"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="3a185-115"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="3a185-116">Listar snippets disponíveis</span><span class="sxs-lookup"><span data-stu-id="3a185-116">List available snippets</span></span>               | <span data-ttu-id="3a185-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="3a185-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="3a185-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="3a185-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="3a185-119">Associações de teclas personalizadas</span><span class="sxs-lookup"><span data-stu-id="3a185-119">Custom Key bindings</span></span>

<span data-ttu-id="3a185-120">Você também pode [configurar suas próprias associações de teclas](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) no VSCode.</span><span class="sxs-lookup"><span data-stu-id="3a185-120">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="simplified-ise-like-ui"></a><span data-ttu-id="3a185-121">Interface do usuário simplificada semelhante à do ISE</span><span class="sxs-lookup"><span data-stu-id="3a185-121">Simplified ISE-like UI</span></span>

<span data-ttu-id="3a185-122">Se você estiver procurando simplificar a interface do usuário do Visual Studio Code para ter uma aparência mais próxima da interface do usuário do ISE, aplique estas duas configurações:</span><span class="sxs-lookup"><span data-stu-id="3a185-122">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

<span data-ttu-id="3a185-123">Isso ocultará as seções "Barra de Atividades" e "Barra Lateral de Depuração" abaixo na caixa vermelha:</span><span class="sxs-lookup"><span data-stu-id="3a185-123">This will hide the "Activity Bar" and the "Debug Side Bar" sections below inside of the red box:</span></span>

![a seção realçada inclui a Barra de Atividades e a Barra Lateral de Depuração](images/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

<span data-ttu-id="3a185-125">O resultado final se parece com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3a185-125">The end result looks like this:</span></span>

![Exibição simplificada do VS Code](images/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a><span data-ttu-id="3a185-127">Preenchimento de guias</span><span class="sxs-lookup"><span data-stu-id="3a185-127">Tab completion</span></span>

<span data-ttu-id="3a185-128">Para habilitar um preenchimento com Tab mais semelhante ao ISE, adicione esta configuração:</span><span class="sxs-lookup"><span data-stu-id="3a185-128">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> <span data-ttu-id="3a185-129">Essa configuração foi adicionada diretamente ao VSCode (não à extensão).</span><span class="sxs-lookup"><span data-stu-id="3a185-129">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="3a185-130">Seu comportamento é determinado diretamente pelo VSCode e não pode ser alterado pela extensão.</span><span class="sxs-lookup"><span data-stu-id="3a185-130">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="3a185-131">Sem destaque no console durante a execução</span><span class="sxs-lookup"><span data-stu-id="3a185-131">No focus on console when executing</span></span>

<span data-ttu-id="3a185-132">Para manter o destaque no editor ao executar com <kbd>F8</kbd>:</span><span class="sxs-lookup"><span data-stu-id="3a185-132">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

<span data-ttu-id="3a185-133">O padrão é `true` para fins de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="3a185-133">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="3a185-134">Não inicie o console integrado na inicialização</span><span class="sxs-lookup"><span data-stu-id="3a185-134">Don't start integrated console on startup</span></span>

<span data-ttu-id="3a185-135">Para interromper o console integrado na inicialização, defina:</span><span class="sxs-lookup"><span data-stu-id="3a185-135">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="3a185-136">O processo do PowerShell em segundo plano ainda será iniciado, uma vez que isso proporciona análise de script, navegação de símbolo, IntelliSense, etc. Porém o console não será mostrado.</span><span class="sxs-lookup"><span data-stu-id="3a185-136">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="3a185-137">Pressupor que os arquivos sejam do PowerShell por padrão</span><span class="sxs-lookup"><span data-stu-id="3a185-137">Assume files are PowerShell by default</span></span>

<span data-ttu-id="3a185-138">Para tornar os arquivos novos/sem título, registre-os como PowerShell por padrão:</span><span class="sxs-lookup"><span data-stu-id="3a185-138">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell",
```

## <a name="color-scheme"></a><span data-ttu-id="3a185-139">Esquema de cores</span><span class="sxs-lookup"><span data-stu-id="3a185-139">Color scheme</span></span>

<span data-ttu-id="3a185-140">Há vários temas do ISE disponíveis para VSCode para tornar a aparência do editor muito mais parecida com a do ISE.</span><span class="sxs-lookup"><span data-stu-id="3a185-140">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="3a185-141">Na [Paleta de Comandos], digite `theme` para obter `Preferences: Color Theme` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3a185-141">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="3a185-142">Na lista suspensa, selecione `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="3a185-142">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="3a185-143">Você pode definir esse tema nas configurações com:</span><span class="sxs-lookup"><span data-stu-id="3a185-143">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE",
```

## <a name="powershell-command-explorer"></a><span data-ttu-id="3a185-144">Gerenciador de comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a185-144">PowerShell Command Explorer</span></span>

<span data-ttu-id="3a185-145">Graças ao trabalho de [@corbob](https://github.com/corbob), a extensão do PowerShell tem os princípios de seu próprio gerenciador de comandos.</span><span class="sxs-lookup"><span data-stu-id="3a185-145">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="3a185-146">Na [Paleta de Comandos], digite `PowerShell Command Explorer` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3a185-146">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="3a185-147">Abrir no ISE</span><span class="sxs-lookup"><span data-stu-id="3a185-147">Open in the ISE</span></span>

<span data-ttu-id="3a185-148">Caso queira abrir um arquivo no ISE mesmo assim, use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3a185-148">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="3a185-149">Outros recursos</span><span class="sxs-lookup"><span data-stu-id="3a185-149">Other resources</span></span>

- <span data-ttu-id="3a185-150">O blog 4sysops tem [um excelente artigo](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) sobre como configurar o VSCode para ser mais parecido com o ISE.</span><span class="sxs-lookup"><span data-stu-id="3a185-150">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="3a185-151">Mike F. Robbins tem [uma excelente postagem](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) sobre como configurar o VSCode.</span><span class="sxs-lookup"><span data-stu-id="3a185-151">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="3a185-152">Saiba que o PowerShell conta com [um excelente manual detalhado](https://www.learnpwsh.com/setup-vs-code-for-powershell/) sobre a configuração do VSCode para PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a185-152">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="3a185-153">Mais configurações</span><span class="sxs-lookup"><span data-stu-id="3a185-153">More settings</span></span>

<span data-ttu-id="3a185-154">Se você conhece outras maneiras de tornar o VSCode mais familiar aos usuários do ISE, contribua com esse documento. Se você está procurando por uma configuração de compatibilidade, mas não consegue encontrar onde habilitá-la, [abra uma ocorrência](https://github.com/PowerShell/vscode-powershell/issues/new/choose) e pergunte!</span><span class="sxs-lookup"><span data-stu-id="3a185-154">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="3a185-155">Também gostamos de receber PRs e contribuições!</span><span class="sxs-lookup"><span data-stu-id="3a185-155">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="3a185-156">Dicas do VSCode</span><span class="sxs-lookup"><span data-stu-id="3a185-156">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="3a185-157">Paleta de comandos</span><span class="sxs-lookup"><span data-stu-id="3a185-157">Command Palette</span></span>

<span data-ttu-id="3a185-158"><kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS)</span><span class="sxs-lookup"><span data-stu-id="3a185-158"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="3a185-159">Uma maneira útil de executar comandos no VSCode.</span><span class="sxs-lookup"><span data-stu-id="3a185-159">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="3a185-160">Para saber mais, confira [os documentos do VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span><span class="sxs-lookup"><span data-stu-id="3a185-160">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[Paleta de comandos]: #command-palette
[Command Palette]: #command-palette
