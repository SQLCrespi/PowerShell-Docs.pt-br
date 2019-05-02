---
title: Como replicar a experiência do ISE no Visual Studio Code
description: Como replicar a experiência do ISE no Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 983da850c13d72bcdc7b2d33970c6e9e06b3d869
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058498"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="b05da-103">Como replicar a experiência do ISE no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b05da-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="b05da-104">Embora a extensão do PowerShell para VSCode não exija paridade de recursos perfeita com o ISE do PowerShell, há recursos definidos para tornar a experiência do VSCode mais natural aos usuários do ISE.</span><span class="sxs-lookup"><span data-stu-id="b05da-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="b05da-105">Este documento tenta listar configurações que você pode definir no VSCode para tornar a experiência do usuário um pouco mais familiar em comparação com o ISE.</span><span class="sxs-lookup"><span data-stu-id="b05da-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="b05da-106">Associações de teclas</span><span class="sxs-lookup"><span data-stu-id="b05da-106">Key bindings</span></span>

| <span data-ttu-id="b05da-107">Função</span><span class="sxs-lookup"><span data-stu-id="b05da-107">Function</span></span>                              | <span data-ttu-id="b05da-108">Associação do ISE</span><span class="sxs-lookup"><span data-stu-id="b05da-108">ISE Binding</span></span>                  | <span data-ttu-id="b05da-109">Associação do VSCode</span><span class="sxs-lookup"><span data-stu-id="b05da-109">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="b05da-110">Interromper o depurador</span><span class="sxs-lookup"><span data-stu-id="b05da-110">Interrupt and break debugger</span></span>          | <span data-ttu-id="b05da-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="b05da-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="b05da-112"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="b05da-112"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="b05da-113">Executar texto destacado/linha atual</span><span class="sxs-lookup"><span data-stu-id="b05da-113">Execute current line/highlighted text</span></span> | <span data-ttu-id="b05da-114"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="b05da-114"><kbd>F8</kbd></span></span>                | <span data-ttu-id="b05da-115"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="b05da-115"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="b05da-116">Listar snippets disponíveis</span><span class="sxs-lookup"><span data-stu-id="b05da-116">List available snippets</span></span>               | <span data-ttu-id="b05da-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="b05da-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="b05da-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="b05da-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="b05da-119">Associações de teclas personalizadas</span><span class="sxs-lookup"><span data-stu-id="b05da-119">Custom Key bindings</span></span>

<span data-ttu-id="b05da-120">Você também pode [configurar suas próprias associações de teclas](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) no VSCode.</span><span class="sxs-lookup"><span data-stu-id="b05da-120">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="tab-completion"></a><span data-ttu-id="b05da-121">Preenchimento de guias</span><span class="sxs-lookup"><span data-stu-id="b05da-121">Tab completion</span></span>

<span data-ttu-id="b05da-122">Para habilitar um preenchimento com Tab mais semelhante ao ISE, adicione esta configuração:</span><span class="sxs-lookup"><span data-stu-id="b05da-122">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> <span data-ttu-id="b05da-123">Essa configuração foi adicionada diretamente ao VSCode (não à extensão).</span><span class="sxs-lookup"><span data-stu-id="b05da-123">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="b05da-124">Seu comportamento é determinado diretamente pelo VSCode e não pode ser alterado pela extensão.</span><span class="sxs-lookup"><span data-stu-id="b05da-124">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="b05da-125">Sem destaque no console durante a execução</span><span class="sxs-lookup"><span data-stu-id="b05da-125">No focus on console when executing</span></span>

<span data-ttu-id="b05da-126">Para manter o destaque no editor ao executar com <kbd>F8</kbd>:</span><span class="sxs-lookup"><span data-stu-id="b05da-126">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

<span data-ttu-id="b05da-127">O padrão é `true` para fins de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="b05da-127">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="b05da-128">Não inicie o console integrado na inicialização</span><span class="sxs-lookup"><span data-stu-id="b05da-128">Don't start integrated console on startup</span></span>

<span data-ttu-id="b05da-129">Para interromper o console integrado na inicialização, defina:</span><span class="sxs-lookup"><span data-stu-id="b05da-129">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="b05da-130">O processo do PowerShell em segundo plano ainda será iniciado, uma vez que isso proporciona análise de script, navegação de símbolo, IntelliSense, etc. Porém o console não será mostrado.</span><span class="sxs-lookup"><span data-stu-id="b05da-130">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="b05da-131">Pressupor que os arquivos sejam do PowerShell por padrão</span><span class="sxs-lookup"><span data-stu-id="b05da-131">Assume files are PowerShell by default</span></span>

<span data-ttu-id="b05da-132">Para tornar os arquivos novos/sem título, registre-os como PowerShell por padrão:</span><span class="sxs-lookup"><span data-stu-id="b05da-132">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a><span data-ttu-id="b05da-133">Esquema de cores</span><span class="sxs-lookup"><span data-stu-id="b05da-133">Color scheme</span></span>

<span data-ttu-id="b05da-134">Há vários temas do ISE disponíveis para VSCode para tornar a aparência do editor muito mais parecida com a do ISE.</span><span class="sxs-lookup"><span data-stu-id="b05da-134">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="b05da-135">Na [Paleta de Comandos], digite `theme` para obter `Preferences: Color Theme` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="b05da-135">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="b05da-136">Na lista suspensa, selecione `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="b05da-136">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="b05da-137">Você pode definir esse tema nas configurações com:</span><span class="sxs-lookup"><span data-stu-id="b05da-137">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a><span data-ttu-id="b05da-138">Gerenciador de comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b05da-138">PowerShell Command Explorer</span></span>

<span data-ttu-id="b05da-139">Graças ao trabalho de [@corbob](https://github.com/corbob), a extensão do PowerShell tem os princípios de seu próprio gerenciador de comandos.</span><span class="sxs-lookup"><span data-stu-id="b05da-139">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="b05da-140">Na [Paleta de Comandos], digite `PowerShell Command Explorer` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="b05da-140">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="b05da-141">Abrir no ISE</span><span class="sxs-lookup"><span data-stu-id="b05da-141">Open in the ISE</span></span>

<span data-ttu-id="b05da-142">Caso queira abrir um arquivo no ISE mesmo assim, use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="b05da-142">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="b05da-143">Outros recursos</span><span class="sxs-lookup"><span data-stu-id="b05da-143">Other resources</span></span>

- <span data-ttu-id="b05da-144">O blog 4sysops tem [um excelente artigo](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) sobre como configurar o VSCode para ser mais parecido com o ISE.</span><span class="sxs-lookup"><span data-stu-id="b05da-144">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="b05da-145">Mike F. Robbins tem [uma excelente postagem](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) sobre como configurar o VSCode.</span><span class="sxs-lookup"><span data-stu-id="b05da-145">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="b05da-146">Saiba que o PowerShell conta com [um excelente manual detalhado](https://www.learnpwsh.com/setup-vs-code-for-powershell/) sobre a configuração do VSCode para PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b05da-146">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="b05da-147">Mais configurações</span><span class="sxs-lookup"><span data-stu-id="b05da-147">More settings</span></span>

<span data-ttu-id="b05da-148">Se você conhece outras maneiras de tornar o VSCode mais familiar aos usuários do ISE, contribua com esse documento. Se você está procurando por uma configuração de compatibilidade, mas não consegue encontrar onde habilitá-la, [abra uma ocorrência](https://github.com/PowerShell/vscode-powershell/issues/new/choose) e pergunte!</span><span class="sxs-lookup"><span data-stu-id="b05da-148">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="b05da-149">Também gostamos de receber PRs e contribuições!</span><span class="sxs-lookup"><span data-stu-id="b05da-149">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="b05da-150">Dicas do VSCode</span><span class="sxs-lookup"><span data-stu-id="b05da-150">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="b05da-151">Paleta de comandos</span><span class="sxs-lookup"><span data-stu-id="b05da-151">Command Palette</span></span>

<span data-ttu-id="b05da-152"><kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS)</span><span class="sxs-lookup"><span data-stu-id="b05da-152"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="b05da-153">Uma maneira útil de executar comandos no VSCode.</span><span class="sxs-lookup"><span data-stu-id="b05da-153">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="b05da-154">Para saber mais, confira [os documentos do VSCode](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span><span class="sxs-lookup"><span data-stu-id="b05da-154">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[Paleta de comandos]: #command-palette
[Command Palette]: #command-palette
