---
title: Como replicar a experiência do ISE no Visual Studio Code
description: Como replicar a experiência do ISE no Visual Studio Code
ms.date: 08/06/2018
ms.openlocfilehash: 899e1c393fd49b0659631b88d610e80ec885e69e
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809592"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="a6733-103">Como replicar a experiência do ISE no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a6733-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="a6733-104">Embora a extensão do PowerShell para VS Code não exija paridade de recursos perfeita com o ISE do PowerShell, há recursos definidos para tornar a experiência do VS Code mais natural aos usuários do ISE.</span><span class="sxs-lookup"><span data-stu-id="a6733-104">While the PowerShell extension for VS Code doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VS Code experience more natural for users of the ISE.</span></span>

<span data-ttu-id="a6733-105">Este documento tenta listar configurações que você pode definir no VS Code para tornar a experiência do usuário um pouco mais familiar em comparação com o ISE.</span><span class="sxs-lookup"><span data-stu-id="a6733-105">This document tries to list settings you can configure in VS Code to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="a6733-106">Modo ISE</span><span class="sxs-lookup"><span data-stu-id="a6733-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="a6733-107">Esse recurso está disponível na extensão do da Versão Prévia do PowerShell desde a versão 2019.12.0 e na extensão do PowerShell desde a versão 2020.3.0.</span><span class="sxs-lookup"><span data-stu-id="a6733-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="a6733-108">A maneira mais fácil de replicar a experiência do ISE no Visual Studio Code é ativar o "Modo ISE".</span><span class="sxs-lookup"><span data-stu-id="a6733-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="a6733-109">Para fazer isso, abra a paleta de comandos (<kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OU <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS) e digite "Modo ISE".</span><span class="sxs-lookup"><span data-stu-id="a6733-109">To do this, open the command palette (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span> <span data-ttu-id="a6733-110">Selecione "PowerShell: Habilitar modo ISE" na lista.</span><span class="sxs-lookup"><span data-stu-id="a6733-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="a6733-111">Esse comando aplica automaticamente as configurações descritas abaixo. O resultado é semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="a6733-111">This command automatically applies the settings described below The result looks like this:</span></span>

![Modo ISE](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a><span data-ttu-id="a6733-113">Definições de configuração do modo ISE</span><span class="sxs-lookup"><span data-stu-id="a6733-113">ISE Mode configuration settings</span></span>

<span data-ttu-id="a6733-114">O modo ISE faz as alterações a seguir nas configurações do VS Code.</span><span class="sxs-lookup"><span data-stu-id="a6733-114">ISE Mode makes the following changes to VS Code settings.</span></span>

- <span data-ttu-id="a6733-115">Associações de teclas</span><span class="sxs-lookup"><span data-stu-id="a6733-115">Key bindings</span></span>

  |               <span data-ttu-id="a6733-116">Função</span><span class="sxs-lookup"><span data-stu-id="a6733-116">Function</span></span>                |         <span data-ttu-id="a6733-117">Associação do ISE</span><span class="sxs-lookup"><span data-stu-id="a6733-117">ISE Binding</span></span>          |              <span data-ttu-id="a6733-118">Associação do VS Code</span><span class="sxs-lookup"><span data-stu-id="a6733-118">VS Code Binding</span></span>                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | <span data-ttu-id="a6733-119">Interromper o depurador</span><span class="sxs-lookup"><span data-stu-id="a6733-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="a6733-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="a6733-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="a6733-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="a6733-121"><kbd>F6</kbd></span></span>                               |
  | <span data-ttu-id="a6733-122">Executar texto destacado/linha atual</span><span class="sxs-lookup"><span data-stu-id="a6733-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="a6733-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="a6733-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="a6733-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="a6733-124"><kbd>F8</kbd></span></span>                               |
  | <span data-ttu-id="a6733-125">Listar snippets disponíveis</span><span class="sxs-lookup"><span data-stu-id="a6733-125">List available snippets</span></span>               | <span data-ttu-id="a6733-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="a6733-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="a6733-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="a6733-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

  > [!NOTE]
  > <span data-ttu-id="a6733-128">Você também pode [configurar suas próprias associações de teclas](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) no VS Code.</span><span class="sxs-lookup"><span data-stu-id="a6733-128">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VS Code as well.</span></span>

- <span data-ttu-id="a6733-129">Interface do usuário simplificada semelhante à do ISE</span><span class="sxs-lookup"><span data-stu-id="a6733-129">Simplified ISE-like UI</span></span>

  <span data-ttu-id="a6733-130">Se você estiver procurando simplificar a interface do usuário do Visual Studio Code para ter uma aparência mais próxima da interface do usuário do ISE, aplique estas duas configurações:</span><span class="sxs-lookup"><span data-stu-id="a6733-130">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  <span data-ttu-id="a6733-131">Essas configurações ocultam as seções "Barra de Atividades" e "Barra Lateral de Depuração" mostradas na caixa vermelha abaixo:</span><span class="sxs-lookup"><span data-stu-id="a6733-131">These settings hide the "Activity Bar" and the "Debug Side Bar" sections shown inside the red box below:</span></span>

  ![a seção realçada inclui a Barra de Atividades e a Barra Lateral de Depuração](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  <span data-ttu-id="a6733-133">O resultado final se parece com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a6733-133">The end result looks like this:</span></span>

  ![Exibição simplificada do VS Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- <span data-ttu-id="a6733-135">Preenchimento de guias</span><span class="sxs-lookup"><span data-stu-id="a6733-135">Tab completion</span></span>

  <span data-ttu-id="a6733-136">Para habilitar um preenchimento com Tab mais semelhante ao ISE, adicione esta configuração:</span><span class="sxs-lookup"><span data-stu-id="a6733-136">To enable more ISE-like tab completion, add this setting:</span></span>

  ```json
  "editor.tabCompletion": "on",
  ```

- <span data-ttu-id="a6733-137">Sem foco no console ao executar</span><span class="sxs-lookup"><span data-stu-id="a6733-137">No focus on console when executing</span></span>

  <span data-ttu-id="a6733-138">Para manter o destaque no editor ao executar com <kbd>F8</kbd>:</span><span class="sxs-lookup"><span data-stu-id="a6733-138">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  <span data-ttu-id="a6733-139">O padrão é `true` para fins de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="a6733-139">The default is `true` for accessibility purposes.</span></span>

- <span data-ttu-id="a6733-140">Não inicie o console integrado na inicialização</span><span class="sxs-lookup"><span data-stu-id="a6733-140">Don't start integrated console on startup</span></span>

  <span data-ttu-id="a6733-141">Para interromper o console integrado na inicialização, defina:</span><span class="sxs-lookup"><span data-stu-id="a6733-141">To stop the integrated console on startup, set:</span></span>

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > <span data-ttu-id="a6733-142">O processo em segundo plano do PowerShell ainda começa a fornecer IntelliSense, análise de script, navegação de símbolos, entre outros, mas o console não será mostrado.</span><span class="sxs-lookup"><span data-stu-id="a6733-142">The background PowerShell process still starts to provide IntelliSense, script analysis, symbol navigation, etc., but the console won't be shown.</span></span>

- <span data-ttu-id="a6733-143">Pressupor que os arquivos sejam do PowerShell por padrão</span><span class="sxs-lookup"><span data-stu-id="a6733-143">Assume files are PowerShell by default</span></span>

  <span data-ttu-id="a6733-144">Para tornar os arquivos novos/sem título, registre-os como PowerShell por padrão:</span><span class="sxs-lookup"><span data-stu-id="a6733-144">To make new/untitled files, register as PowerShell by default:</span></span>

  ```json
  "files.defaultLanguage": "powershell",
  ```

- <span data-ttu-id="a6733-145">Esquema de cores</span><span class="sxs-lookup"><span data-stu-id="a6733-145">Color scheme</span></span>

  <span data-ttu-id="a6733-146">Há vários temas do ISE disponíveis para VS Code a fim de tornar a aparência do editor muito mais parecida com a do ISE.</span><span class="sxs-lookup"><span data-stu-id="a6733-146">There are a number of ISE themes available for VS Code to make the editor look much more like the ISE.</span></span>

  <span data-ttu-id="a6733-147">Na [Paleta de Comandos][], digite `theme` para obter `Preferences: Color Theme` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a6733-147">In the [Command Palette][] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span> <span data-ttu-id="a6733-148">Na lista suspensa, selecione `PowerShell ISE`.</span><span class="sxs-lookup"><span data-stu-id="a6733-148">In the drop-down list, select `PowerShell ISE`.</span></span>

  <span data-ttu-id="a6733-149">Você pode definir esse tema nas configurações com:</span><span class="sxs-lookup"><span data-stu-id="a6733-149">You can set this theme in the settings with:</span></span>

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- <span data-ttu-id="a6733-150">Gerenciador de comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6733-150">PowerShell Command Explorer</span></span>

  <span data-ttu-id="a6733-151">Graças ao trabalho de [@corbob](https://github.com/corbob), a extensão do PowerShell tem os princípios de seu próprio gerenciador de comandos.</span><span class="sxs-lookup"><span data-stu-id="a6733-151">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

  <span data-ttu-id="a6733-152">Na [Paleta de Comandos][], digite `PowerShell Command Explorer` e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="a6733-152">In the [Command Palette][], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

- <span data-ttu-id="a6733-153">Abrir no ISE</span><span class="sxs-lookup"><span data-stu-id="a6733-153">Open in the ISE</span></span>

  <span data-ttu-id="a6733-154">Se você, ainda assim, deseja abrir um arquivo no Windows PowerShell ISE, abra a [Paleta de Comandos][], procure "abrir no ise" e selecione **PowerShell: abrir o arquivo atual no ISE do PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a6733-154">If you want to open a file in the Windows PowerShell ISE anyway, open the [Command Palette][], search for "open in ise", then select **PowerShell: Open Current File in PowerShell ISE**.</span></span>

## <a name="other-resources"></a><span data-ttu-id="a6733-155">Outros recursos</span><span class="sxs-lookup"><span data-stu-id="a6733-155">Other resources</span></span>

- <span data-ttu-id="a6733-156">O blog 4sysops tem [um excelente artigo][4sysops] sobre como configurar o VS Code para que ele fique mais parecido com o ISE.</span><span class="sxs-lookup"><span data-stu-id="a6733-156">4sysops has [a great article][4sysops] on configuring VS Code to be more like the ISE.</span></span>
- <span data-ttu-id="a6733-157">Mike F. Robbins tem [uma excelente postagem][mikefrobbins] sobre como configurar o VS Code.</span><span class="sxs-lookup"><span data-stu-id="a6733-157">Mike F Robbins has [a great post][mikefrobbins] on setting up VS Code.</span></span>
- <span data-ttu-id="a6733-158">Saiba mais sobre a [excelente configuração de gravação][learnpwsh] para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6733-158">Learn PowerShell has [an excellent write up][learnpwsh] setup for PowerShell.</span></span>

## <a name="vs-code-tips"></a><span data-ttu-id="a6733-159">Dicas de VS Code</span><span class="sxs-lookup"><span data-stu-id="a6733-159">VS Code Tips</span></span>

- <span data-ttu-id="a6733-160">Paleta de Comandos</span><span class="sxs-lookup"><span data-stu-id="a6733-160">Command Palette</span></span>

  <span data-ttu-id="a6733-161">A Paleta de Comandos é um recurso prático que permite executar comandos no VS Code.</span><span class="sxs-lookup"><span data-stu-id="a6733-161">The Command Palette is handy way of executing commands in VS Code.</span></span> <span data-ttu-id="a6733-162">Abra a paleta de comandos clicando em <kbd>F1</kbd> OU <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OU <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS.</span><span class="sxs-lookup"><span data-stu-id="a6733-162">Open the command palette using <kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS.</span></span>

  <span data-ttu-id="a6733-163">Para saber mais, confira [a documentação VS Code][vsc-docs].</span><span class="sxs-lookup"><span data-stu-id="a6733-163">For more information, see [the VS Code documentation][vsc-docs].</span></span>

- <span data-ttu-id="a6733-164">Desabilitar o console de depuração</span><span class="sxs-lookup"><span data-stu-id="a6733-164">Disable the Debug Console</span></span>

  <span data-ttu-id="a6733-165">Se você planeja usar o VS Code apenas para scripts do PowerShell, é possível ocultar o **Console de Depuração**, pois ele não é usado pela extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6733-165">If you only plan on using VS Code for PowerShell scripting, you can hide the **Debug Console** since it is not used by the PowerShell extension.</span></span> <span data-ttu-id="a6733-166">Para fazer isso, clique com o botão direito do mouse em **Console de Depuração** e clique na marca de seleção para ocultá-lo.</span><span class="sxs-lookup"><span data-stu-id="a6733-166">To do so, right click on **Debug Console** then click on the check mark to hide it.</span></span>

## <a name="more-settings"></a><span data-ttu-id="a6733-167">Mais configurações</span><span class="sxs-lookup"><span data-stu-id="a6733-167">More settings</span></span>

<span data-ttu-id="a6733-168">Se você souber mais maneiras de fazer o VS Code parecer mais familiar para os usuários do ISE, colabore com este documento. Se você está procurando por uma configuração de compatibilidade, mas não consegue encontrar onde habilitá-la, [abra uma ocorrência][] e pergunte!</span><span class="sxs-lookup"><span data-stu-id="a6733-168">If you know of more ways to make VS Code feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue][] and ask away!</span></span>

<span data-ttu-id="a6733-169">Também gostamos de receber PRs e contribuições!</span><span class="sxs-lookup"><span data-stu-id="a6733-169">We're always happy to accept PRs and contributions as well!</span></span>

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[Paleta de comandos]: #vs-code-tips
[Command Palette]: #vs-code-tips
[abra uma ocorrência]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose
[open an issue]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
