---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
Locale: en-US
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: 4836abfec465ba7cdfb6800c1e60104fba19ce08
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "99597604"
---
# <a name="psreadline"></a><span data-ttu-id="293ea-103">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="293ea-103">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="293ea-104">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="293ea-104">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="293ea-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="293ea-105">Short Description</span></span>

<span data-ttu-id="293ea-106">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-106">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="293ea-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="293ea-107">Long Description</span></span>

<span data-ttu-id="293ea-108">O PSReadLine 2,2 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-108">PSReadLine 2.2 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="293ea-109">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="293ea-109">It provides:</span></span>

- <span data-ttu-id="293ea-110">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="293ea-110">Syntax coloring of the command line</span></span>
- <span data-ttu-id="293ea-111">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="293ea-111">A visual indication of syntax errors</span></span>
- <span data-ttu-id="293ea-112">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="293ea-112">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="293ea-113">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="293ea-113">Customizable key bindings</span></span>
- <span data-ttu-id="293ea-114">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="293ea-114">Cmd and Emacs modes</span></span>
- <span data-ttu-id="293ea-115">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="293ea-115">Many configuration options</span></span>
- <span data-ttu-id="293ea-116">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="293ea-116">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="293ea-117">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="293ea-117">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="293ea-118">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="293ea-118">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="293ea-119">IntelliSense preditiva</span><span class="sxs-lookup"><span data-stu-id="293ea-119">Predictive IntelliSense</span></span>

<span data-ttu-id="293ea-120">PSReadLine 2.2.0 adicionou dois novos recursos de previsão do IntelliSense:</span><span class="sxs-lookup"><span data-stu-id="293ea-120">PSReadLine 2.2.0 added two new predictive IntelliSense features:</span></span>

- <span data-ttu-id="293ea-121">Adicionado o parâmetro **PredictionViewStyle** para permitir a seleção do novo `ListView` .</span><span class="sxs-lookup"><span data-stu-id="293ea-121">Added the **PredictionViewStyle** parameter to allow for the selection of the new `ListView`.</span></span>
- <span data-ttu-id="293ea-122">PSReadLine conectados às `CommandPrediction` APIs introduzidas no PS 7,1 para permitir que um usuário possa importar um módulo de previsão que pode renderizar as sugestões de uma fonte personalizada.</span><span class="sxs-lookup"><span data-stu-id="293ea-122">Connected PSReadLine to the `CommandPrediction` APIs introduced in PS 7.1 to allow a user can import a predictor module that can render the suggestions from a custom source.</span></span>

<span data-ttu-id="293ea-123">O PSReadLine requer o PowerShell 3,0 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="293ea-123">PSReadLine requires PowerShell 3.0, or newer.</span></span> <span data-ttu-id="293ea-124">O PSReadLine funciona com o host de console padrão, Visual Studio Code e terminal de janela.</span><span class="sxs-lookup"><span data-stu-id="293ea-124">PSReadLine works with default console host, Visual Studio Code, and Window Terminal.</span></span> <span data-ttu-id="293ea-125">Ele não funciona no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-125">It does not work in PowerShell ISE.</span></span>

<span data-ttu-id="293ea-126">O PSReadLine 2.2.0 é fornecido com o PowerShell 7,2 e tem suporte em todas as versões com suporte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-126">PSReadLine 2.2.0 ships with PowerShell 7.2 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="293ea-127">Ele está disponível para instalação do Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-127">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="293ea-128">Para instalar o PSReadLine 2.2.0 em uma versão com suporte do PowerShell, execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="293ea-128">To install PSReadLine 2.2.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -AllowPrerelease
```

> [!NOTE]
> <span data-ttu-id="293ea-129">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="293ea-129">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="293ea-130">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="293ea-130">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="293ea-131">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="293ea-131">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="293ea-132">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="293ea-132">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="293ea-133">IntelliSense preditiva</span><span class="sxs-lookup"><span data-stu-id="293ea-133">Predictive IntelliSense</span></span>

<span data-ttu-id="293ea-134">O IntelliSense preditiva é uma adição ao conceito de preenchimento com Tab que ajuda o usuário a concluir comandos com êxito.</span><span class="sxs-lookup"><span data-stu-id="293ea-134">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="293ea-135">Ele permite que os usuários descubram, editem e executem comandos completos com base em previsões correspondentes do histórico do usuário e de plugins específicos de domínio adicionais.</span><span class="sxs-lookup"><span data-stu-id="293ea-135">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="293ea-136">Habilitar IntelliSense Preditivo</span><span class="sxs-lookup"><span data-stu-id="293ea-136">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="293ea-137">O IntelliSense preditiva é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="293ea-137">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="293ea-138">Para habilitar previsões, basta executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="293ea-138">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="293ea-139">O parâmetro **PredictionSource** também pode aceitar plug-ins para requisitos personalizados e específicos de domínio.</span><span class="sxs-lookup"><span data-stu-id="293ea-139">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="293ea-140">Para desabilitar o IntelliSense preditiva, basta executar:</span><span class="sxs-lookup"><span data-stu-id="293ea-140">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="293ea-141">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]**.</span><span class="sxs-lookup"><span data-stu-id="293ea-141">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="293ea-142">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="293ea-142">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="293ea-143">Anular</span><span class="sxs-lookup"><span data-stu-id="293ea-143">Abort</span></span>

<span data-ttu-id="293ea-144">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="293ea-144">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="293ea-145">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="293ea-145">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="293ea-146">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="293ea-146">AcceptAndGetNext</span></span>

<span data-ttu-id="293ea-147">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-147">Attempt to execute the current input.</span></span> <span data-ttu-id="293ea-148">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="293ea-148">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="293ea-149">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="293ea-149">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="293ea-150">Aceitar</span><span class="sxs-lookup"><span data-stu-id="293ea-150">AcceptLine</span></span>

<span data-ttu-id="293ea-151">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-151">Attempt to execute the current input.</span></span> <span data-ttu-id="293ea-152">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-152">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="293ea-153">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-153">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="293ea-154">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-154">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="293ea-155">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-155">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="293ea-156">AddLine</span><span class="sxs-lookup"><span data-stu-id="293ea-156">AddLine</span></span>

<span data-ttu-id="293ea-157">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-157">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="293ea-158">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="293ea-158">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="293ea-159">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-159">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="293ea-160">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-160">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="293ea-161">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-161">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="293ea-162">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-162">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="293ea-163">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="293ea-163">BackwardDeleteChar</span></span>

<span data-ttu-id="293ea-164">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-164">Delete the character before the cursor.</span></span>

- <span data-ttu-id="293ea-165">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="293ea-165">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="293ea-166">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="293ea-166">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="293ea-167">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="293ea-167">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="293ea-168">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="293ea-168">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="293ea-169">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="293ea-169">BackwardDeleteLine</span></span>

<span data-ttu-id="293ea-170">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-170">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="293ea-171">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-171">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="293ea-172">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-172">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="293ea-173">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="293ea-173">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="293ea-174">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="293ea-174">BackwardDeleteWord</span></span>

<span data-ttu-id="293ea-175">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-175">Deletes the previous word.</span></span>

- <span data-ttu-id="293ea-176">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="293ea-176">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="293ea-177">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="293ea-177">BackwardKillLine</span></span>

<span data-ttu-id="293ea-178">Limpe a entrada do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-178">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="293ea-179">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-179">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="293ea-180">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="293ea-180">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="293ea-181">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="293ea-181">BackwardKillWord</span></span>

<span data-ttu-id="293ea-182">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-182">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="293ea-183">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-183">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="293ea-184">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-184">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="293ea-185">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="293ea-185">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="293ea-186">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="293ea-186">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="293ea-187">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="293ea-187">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="293ea-188">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="293ea-188">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="293ea-189">Cancelar</span><span class="sxs-lookup"><span data-stu-id="293ea-189">CancelLine</span></span>

<span data-ttu-id="293ea-190">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="293ea-190">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="293ea-191">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="293ea-191">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="293ea-192">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="293ea-192">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="293ea-193">Copiar</span><span class="sxs-lookup"><span data-stu-id="293ea-193">Copy</span></span>

<span data-ttu-id="293ea-194">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="293ea-194">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="293ea-195">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="293ea-195">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="293ea-196">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="293ea-196">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="293ea-197">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="293ea-197">CopyOrCancelLine</span></span>

<span data-ttu-id="293ea-198">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-198">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="293ea-199">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="293ea-199">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="293ea-200">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="293ea-200">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="293ea-201">Recortar</span><span class="sxs-lookup"><span data-stu-id="293ea-201">Cut</span></span>

<span data-ttu-id="293ea-202">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="293ea-202">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="293ea-203">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="293ea-203">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="293ea-204">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="293ea-204">DeleteChar</span></span>

<span data-ttu-id="293ea-205">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-205">Delete the character under the cursor.</span></span>

- <span data-ttu-id="293ea-206">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="293ea-206">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="293ea-207">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="293ea-207">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="293ea-208">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="293ea-208">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="293ea-209">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="293ea-209">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="293ea-210">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="293ea-210">DeleteCharOrExit</span></span>

<span data-ttu-id="293ea-211">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="293ea-211">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="293ea-212">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="293ea-212">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="293ea-213">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="293ea-213">DeleteEndOfBuffer</span></span>

<span data-ttu-id="293ea-214">Exclui para o final do buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-214">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="293ea-215">Modo de comando vi: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="293ea-215">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="293ea-216">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="293ea-216">DeleteEndOfWord</span></span>

<span data-ttu-id="293ea-217">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-217">Delete to the end of the word.</span></span>

- <span data-ttu-id="293ea-218">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="293ea-218">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="293ea-219">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="293ea-219">DeleteLine</span></span>

<span data-ttu-id="293ea-220">Exclui a linha lógica atual de um buffer de várias linhas, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="293ea-220">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="293ea-221">Modo de comando vi: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="293ea-221">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="293ea-222">DeletePreviousLines</span><span class="sxs-lookup"><span data-stu-id="293ea-222">DeletePreviousLines</span></span>

<span data-ttu-id="293ea-223">Exclui as linhas lógicas solicitadas anteriores e a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-223">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="293ea-224">Modo de comando vi: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="293ea-224">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="293ea-225">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="293ea-225">DeleteRelativeLines</span></span>

<span data-ttu-id="293ea-226">Exclui desde o início do buffer até a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-226">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="293ea-227">Como a maioria dos comandos vi, o `<d,g,g>` comando pode ser anexado com um argumento numérico que especifica um número de linha absoluto, que, junto com o número de linha atual, compõem um intervalo de linhas a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="293ea-227">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="293ea-228">Se não for especificado, o argumento numérico usa como padrão 1, que se refere à primeira linha lógica em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-228">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="293ea-229">O número real de linhas a serem excluídas da multilinha é calculado como a diferença entre o número da linha lógica atual e o argumento numérico especificado, que pode ser, portanto, negativo.</span><span class="sxs-lookup"><span data-stu-id="293ea-229">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="293ea-230">Portanto, a parte _relativa_ do nome do método.</span><span class="sxs-lookup"><span data-stu-id="293ea-230">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="293ea-231">Modo de comando vi: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="293ea-231">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="293ea-232">DeleteNextLines</span><span class="sxs-lookup"><span data-stu-id="293ea-232">DeleteNextLines</span></span>

<span data-ttu-id="293ea-233">Exclui a linha lógica atual e as próximas linhas lógicas solicitadas em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-233">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="293ea-234">Modo de comando vi: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="293ea-234">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="293ea-235">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="293ea-235">DeleteLineToFirstChar</span></span>

<span data-ttu-id="293ea-236">Exclui do primeiro caractere não em branco da linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-236">Deletes from the first non-blank character of the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="293ea-237">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="293ea-237">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="293ea-238">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="293ea-238">DeleteToEnd</span></span>

<span data-ttu-id="293ea-239">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-239">Delete to the end of the line.</span></span>

- <span data-ttu-id="293ea-240">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="293ea-240">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="293ea-241">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="293ea-241">DeleteWord</span></span>

<span data-ttu-id="293ea-242">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-242">Delete the next word.</span></span>

- <span data-ttu-id="293ea-243">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="293ea-243">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="293ea-244">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="293ea-244">ForwardDeleteLine</span></span>

<span data-ttu-id="293ea-245">Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-245">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="293ea-246">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-246">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="293ea-247">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-247">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="293ea-248">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-248">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="293ea-249">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="293ea-249">InsertLineAbove</span></span>

<span data-ttu-id="293ea-250">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-250">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="293ea-251">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-251">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="293ea-252">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-252">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="293ea-253">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="293ea-253">InsertLineBelow</span></span>

<span data-ttu-id="293ea-254">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-254">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="293ea-255">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-255">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="293ea-256">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-256">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="293ea-257">InvertCase</span><span class="sxs-lookup"><span data-stu-id="293ea-257">InvertCase</span></span>

<span data-ttu-id="293ea-258">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="293ea-258">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="293ea-259">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="293ea-259">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="293ea-260">Finalizar</span><span class="sxs-lookup"><span data-stu-id="293ea-260">KillLine</span></span>

<span data-ttu-id="293ea-261">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-261">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="293ea-262">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-262">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="293ea-263">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="293ea-263">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="293ea-264">KillRegion</span><span class="sxs-lookup"><span data-stu-id="293ea-264">KillRegion</span></span>

<span data-ttu-id="293ea-265">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="293ea-265">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="293ea-266">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-266">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="293ea-267">KillWord</span><span class="sxs-lookup"><span data-stu-id="293ea-267">KillWord</span></span>

<span data-ttu-id="293ea-268">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-268">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="293ea-269">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-269">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="293ea-270">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-270">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="293ea-271">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="293ea-271">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="293ea-272">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="293ea-272">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="293ea-273">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="293ea-273">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="293ea-274">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="293ea-274">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="293ea-275">Colar</span><span class="sxs-lookup"><span data-stu-id="293ea-275">Paste</span></span>

<span data-ttu-id="293ea-276">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="293ea-276">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="293ea-277">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="293ea-277">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="293ea-278">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="293ea-278">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="293ea-279">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="293ea-279">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="293ea-280">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="293ea-280">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="293ea-281">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-281">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="293ea-282">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="293ea-282">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="293ea-283">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="293ea-283">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="293ea-284">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="293ea-284">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="293ea-285">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="293ea-285">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="293ea-286">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="293ea-286">PasteAfter</span></span>

<span data-ttu-id="293ea-287">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="293ea-287">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="293ea-288">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="293ea-288">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="293ea-289">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="293ea-289">PasteBefore</span></span>

<span data-ttu-id="293ea-290">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="293ea-290">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="293ea-291">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="293ea-291">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="293ea-292">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="293ea-292">PrependAndAccept</span></span>

<span data-ttu-id="293ea-293">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-293">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="293ea-294">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="293ea-294">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="293ea-295">Refazer</span><span class="sxs-lookup"><span data-stu-id="293ea-295">Redo</span></span>

<span data-ttu-id="293ea-296">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="293ea-296">Undo an undo.</span></span>

- <span data-ttu-id="293ea-297">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="293ea-297">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="293ea-298">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="293ea-298">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="293ea-299">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="293ea-299">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="293ea-300">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="293ea-300">RepeatLastCommand</span></span>

<span data-ttu-id="293ea-301">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="293ea-301">Repeat the last text modification.</span></span>

- <span data-ttu-id="293ea-302">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="293ea-302">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="293ea-303">Reverter</span><span class="sxs-lookup"><span data-stu-id="293ea-303">RevertLine</span></span>

<span data-ttu-id="293ea-304">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-304">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="293ea-305">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="293ea-305">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="293ea-306">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="293ea-306">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="293ea-307">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="293ea-307">ShellBackwardKillWord</span></span>

<span data-ttu-id="293ea-308">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-308">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="293ea-309">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-309">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="293ea-310">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-310">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="293ea-311">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-311">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="293ea-312">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="293ea-312">ShellKillWord</span></span>

<span data-ttu-id="293ea-313">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-313">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="293ea-314">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-314">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="293ea-315">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-315">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="293ea-316">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-316">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="293ea-317">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="293ea-317">SwapCharacters</span></span>

<span data-ttu-id="293ea-318">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-318">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="293ea-319">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="293ea-319">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="293ea-320">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="293ea-320">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="293ea-321">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="293ea-321">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="293ea-322">Desfazer</span><span class="sxs-lookup"><span data-stu-id="293ea-322">Undo</span></span>

<span data-ttu-id="293ea-323">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-323">Undo a previous edit.</span></span>

- <span data-ttu-id="293ea-324">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="293ea-324">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="293ea-325">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="293ea-325">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="293ea-326">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="293ea-326">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="293ea-327">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="293ea-327">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="293ea-328">UndoAll</span><span class="sxs-lookup"><span data-stu-id="293ea-328">UndoAll</span></span>

<span data-ttu-id="293ea-329">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-329">Undo all previous edits for line.</span></span>

- <span data-ttu-id="293ea-330">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="293ea-330">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="293ea-331">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="293ea-331">UnixWordRubout</span></span>

<span data-ttu-id="293ea-332">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-332">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="293ea-333">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-333">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="293ea-334">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-334">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="293ea-335">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="293ea-335">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="293ea-336">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="293ea-336">ValidateAndAcceptLine</span></span>

<span data-ttu-id="293ea-337">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-337">Attempt to execute the current input.</span></span> <span data-ttu-id="293ea-338">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-338">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="293ea-339">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="293ea-339">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="293ea-340">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="293ea-340">ViAcceptLine</span></span>

<span data-ttu-id="293ea-341">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="293ea-341">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="293ea-342">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="293ea-342">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="293ea-343">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="293ea-343">ViAcceptLineOrExit</span></span>

<span data-ttu-id="293ea-344">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-344">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="293ea-345">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="293ea-345">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="293ea-346">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="293ea-346">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="293ea-347">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="293ea-347">ViAppendLine</span></span>

<span data-ttu-id="293ea-348">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-348">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="293ea-349">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="293ea-349">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="293ea-350">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-350">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="293ea-351">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-351">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="293ea-352">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="293ea-352">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="293ea-353">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-353">ViBackwardGlob</span></span>

<span data-ttu-id="293ea-354">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="293ea-354">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="293ea-355">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="293ea-355">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="293ea-356">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="293ea-356">ViDeleteBrace</span></span>

<span data-ttu-id="293ea-357">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="293ea-357">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="293ea-358">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="293ea-358">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="293ea-359">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-359">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="293ea-360">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-360">Delete to the end of the word.</span></span>

- <span data-ttu-id="293ea-361">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="293ea-361">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="293ea-362">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-362">ViDeleteGlob</span></span>

<span data-ttu-id="293ea-363">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="293ea-363">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="293ea-364">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="293ea-364">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="293ea-365">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="293ea-365">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="293ea-366">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-366">Deletes until given character.</span></span>

- <span data-ttu-id="293ea-367">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="293ea-367">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="293ea-368">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-368">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="293ea-369">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-369">Deletes until given character.</span></span>

- <span data-ttu-id="293ea-370">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="293ea-370">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="293ea-371">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="293ea-371">ViDeleteToChar</span></span>

<span data-ttu-id="293ea-372">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-372">Deletes until given character.</span></span>

- <span data-ttu-id="293ea-373">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="293ea-373">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="293ea-374">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-374">ViDeleteToCharBackward</span></span>

<span data-ttu-id="293ea-375">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-375">Deletes backwards until given character.</span></span>

- <span data-ttu-id="293ea-376">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="293ea-376">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="293ea-377">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="293ea-377">ViInsertAtBegining</span></span>

<span data-ttu-id="293ea-378">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-378">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="293ea-379">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="293ea-379">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="293ea-380">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="293ea-380">ViInsertAtEnd</span></span>

<span data-ttu-id="293ea-381">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-381">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="293ea-382">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="293ea-382">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="293ea-383">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="293ea-383">ViInsertLine</span></span>

<span data-ttu-id="293ea-384">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-384">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="293ea-385">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="293ea-385">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="293ea-386">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="293ea-386">ViInsertWithAppend</span></span>

<span data-ttu-id="293ea-387">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-387">Append from the current line position.</span></span>

- <span data-ttu-id="293ea-388">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="293ea-388">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="293ea-389">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="293ea-389">ViInsertWithDelete</span></span>

<span data-ttu-id="293ea-390">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="293ea-390">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="293ea-391">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="293ea-391">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="293ea-392">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="293ea-392">ViJoinLines</span></span>

<span data-ttu-id="293ea-393">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-393">Joins the current line and the next line.</span></span>

- <span data-ttu-id="293ea-394">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="293ea-394">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="293ea-395">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="293ea-395">ViReplaceLine</span></span>

<span data-ttu-id="293ea-396">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="293ea-396">Erase the entire command line.</span></span>

- <span data-ttu-id="293ea-397">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="293ea-397">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="293ea-398">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="293ea-398">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="293ea-399">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-399">Replaces until given character.</span></span>

- <span data-ttu-id="293ea-400">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="293ea-400">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="293ea-401">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-401">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="293ea-402">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-402">Replaces until given character.</span></span>

- <span data-ttu-id="293ea-403">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="293ea-403">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="293ea-404">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="293ea-404">ViReplaceToChar</span></span>

<span data-ttu-id="293ea-405">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-405">Deletes until given character.</span></span>

- <span data-ttu-id="293ea-406">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="293ea-406">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="293ea-407">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-407">ViReplaceToCharBackward</span></span>

<span data-ttu-id="293ea-408">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="293ea-408">Replaces until given character.</span></span>

- <span data-ttu-id="293ea-409">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="293ea-409">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="293ea-410">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="293ea-410">ViYankBeginningOfLine</span></span>

<span data-ttu-id="293ea-411">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-411">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="293ea-412">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="293ea-412">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="293ea-413">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-413">ViYankEndOfGlob</span></span>

<span data-ttu-id="293ea-414">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="293ea-414">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="293ea-415">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="293ea-415">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="293ea-416">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="293ea-416">ViYankEndOfWord</span></span>

<span data-ttu-id="293ea-417">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="293ea-417">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="293ea-418">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="293ea-418">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="293ea-419">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="293ea-419">ViYankLeft</span></span>

<span data-ttu-id="293ea-420">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-420">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="293ea-421">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="293ea-421">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="293ea-422">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="293ea-422">ViYankLine</span></span>

<span data-ttu-id="293ea-423">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="293ea-423">Yank the entire buffer.</span></span>

- <span data-ttu-id="293ea-424">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="293ea-424">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="293ea-425">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-425">ViYankNextGlob</span></span>

<span data-ttu-id="293ea-426">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="293ea-426">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="293ea-427">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="293ea-427">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="293ea-428">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="293ea-428">ViYankNextWord</span></span>

<span data-ttu-id="293ea-429">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-429">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="293ea-430">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="293ea-430">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="293ea-431">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="293ea-431">ViYankPercent</span></span>

<span data-ttu-id="293ea-432">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="293ea-432">Yank to/from matching brace.</span></span>

- <span data-ttu-id="293ea-433">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="293ea-433">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="293ea-434">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-434">ViYankPreviousGlob</span></span>

<span data-ttu-id="293ea-435">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-435">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="293ea-436">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="293ea-436">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="293ea-437">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="293ea-437">ViYankPreviousWord</span></span>

<span data-ttu-id="293ea-438">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-438">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="293ea-439">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="293ea-439">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="293ea-440">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="293ea-440">ViYankRight</span></span>

<span data-ttu-id="293ea-441">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-441">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="293ea-442">Modo de comando vi: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="293ea-442">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="293ea-443">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="293ea-443">ViYankToEndOfLine</span></span>

<span data-ttu-id="293ea-444">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="293ea-444">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="293ea-445">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="293ea-445">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="293ea-446">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="293ea-446">ViYankToFirstChar</span></span>

<span data-ttu-id="293ea-447">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-447">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="293ea-448">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="293ea-448">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="293ea-449">Yank</span><span class="sxs-lookup"><span data-stu-id="293ea-449">Yank</span></span>

<span data-ttu-id="293ea-450">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-450">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="293ea-451">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="293ea-451">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="293ea-452">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="293ea-452">YankLastArg</span></span>

<span data-ttu-id="293ea-453">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-453">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="293ea-454">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="293ea-454">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="293ea-455">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="293ea-455">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="293ea-456">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="293ea-456">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="293ea-457">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="293ea-457">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="293ea-458">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="293ea-458">YankNthArg</span></span>

<span data-ttu-id="293ea-459">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-459">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="293ea-460">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="293ea-460">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="293ea-461">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="293ea-461">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="293ea-462">YankPop</span><span class="sxs-lookup"><span data-stu-id="293ea-462">YankPop</span></span>

<span data-ttu-id="293ea-463">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-463">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="293ea-464">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="293ea-464">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="293ea-465">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="293ea-465">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="293ea-466">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="293ea-466">BackwardChar</span></span>

<span data-ttu-id="293ea-467">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="293ea-467">Move the cursor one character to the left.</span></span> <span data-ttu-id="293ea-468">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-468">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="293ea-469">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-469">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="293ea-470">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="293ea-470">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="293ea-471">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-471">BackwardWord</span></span>

<span data-ttu-id="293ea-472">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-472">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="293ea-473">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="293ea-473">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="293ea-474">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-474">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="293ea-475">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="293ea-475">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="293ea-476">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-476">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="293ea-477">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-477">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="293ea-478">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="293ea-478">BeginningOfLine</span></span>

<span data-ttu-id="293ea-479">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-479">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="293ea-480">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-480">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="293ea-481">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-481">Cmd: `<Home>`</span></span>
- <span data-ttu-id="293ea-482">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="293ea-482">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="293ea-483">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-483">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="293ea-484">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-484">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="293ea-485">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="293ea-485">EndOfLine</span></span>

<span data-ttu-id="293ea-486">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-486">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="293ea-487">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-487">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="293ea-488">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-488">Cmd: `<End>`</span></span>
- <span data-ttu-id="293ea-489">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="293ea-489">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="293ea-490">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-490">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="293ea-491">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="293ea-491">ForwardChar</span></span>

<span data-ttu-id="293ea-492">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="293ea-492">Move the cursor one character to the right.</span></span> <span data-ttu-id="293ea-493">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-493">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="293ea-494">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-494">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="293ea-495">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="293ea-495">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="293ea-496">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-496">ForwardWord</span></span>

<span data-ttu-id="293ea-497">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-497">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="293ea-498">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="293ea-498">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="293ea-499">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="293ea-499">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="293ea-500">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="293ea-500">GotoBrace</span></span>

<span data-ttu-id="293ea-501">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="293ea-501">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="293ea-502">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="293ea-502">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="293ea-503">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="293ea-503">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="293ea-504">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="293ea-504">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="293ea-505">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="293ea-505">GotoColumn</span></span>

<span data-ttu-id="293ea-506">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="293ea-506">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="293ea-507">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="293ea-507">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="293ea-508">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="293ea-508">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="293ea-509">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-509">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="293ea-510">Modo de comando vi: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="293ea-510">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="293ea-511">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="293ea-511">MoveToEndOfLine</span></span>

<span data-ttu-id="293ea-512">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-512">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="293ea-513">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="293ea-513">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="293ea-514">Próxima</span><span class="sxs-lookup"><span data-stu-id="293ea-514">NextLine</span></span>

<span data-ttu-id="293ea-515">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-515">Move the cursor to the next line.</span></span>

- <span data-ttu-id="293ea-516">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-516">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="293ea-517">NextWord</span><span class="sxs-lookup"><span data-stu-id="293ea-517">NextWord</span></span>

<span data-ttu-id="293ea-518">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="293ea-519">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="293ea-519">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="293ea-520">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-520">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="293ea-521">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-521">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="293ea-522">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-522">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="293ea-523">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="293ea-523">NextWordEnd</span></span>

<span data-ttu-id="293ea-524">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-524">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="293ea-525">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="293ea-525">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="293ea-526">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="293ea-526">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="293ea-527">Anterior</span><span class="sxs-lookup"><span data-stu-id="293ea-527">PreviousLine</span></span>

<span data-ttu-id="293ea-528">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-528">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="293ea-529">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-529">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="293ea-530">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-530">ShellBackwardWord</span></span>

<span data-ttu-id="293ea-531">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="293ea-532">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-532">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="293ea-533">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-533">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="293ea-534">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-534">ShellForwardWord</span></span>

<span data-ttu-id="293ea-535">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-535">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="293ea-536">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-536">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="293ea-537">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-537">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="293ea-538">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="293ea-538">ShellNextWord</span></span>

<span data-ttu-id="293ea-539">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-539">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="293ea-540">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-540">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="293ea-541">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-541">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="293ea-542">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="293ea-542">ViBackwardChar</span></span>

<span data-ttu-id="293ea-543">Mover o cursor um caractere para a esquerda no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="293ea-543">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="293ea-544">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-544">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="293ea-545">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-545">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="293ea-546">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="293ea-546">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="293ea-547">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-547">ViBackwardWord</span></span>

<span data-ttu-id="293ea-548">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-548">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="293ea-549">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="293ea-549">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="293ea-550">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="293ea-550">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="293ea-551">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="293ea-551">ViForwardChar</span></span>

<span data-ttu-id="293ea-552">Mover o cursor um caractere para a direita no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="293ea-552">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="293ea-553">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-553">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="293ea-554">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-554">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="293ea-555">Modo de comando vi: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="293ea-555">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="293ea-556">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-556">ViEndOfGlob</span></span>

<span data-ttu-id="293ea-557">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="293ea-557">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="293ea-558">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="293ea-558">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="293ea-559">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-559">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="293ea-560">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-560">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="293ea-561">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-561">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="293ea-562">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="293ea-562">ViGotoBrace</span></span>

<span data-ttu-id="293ea-563">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="293ea-563">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="293ea-564">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="293ea-564">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="293ea-565">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="293ea-565">ViNextGlob</span></span>

<span data-ttu-id="293ea-566">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-566">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="293ea-567">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="293ea-567">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="293ea-568">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="293ea-568">ViNextWord</span></span>

<span data-ttu-id="293ea-569">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-569">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="293ea-570">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="293ea-570">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="293ea-571">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="293ea-571">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="293ea-572">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="293ea-572">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="293ea-573">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="293ea-573">BeginningOfHistory</span></span>

<span data-ttu-id="293ea-574">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="293ea-574">Move to the first item in the history.</span></span>

- <span data-ttu-id="293ea-575">Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="293ea-575">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="293ea-576">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="293ea-576">ClearHistory</span></span>

<span data-ttu-id="293ea-577">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="293ea-577">Clears history in PSReadLine.</span></span> <span data-ttu-id="293ea-578">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="293ea-578">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="293ea-579">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="293ea-579">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="293ea-580">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="293ea-580">EndOfHistory</span></span>

<span data-ttu-id="293ea-581">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="293ea-581">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="293ea-582">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="293ea-582">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="293ea-583">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="293ea-583">ForwardSearchHistory</span></span>

<span data-ttu-id="293ea-584">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="293ea-584">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="293ea-585">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="293ea-585">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="293ea-586">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="293ea-586">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="293ea-587">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-587">HistorySearchBackward</span></span>

<span data-ttu-id="293ea-588">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-588">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="293ea-589">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="293ea-589">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="293ea-590">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="293ea-590">HistorySearchForward</span></span>

<span data-ttu-id="293ea-591">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-591">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="293ea-592">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="293ea-592">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="293ea-593">NextHistory</span><span class="sxs-lookup"><span data-stu-id="293ea-593">NextHistory</span></span>

<span data-ttu-id="293ea-594">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="293ea-594">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="293ea-595">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-595">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="293ea-596">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="293ea-596">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="293ea-597">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-597">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="293ea-598">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="293ea-598">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="293ea-599">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="293ea-599">PreviousHistory</span></span>

<span data-ttu-id="293ea-600">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="293ea-600">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="293ea-601">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-601">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="293ea-602">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="293ea-602">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="293ea-603">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-603">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="293ea-604">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="293ea-604">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="293ea-605">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="293ea-605">ReverseSearchHistory</span></span>

<span data-ttu-id="293ea-606">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="293ea-606">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="293ea-607">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="293ea-607">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="293ea-608">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="293ea-608">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="293ea-609">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-609">ViSearchHistoryBackward</span></span>

<span data-ttu-id="293ea-610">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="293ea-610">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="293ea-611">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="293ea-611">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="293ea-612">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="293ea-612">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="293ea-613">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="293ea-613">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="293ea-614">Concluir</span><span class="sxs-lookup"><span data-stu-id="293ea-614">Complete</span></span>

<span data-ttu-id="293ea-615">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-615">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="293ea-616">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="293ea-616">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="293ea-617">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="293ea-617">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="293ea-618">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="293ea-618">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="293ea-619">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="293ea-619">MenuComplete</span></span>

<span data-ttu-id="293ea-620">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-620">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="293ea-621">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="293ea-621">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="293ea-622">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="293ea-622">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="293ea-623">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="293ea-623">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="293ea-624">Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="293ea-624">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="293ea-625">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="293ea-625">PossibleCompletions</span></span>

<span data-ttu-id="293ea-626">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="293ea-626">Display the list of possible completions.</span></span>

- <span data-ttu-id="293ea-627">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="293ea-627">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="293ea-628">Modo de inserção de vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="293ea-628">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="293ea-629">Modo de comando vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="293ea-629">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="293ea-630">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="293ea-630">TabCompleteNext</span></span>

<span data-ttu-id="293ea-631">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="293ea-631">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="293ea-632">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="293ea-632">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="293ea-633">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="293ea-633">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="293ea-634">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="293ea-634">TabCompletePrevious</span></span>

<span data-ttu-id="293ea-635">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-635">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="293ea-636">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="293ea-636">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="293ea-637">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="293ea-637">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="293ea-638">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="293ea-638">ViTabCompleteNext</span></span>

<span data-ttu-id="293ea-639">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="293ea-639">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="293ea-640">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="293ea-640">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="293ea-641">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="293ea-641">ViTabCompletePrevious</span></span>

<span data-ttu-id="293ea-642">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="293ea-642">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="293ea-643">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="293ea-643">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="293ea-644">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="293ea-644">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="293ea-645">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="293ea-645">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="293ea-646">Aceite a próxima palavra da sugestão embutida ou selecionada.</span><span class="sxs-lookup"><span data-stu-id="293ea-646">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="293ea-647">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-647">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="293ea-648">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="293ea-648">AcceptSuggestion</span></span>

<span data-ttu-id="293ea-649">Aceite a sugestão embutida ou selecionada atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-649">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="293ea-650">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-650">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="293ea-651">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="293ea-651">CaptureScreen</span></span>

<span data-ttu-id="293ea-652">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="293ea-652">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="293ea-653">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-653">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="293ea-654">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="293ea-654">ClearScreen</span></span>

<span data-ttu-id="293ea-655">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="293ea-655">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="293ea-656">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="293ea-656">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="293ea-657">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="293ea-657">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="293ea-658">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="293ea-658">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="293ea-659">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="293ea-659">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="293ea-660">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="293ea-660">DigitArgument</span></span>

<span data-ttu-id="293ea-661">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="293ea-661">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="293ea-662">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="293ea-662">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="293ea-663">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="293ea-663">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="293ea-664">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="293ea-664">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="293ea-665">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="293ea-665">InvokePrompt</span></span>

<span data-ttu-id="293ea-666">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="293ea-666">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="293ea-667">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-667">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="293ea-668">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-668">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="293ea-669">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="293ea-669">ScrollDisplayDown</span></span>

<span data-ttu-id="293ea-670">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="293ea-670">Scroll the display down one screen.</span></span>

- <span data-ttu-id="293ea-671">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="293ea-671">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="293ea-672">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="293ea-672">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="293ea-673">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="293ea-673">ScrollDisplayDownLine</span></span>

<span data-ttu-id="293ea-674">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="293ea-674">Scroll the display down one line.</span></span>

- <span data-ttu-id="293ea-675">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="293ea-675">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="293ea-676">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="293ea-676">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="293ea-677">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="293ea-677">ScrollDisplayToCursor</span></span>

<span data-ttu-id="293ea-678">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-678">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="293ea-679">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-679">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="293ea-680">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="293ea-680">ScrollDisplayTop</span></span>

<span data-ttu-id="293ea-681">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="293ea-681">Scroll the display to the top.</span></span>

- <span data-ttu-id="293ea-682">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-682">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="293ea-683">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="293ea-683">ScrollDisplayUp</span></span>

<span data-ttu-id="293ea-684">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="293ea-684">Scroll the display up one screen.</span></span>

- <span data-ttu-id="293ea-685">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="293ea-685">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="293ea-686">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="293ea-686">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="293ea-687">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="293ea-687">ScrollDisplayUpLine</span></span>

<span data-ttu-id="293ea-688">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="293ea-688">Scroll the display up one line.</span></span>

- <span data-ttu-id="293ea-689">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="293ea-689">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="293ea-690">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="293ea-690">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="293ea-691">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="293ea-691">SelfInsert</span></span>

<span data-ttu-id="293ea-692">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="293ea-692">Insert the key.</span></span>

- <span data-ttu-id="293ea-693">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-693">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="293ea-694">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="293ea-694">ShowKeyBindings</span></span>

<span data-ttu-id="293ea-695">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="293ea-695">Show all bound keys.</span></span>

- <span data-ttu-id="293ea-696">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="293ea-696">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="293ea-697">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="293ea-697">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="293ea-698">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="293ea-698">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="293ea-699">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="293ea-699">ViCommandMode</span></span>

<span data-ttu-id="293ea-700">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="293ea-700">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="293ea-701">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="293ea-701">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="293ea-702">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="293ea-702">ViDigitArgumentInChord</span></span>

<span data-ttu-id="293ea-703">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="293ea-703">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="293ea-704">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-704">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="293ea-705">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="293ea-705">ViEditVisually</span></span>

<span data-ttu-id="293ea-706">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="293ea-706">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="293ea-707">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="293ea-707">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="293ea-708">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="293ea-708">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="293ea-709">ViExit</span><span class="sxs-lookup"><span data-stu-id="293ea-709">ViExit</span></span>

<span data-ttu-id="293ea-710">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="293ea-710">Exits the shell.</span></span>

- <span data-ttu-id="293ea-711">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-711">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="293ea-712">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="293ea-712">ViInsertMode</span></span>

<span data-ttu-id="293ea-713">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="293ea-713">Switch to Insert mode.</span></span>

- <span data-ttu-id="293ea-714">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="293ea-714">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="293ea-715">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="293ea-715">WhatIsKey</span></span>

<span data-ttu-id="293ea-716">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="293ea-716">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="293ea-717">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="293ea-717">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="293ea-718">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="293ea-718">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="293ea-719">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="293ea-719">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="293ea-720">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="293ea-720">ExchangePointAndMark</span></span>

<span data-ttu-id="293ea-721">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-721">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="293ea-722">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="293ea-722">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="293ea-723">SelectAll</span><span class="sxs-lookup"><span data-stu-id="293ea-723">SelectAll</span></span>

<span data-ttu-id="293ea-724">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="293ea-724">Select the entire line.</span></span>

- <span data-ttu-id="293ea-725">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="293ea-725">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="293ea-726">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="293ea-726">SelectBackwardChar</span></span>

<span data-ttu-id="293ea-727">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-727">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="293ea-728">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-728">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="293ea-729">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-729">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="293ea-730">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="293ea-730">SelectBackwardsLine</span></span>

<span data-ttu-id="293ea-731">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-731">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="293ea-732">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-732">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="293ea-733">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="293ea-733">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="293ea-734">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-734">SelectBackwardWord</span></span>

<span data-ttu-id="293ea-735">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="293ea-735">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="293ea-736">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-736">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="293ea-737">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="293ea-737">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="293ea-738">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="293ea-738">SelectForwardChar</span></span>

<span data-ttu-id="293ea-739">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-739">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="293ea-740">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-740">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="293ea-741">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-741">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="293ea-742">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-742">SelectForwardWord</span></span>

<span data-ttu-id="293ea-743">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="293ea-743">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="293ea-744">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="293ea-744">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="293ea-745">Seleção</span><span class="sxs-lookup"><span data-stu-id="293ea-745">SelectLine</span></span>

<span data-ttu-id="293ea-746">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="293ea-746">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="293ea-747">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-747">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="293ea-748">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="293ea-748">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="293ea-749">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="293ea-749">SelectNextWord</span></span>

<span data-ttu-id="293ea-750">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="293ea-750">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="293ea-751">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="293ea-751">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="293ea-752">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-752">SelectShellBackwardWord</span></span>

<span data-ttu-id="293ea-753">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="293ea-753">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="293ea-754">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-754">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="293ea-755">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="293ea-755">SelectShellForwardWord</span></span>

<span data-ttu-id="293ea-756">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="293ea-756">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="293ea-757">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-757">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="293ea-758">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="293ea-758">SelectShellNextWord</span></span>

<span data-ttu-id="293ea-759">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="293ea-759">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="293ea-760">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="293ea-760">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="293ea-761">Definir marca</span><span class="sxs-lookup"><span data-stu-id="293ea-761">SetMark</span></span>

<span data-ttu-id="293ea-762">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="293ea-762">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="293ea-763">Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="293ea-763">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="293ea-764">Funções IntelliSense preditivas</span><span class="sxs-lookup"><span data-stu-id="293ea-764">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="293ea-765">O IntelliSense preditiva precisa ser habilitado para usar essas funções.</span><span class="sxs-lookup"><span data-stu-id="293ea-765">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="293ea-766">AcceptNextWordSuggestion</span><span class="sxs-lookup"><span data-stu-id="293ea-766">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="293ea-767">Aceita a próxima palavra da sugestão embutida do IntelliSense preditiva.</span><span class="sxs-lookup"><span data-stu-id="293ea-767">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="293ea-768">Essa função pode ser associada com <kbd>Ctrl</kbd> + <kbd>F</kbd> executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="293ea-768">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="293ea-769">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="293ea-769">AcceptSuggestion</span></span>

<span data-ttu-id="293ea-770">Aceita a sugestão embutida atual do IntelliSense preditiva pressionando <kbd>RIGHTARROW</kbd> quando o cursor está no final da linha atual.</span><span class="sxs-lookup"><span data-stu-id="293ea-770">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="293ea-771">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="293ea-771">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="293ea-772">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="293ea-772">CharacterSearch</span></span>

<span data-ttu-id="293ea-773">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-773">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="293ea-774">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="293ea-774">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="293ea-775">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="293ea-775">Cmd: `<F3>`</span></span>
- <span data-ttu-id="293ea-776">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="293ea-776">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="293ea-777">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="293ea-777">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="293ea-778">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="293ea-778">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="293ea-779">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-779">CharacterSearchBackward</span></span>

<span data-ttu-id="293ea-780">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-780">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="293ea-781">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="293ea-781">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="293ea-782">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="293ea-782">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="293ea-783">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="293ea-783">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="293ea-784">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="293ea-784">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="293ea-785">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="293ea-785">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="293ea-786">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="293ea-786">RepeatLastCharSearch</span></span>

<span data-ttu-id="293ea-787">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="293ea-787">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="293ea-788">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="293ea-788">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="293ea-789">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="293ea-789">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="293ea-790">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="293ea-790">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="293ea-791">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="293ea-791">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="293ea-792">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="293ea-792">RepeatSearch</span></span>

<span data-ttu-id="293ea-793">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="293ea-793">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="293ea-794">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="293ea-794">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="293ea-795">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-795">RepeatSearchBackward</span></span>

<span data-ttu-id="293ea-796">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="293ea-796">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="293ea-797">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="293ea-797">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="293ea-798">SearchChar</span><span class="sxs-lookup"><span data-stu-id="293ea-798">SearchChar</span></span>

<span data-ttu-id="293ea-799">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-799">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="293ea-800">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="293ea-800">This is for 't' functionality.</span></span>

- <span data-ttu-id="293ea-801">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="293ea-801">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="293ea-802">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="293ea-802">SearchCharBackward</span></span>

<span data-ttu-id="293ea-803">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-803">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="293ea-804">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="293ea-804">This is for 'T' functionality.</span></span>

- <span data-ttu-id="293ea-805">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="293ea-805">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="293ea-806">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="293ea-806">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="293ea-807">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-807">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="293ea-808">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="293ea-808">This is for 'T' functionality.</span></span>

- <span data-ttu-id="293ea-809">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="293ea-809">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="293ea-810">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="293ea-810">SearchCharWithBackoff</span></span>

<span data-ttu-id="293ea-811">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="293ea-811">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="293ea-812">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="293ea-812">This is for 't' functionality.</span></span>

- <span data-ttu-id="293ea-813">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="293ea-813">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="293ea-814">SearchForward</span><span class="sxs-lookup"><span data-stu-id="293ea-814">SearchForward</span></span>

<span data-ttu-id="293ea-815">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="293ea-815">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="293ea-816">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="293ea-816">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="293ea-817">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="293ea-817">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="293ea-818">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="293ea-818">Custom Key Bindings</span></span>

<span data-ttu-id="293ea-819">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="293ea-819">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="293ea-820">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="293ea-820">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="293ea-821">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="293ea-821">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="293ea-822">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="293ea-822">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="293ea-823">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="293ea-823">Some useful examples include</span></span>

- <span data-ttu-id="293ea-824">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="293ea-824">edit the command line</span></span>
- <span data-ttu-id="293ea-825">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="293ea-825">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="293ea-826">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="293ea-826">change directories without changing the command line</span></span>

<span data-ttu-id="293ea-827">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="293ea-827">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="293ea-828">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="293ea-828">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="293ea-829">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="293ea-829">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="293ea-830">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="293ea-830">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="293ea-831">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="293ea-831">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="293ea-832">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="293ea-832">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="293ea-833">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="293ea-833">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="293ea-834">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="293ea-834">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="293ea-835">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="293ea-835">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="293ea-836">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="293ea-836">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="293ea-837">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="293ea-837">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="293ea-838">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="293ea-838">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="293ea-839">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="293ea-839">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="293ea-840">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="293ea-840">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="293ea-841">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="293ea-841">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="293ea-842">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="293ea-842">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="293ea-843">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="293ea-843">Clear the kill-ring.</span></span>  <span data-ttu-id="293ea-844">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="293ea-844">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="293ea-845">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="293ea-845">Delete length characters from start.</span></span>  <span data-ttu-id="293ea-846">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="293ea-846">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="293ea-847">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="293ea-847">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="293ea-848">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="293ea-848">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="293ea-849">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="293ea-849">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="293ea-850">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="293ea-850">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="293ea-851">Essas duas funções são usadas pelo `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="293ea-851">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="293ea-852">O primeiro é usado para obter todas as associações de chave.</span><span class="sxs-lookup"><span data-stu-id="293ea-852">The first is used to get all key bindings.</span></span> <span data-ttu-id="293ea-853">O segundo é usado para obter associações de chave específicas.</span><span class="sxs-lookup"><span data-stu-id="293ea-853">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="293ea-854">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="293ea-854">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="293ea-855">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="293ea-855">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="293ea-856">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="293ea-856">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="293ea-857">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="293ea-857">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="293ea-858">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="293ea-858">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="293ea-859">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="293ea-859">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="293ea-860">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="293ea-860">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="293ea-861">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="293ea-861">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="293ea-862">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="293ea-862">Replace some of the input.</span></span> <span data-ttu-id="293ea-863">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="293ea-863">This operation supports undo/redo.</span></span> <span data-ttu-id="293ea-864">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="293ea-864">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="293ea-865">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="293ea-865">Move the cursor to the given offset.</span></span> <span data-ttu-id="293ea-866">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="293ea-866">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="293ea-867">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="293ea-867">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="293ea-868">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="293ea-868">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="293ea-869">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="293ea-869">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="notes"></a><span data-ttu-id="293ea-870">Observações</span><span class="sxs-lookup"><span data-stu-id="293ea-870">Notes</span></span>

### <a name="command-history"></a><span data-ttu-id="293ea-871">Histórico de comandos</span><span class="sxs-lookup"><span data-stu-id="293ea-871">Command History</span></span>

<span data-ttu-id="293ea-872">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="293ea-872">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="293ea-873">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="293ea-873">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="293ea-874">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="293ea-874">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="293ea-875">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="293ea-875">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="293ea-876">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="293ea-876">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="293ea-877">Em sistemas não Windows, os arquivos de histórico são armazenados em `$env:XDG_DATA_HOME/powershell/PSReadLine` ou `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="293ea-877">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="293ea-878">Comentários & contribuindo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="293ea-878">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="293ea-879">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="293ea-879">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="293ea-880">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="293ea-880">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="293ea-881">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="293ea-881">See Also</span></span>

<span data-ttu-id="293ea-882">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="293ea-882">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
