---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: ddc88dda3514e4279b6d91b023e26da88f645af7
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685221"
---
# <a name="psreadline"></a><span data-ttu-id="f1346-103">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f1346-103">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="f1346-104">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f1346-104">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="f1346-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f1346-105">Short Description</span></span>

<span data-ttu-id="f1346-106">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-106">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="f1346-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f1346-107">Long Description</span></span>

<span data-ttu-id="f1346-108">O PSReadLine 2,2 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-108">PSReadLine 2.2 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="f1346-109">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="f1346-109">It provides:</span></span>

- <span data-ttu-id="f1346-110">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="f1346-110">Syntax coloring of the command line</span></span>
- <span data-ttu-id="f1346-111">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="f1346-111">A visual indication of syntax errors</span></span>
- <span data-ttu-id="f1346-112">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="f1346-112">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="f1346-113">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="f1346-113">Customizable key bindings</span></span>
- <span data-ttu-id="f1346-114">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="f1346-114">Cmd and Emacs modes</span></span>
- <span data-ttu-id="f1346-115">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="f1346-115">Many configuration options</span></span>
- <span data-ttu-id="f1346-116">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="f1346-116">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="f1346-117">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="f1346-117">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="f1346-118">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="f1346-118">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="f1346-119">IntelliSense preditiva</span><span class="sxs-lookup"><span data-stu-id="f1346-119">Predictive IntelliSense</span></span>

<span data-ttu-id="f1346-120">PSReadLine 2.2.0 adicionou dois novos recursos de previsão do IntelliSense:</span><span class="sxs-lookup"><span data-stu-id="f1346-120">PSReadLine 2.2.0 added two new predictive IntelliSense features:</span></span>

- <span data-ttu-id="f1346-121">Adicionado o parâmetro **PredictionViewStyle** para permitir a seleção do novo `ListView` .</span><span class="sxs-lookup"><span data-stu-id="f1346-121">Added the **PredictionViewStyle** parameter to allow for the selection of the new `ListView`.</span></span>
- <span data-ttu-id="f1346-122">PSReadLine conectados às `CommandPrediction` APIs introduzidas no PS 7,1 para permitir que um usuário possa importar um módulo de previsão que pode renderizar as sugestões de uma fonte personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1346-122">Connected PSReadLine to the `CommandPrediction` APIs introduced in PS 7.1 to allow a user can import a predictor module that can render the suggestions from a custom source.</span></span>

<span data-ttu-id="f1346-123">O PSReadLine requer o PowerShell 3,0 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="f1346-123">PSReadLine requires PowerShell 3.0, or newer.</span></span> <span data-ttu-id="f1346-124">O PSReadLine funciona com o host de console padrão, Visual Studio Code e terminal de janela.</span><span class="sxs-lookup"><span data-stu-id="f1346-124">PSReadLine works with default console host, Visual Studio Code, and Window Terminal.</span></span> <span data-ttu-id="f1346-125">Ele não funciona no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-125">It does not work in PowerShell ISE.</span></span>

<span data-ttu-id="f1346-126">O PSReadLine 2.2.0 é fornecido com o PowerShell 7,2 e tem suporte em todas as versões com suporte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-126">PSReadLine 2.2.0 ships with PowerShell 7.2 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="f1346-127">Ele está disponível para instalação do Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-127">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="f1346-128">Para instalar o PSReadLine 2.2.0 em uma versão com suporte do PowerShell, execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="f1346-128">To install PSReadLine 2.2.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> <span data-ttu-id="f1346-129">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="f1346-129">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="f1346-130">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="f1346-130">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="f1346-131">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="f1346-131">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="f1346-132">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="f1346-132">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="f1346-133">IntelliSense preditiva</span><span class="sxs-lookup"><span data-stu-id="f1346-133">Predictive IntelliSense</span></span>

<span data-ttu-id="f1346-134">O IntelliSense preditiva é uma adição ao conceito de preenchimento com Tab que ajuda o usuário a concluir comandos com êxito.</span><span class="sxs-lookup"><span data-stu-id="f1346-134">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="f1346-135">Ele permite que os usuários descubram, editem e executem comandos completos com base em previsões correspondentes do histórico do usuário e de plugins específicos de domínio adicionais.</span><span class="sxs-lookup"><span data-stu-id="f1346-135">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="f1346-136">Habilitar IntelliSense Preditivo</span><span class="sxs-lookup"><span data-stu-id="f1346-136">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="f1346-137">O IntelliSense preditiva é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f1346-137">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="f1346-138">Para habilitar previsões, basta executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f1346-138">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="f1346-139">O parâmetro **PredictionSource** também pode aceitar plug-ins para requisitos personalizados e específicos de domínio.</span><span class="sxs-lookup"><span data-stu-id="f1346-139">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="f1346-140">Para desabilitar o IntelliSense preditiva, basta executar:</span><span class="sxs-lookup"><span data-stu-id="f1346-140">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="f1346-141">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]**.</span><span class="sxs-lookup"><span data-stu-id="f1346-141">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="f1346-142">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="f1346-142">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="f1346-143">Anular</span><span class="sxs-lookup"><span data-stu-id="f1346-143">Abort</span></span>

<span data-ttu-id="f1346-144">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="f1346-144">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="f1346-145">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="f1346-145">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="f1346-146">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="f1346-146">AcceptAndGetNext</span></span>

<span data-ttu-id="f1346-147">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-147">Attempt to execute the current input.</span></span> <span data-ttu-id="f1346-148">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="f1346-148">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="f1346-149">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="f1346-149">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="f1346-150">Aceitar</span><span class="sxs-lookup"><span data-stu-id="f1346-150">AcceptLine</span></span>

<span data-ttu-id="f1346-151">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-151">Attempt to execute the current input.</span></span> <span data-ttu-id="f1346-152">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-152">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f1346-153">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-153">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="f1346-154">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-154">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="f1346-155">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-155">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="f1346-156">AddLine</span><span class="sxs-lookup"><span data-stu-id="f1346-156">AddLine</span></span>

<span data-ttu-id="f1346-157">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-157">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="f1346-158">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="f1346-158">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="f1346-159">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-159">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f1346-160">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-160">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f1346-161">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-161">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="f1346-162">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-162">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="f1346-163">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="f1346-163">BackwardDeleteChar</span></span>

<span data-ttu-id="f1346-164">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-164">Delete the character before the cursor.</span></span>

- <span data-ttu-id="f1346-165">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-165">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f1346-166">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-166">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="f1346-167">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1346-167">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="f1346-168">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-168">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteinput"></a><span data-ttu-id="f1346-169">BackwardDeleteInput</span><span class="sxs-lookup"><span data-stu-id="f1346-169">BackwardDeleteInput</span></span>

<span data-ttu-id="f1346-170">Como BackwardKillInput-exclui o texto do ponto para o início da entrada, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-170">Like BackwardKillInput - deletes text from the point to the start of the input, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f1346-171">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-171">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f1346-172">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-172">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="f1346-173">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-173">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="f1346-174">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="f1346-174">BackwardDeleteLine</span></span>

<span data-ttu-id="f1346-175">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-175">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f1346-176">Modo de comando vi: `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="f1346-176">Vi command mode: `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="f1346-177">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="f1346-177">BackwardDeleteWord</span></span>

<span data-ttu-id="f1346-178">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-178">Deletes the previous word.</span></span>

- <span data-ttu-id="f1346-179">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="f1346-179">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillinput"></a><span data-ttu-id="f1346-180">BackwardKillInput</span><span class="sxs-lookup"><span data-stu-id="f1346-180">BackwardKillInput</span></span>

<span data-ttu-id="f1346-181">Limpe o texto do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-181">Clear the text from the start of the input to the cursor.</span></span> <span data-ttu-id="f1346-182">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-182">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1346-183">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1346-183">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="f1346-184">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="f1346-184">BackwardKillLine</span></span>

<span data-ttu-id="f1346-185">Limpe o texto do início da linha lógica atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-185">Clear the text from the start of the current logical line to the cursor.</span></span> <span data-ttu-id="f1346-186">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-186">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1346-187">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-187">Function is unbound.</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="f1346-188">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="f1346-188">BackwardKillWord</span></span>

<span data-ttu-id="f1346-189">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-189">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f1346-190">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-190">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f1346-191">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-191">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1346-192">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="f1346-192">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="f1346-193">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1346-193">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="f1346-194">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1346-194">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="f1346-195">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="f1346-195">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="f1346-196">Cancelar</span><span class="sxs-lookup"><span data-stu-id="f1346-196">CancelLine</span></span>

<span data-ttu-id="f1346-197">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="f1346-197">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="f1346-198">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1346-198">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f1346-199">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1346-199">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="f1346-200">Copiar</span><span class="sxs-lookup"><span data-stu-id="f1346-200">Copy</span></span>

<span data-ttu-id="f1346-201">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="f1346-201">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="f1346-202">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="f1346-202">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="f1346-203">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="f1346-203">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="f1346-204">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="f1346-204">CopyOrCancelLine</span></span>

<span data-ttu-id="f1346-205">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-205">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="f1346-206">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1346-206">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="f1346-207">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="f1346-207">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="f1346-208">Recortar</span><span class="sxs-lookup"><span data-stu-id="f1346-208">Cut</span></span>

<span data-ttu-id="f1346-209">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="f1346-209">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="f1346-210">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f1346-210">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="f1346-211">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="f1346-211">DeleteChar</span></span>

<span data-ttu-id="f1346-212">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-212">Delete the character under the cursor.</span></span>

- <span data-ttu-id="f1346-213">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1346-213">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="f1346-214">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1346-214">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="f1346-215">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1346-215">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="f1346-216">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f1346-216">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="f1346-217">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="f1346-217">DeleteCharOrExit</span></span>

<span data-ttu-id="f1346-218">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="f1346-218">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="f1346-219">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f1346-219">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="f1346-220">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="f1346-220">DeleteEndOfBuffer</span></span>

<span data-ttu-id="f1346-221">Exclui para o final do buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-221">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="f1346-222">Modo de comando vi: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="f1346-222">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="f1346-223">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="f1346-223">DeleteEndOfWord</span></span>

<span data-ttu-id="f1346-224">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-224">Delete to the end of the word.</span></span>

- <span data-ttu-id="f1346-225">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="f1346-225">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="f1346-226">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="f1346-226">DeleteLine</span></span>

<span data-ttu-id="f1346-227">Exclui a linha lógica atual de um buffer de várias linhas, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="f1346-227">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="f1346-228">Modo de comando vi: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="f1346-228">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="f1346-229">DeletePreviousLines</span><span class="sxs-lookup"><span data-stu-id="f1346-229">DeletePreviousLines</span></span>

<span data-ttu-id="f1346-230">Exclui as linhas lógicas solicitadas anteriores e a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-230">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="f1346-231">Modo de comando vi: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="f1346-231">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="f1346-232">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="f1346-232">DeleteRelativeLines</span></span>

<span data-ttu-id="f1346-233">Exclui desde o início do buffer até a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-233">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="f1346-234">Como a maioria dos comandos vi, o `<d,g,g>` comando pode ser anexado com um argumento numérico que especifica um número de linha absoluto, que, junto com o número de linha atual, compõem um intervalo de linhas a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="f1346-234">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="f1346-235">Se não for especificado, o argumento numérico usa como padrão 1, que se refere à primeira linha lógica em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-235">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="f1346-236">O número real de linhas a serem excluídas da multilinha é calculado como a diferença entre o número da linha lógica atual e o argumento numérico especificado, que pode ser, portanto, negativo.</span><span class="sxs-lookup"><span data-stu-id="f1346-236">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="f1346-237">Portanto, a parte _relativa_ do nome do método.</span><span class="sxs-lookup"><span data-stu-id="f1346-237">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="f1346-238">Modo de comando vi: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="f1346-238">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="f1346-239">DeleteNextLines</span><span class="sxs-lookup"><span data-stu-id="f1346-239">DeleteNextLines</span></span>

<span data-ttu-id="f1346-240">Exclui a linha lógica atual e as próximas linhas lógicas solicitadas em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-240">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="f1346-241">Modo de comando vi: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="f1346-241">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="f1346-242">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="f1346-242">DeleteLineToFirstChar</span></span>

<span data-ttu-id="f1346-243">Exclui do primeiro caractere não em branco da linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-243">Deletes from the first non-blank character of the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="f1346-244">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="f1346-244">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="f1346-245">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="f1346-245">DeleteToEnd</span></span>

<span data-ttu-id="f1346-246">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-246">Delete to the end of the line.</span></span>

- <span data-ttu-id="f1346-247">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="f1346-247">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="f1346-248">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="f1346-248">DeleteWord</span></span>

<span data-ttu-id="f1346-249">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-249">Delete the next word.</span></span>

- <span data-ttu-id="f1346-250">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="f1346-250">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteinput"></a><span data-ttu-id="f1346-251">ForwardDeleteInput</span><span class="sxs-lookup"><span data-stu-id="f1346-251">ForwardDeleteInput</span></span>

<span data-ttu-id="f1346-252">Como finalizar-exclui o texto do ponto até o fim da entrada, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-252">Like KillLine - deletes text from the point to the end of the input, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f1346-253">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-253">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f1346-254">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-254">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="f1346-255">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-255">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="f1346-256">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="f1346-256">ForwardDeleteLine</span></span>

<span data-ttu-id="f1346-257">Exclui o texto do ponto até o fim da linha lógica atual, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-257">Deletes text from the point to the end of the current logical line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="f1346-258">A função está desassociada</span><span class="sxs-lookup"><span data-stu-id="f1346-258">Function is unbound</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="f1346-259">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="f1346-259">InsertLineAbove</span></span>

<span data-ttu-id="f1346-260">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-260">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f1346-261">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-261">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f1346-262">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-262">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="f1346-263">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="f1346-263">InsertLineBelow</span></span>

<span data-ttu-id="f1346-264">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-264">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="f1346-265">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-265">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="f1346-266">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-266">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="f1346-267">InvertCase</span><span class="sxs-lookup"><span data-stu-id="f1346-267">InvertCase</span></span>

<span data-ttu-id="f1346-268">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="f1346-268">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="f1346-269">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="f1346-269">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="f1346-270">Finalizar</span><span class="sxs-lookup"><span data-stu-id="f1346-270">KillLine</span></span>

<span data-ttu-id="f1346-271">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-271">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="f1346-272">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-272">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1346-273">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="f1346-273">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="f1346-274">KillRegion</span><span class="sxs-lookup"><span data-stu-id="f1346-274">KillRegion</span></span>

<span data-ttu-id="f1346-275">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="f1346-275">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="f1346-276">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-276">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="f1346-277">KillWord</span><span class="sxs-lookup"><span data-stu-id="f1346-277">KillWord</span></span>

<span data-ttu-id="f1346-278">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-278">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f1346-279">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-279">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f1346-280">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-280">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1346-281">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1346-281">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f1346-282">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="f1346-282">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="f1346-283">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1346-283">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="f1346-284">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="f1346-284">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="f1346-285">Colar</span><span class="sxs-lookup"><span data-stu-id="f1346-285">Paste</span></span>

<span data-ttu-id="f1346-286">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="f1346-286">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="f1346-287">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="f1346-287">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="f1346-288">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f1346-288">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="f1346-289">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="f1346-289">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1346-290">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1346-290">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="f1346-291">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-291">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="f1346-292">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="f1346-292">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="f1346-293">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="f1346-293">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="f1346-294">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="f1346-294">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="f1346-295">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="f1346-295">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="f1346-296">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="f1346-296">PasteAfter</span></span>

<span data-ttu-id="f1346-297">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="f1346-297">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f1346-298">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="f1346-298">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="f1346-299">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="f1346-299">PasteBefore</span></span>

<span data-ttu-id="f1346-300">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="f1346-300">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="f1346-301">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="f1346-301">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="f1346-302">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="f1346-302">PrependAndAccept</span></span>

<span data-ttu-id="f1346-303">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-303">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="f1346-304">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="f1346-304">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="f1346-305">Refazer</span><span class="sxs-lookup"><span data-stu-id="f1346-305">Redo</span></span>

<span data-ttu-id="f1346-306">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="f1346-306">Undo an undo.</span></span>

- <span data-ttu-id="f1346-307">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1346-307">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f1346-308">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1346-308">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="f1346-309">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1346-309">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="f1346-310">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="f1346-310">RepeatLastCommand</span></span>

<span data-ttu-id="f1346-311">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="f1346-311">Repeat the last text modification.</span></span>

- <span data-ttu-id="f1346-312">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="f1346-312">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="f1346-313">Reverter</span><span class="sxs-lookup"><span data-stu-id="f1346-313">RevertLine</span></span>

<span data-ttu-id="f1346-314">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-314">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="f1346-315">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f1346-315">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="f1346-316">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="f1346-316">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="f1346-317">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="f1346-317">ShellBackwardKillWord</span></span>

<span data-ttu-id="f1346-318">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-318">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f1346-319">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-319">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f1346-320">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-320">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f1346-321">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-321">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="f1346-322">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="f1346-322">ShellKillWord</span></span>

<span data-ttu-id="f1346-323">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-323">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="f1346-324">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-324">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="f1346-325">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-325">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="f1346-326">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-326">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="f1346-327">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="f1346-327">SwapCharacters</span></span>

<span data-ttu-id="f1346-328">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-328">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="f1346-329">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f1346-329">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f1346-330">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f1346-330">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="f1346-331">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="f1346-331">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="f1346-332">Desfazer</span><span class="sxs-lookup"><span data-stu-id="f1346-332">Undo</span></span>

<span data-ttu-id="f1346-333">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-333">Undo a previous edit.</span></span>

- <span data-ttu-id="f1346-334">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f1346-334">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f1346-335">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="f1346-335">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="f1346-336">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="f1346-336">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="f1346-337">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="f1346-337">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="f1346-338">UndoAll</span><span class="sxs-lookup"><span data-stu-id="f1346-338">UndoAll</span></span>

<span data-ttu-id="f1346-339">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-339">Undo all previous edits for line.</span></span>

- <span data-ttu-id="f1346-340">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="f1346-340">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="f1346-341">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="f1346-341">UnixWordRubout</span></span>

<span data-ttu-id="f1346-342">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-342">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="f1346-343">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-343">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="f1346-344">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-344">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="f1346-345">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="f1346-345">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="f1346-346">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="f1346-346">ValidateAndAcceptLine</span></span>

<span data-ttu-id="f1346-347">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-347">Attempt to execute the current input.</span></span> <span data-ttu-id="f1346-348">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-348">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="f1346-349">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="f1346-349">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="f1346-350">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="f1346-350">ViAcceptLine</span></span>

<span data-ttu-id="f1346-351">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="f1346-351">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="f1346-352">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="f1346-352">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="f1346-353">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="f1346-353">ViAcceptLineOrExit</span></span>

<span data-ttu-id="f1346-354">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-354">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="f1346-355">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f1346-355">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="f1346-356">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="f1346-356">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="f1346-357">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="f1346-357">ViAppendLine</span></span>

<span data-ttu-id="f1346-358">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-358">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="f1346-359">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="f1346-359">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="f1346-360">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-360">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="f1346-361">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-361">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="f1346-362">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="f1346-362">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="f1346-363">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-363">ViBackwardGlob</span></span>

<span data-ttu-id="f1346-364">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="f1346-364">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f1346-365">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="f1346-365">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="f1346-366">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="f1346-366">ViDeleteBrace</span></span>

<span data-ttu-id="f1346-367">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="f1346-367">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="f1346-368">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="f1346-368">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="f1346-369">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-369">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="f1346-370">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-370">Delete to the end of the word.</span></span>

- <span data-ttu-id="f1346-371">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="f1346-371">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="f1346-372">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-372">ViDeleteGlob</span></span>

<span data-ttu-id="f1346-373">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="f1346-373">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="f1346-374">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="f1346-374">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="f1346-375">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="f1346-375">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="f1346-376">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-376">Deletes until given character.</span></span>

- <span data-ttu-id="f1346-377">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="f1346-377">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="f1346-378">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-378">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="f1346-379">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-379">Deletes until given character.</span></span>

- <span data-ttu-id="f1346-380">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="f1346-380">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="f1346-381">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="f1346-381">ViDeleteToChar</span></span>

<span data-ttu-id="f1346-382">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-382">Deletes until given character.</span></span>

- <span data-ttu-id="f1346-383">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="f1346-383">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="f1346-384">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-384">ViDeleteToCharBackward</span></span>

<span data-ttu-id="f1346-385">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-385">Deletes backwards until given character.</span></span>

- <span data-ttu-id="f1346-386">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="f1346-386">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="f1346-387">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="f1346-387">ViInsertAtBegining</span></span>

<span data-ttu-id="f1346-388">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-388">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="f1346-389">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="f1346-389">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="f1346-390">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="f1346-390">ViInsertAtEnd</span></span>

<span data-ttu-id="f1346-391">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-391">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="f1346-392">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="f1346-392">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="f1346-393">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="f1346-393">ViInsertLine</span></span>

<span data-ttu-id="f1346-394">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-394">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="f1346-395">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="f1346-395">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="f1346-396">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="f1346-396">ViInsertWithAppend</span></span>

<span data-ttu-id="f1346-397">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-397">Append from the current line position.</span></span>

- <span data-ttu-id="f1346-398">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="f1346-398">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="f1346-399">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="f1346-399">ViInsertWithDelete</span></span>

<span data-ttu-id="f1346-400">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="f1346-400">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="f1346-401">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="f1346-401">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="f1346-402">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="f1346-402">ViJoinLines</span></span>

<span data-ttu-id="f1346-403">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-403">Joins the current line and the next line.</span></span>

- <span data-ttu-id="f1346-404">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="f1346-404">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="f1346-405">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="f1346-405">ViReplaceLine</span></span>

<span data-ttu-id="f1346-406">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="f1346-406">Erase the entire command line.</span></span>

- <span data-ttu-id="f1346-407">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="f1346-407">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="f1346-408">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="f1346-408">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="f1346-409">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-409">Replaces until given character.</span></span>

- <span data-ttu-id="f1346-410">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="f1346-410">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="f1346-411">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-411">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="f1346-412">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-412">Replaces until given character.</span></span>

- <span data-ttu-id="f1346-413">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="f1346-413">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="f1346-414">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="f1346-414">ViReplaceToChar</span></span>

<span data-ttu-id="f1346-415">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-415">Deletes until given character.</span></span>

- <span data-ttu-id="f1346-416">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="f1346-416">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="f1346-417">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-417">ViReplaceToCharBackward</span></span>

<span data-ttu-id="f1346-418">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="f1346-418">Replaces until given character.</span></span>

- <span data-ttu-id="f1346-419">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="f1346-419">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="f1346-420">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="f1346-420">ViYankBeginningOfLine</span></span>

<span data-ttu-id="f1346-421">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-421">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="f1346-422">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="f1346-422">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="f1346-423">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-423">ViYankEndOfGlob</span></span>

<span data-ttu-id="f1346-424">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="f1346-424">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="f1346-425">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="f1346-425">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="f1346-426">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="f1346-426">ViYankEndOfWord</span></span>

<span data-ttu-id="f1346-427">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="f1346-427">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="f1346-428">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="f1346-428">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="f1346-429">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="f1346-429">ViYankLeft</span></span>

<span data-ttu-id="f1346-430">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-430">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="f1346-431">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-431">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="f1346-432">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="f1346-432">ViYankLine</span></span>

<span data-ttu-id="f1346-433">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="f1346-433">Yank the entire buffer.</span></span>

- <span data-ttu-id="f1346-434">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="f1346-434">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="f1346-435">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-435">ViYankNextGlob</span></span>

<span data-ttu-id="f1346-436">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="f1346-436">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="f1346-437">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="f1346-437">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="f1346-438">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="f1346-438">ViYankNextWord</span></span>

<span data-ttu-id="f1346-439">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-439">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="f1346-440">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="f1346-440">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="f1346-441">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="f1346-441">ViYankPercent</span></span>

<span data-ttu-id="f1346-442">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="f1346-442">Yank to/from matching brace.</span></span>

- <span data-ttu-id="f1346-443">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="f1346-443">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="f1346-444">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-444">ViYankPreviousGlob</span></span>

<span data-ttu-id="f1346-445">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-445">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="f1346-446">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="f1346-446">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="f1346-447">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="f1346-447">ViYankPreviousWord</span></span>

<span data-ttu-id="f1346-448">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-448">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="f1346-449">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="f1346-449">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="f1346-450">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="f1346-450">ViYankRight</span></span>

<span data-ttu-id="f1346-451">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-451">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="f1346-452">Modo de comando vi: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f1346-452">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="f1346-453">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="f1346-453">ViYankToEndOfLine</span></span>

<span data-ttu-id="f1346-454">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="f1346-454">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="f1346-455">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="f1346-455">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="f1346-456">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="f1346-456">ViYankToFirstChar</span></span>

<span data-ttu-id="f1346-457">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-457">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="f1346-458">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="f1346-458">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="f1346-459">Yank</span><span class="sxs-lookup"><span data-stu-id="f1346-459">Yank</span></span>

<span data-ttu-id="f1346-460">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-460">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="f1346-461">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1346-461">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="f1346-462">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="f1346-462">YankLastArg</span></span>

<span data-ttu-id="f1346-463">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-463">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="f1346-464">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="f1346-464">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="f1346-465">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="f1346-465">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="f1346-466">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="f1346-466">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="f1346-467">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="f1346-467">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="f1346-468">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="f1346-468">YankNthArg</span></span>

<span data-ttu-id="f1346-469">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-469">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="f1346-470">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="f1346-470">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="f1346-471">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="f1346-471">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="f1346-472">YankPop</span><span class="sxs-lookup"><span data-stu-id="f1346-472">YankPop</span></span>

<span data-ttu-id="f1346-473">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-473">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="f1346-474">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="f1346-474">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="f1346-475">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="f1346-475">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="f1346-476">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="f1346-476">BackwardChar</span></span>

<span data-ttu-id="f1346-477">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="f1346-477">Move the cursor one character to the left.</span></span> <span data-ttu-id="f1346-478">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-478">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="f1346-479">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-479">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="f1346-480">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="f1346-480">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="f1346-481">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-481">BackwardWord</span></span>

<span data-ttu-id="f1346-482">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-482">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f1346-483">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1346-483">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1346-484">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-484">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f1346-485">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="f1346-485">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="f1346-486">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-486">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f1346-487">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-487">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="f1346-488">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="f1346-488">BeginningOfLine</span></span>

<span data-ttu-id="f1346-489">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-489">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="f1346-490">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-490">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="f1346-491">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-491">Cmd: `<Home>`</span></span>
- <span data-ttu-id="f1346-492">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f1346-492">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="f1346-493">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-493">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="f1346-494">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-494">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="f1346-495">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="f1346-495">EndOfLine</span></span>

<span data-ttu-id="f1346-496">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-496">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="f1346-497">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-497">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="f1346-498">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-498">Cmd: `<End>`</span></span>
- <span data-ttu-id="f1346-499">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f1346-499">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="f1346-500">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-500">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="f1346-501">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="f1346-501">ForwardChar</span></span>

<span data-ttu-id="f1346-502">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="f1346-502">Move the cursor one character to the right.</span></span> <span data-ttu-id="f1346-503">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-503">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="f1346-504">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-504">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="f1346-505">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="f1346-505">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="f1346-506">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-506">ForwardWord</span></span>

<span data-ttu-id="f1346-507">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-507">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f1346-508">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1346-508">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1346-509">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="f1346-509">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="f1346-510">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="f1346-510">GotoBrace</span></span>

<span data-ttu-id="f1346-511">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="f1346-511">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="f1346-512">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1346-512">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f1346-513">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1346-513">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f1346-514">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1346-514">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="f1346-515">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="f1346-515">GotoColumn</span></span>

<span data-ttu-id="f1346-516">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="f1346-516">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="f1346-517">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="f1346-517">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="f1346-518">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="f1346-518">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="f1346-519">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-519">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="f1346-520">Modo de comando vi: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="f1346-520">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="f1346-521">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="f1346-521">MoveToEndOfLine</span></span>

<span data-ttu-id="f1346-522">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-522">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="f1346-523">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="f1346-523">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="f1346-524">Próxima</span><span class="sxs-lookup"><span data-stu-id="f1346-524">NextLine</span></span>

<span data-ttu-id="f1346-525">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-525">Move the cursor to the next line.</span></span>

- <span data-ttu-id="f1346-526">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-526">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="f1346-527">NextWord</span><span class="sxs-lookup"><span data-stu-id="f1346-527">NextWord</span></span>

<span data-ttu-id="f1346-528">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-528">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f1346-529">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1346-529">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1346-530">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-530">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f1346-531">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-531">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="f1346-532">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-532">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="f1346-533">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="f1346-533">NextWordEnd</span></span>

<span data-ttu-id="f1346-534">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-534">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f1346-535">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1346-535">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1346-536">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="f1346-536">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="f1346-537">Anterior</span><span class="sxs-lookup"><span data-stu-id="f1346-537">PreviousLine</span></span>

<span data-ttu-id="f1346-538">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-538">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="f1346-539">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-539">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="f1346-540">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-540">ShellBackwardWord</span></span>

<span data-ttu-id="f1346-541">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-541">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f1346-542">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-542">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f1346-543">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-543">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="f1346-544">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-544">ShellForwardWord</span></span>

<span data-ttu-id="f1346-545">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-545">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f1346-546">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-546">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f1346-547">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-547">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="f1346-548">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="f1346-548">ShellNextWord</span></span>

<span data-ttu-id="f1346-549">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-549">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="f1346-550">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-550">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="f1346-551">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-551">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="f1346-552">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="f1346-552">ViBackwardChar</span></span>

<span data-ttu-id="f1346-553">Mover o cursor um caractere para a esquerda no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="f1346-553">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="f1346-554">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-554">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="f1346-555">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-555">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="f1346-556">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-556">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="f1346-557">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-557">ViBackwardWord</span></span>

<span data-ttu-id="f1346-558">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-558">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="f1346-559">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1346-559">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1346-560">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="f1346-560">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="f1346-561">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="f1346-561">ViForwardChar</span></span>

<span data-ttu-id="f1346-562">Mover o cursor um caractere para a direita no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="f1346-562">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="f1346-563">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-563">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="f1346-564">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-564">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="f1346-565">Modo de comando vi: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="f1346-565">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="f1346-566">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-566">ViEndOfGlob</span></span>

<span data-ttu-id="f1346-567">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="f1346-567">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="f1346-568">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="f1346-568">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="f1346-569">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-569">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="f1346-570">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-570">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f1346-571">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-571">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="f1346-572">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="f1346-572">ViGotoBrace</span></span>

<span data-ttu-id="f1346-573">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="f1346-573">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="f1346-574">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="f1346-574">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="f1346-575">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="f1346-575">ViNextGlob</span></span>

<span data-ttu-id="f1346-576">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-576">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="f1346-577">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="f1346-577">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="f1346-578">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="f1346-578">ViNextWord</span></span>

<span data-ttu-id="f1346-579">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-579">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="f1346-580">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1346-580">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="f1346-581">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="f1346-581">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="f1346-582">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="f1346-582">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="f1346-583">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="f1346-583">BeginningOfHistory</span></span>

<span data-ttu-id="f1346-584">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="f1346-584">Move to the first item in the history.</span></span>

- <span data-ttu-id="f1346-585">Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="f1346-585">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="f1346-586">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="f1346-586">ClearHistory</span></span>

<span data-ttu-id="f1346-587">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1346-587">Clears history in PSReadLine.</span></span> <span data-ttu-id="f1346-588">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1346-588">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="f1346-589">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="f1346-589">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="f1346-590">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="f1346-590">EndOfHistory</span></span>

<span data-ttu-id="f1346-591">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="f1346-591">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="f1346-592">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="f1346-592">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="f1346-593">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="f1346-593">ForwardSearchHistory</span></span>

<span data-ttu-id="f1346-594">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="f1346-594">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="f1346-595">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1346-595">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f1346-596">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1346-596">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="f1346-597">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-597">HistorySearchBackward</span></span>

<span data-ttu-id="f1346-598">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-598">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f1346-599">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="f1346-599">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="f1346-600">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="f1346-600">HistorySearchForward</span></span>

<span data-ttu-id="f1346-601">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-601">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="f1346-602">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="f1346-602">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="f1346-603">NextHistory</span><span class="sxs-lookup"><span data-stu-id="f1346-603">NextHistory</span></span>

<span data-ttu-id="f1346-604">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1346-604">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="f1346-605">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-605">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="f1346-606">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="f1346-606">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="f1346-607">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-607">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="f1346-608">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="f1346-608">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="f1346-609">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="f1346-609">PreviousHistory</span></span>

<span data-ttu-id="f1346-610">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1346-610">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="f1346-611">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-611">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="f1346-612">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="f1346-612">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="f1346-613">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-613">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="f1346-614">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="f1346-614">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="f1346-615">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="f1346-615">ReverseSearchHistory</span></span>

<span data-ttu-id="f1346-616">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="f1346-616">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="f1346-617">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1346-617">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f1346-618">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1346-618">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="f1346-619">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-619">ViSearchHistoryBackward</span></span>

<span data-ttu-id="f1346-620">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="f1346-620">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f1346-621">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1346-621">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="f1346-622">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="f1346-622">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="f1346-623">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="f1346-623">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="f1346-624">Concluir</span><span class="sxs-lookup"><span data-stu-id="f1346-624">Complete</span></span>

<span data-ttu-id="f1346-625">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-625">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f1346-626">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="f1346-626">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f1346-627">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="f1346-627">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f1346-628">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1346-628">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="f1346-629">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="f1346-629">MenuComplete</span></span>

<span data-ttu-id="f1346-630">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-630">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="f1346-631">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="f1346-631">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="f1346-632">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="f1346-632">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="f1346-633">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f1346-633">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="f1346-634">Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f1346-634">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="f1346-635">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="f1346-635">PossibleCompletions</span></span>

<span data-ttu-id="f1346-636">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="f1346-636">Display the list of possible completions.</span></span>

- <span data-ttu-id="f1346-637">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="f1346-637">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="f1346-638">Modo de inserção de vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f1346-638">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="f1346-639">Modo de comando vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="f1346-639">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="f1346-640">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="f1346-640">TabCompleteNext</span></span>

<span data-ttu-id="f1346-641">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="f1346-641">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="f1346-642">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1346-642">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="f1346-643">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1346-643">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="f1346-644">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="f1346-644">TabCompletePrevious</span></span>

<span data-ttu-id="f1346-645">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-645">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="f1346-646">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1346-646">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="f1346-647">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1346-647">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="f1346-648">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="f1346-648">ViTabCompleteNext</span></span>

<span data-ttu-id="f1346-649">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="f1346-649">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="f1346-650">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1346-650">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="f1346-651">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="f1346-651">ViTabCompletePrevious</span></span>

<span data-ttu-id="f1346-652">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="f1346-652">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="f1346-653">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="f1346-653">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="prediction-functions"></a><span data-ttu-id="f1346-654">Funções de previsão</span><span class="sxs-lookup"><span data-stu-id="f1346-654">Prediction functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="f1346-655">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="f1346-655">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="f1346-656">Ao usar `InlineView` como o estilo de exibição para previsão, aceite a próxima palavra da sugestão embutida.</span><span class="sxs-lookup"><span data-stu-id="f1346-656">When using `InlineView` as the view style for prediction, accept the next word of the inline suggestion.</span></span>

- <span data-ttu-id="f1346-657">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-657">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="f1346-658">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="f1346-658">AcceptSuggestion</span></span>

<span data-ttu-id="f1346-659">Ao usar `InlineView` como o estilo de exibição para previsão, aceite a sugestão embutida atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-659">When using `InlineView` as the view style for prediction, accept the current inline suggestion.</span></span>

- <span data-ttu-id="f1346-660">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-660">Function is unbound.</span></span>

### <a name="nextsuggestion"></a><span data-ttu-id="f1346-661">NextSuggestion</span><span class="sxs-lookup"><span data-stu-id="f1346-661">NextSuggestion</span></span>

<span data-ttu-id="f1346-662">Ao usar `ListView` como o estilo de exibição para previsão, navegue até a próxima sugestão na lista.</span><span class="sxs-lookup"><span data-stu-id="f1346-662">When using `ListView` as the view style for prediction, navigate to the next suggestion in the list.</span></span>

- <span data-ttu-id="f1346-663">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-663">Function is unbound.</span></span>

### <a name="previoussuggestion"></a><span data-ttu-id="f1346-664">PreviousSuggestion</span><span class="sxs-lookup"><span data-stu-id="f1346-664">PreviousSuggestion</span></span>

<span data-ttu-id="f1346-665">Ao usar `ListView` como o estilo de exibição para previsão, navegue até a sugestão anterior na lista.</span><span class="sxs-lookup"><span data-stu-id="f1346-665">When using `ListView` as the view style for prediction, navigate to the previous suggestion in the list.</span></span>

- <span data-ttu-id="f1346-666">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-666">Function is unbound.</span></span>

### <a name="switchpredictionview"></a><span data-ttu-id="f1346-667">SwitchPredictionView</span><span class="sxs-lookup"><span data-stu-id="f1346-667">SwitchPredictionView</span></span>

<span data-ttu-id="f1346-668">Alterne o estilo de exibição para previsão entre `InlineView` e `ListView` .</span><span class="sxs-lookup"><span data-stu-id="f1346-668">Switch the view style for prediction between `InlineView` and `ListView`.</span></span>

- <span data-ttu-id="f1346-669">Cmd `<F2>`</span><span class="sxs-lookup"><span data-stu-id="f1346-669">Cmd: `<F2>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="f1346-670">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="f1346-670">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="f1346-671">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="f1346-671">CaptureScreen</span></span>

<span data-ttu-id="f1346-672">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="f1346-672">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="f1346-673">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-673">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="f1346-674">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="f1346-674">ClearScreen</span></span>

<span data-ttu-id="f1346-675">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="f1346-675">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="f1346-676">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1346-676">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f1346-677">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1346-677">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f1346-678">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1346-678">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="f1346-679">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="f1346-679">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="f1346-680">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="f1346-680">DigitArgument</span></span>

<span data-ttu-id="f1346-681">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="f1346-681">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="f1346-682">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f1346-682">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f1346-683">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="f1346-683">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="f1346-684">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="f1346-684">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="f1346-685">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="f1346-685">InvokePrompt</span></span>

<span data-ttu-id="f1346-686">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="f1346-686">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="f1346-687">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-687">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="f1346-688">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-688">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="f1346-689">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="f1346-689">ScrollDisplayDown</span></span>

<span data-ttu-id="f1346-690">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="f1346-690">Scroll the display down one screen.</span></span>

- <span data-ttu-id="f1346-691">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1346-691">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="f1346-692">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1346-692">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="f1346-693">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="f1346-693">ScrollDisplayDownLine</span></span>

<span data-ttu-id="f1346-694">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="f1346-694">Scroll the display down one line.</span></span>

- <span data-ttu-id="f1346-695">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1346-695">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="f1346-696">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="f1346-696">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="f1346-697">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="f1346-697">ScrollDisplayToCursor</span></span>

<span data-ttu-id="f1346-698">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-698">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="f1346-699">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-699">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="f1346-700">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="f1346-700">ScrollDisplayTop</span></span>

<span data-ttu-id="f1346-701">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="f1346-701">Scroll the display to the top.</span></span>

- <span data-ttu-id="f1346-702">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-702">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="f1346-703">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="f1346-703">ScrollDisplayUp</span></span>

<span data-ttu-id="f1346-704">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="f1346-704">Scroll the display up one screen.</span></span>

- <span data-ttu-id="f1346-705">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1346-705">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="f1346-706">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1346-706">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="f1346-707">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="f1346-707">ScrollDisplayUpLine</span></span>

<span data-ttu-id="f1346-708">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="f1346-708">Scroll the display up one line.</span></span>

- <span data-ttu-id="f1346-709">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1346-709">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="f1346-710">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="f1346-710">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="f1346-711">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="f1346-711">SelfInsert</span></span>

<span data-ttu-id="f1346-712">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="f1346-712">Insert the key.</span></span>

- <span data-ttu-id="f1346-713">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-713">Function is unbound.</span></span>

### <a name="showcommandhelp"></a><span data-ttu-id="f1346-714">ShowCommandHelp</span><span class="sxs-lookup"><span data-stu-id="f1346-714">ShowCommandHelp</span></span>

<span data-ttu-id="f1346-715">Fornece uma exibição da ajuda completa do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1346-715">Provides a view of full cmdlet help.</span></span> <span data-ttu-id="f1346-716">Quando o cursor está no final de um parâmetro totalmente expandido, atingir as `<F1>` posições da chave na exibição da ajuda no local desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f1346-716">When the cursor is at the end of a fully-expanded parameter, hitting the `<F1>` key positions the display of help at the location of that parameter.</span></span>

<span data-ttu-id="f1346-717">A ajuda é exibida em um buffer de tela alternativo usando um pager do **Microsoft. PowerShell. pager**.</span><span class="sxs-lookup"><span data-stu-id="f1346-717">The help is displayed on an alternate screen buffer using a Pager from **Microsoft.PowerShell.Pager**.</span></span> <span data-ttu-id="f1346-718">Quando você sair do pager, retornará à posição original do cursor na tela original.</span><span class="sxs-lookup"><span data-stu-id="f1346-718">When you exit the pager you are returned to the original cursor position on the original screen.</span></span> <span data-ttu-id="f1346-719">Esse pager só funciona em aplicativos de terminal modernos, como o [Windows terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).</span><span class="sxs-lookup"><span data-stu-id="f1346-719">This pager only works in modern terminal applications such as [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).</span></span>

- <span data-ttu-id="f1346-720">Cmd `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f1346-720">Cmd: `<F1>`</span></span>
- <span data-ttu-id="f1346-721">Emacs `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f1346-721">Emacs: `<F1>`</span></span>
- <span data-ttu-id="f1346-722">Modo de inserção de vi: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f1346-722">Vi insert mode: `<F1>`</span></span>
- <span data-ttu-id="f1346-723">Modo de comando vi: `<F1>`</span><span class="sxs-lookup"><span data-stu-id="f1346-723">Vi command mode: `<F1>`</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="f1346-724">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="f1346-724">ShowKeyBindings</span></span>

<span data-ttu-id="f1346-725">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="f1346-725">Show all bound keys.</span></span>

- <span data-ttu-id="f1346-726">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1346-726">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f1346-727">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1346-727">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="f1346-728">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1346-728">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="showparameterhelp"></a><span data-ttu-id="f1346-729">ShowParameterHelp</span><span class="sxs-lookup"><span data-stu-id="f1346-729">ShowParameterHelp</span></span>

<span data-ttu-id="f1346-730">Fornece ajuda dinâmica para parâmetros mostrando-o abaixo da linha de comando atual, como `MenuComplete` .</span><span class="sxs-lookup"><span data-stu-id="f1346-730">Provides dynamic help for parameters by showing it below the current command line like `MenuComplete`.</span></span> <span data-ttu-id="f1346-731">O cursor deve estar no final do nome de parâmetro totalmente expandido quando você pressiona a `<Alt+h>` tecla.</span><span class="sxs-lookup"><span data-stu-id="f1346-731">The cursor must be at the end of the fully-expanded parameter name when you press the `<Alt+h>` key.</span></span>

- <span data-ttu-id="f1346-732">Cmd `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-732">Cmd: `<Alt+h>`</span></span>
- <span data-ttu-id="f1346-733">Emacs `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-733">Emacs: `<Alt+h>`</span></span>
- <span data-ttu-id="f1346-734">Modo de inserção de vi: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-734">Vi insert mode: `<Alt+h>`</span></span>
- <span data-ttu-id="f1346-735">Modo de comando vi: `<Alt+h>`</span><span class="sxs-lookup"><span data-stu-id="f1346-735">Vi command mode: `<Alt+h>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="f1346-736">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="f1346-736">ViCommandMode</span></span>

<span data-ttu-id="f1346-737">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="f1346-737">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="f1346-738">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="f1346-738">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="f1346-739">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="f1346-739">ViDigitArgumentInChord</span></span>

<span data-ttu-id="f1346-740">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="f1346-740">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="f1346-741">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-741">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="f1346-742">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="f1346-742">ViEditVisually</span></span>

<span data-ttu-id="f1346-743">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="f1346-743">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="f1346-744">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="f1346-744">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="f1346-745">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="f1346-745">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="f1346-746">ViExit</span><span class="sxs-lookup"><span data-stu-id="f1346-746">ViExit</span></span>

<span data-ttu-id="f1346-747">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="f1346-747">Exits the shell.</span></span>

- <span data-ttu-id="f1346-748">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-748">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="f1346-749">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="f1346-749">ViInsertMode</span></span>

<span data-ttu-id="f1346-750">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="f1346-750">Switch to Insert mode.</span></span>

- <span data-ttu-id="f1346-751">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="f1346-751">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="f1346-752">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="f1346-752">WhatIsKey</span></span>

<span data-ttu-id="f1346-753">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="f1346-753">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="f1346-754">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1346-754">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="f1346-755">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="f1346-755">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="f1346-756">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="f1346-756">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="f1346-757">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="f1346-757">ExchangePointAndMark</span></span>

<span data-ttu-id="f1346-758">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-758">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="f1346-759">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="f1346-759">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="f1346-760">SelectAll</span><span class="sxs-lookup"><span data-stu-id="f1346-760">SelectAll</span></span>

<span data-ttu-id="f1346-761">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="f1346-761">Select the entire line.</span></span>

- <span data-ttu-id="f1346-762">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="f1346-762">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="f1346-763">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="f1346-763">SelectBackwardChar</span></span>

<span data-ttu-id="f1346-764">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-764">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="f1346-765">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-765">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="f1346-766">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-766">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="f1346-767">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="f1346-767">SelectBackwardsLine</span></span>

<span data-ttu-id="f1346-768">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-768">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="f1346-769">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-769">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="f1346-770">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="f1346-770">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="f1346-771">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-771">SelectBackwardWord</span></span>

<span data-ttu-id="f1346-772">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="f1346-772">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="f1346-773">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-773">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="f1346-774">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="f1346-774">Emacs: `<Alt+B>`</span></span>

### <a name="selectcommandargument"></a><span data-ttu-id="f1346-775">SelectCommandArgument</span><span class="sxs-lookup"><span data-stu-id="f1346-775">SelectCommandArgument</span></span>

<span data-ttu-id="f1346-776">Faça a seleção visual dos argumentos do comando.</span><span class="sxs-lookup"><span data-stu-id="f1346-776">Make visual selection of the command arguments.</span></span> <span data-ttu-id="f1346-777">A seleção de argumentos é delimitada em um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="f1346-777">Selection of arguments is scoped within a script block.</span></span> <span data-ttu-id="f1346-778">Com base na posição do cursor, ele pesquisa do bloco de script mais interno para o bloco de script mais baixo e para quando encontra qualquer argumento em um escopo de bloco de script.</span><span class="sxs-lookup"><span data-stu-id="f1346-778">Based on the cursor position, it searches from the innermost script block to the outmost script block, and stops when it finds any arguments in a script block scope.</span></span>

<span data-ttu-id="f1346-779">Essa função honra DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="f1346-779">This function honors DigitArgument.</span></span> <span data-ttu-id="f1346-780">Ele trata os valores de argumento positivo ou negativo como deslocamentos para frente ou para trás do argumento atualmente selecionado ou da posição atual do cursor quando nenhum argumento é selecionado.</span><span class="sxs-lookup"><span data-stu-id="f1346-780">It treats the positive or negative argument values as the forward or backward offsets from the currently selected argument, or from the current cursor position when no argument is selected.</span></span>

- <span data-ttu-id="f1346-781">Cmd `<Alt+a>`</span><span class="sxs-lookup"><span data-stu-id="f1346-781">Cmd: `<Alt+a>`</span></span>
- <span data-ttu-id="f1346-782">Emacs `<Alt+a>`</span><span class="sxs-lookup"><span data-stu-id="f1346-782">Emacs: `<Alt+a>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="f1346-783">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="f1346-783">SelectForwardChar</span></span>

<span data-ttu-id="f1346-784">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-784">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="f1346-785">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-785">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="f1346-786">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-786">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="f1346-787">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-787">SelectForwardWord</span></span>

<span data-ttu-id="f1346-788">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="f1346-788">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="f1346-789">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="f1346-789">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="f1346-790">Seleção</span><span class="sxs-lookup"><span data-stu-id="f1346-790">SelectLine</span></span>

<span data-ttu-id="f1346-791">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="f1346-791">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="f1346-792">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-792">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="f1346-793">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="f1346-793">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="f1346-794">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="f1346-794">SelectNextWord</span></span>

<span data-ttu-id="f1346-795">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="f1346-795">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="f1346-796">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="f1346-796">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="f1346-797">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-797">SelectShellBackwardWord</span></span>

<span data-ttu-id="f1346-798">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="f1346-798">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="f1346-799">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-799">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="f1346-800">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="f1346-800">SelectShellForwardWord</span></span>

<span data-ttu-id="f1346-801">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="f1346-801">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="f1346-802">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-802">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="f1346-803">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="f1346-803">SelectShellNextWord</span></span>

<span data-ttu-id="f1346-804">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="f1346-804">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="f1346-805">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="f1346-805">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="f1346-806">Definir marca</span><span class="sxs-lookup"><span data-stu-id="f1346-806">SetMark</span></span>

<span data-ttu-id="f1346-807">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="f1346-807">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="f1346-808">Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="f1346-808">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="f1346-809">Funções IntelliSense preditivas</span><span class="sxs-lookup"><span data-stu-id="f1346-809">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="f1346-810">O IntelliSense preditiva precisa ser habilitado para usar essas funções.</span><span class="sxs-lookup"><span data-stu-id="f1346-810">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="f1346-811">AcceptNextWordSuggestion</span><span class="sxs-lookup"><span data-stu-id="f1346-811">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="f1346-812">Aceita a próxima palavra da sugestão embutida do IntelliSense preditiva.</span><span class="sxs-lookup"><span data-stu-id="f1346-812">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="f1346-813">Essa função pode ser associada com <kbd>Ctrl</kbd> + <kbd>F</kbd> executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="f1346-813">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="f1346-814">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="f1346-814">AcceptSuggestion</span></span>

<span data-ttu-id="f1346-815">Aceita a sugestão embutida atual do IntelliSense preditiva pressionando <kbd>RIGHTARROW</kbd> quando o cursor está no final da linha atual.</span><span class="sxs-lookup"><span data-stu-id="f1346-815">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="f1346-816">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="f1346-816">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="f1346-817">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="f1346-817">CharacterSearch</span></span>

<span data-ttu-id="f1346-818">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-818">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="f1346-819">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="f1346-819">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f1346-820">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f1346-820">Cmd: `<F3>`</span></span>
- <span data-ttu-id="f1346-821">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="f1346-821">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="f1346-822">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f1346-822">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="f1346-823">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="f1346-823">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="f1346-824">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-824">CharacterSearchBackward</span></span>

<span data-ttu-id="f1346-825">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-825">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="f1346-826">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="f1346-826">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="f1346-827">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f1346-827">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="f1346-828">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="f1346-828">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="f1346-829">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f1346-829">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="f1346-830">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="f1346-830">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="f1346-831">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="f1346-831">RepeatLastCharSearch</span></span>

<span data-ttu-id="f1346-832">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="f1346-832">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="f1346-833">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="f1346-833">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="f1346-834">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="f1346-834">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="f1346-835">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="f1346-835">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="f1346-836">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="f1346-836">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="f1346-837">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="f1346-837">RepeatSearch</span></span>

<span data-ttu-id="f1346-838">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="f1346-838">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f1346-839">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="f1346-839">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="f1346-840">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-840">RepeatSearchBackward</span></span>

<span data-ttu-id="f1346-841">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="f1346-841">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="f1346-842">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="f1346-842">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="f1346-843">SearchChar</span><span class="sxs-lookup"><span data-stu-id="f1346-843">SearchChar</span></span>

<span data-ttu-id="f1346-844">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-844">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f1346-845">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="f1346-845">This is for 't' functionality.</span></span>

- <span data-ttu-id="f1346-846">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="f1346-846">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="f1346-847">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="f1346-847">SearchCharBackward</span></span>

<span data-ttu-id="f1346-848">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-848">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f1346-849">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="f1346-849">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f1346-850">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="f1346-850">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="f1346-851">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="f1346-851">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="f1346-852">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-852">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="f1346-853">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="f1346-853">This is for 'T' functionality.</span></span>

- <span data-ttu-id="f1346-854">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="f1346-854">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="f1346-855">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="f1346-855">SearchCharWithBackoff</span></span>

<span data-ttu-id="f1346-856">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="f1346-856">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="f1346-857">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="f1346-857">This is for 't' functionality.</span></span>

- <span data-ttu-id="f1346-858">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="f1346-858">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="f1346-859">SearchForward</span><span class="sxs-lookup"><span data-stu-id="f1346-859">SearchForward</span></span>

<span data-ttu-id="f1346-860">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="f1346-860">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="f1346-861">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1346-861">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="f1346-862">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="f1346-862">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="f1346-863">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="f1346-863">Custom Key Bindings</span></span>

<span data-ttu-id="f1346-864">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="f1346-864">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="f1346-865">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="f1346-865">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="f1346-866">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="f1346-866">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="f1346-867">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="f1346-867">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="f1346-868">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="f1346-868">Some useful examples include</span></span>

- <span data-ttu-id="f1346-869">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="f1346-869">edit the command line</span></span>
- <span data-ttu-id="f1346-870">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="f1346-870">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="f1346-871">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="f1346-871">change directories without changing the command line</span></span>

<span data-ttu-id="f1346-872">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="f1346-872">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="f1346-873">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1346-873">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="f1346-874">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="f1346-874">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="f1346-875">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="f1346-875">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="f1346-876">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="f1346-876">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="f1346-877">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="f1346-877">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="f1346-878">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="f1346-878">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="f1346-879">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="f1346-879">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="f1346-880">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="f1346-880">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

```powershell
$parameters = @{
    Key = 'Alt+w'
    BriefDescription = 'SaveInHistory'
    LongDescription = 'Save current line in history but do not execute'
    ScriptBlock = {
      param($key, $arg)   # The arguments are ignored in this example

      # GetBufferState gives us the command line (with the cursor position)
      $line = $null
      $cursor = $null
      [Microsoft.PowerShell.PSConsoleReadLine]::GetBufferState([ref]$line,
        [ref]$cursor)

      # AddToHistory saves the line in history, but does not execute it.
      [Microsoft.PowerShell.PSConsoleReadLine]::AddToHistory($line)

      # RevertLine is like pressing Escape.
      [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
  }
}
Set-PSReadLineKeyHandler @parameters
```

<span data-ttu-id="f1346-881">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1346-881">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="f1346-882">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f1346-882">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="f1346-883">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="f1346-883">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="f1346-884">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="f1346-884">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="f1346-885">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="f1346-885">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="f1346-886">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f1346-886">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="f1346-887">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="f1346-887">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="f1346-888">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="f1346-888">Clear the kill-ring.</span></span>  <span data-ttu-id="f1346-889">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="f1346-889">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="f1346-890">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="f1346-890">Delete length characters from start.</span></span>  <span data-ttu-id="f1346-891">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="f1346-891">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="f1346-892">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f1346-892">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="f1346-893">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="f1346-893">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="f1346-894">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="f1346-894">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="f1346-895">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="f1346-895">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="f1346-896">Essas duas funções são usadas pelo `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="f1346-896">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="f1346-897">O primeiro é usado para obter todas as associações de chave.</span><span class="sxs-lookup"><span data-stu-id="f1346-897">The first is used to get all key bindings.</span></span> <span data-ttu-id="f1346-898">O segundo é usado para obter associações de chave específicas.</span><span class="sxs-lookup"><span data-stu-id="f1346-898">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="f1346-899">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1346-899">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="f1346-900">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="f1346-900">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="f1346-901">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="f1346-901">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="f1346-902">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="f1346-902">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="f1346-903">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="f1346-903">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="f1346-904">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="f1346-904">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="f1346-905">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1346-905">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="f1346-906">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1346-906">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="f1346-907">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="f1346-907">Replace some of the input.</span></span> <span data-ttu-id="f1346-908">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="f1346-908">This operation supports undo/redo.</span></span> <span data-ttu-id="f1346-909">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="f1346-909">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="f1346-910">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="f1346-910">Move the cursor to the given offset.</span></span> <span data-ttu-id="f1346-911">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="f1346-911">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="f1346-912">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="f1346-912">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="f1346-913">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="f1346-913">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="f1346-914">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="f1346-914">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a><span data-ttu-id="f1346-915">Observações</span><span class="sxs-lookup"><span data-stu-id="f1346-915">Notes</span></span>

### <a name="command-history"></a><span data-ttu-id="f1346-916">Histórico de comandos</span><span class="sxs-lookup"><span data-stu-id="f1346-916">Command History</span></span>

<span data-ttu-id="f1346-917">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f1346-917">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="f1346-918">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="f1346-918">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="f1346-919">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="f1346-919">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="f1346-920">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="f1346-920">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="f1346-921">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="f1346-921">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="f1346-922">Em sistemas não Windows, os arquivos de histórico são armazenados em `$env:XDG_DATA_HOME/powershell/PSReadLine` ou `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="f1346-922">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="f1346-923">Comentários & contribuindo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="f1346-923">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="f1346-924">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="f1346-924">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="f1346-925">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1346-925">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1346-926">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1346-926">See Also</span></span>

<span data-ttu-id="f1346-927">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="f1346-927">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
