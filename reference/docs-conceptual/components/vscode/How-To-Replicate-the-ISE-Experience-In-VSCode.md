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
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="e3e6c-103">Como replicar a experiência do ISE no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e3e6c-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="e3e6c-104">Embora a extensão do PowerShell para VSCode não exija paridade de recursos perfeita com o ISE do PowerShell, há recursos definidos para tornar a experiência do VSCode mais natural aos usuários do ISE.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="e3e6c-105">Este documento tenta listar configurações que você pode definir no VSCode para tornar a experiência do usuário um pouco mais familiar em comparação com o ISE.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="e3e6c-106">Modo ISE</span><span class="sxs-lookup"><span data-stu-id="e3e6c-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="e3e6c-107">Esse recurso está disponível na extensão do da Versão Prévia do PowerShell desde a versão 2019.12.0 e na extensão do PowerShell desde a versão 2020.3.0.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="e3e6c-108">A maneira mais fácil de replicar a experiência do ISE no Visual Studio Code é ativar o "Modo ISE".</span><span class="sxs-lookup"><span data-stu-id="e3e6c-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="e3e6c-109">Para fazer isso, abra a paleta de comandos (<kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OU <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS) e digite "Modo ISE".</span><span class="sxs-lookup"><span data-stu-id="e3e6c-109">To do this, open the command pallet (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span>
<span data-ttu-id="e3e6c-110">Selecione "PowerShell: Habilitar modo ISE" na lista.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="e3e6c-111">Este comando aplicará muitas das configurações encontradas neste documento automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-111">This command will apply a lot of the settings found in this document automatically.</span></span>
<span data-ttu-id="e3e6c-112">O resultado será semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-112">The result looks like this:</span></span>

![Modo ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

<span data-ttu-id="e3e6c-114">O restante deste artigo inclui informações mais detalhadas sobre configurações no modo ISE e algumas configurações adicionais.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-114">The rest of this article includes more detailed information on settings in ISE Mode and some additional settings.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="e3e6c-115">Associações de teclas</span><span class="sxs-lookup"><span data-stu-id="e3e6c-115">Key bindings</span></span>

| <span data-ttu-id="e3e6c-116">Função</span><span class="sxs-lookup"><span data-stu-id="e3e6c-116">Function</span></span>                              | <span data-ttu-id="e3e6c-117">Associação do ISE</span><span class="sxs-lookup"><span data-stu-id="e3e6c-117">ISE Binding</span></span>                  | <span data-ttu-id="e3e6c-118">Associação do VSCode</span><span class="sxs-lookup"><span data-stu-id="e3e6c-118">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="e3e6c-119">Interromper o depurador</span><span class="sxs-lookup"><span data-stu-id="e3e6c-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="e3e6c-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="e3e6c-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="e3e6c-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="e3e6c-121"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="e3e6c-122">Executar texto destacado/linha atual</span><span class="sxs-lookup"><span data-stu-id="e3e6c-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="e3e6c-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="e3e6c-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="e3e6c-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="e3e6c-124"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="e3e6c-125">Listar snippets disponíveis</span><span class="sxs-lookup"><span data-stu-id="e3e6c-125">List available snippets</span></span>               | <span data-ttu-id="e3e6c-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="e3e6c-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="e3e6c-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="e3e6c-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="e3e6c-128">Associações de teclas personalizadas</span><span class="sxs-lookup"><span data-stu-id="e3e6c-128">Custom Key bindings</span></span>

<span data-ttu-id="e3e6c-129">Você também pode [configurar suas próprias associações de teclas](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) no VSCode.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-129">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="simplified-ise-like-ui"></a><span data-ttu-id="e3e6c-130">Interface do usuário simplificada semelhante à do ISE</span><span class="sxs-lookup"><span data-stu-id="e3e6c-130">Simplified ISE-like UI</span></span>

<span data-ttu-id="e3e6c-131">Se você estiver procurando simplificar a interface do usuário do Visual Studio Code para ter uma aparência mais próxima da interface do usuário do ISE, aplique estas duas configurações:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-131">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

> [!NOTE]
> <span data-ttu-id="e3e6c-132">Essas configurações estão incluídas no ["Modo ISE"](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-132">These settings are included in ["ISE Mode"](#ise-mode).</span></span>

<span data-ttu-id="e3e6c-133">Isso ocultará as seções "Barra de Atividades" e "Barra Lateral de Depuração" abaixo na caixa vermelha:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-133">This will hide the "Activity Bar" and the "Debug Side Bar" sections below inside of the red box:</span></span>

![a seção realçada inclui a Barra de Atividades e a Barra Lateral de Depuração](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

<span data-ttu-id="e3e6c-135">O resultado final se parece com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-135">The end result looks like this:</span></span>

![Exibição simplificada do VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a><span data-ttu-id="e3e6c-137">Preenchimento de guias</span><span class="sxs-lookup"><span data-stu-id="e3e6c-137">Tab completion</span></span>

<span data-ttu-id="e3e6c-138">Para habilitar um preenchimento com Tab mais semelhante ao ISE, adicione esta configuração:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-138">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> <span data-ttu-id="e3e6c-139">Essa configuração foi adicionada diretamente ao VSCode (não à extensão).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-139">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="e3e6c-140">Seu comportamento é determinado diretamente pelo VSCode e não pode ser alterado pela extensão.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-140">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

> [!NOTE]
> <span data-ttu-id="e3e6c-141">Essa configuração está incluída no ["Modo ISE"](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-141">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="e3e6c-142">Sem foco no console ao executar</span><span class="sxs-lookup"><span data-stu-id="e3e6c-142">No focus on console when executing</span></span>

<span data-ttu-id="e3e6c-143">Para manter o destaque no editor ao executar com <kbd>F8</kbd>:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-143">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

> [!NOTE]
> <span data-ttu-id="e3e6c-144">Essa configuração está incluída no ["Modo ISE"](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-144">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

<span data-ttu-id="e3e6c-145">O padrão é `true` para fins de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-145">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="e3e6c-146">Não inicie o console integrado na inicialização</span><span class="sxs-lookup"><span data-stu-id="e3e6c-146">Don't start integrated console on startup</span></span>

<span data-ttu-id="e3e6c-147">Para interromper o console integrado na inicialização, defina:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-147">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="e3e6c-148">O processo do PowerShell em segundo plano ainda será iniciado, uma vez que isso proporciona análise de script, navegação de símbolo, IntelliSense, etc. Porém o console não será mostrado.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-148">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="e3e6c-149">Pressupor que os arquivos sejam do PowerShell por padrão</span><span class="sxs-lookup"><span data-stu-id="e3e6c-149">Assume files are PowerShell by default</span></span>

<span data-ttu-id="e3e6c-150">Para tornar os arquivos novos/sem título, registre-os como PowerShell por padrão:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-150">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell",
```

> [!NOTE]
> <span data-ttu-id="e3e6c-151">Essa configuração está incluída no ["Modo ISE"](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-151">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="color-scheme"></a><span data-ttu-id="e3e6c-152">Esquema de cores</span><span class="sxs-lookup"><span data-stu-id="e3e6c-152">Color scheme</span></span>

<span data-ttu-id="e3e6c-153">Há vários temas do ISE disponíveis para VSCode para tornar a aparência do editor muito mais parecida com a do ISE.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-153">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="e3e6c-154">Na [Paleta de Comandos], digite `theme` para obter `Preferences: Color Theme` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-154">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="e3e6c-155">Na lista suspensa, selecione `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-155">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="e3e6c-156">Você pode definir esse tema nas configurações com:</span><span class="sxs-lookup"><span data-stu-id="e3e6c-156">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE",
```

> [!NOTE]
> <span data-ttu-id="e3e6c-157">Essa configuração está incluída no ["Modo ISE"](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-157">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="powershell-command-explorer"></a><span data-ttu-id="e3e6c-158">Gerenciador de comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3e6c-158">PowerShell Command Explorer</span></span>

<span data-ttu-id="e3e6c-159">Graças ao trabalho de [@corbob](https://github.com/corbob), a extensão do PowerShell tem os princípios de seu próprio gerenciador de comandos.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-159">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="e3e6c-160">Na [Paleta de Comandos], digite `PowerShell Command Explorer` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-160">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

> [!NOTE]
> <span data-ttu-id="e3e6c-161">Isto é mostrado automaticamente no ["Modo ISE"](#ise-mode).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-161">This is shown automatically in ["ISE Mode"](#ise-mode).</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="e3e6c-162">Abrir no ISE</span><span class="sxs-lookup"><span data-stu-id="e3e6c-162">Open in the ISE</span></span>

<span data-ttu-id="e3e6c-163">Caso queira abrir um arquivo no ISE mesmo assim, use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-163">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="e3e6c-164">Outros recursos</span><span class="sxs-lookup"><span data-stu-id="e3e6c-164">Other resources</span></span>

- <span data-ttu-id="e3e6c-165">O blog 4sysops tem [um excelente artigo](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) sobre como configurar o VSCode para ser mais parecido com o ISE.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-165">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="e3e6c-166">Mike F. Robbins tem [uma excelente postagem](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) sobre como configurar o VSCode.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-166">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="e3e6c-167">Saiba que o PowerShell conta com [um excelente manual detalhado](https://www.learnpwsh.com/setup-vs-code-for-powershell/) sobre a configuração do VSCode para PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-167">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="e3e6c-168">Mais configurações</span><span class="sxs-lookup"><span data-stu-id="e3e6c-168">More settings</span></span>

<span data-ttu-id="e3e6c-169">Se você conhece outras maneiras de tornar o VSCode mais familiar aos usuários do ISE, contribua com esse documento. Se você está procurando por uma configuração de compatibilidade, mas não consegue encontrar onde habilitá-la, [abra uma ocorrência](https://github.com/PowerShell/vscode-powershell/issues/new/choose) e pergunte!</span><span class="sxs-lookup"><span data-stu-id="e3e6c-169">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="e3e6c-170">Também gostamos de receber PRs e contribuições!</span><span class="sxs-lookup"><span data-stu-id="e3e6c-170">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="e3e6c-171">Dicas do VSCode</span><span class="sxs-lookup"><span data-stu-id="e3e6c-171">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="e3e6c-172">Paleta de Comandos</span><span class="sxs-lookup"><span data-stu-id="e3e6c-172">Command Palette</span></span>

<span data-ttu-id="e3e6c-173"><kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS)</span><span class="sxs-lookup"><span data-stu-id="e3e6c-173"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="e3e6c-174">Uma maneira útil de executar comandos no VSCode.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-174">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="e3e6c-175">Para saber mais, confira [os documentos do VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span><span class="sxs-lookup"><span data-stu-id="e3e6c-175">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[Paleta de comandos]: #command-palette
[Command Palette]: #command-palette
