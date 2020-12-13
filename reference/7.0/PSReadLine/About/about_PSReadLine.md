---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: f5ae99a7c8bdae82372423a3e4d8261d95ab83d5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692200"
---
# <a name="psreadline"></a><span data-ttu-id="2d644-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="2d644-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="2d644-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="2d644-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="2d644-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="2d644-106">Short Description</span></span>

<span data-ttu-id="2d644-107">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d644-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="2d644-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="2d644-108">Long Description</span></span>

<span data-ttu-id="2d644-109">O PSReadLine 2,0 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d644-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="2d644-110">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="2d644-110">It provides:</span></span>

- <span data-ttu-id="2d644-111">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="2d644-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="2d644-112">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="2d644-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="2d644-113">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="2d644-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="2d644-114">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="2d644-114">Customizable key bindings</span></span>
- <span data-ttu-id="2d644-115">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="2d644-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="2d644-116">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="2d644-116">Many configuration options</span></span>
- <span data-ttu-id="2d644-117">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="2d644-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="2d644-118">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="2d644-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="2d644-119">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="2d644-119">PowerShell token based "word" movement and kill</span></span>

> [!NOTE]
> <span data-ttu-id="2d644-120">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="2d644-120">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="2d644-121">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="2d644-121">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="2d644-122">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="2d644-122">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="2d644-123">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2d644-123">You can manually load the module if necessary.</span></span>

<span data-ttu-id="2d644-124">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]**.</span><span class="sxs-lookup"><span data-stu-id="2d644-124">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="2d644-125">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="2d644-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="2d644-126">Anular</span><span class="sxs-lookup"><span data-stu-id="2d644-126">Abort</span></span>

<span data-ttu-id="2d644-127">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="2d644-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="2d644-128">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="2d644-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="2d644-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="2d644-129">AcceptAndGetNext</span></span>

<span data-ttu-id="2d644-130">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-130">Attempt to execute the current input.</span></span> <span data-ttu-id="2d644-131">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="2d644-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="2d644-132">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="2d644-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="2d644-133">Aceitar</span><span class="sxs-lookup"><span data-stu-id="2d644-133">AcceptLine</span></span>

<span data-ttu-id="2d644-134">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-134">Attempt to execute the current input.</span></span> <span data-ttu-id="2d644-135">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="2d644-136">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="2d644-137">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="2d644-138">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="2d644-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="2d644-139">AddLine</span></span>

<span data-ttu-id="2d644-140">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="2d644-141">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="2d644-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="2d644-142">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="2d644-143">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="2d644-144">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="2d644-145">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="2d644-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="2d644-146">BackwardDeleteChar</span></span>

<span data-ttu-id="2d644-147">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="2d644-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="2d644-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="2d644-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="2d644-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="2d644-150">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2d644-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="2d644-151">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="2d644-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="2d644-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="2d644-152">BackwardDeleteLine</span></span>

<span data-ttu-id="2d644-153">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="2d644-154">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="2d644-155">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="2d644-156">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="2d644-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="2d644-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="2d644-157">BackwardDeleteWord</span></span>

<span data-ttu-id="2d644-158">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-158">Deletes the previous word.</span></span>

- <span data-ttu-id="2d644-159">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="2d644-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="2d644-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="2d644-160">BackwardKillLine</span></span>

<span data-ttu-id="2d644-161">Limpe a entrada do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="2d644-162">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2d644-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2d644-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="2d644-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="2d644-164">BackwardKillWord</span></span>

<span data-ttu-id="2d644-165">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="2d644-166">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="2d644-167">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2d644-168">Cmd `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2d644-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="2d644-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2d644-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="2d644-170">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2d644-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="2d644-171">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="2d644-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="2d644-172">Cancelar</span><span class="sxs-lookup"><span data-stu-id="2d644-172">CancelLine</span></span>

<span data-ttu-id="2d644-173">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="2d644-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="2d644-174">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2d644-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="2d644-175">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2d644-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="2d644-176">Copiar</span><span class="sxs-lookup"><span data-stu-id="2d644-176">Copy</span></span>

<span data-ttu-id="2d644-177">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="2d644-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="2d644-178">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="2d644-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="2d644-179">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="2d644-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="2d644-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="2d644-180">CopyOrCancelLine</span></span>

<span data-ttu-id="2d644-181">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="2d644-182">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2d644-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="2d644-183">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="2d644-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="2d644-184">Recortar</span><span class="sxs-lookup"><span data-stu-id="2d644-184">Cut</span></span>

<span data-ttu-id="2d644-185">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="2d644-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="2d644-186">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="2d644-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="2d644-187">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="2d644-187">DeleteChar</span></span>

<span data-ttu-id="2d644-188">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="2d644-189">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="2d644-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="2d644-190">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="2d644-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="2d644-191">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="2d644-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="2d644-192">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="2d644-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="2d644-193">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="2d644-193">DeleteCharOrExit</span></span>

<span data-ttu-id="2d644-194">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="2d644-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="2d644-195">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="2d644-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="2d644-196">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="2d644-196">DeleteEndOfWord</span></span>

<span data-ttu-id="2d644-197">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="2d644-198">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="2d644-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="2d644-199">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="2d644-199">DeleteLine</span></span>

<span data-ttu-id="2d644-200">Exclui a linha atual, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="2d644-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="2d644-201">Modo de comando vi: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="2d644-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="2d644-202">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="2d644-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="2d644-203">Exclui o texto do cursor para o primeiro caractere que não seja em branco da linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="2d644-204">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="2d644-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="2d644-205">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="2d644-205">DeleteToEnd</span></span>

<span data-ttu-id="2d644-206">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="2d644-207">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="2d644-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="2d644-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="2d644-208">DeleteWord</span></span>

<span data-ttu-id="2d644-209">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-209">Delete the next word.</span></span>

- <span data-ttu-id="2d644-210">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="2d644-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="2d644-211">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="2d644-211">ForwardDeleteLine</span></span>

<span data-ttu-id="2d644-212">Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="2d644-213">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="2d644-214">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="2d644-215">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="2d644-216">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="2d644-216">InsertLineAbove</span></span>

<span data-ttu-id="2d644-217">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="2d644-218">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="2d644-219">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="2d644-220">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="2d644-220">InsertLineBelow</span></span>

<span data-ttu-id="2d644-221">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="2d644-222">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="2d644-223">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="2d644-224">InvertCase</span><span class="sxs-lookup"><span data-stu-id="2d644-224">InvertCase</span></span>

<span data-ttu-id="2d644-225">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="2d644-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="2d644-226">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="2d644-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="2d644-227">Finalizar</span><span class="sxs-lookup"><span data-stu-id="2d644-227">KillLine</span></span>

<span data-ttu-id="2d644-228">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="2d644-229">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2d644-230">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="2d644-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="2d644-231">KillRegion</span><span class="sxs-lookup"><span data-stu-id="2d644-231">KillRegion</span></span>

<span data-ttu-id="2d644-232">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="2d644-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="2d644-233">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="2d644-234">KillWord</span><span class="sxs-lookup"><span data-stu-id="2d644-234">KillWord</span></span>

<span data-ttu-id="2d644-235">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="2d644-236">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="2d644-237">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2d644-238">Cmd `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="2d644-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="2d644-239">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="2d644-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="2d644-240">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="2d644-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="2d644-241">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="2d644-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="2d644-242">Colar</span><span class="sxs-lookup"><span data-stu-id="2d644-242">Paste</span></span>

<span data-ttu-id="2d644-243">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="2d644-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="2d644-244">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="2d644-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="2d644-245">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="2d644-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="2d644-246">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="2d644-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d644-247">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="2d644-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="2d644-248">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d644-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="2d644-249">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="2d644-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="2d644-250">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="2d644-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="2d644-251">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="2d644-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="2d644-252">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="2d644-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="2d644-253">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="2d644-253">PasteAfter</span></span>

<span data-ttu-id="2d644-254">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="2d644-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="2d644-255">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="2d644-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="2d644-256">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="2d644-256">PasteBefore</span></span>

<span data-ttu-id="2d644-257">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="2d644-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="2d644-258">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="2d644-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="2d644-259">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="2d644-259">PrependAndAccept</span></span>

<span data-ttu-id="2d644-260">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="2d644-261">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="2d644-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="2d644-262">Refaz</span><span class="sxs-lookup"><span data-stu-id="2d644-262">Redo</span></span>

<span data-ttu-id="2d644-263">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="2d644-263">Undo an undo.</span></span>

- <span data-ttu-id="2d644-264">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2d644-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="2d644-265">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2d644-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="2d644-266">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2d644-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="2d644-267">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="2d644-267">RepeatLastCommand</span></span>

<span data-ttu-id="2d644-268">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="2d644-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="2d644-269">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="2d644-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="2d644-270">Reverter</span><span class="sxs-lookup"><span data-stu-id="2d644-270">RevertLine</span></span>

<span data-ttu-id="2d644-271">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="2d644-272">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="2d644-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="2d644-273">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="2d644-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="2d644-274">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="2d644-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="2d644-275">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="2d644-276">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="2d644-277">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="2d644-278">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="2d644-279">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="2d644-279">ShellKillWord</span></span>

<span data-ttu-id="2d644-280">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="2d644-281">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="2d644-282">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="2d644-283">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="2d644-284">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="2d644-284">SwapCharacters</span></span>

<span data-ttu-id="2d644-285">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="2d644-286">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="2d644-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="2d644-287">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="2d644-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="2d644-288">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="2d644-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="2d644-289">Desfazer</span><span class="sxs-lookup"><span data-stu-id="2d644-289">Undo</span></span>

<span data-ttu-id="2d644-290">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-290">Undo a previous edit.</span></span>

- <span data-ttu-id="2d644-291">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="2d644-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="2d644-292">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="2d644-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="2d644-293">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="2d644-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="2d644-294">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="2d644-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="2d644-295">UndoAll</span><span class="sxs-lookup"><span data-stu-id="2d644-295">UndoAll</span></span>

<span data-ttu-id="2d644-296">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="2d644-297">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="2d644-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="2d644-298">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="2d644-298">UnixWordRubout</span></span>

<span data-ttu-id="2d644-299">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="2d644-300">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="2d644-301">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="2d644-302">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="2d644-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="2d644-303">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="2d644-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="2d644-304">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-304">Attempt to execute the current input.</span></span> <span data-ttu-id="2d644-305">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="2d644-306">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="2d644-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="2d644-307">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="2d644-307">ViAcceptLine</span></span>

<span data-ttu-id="2d644-308">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="2d644-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="2d644-309">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="2d644-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="2d644-310">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="2d644-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="2d644-311">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="2d644-312">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="2d644-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="2d644-313">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="2d644-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="2d644-314">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="2d644-314">ViAppendLine</span></span>

<span data-ttu-id="2d644-315">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="2d644-316">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="2d644-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="2d644-317">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="2d644-318">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="2d644-319">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="2d644-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="2d644-320">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-320">ViBackwardGlob</span></span>

<span data-ttu-id="2d644-321">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="2d644-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="2d644-322">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="2d644-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="2d644-323">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="2d644-323">ViDeleteBrace</span></span>

<span data-ttu-id="2d644-324">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="2d644-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="2d644-325">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="2d644-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="2d644-326">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="2d644-327">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="2d644-328">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="2d644-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="2d644-329">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-329">ViDeleteGlob</span></span>

<span data-ttu-id="2d644-330">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="2d644-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="2d644-331">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="2d644-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="2d644-332">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="2d644-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="2d644-333">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-333">Deletes until given character.</span></span>

- <span data-ttu-id="2d644-334">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="2d644-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="2d644-335">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="2d644-336">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-336">Deletes until given character.</span></span>

- <span data-ttu-id="2d644-337">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="2d644-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="2d644-338">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="2d644-338">ViDeleteToChar</span></span>

<span data-ttu-id="2d644-339">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-339">Deletes until given character.</span></span>

- <span data-ttu-id="2d644-340">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="2d644-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="2d644-341">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="2d644-342">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="2d644-343">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="2d644-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="2d644-344">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="2d644-344">ViInsertAtBegining</span></span>

<span data-ttu-id="2d644-345">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="2d644-346">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="2d644-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="2d644-347">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="2d644-347">ViInsertAtEnd</span></span>

<span data-ttu-id="2d644-348">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="2d644-349">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="2d644-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="2d644-350">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="2d644-350">ViInsertLine</span></span>

<span data-ttu-id="2d644-351">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="2d644-352">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="2d644-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="2d644-353">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="2d644-353">ViInsertWithAppend</span></span>

<span data-ttu-id="2d644-354">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-354">Append from the current line position.</span></span>

- <span data-ttu-id="2d644-355">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="2d644-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="2d644-356">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="2d644-356">ViInsertWithDelete</span></span>

<span data-ttu-id="2d644-357">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="2d644-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="2d644-358">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="2d644-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="2d644-359">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="2d644-359">ViJoinLines</span></span>

<span data-ttu-id="2d644-360">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="2d644-361">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="2d644-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="2d644-362">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="2d644-362">ViReplaceLine</span></span>

<span data-ttu-id="2d644-363">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="2d644-363">Erase the entire command line.</span></span>

- <span data-ttu-id="2d644-364">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="2d644-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="2d644-365">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="2d644-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="2d644-366">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-366">Replaces until given character.</span></span>

- <span data-ttu-id="2d644-367">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="2d644-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="2d644-368">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="2d644-369">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-369">Replaces until given character.</span></span>

- <span data-ttu-id="2d644-370">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="2d644-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="2d644-371">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="2d644-371">ViReplaceToChar</span></span>

<span data-ttu-id="2d644-372">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-372">Deletes until given character.</span></span>

- <span data-ttu-id="2d644-373">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="2d644-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="2d644-374">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="2d644-375">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="2d644-375">Replaces until given character.</span></span>

- <span data-ttu-id="2d644-376">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="2d644-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="2d644-377">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="2d644-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="2d644-378">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="2d644-379">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="2d644-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="2d644-380">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="2d644-381">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="2d644-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="2d644-382">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="2d644-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="2d644-383">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="2d644-383">ViYankEndOfWord</span></span>

<span data-ttu-id="2d644-384">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="2d644-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="2d644-385">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="2d644-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="2d644-386">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="2d644-386">ViYankLeft</span></span>

<span data-ttu-id="2d644-387">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="2d644-388">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="2d644-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="2d644-389">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="2d644-389">ViYankLine</span></span>

<span data-ttu-id="2d644-390">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="2d644-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="2d644-391">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="2d644-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="2d644-392">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-392">ViYankNextGlob</span></span>

<span data-ttu-id="2d644-393">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="2d644-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="2d644-394">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="2d644-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="2d644-395">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="2d644-395">ViYankNextWord</span></span>

<span data-ttu-id="2d644-396">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="2d644-397">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="2d644-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="2d644-398">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="2d644-398">ViYankPercent</span></span>

<span data-ttu-id="2d644-399">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="2d644-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="2d644-400">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="2d644-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="2d644-401">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="2d644-402">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="2d644-403">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="2d644-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="2d644-404">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="2d644-404">ViYankPreviousWord</span></span>

<span data-ttu-id="2d644-405">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="2d644-406">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="2d644-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="2d644-407">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="2d644-407">ViYankRight</span></span>

<span data-ttu-id="2d644-408">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="2d644-409">Modo de comando vi: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="2d644-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="2d644-410">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="2d644-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="2d644-411">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="2d644-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="2d644-412">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="2d644-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="2d644-413">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="2d644-413">ViYankToFirstChar</span></span>

<span data-ttu-id="2d644-414">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="2d644-415">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="2d644-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="2d644-416">Yank</span><span class="sxs-lookup"><span data-stu-id="2d644-416">Yank</span></span>

<span data-ttu-id="2d644-417">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="2d644-418">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2d644-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="2d644-419">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="2d644-419">YankLastArg</span></span>

<span data-ttu-id="2d644-420">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="2d644-421">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="2d644-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="2d644-422">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="2d644-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="2d644-423">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="2d644-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="2d644-424">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="2d644-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="2d644-425">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="2d644-425">YankNthArg</span></span>

<span data-ttu-id="2d644-426">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="2d644-427">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="2d644-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="2d644-428">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="2d644-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="2d644-429">YankPop</span><span class="sxs-lookup"><span data-stu-id="2d644-429">YankPop</span></span>

<span data-ttu-id="2d644-430">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="2d644-431">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="2d644-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="2d644-432">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="2d644-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="2d644-433">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="2d644-433">BackwardChar</span></span>

<span data-ttu-id="2d644-434">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="2d644-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="2d644-435">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="2d644-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="2d644-436">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="2d644-437">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="2d644-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="2d644-438">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="2d644-439">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="2d644-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="2d644-440">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-440">BackwardWord</span></span>

<span data-ttu-id="2d644-441">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="2d644-442">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2d644-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2d644-443">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="2d644-444">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="2d644-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="2d644-445">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="2d644-446">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="2d644-447">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="2d644-447">BeginningOfLine</span></span>

<span data-ttu-id="2d644-448">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="2d644-449">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="2d644-450">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="2d644-451">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="2d644-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="2d644-452">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="2d644-453">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="2d644-454">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="2d644-454">EndOfLine</span></span>

<span data-ttu-id="2d644-455">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="2d644-456">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="2d644-457">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="2d644-458">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="2d644-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="2d644-459">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="2d644-460">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="2d644-460">ForwardChar</span></span>

<span data-ttu-id="2d644-461">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="2d644-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="2d644-462">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="2d644-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="2d644-463">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="2d644-464">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="2d644-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="2d644-465">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="2d644-466">Modo de comando vi: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="2d644-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="2d644-467">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-467">ForwardWord</span></span>

<span data-ttu-id="2d644-468">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="2d644-469">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2d644-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2d644-470">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="2d644-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="2d644-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="2d644-471">GotoBrace</span></span>

<span data-ttu-id="2d644-472">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="2d644-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="2d644-473">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2d644-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="2d644-474">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2d644-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="2d644-475">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2d644-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="2d644-476">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="2d644-476">GotoColumn</span></span>

<span data-ttu-id="2d644-477">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="2d644-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="2d644-478">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="2d644-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="2d644-479">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="2d644-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="2d644-480">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="2d644-481">Modo de comando vi: `<^>`</span><span class="sxs-lookup"><span data-stu-id="2d644-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="2d644-482">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="2d644-482">MoveToEndOfLine</span></span>

<span data-ttu-id="2d644-483">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="2d644-484">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="2d644-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="2d644-485">Próxima</span><span class="sxs-lookup"><span data-stu-id="2d644-485">NextLine</span></span>

<span data-ttu-id="2d644-486">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="2d644-487">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="2d644-488">NextWord</span><span class="sxs-lookup"><span data-stu-id="2d644-488">NextWord</span></span>

<span data-ttu-id="2d644-489">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="2d644-490">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2d644-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2d644-491">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="2d644-492">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="2d644-493">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="2d644-494">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="2d644-494">NextWordEnd</span></span>

<span data-ttu-id="2d644-495">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="2d644-496">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2d644-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2d644-497">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="2d644-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="2d644-498">Anterior</span><span class="sxs-lookup"><span data-stu-id="2d644-498">PreviousLine</span></span>

<span data-ttu-id="2d644-499">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="2d644-500">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="2d644-501">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-501">ShellBackwardWord</span></span>

<span data-ttu-id="2d644-502">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="2d644-503">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d644-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="2d644-504">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="2d644-505">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-505">ShellForwardWord</span></span>

<span data-ttu-id="2d644-506">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="2d644-507">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d644-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="2d644-508">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="2d644-509">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="2d644-509">ShellNextWord</span></span>

<span data-ttu-id="2d644-510">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="2d644-511">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d644-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="2d644-512">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="2d644-513">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-513">ViBackwardWord</span></span>

<span data-ttu-id="2d644-514">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="2d644-515">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2d644-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2d644-516">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="2d644-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="2d644-517">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-517">ViEndOfGlob</span></span>

<span data-ttu-id="2d644-518">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="2d644-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="2d644-519">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="2d644-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="2d644-520">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="2d644-521">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="2d644-522">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="2d644-523">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="2d644-523">ViGotoBrace</span></span>

<span data-ttu-id="2d644-524">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="2d644-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="2d644-525">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="2d644-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="2d644-526">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="2d644-526">ViNextGlob</span></span>

<span data-ttu-id="2d644-527">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="2d644-528">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="2d644-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="2d644-529">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="2d644-529">ViNextWord</span></span>

<span data-ttu-id="2d644-530">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="2d644-531">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2d644-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="2d644-532">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="2d644-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="2d644-533">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="2d644-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="2d644-534">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="2d644-534">BeginningOfHistory</span></span>

<span data-ttu-id="2d644-535">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="2d644-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="2d644-536">Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="2d644-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="2d644-537">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="2d644-537">ClearHistory</span></span>

<span data-ttu-id="2d644-538">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="2d644-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="2d644-539">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d644-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="2d644-540">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="2d644-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="2d644-541">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="2d644-541">EndOfHistory</span></span>

<span data-ttu-id="2d644-542">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="2d644-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="2d644-543">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="2d644-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="2d644-544">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="2d644-544">ForwardSearchHistory</span></span>

<span data-ttu-id="2d644-545">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="2d644-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="2d644-546">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2d644-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="2d644-547">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2d644-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="2d644-548">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-548">HistorySearchBackward</span></span>

<span data-ttu-id="2d644-549">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="2d644-550">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="2d644-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="2d644-551">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="2d644-551">HistorySearchForward</span></span>

<span data-ttu-id="2d644-552">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="2d644-553">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="2d644-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="2d644-554">NextHistory</span><span class="sxs-lookup"><span data-stu-id="2d644-554">NextHistory</span></span>

<span data-ttu-id="2d644-555">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="2d644-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="2d644-556">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="2d644-557">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="2d644-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="2d644-558">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="2d644-559">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="2d644-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="2d644-560">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="2d644-560">PreviousHistory</span></span>

<span data-ttu-id="2d644-561">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="2d644-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="2d644-562">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="2d644-563">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="2d644-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="2d644-564">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="2d644-565">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="2d644-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="2d644-566">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="2d644-566">ReverseSearchHistory</span></span>

<span data-ttu-id="2d644-567">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="2d644-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="2d644-568">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2d644-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="2d644-569">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2d644-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="2d644-570">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="2d644-571">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="2d644-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="2d644-572">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2d644-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="2d644-573">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="2d644-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="2d644-574">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="2d644-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="2d644-575">Concluir</span><span class="sxs-lookup"><span data-stu-id="2d644-575">Complete</span></span>

<span data-ttu-id="2d644-576">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="2d644-577">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="2d644-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="2d644-578">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="2d644-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="2d644-579">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2d644-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="2d644-580">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="2d644-580">MenuComplete</span></span>

<span data-ttu-id="2d644-581">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="2d644-582">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="2d644-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="2d644-583">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="2d644-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="2d644-584">Cmd `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2d644-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="2d644-585">Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2d644-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="2d644-586">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="2d644-586">PossibleCompletions</span></span>

<span data-ttu-id="2d644-587">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="2d644-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="2d644-588">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="2d644-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="2d644-589">Modo de inserção de vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2d644-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="2d644-590">Modo de comando vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="2d644-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="2d644-591">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="2d644-591">TabCompleteNext</span></span>

<span data-ttu-id="2d644-592">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="2d644-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="2d644-593">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2d644-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="2d644-594">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2d644-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="2d644-595">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="2d644-595">TabCompletePrevious</span></span>

<span data-ttu-id="2d644-596">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="2d644-597">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="2d644-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="2d644-598">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="2d644-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="2d644-599">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="2d644-599">ViTabCompleteNext</span></span>

<span data-ttu-id="2d644-600">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="2d644-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="2d644-601">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="2d644-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="2d644-602">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="2d644-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="2d644-603">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="2d644-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="2d644-604">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="2d644-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="2d644-605">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="2d644-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="2d644-606">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="2d644-606">CaptureScreen</span></span>

<span data-ttu-id="2d644-607">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="2d644-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="2d644-608">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="2d644-609">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="2d644-609">ClearScreen</span></span>

<span data-ttu-id="2d644-610">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="2d644-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="2d644-611">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2d644-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="2d644-612">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2d644-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="2d644-613">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2d644-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="2d644-614">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="2d644-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="2d644-615">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="2d644-615">DigitArgument</span></span>

<span data-ttu-id="2d644-616">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="2d644-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="2d644-617">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="2d644-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="2d644-618">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="2d644-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="2d644-619">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="2d644-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="2d644-620">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="2d644-620">InvokePrompt</span></span>

<span data-ttu-id="2d644-621">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="2d644-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="2d644-622">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2d644-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="2d644-623">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="2d644-624">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="2d644-624">ScrollDisplayDown</span></span>

<span data-ttu-id="2d644-625">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="2d644-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="2d644-626">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2d644-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="2d644-627">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2d644-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="2d644-628">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="2d644-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="2d644-629">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="2d644-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="2d644-630">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2d644-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="2d644-631">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="2d644-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="2d644-632">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="2d644-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="2d644-633">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="2d644-634">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="2d644-635">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="2d644-635">ScrollDisplayTop</span></span>

<span data-ttu-id="2d644-636">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="2d644-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="2d644-637">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="2d644-638">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="2d644-638">ScrollDisplayUp</span></span>

<span data-ttu-id="2d644-639">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="2d644-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="2d644-640">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2d644-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="2d644-641">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2d644-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="2d644-642">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="2d644-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="2d644-643">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="2d644-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="2d644-644">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2d644-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="2d644-645">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="2d644-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="2d644-646">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="2d644-646">SelfInsert</span></span>

<span data-ttu-id="2d644-647">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="2d644-647">Insert the key.</span></span>

- <span data-ttu-id="2d644-648">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="2d644-649">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="2d644-649">ShowKeyBindings</span></span>

<span data-ttu-id="2d644-650">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="2d644-650">Show all bound keys.</span></span>

- <span data-ttu-id="2d644-651">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2d644-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="2d644-652">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2d644-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="2d644-653">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2d644-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="2d644-654">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="2d644-654">ViCommandMode</span></span>

<span data-ttu-id="2d644-655">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="2d644-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="2d644-656">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="2d644-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="2d644-657">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="2d644-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="2d644-658">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="2d644-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="2d644-659">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="2d644-660">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="2d644-660">ViEditVisually</span></span>

<span data-ttu-id="2d644-661">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="2d644-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="2d644-662">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="2d644-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="2d644-663">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="2d644-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="2d644-664">ViExit</span><span class="sxs-lookup"><span data-stu-id="2d644-664">ViExit</span></span>

<span data-ttu-id="2d644-665">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="2d644-665">Exits the shell.</span></span>

- <span data-ttu-id="2d644-666">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="2d644-667">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="2d644-667">ViInsertMode</span></span>

<span data-ttu-id="2d644-668">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="2d644-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="2d644-669">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="2d644-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="2d644-670">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="2d644-670">WhatIsKey</span></span>

<span data-ttu-id="2d644-671">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="2d644-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="2d644-672">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2d644-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="2d644-673">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="2d644-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="2d644-674">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="2d644-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="2d644-675">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="2d644-675">ExchangePointAndMark</span></span>

<span data-ttu-id="2d644-676">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="2d644-677">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="2d644-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="2d644-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="2d644-678">SelectAll</span></span>

<span data-ttu-id="2d644-679">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="2d644-679">Select the entire line.</span></span>

- <span data-ttu-id="2d644-680">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="2d644-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="2d644-681">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="2d644-681">SelectBackwardChar</span></span>

<span data-ttu-id="2d644-682">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="2d644-683">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="2d644-684">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="2d644-685">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="2d644-685">SelectBackwardsLine</span></span>

<span data-ttu-id="2d644-686">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="2d644-687">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="2d644-688">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="2d644-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="2d644-689">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-689">SelectBackwardWord</span></span>

<span data-ttu-id="2d644-690">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="2d644-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="2d644-691">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="2d644-692">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="2d644-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="2d644-693">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="2d644-693">SelectForwardChar</span></span>

<span data-ttu-id="2d644-694">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="2d644-695">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="2d644-696">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="2d644-697">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-697">SelectForwardWord</span></span>

<span data-ttu-id="2d644-698">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="2d644-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="2d644-699">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="2d644-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="2d644-700">Seleção</span><span class="sxs-lookup"><span data-stu-id="2d644-700">SelectLine</span></span>

<span data-ttu-id="2d644-701">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="2d644-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="2d644-702">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="2d644-703">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="2d644-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="2d644-704">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="2d644-704">SelectNextWord</span></span>

<span data-ttu-id="2d644-705">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="2d644-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="2d644-706">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="2d644-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="2d644-707">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="2d644-708">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="2d644-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="2d644-709">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="2d644-710">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="2d644-710">SelectShellForwardWord</span></span>

<span data-ttu-id="2d644-711">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="2d644-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="2d644-712">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="2d644-713">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="2d644-713">SelectShellNextWord</span></span>

<span data-ttu-id="2d644-714">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="2d644-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="2d644-715">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="2d644-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="2d644-716">Definir marca</span><span class="sxs-lookup"><span data-stu-id="2d644-716">SetMark</span></span>

<span data-ttu-id="2d644-717">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="2d644-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="2d644-718">Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="2d644-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="2d644-719">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2d644-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="2d644-720">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="2d644-720">CharacterSearch</span></span>

<span data-ttu-id="2d644-721">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="2d644-722">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2d644-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="2d644-723">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="2d644-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="2d644-724">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="2d644-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="2d644-725">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="2d644-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="2d644-726">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="2d644-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="2d644-727">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-727">CharacterSearchBackward</span></span>

<span data-ttu-id="2d644-728">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="2d644-729">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2d644-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="2d644-730">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="2d644-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="2d644-731">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="2d644-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="2d644-732">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="2d644-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="2d644-733">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="2d644-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="2d644-734">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="2d644-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="2d644-735">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="2d644-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="2d644-736">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="2d644-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="2d644-737">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="2d644-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="2d644-738">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="2d644-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="2d644-739">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="2d644-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="2d644-740">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="2d644-740">RepeatSearch</span></span>

<span data-ttu-id="2d644-741">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="2d644-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="2d644-742">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="2d644-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="2d644-743">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-743">RepeatSearchBackward</span></span>

<span data-ttu-id="2d644-744">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="2d644-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="2d644-745">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="2d644-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="2d644-746">SearchChar</span><span class="sxs-lookup"><span data-stu-id="2d644-746">SearchChar</span></span>

<span data-ttu-id="2d644-747">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="2d644-748">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="2d644-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="2d644-749">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="2d644-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="2d644-750">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="2d644-750">SearchCharBackward</span></span>

<span data-ttu-id="2d644-751">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="2d644-752">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="2d644-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="2d644-753">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="2d644-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="2d644-754">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="2d644-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="2d644-755">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="2d644-756">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="2d644-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="2d644-757">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="2d644-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="2d644-758">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="2d644-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="2d644-759">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="2d644-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="2d644-760">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="2d644-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="2d644-761">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="2d644-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="2d644-762">SearchForward</span><span class="sxs-lookup"><span data-stu-id="2d644-762">SearchForward</span></span>

<span data-ttu-id="2d644-763">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="2d644-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="2d644-764">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2d644-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="2d644-765">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="2d644-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="2d644-766">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="2d644-766">Custom Key Bindings</span></span>

<span data-ttu-id="2d644-767">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="2d644-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="2d644-768">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="2d644-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="2d644-769">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="2d644-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="2d644-770">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="2d644-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="2d644-771">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="2d644-771">Some useful examples include</span></span>

- <span data-ttu-id="2d644-772">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="2d644-772">edit the command line</span></span>
- <span data-ttu-id="2d644-773">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="2d644-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="2d644-774">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="2d644-774">change directories without changing the command line</span></span>

<span data-ttu-id="2d644-775">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="2d644-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="2d644-776">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="2d644-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="2d644-777">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="2d644-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="2d644-778">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="2d644-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="2d644-779">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="2d644-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="2d644-780">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="2d644-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="2d644-781">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="2d644-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="2d644-782">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="2d644-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="2d644-783">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="2d644-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="2d644-784">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="2d644-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="2d644-785">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2d644-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="2d644-786">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="2d644-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="2d644-787">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="2d644-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="2d644-788">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="2d644-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="2d644-789">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2d644-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="2d644-790">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="2d644-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="2d644-791">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="2d644-791">Clear the kill-ring.</span></span>  <span data-ttu-id="2d644-792">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="2d644-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="2d644-793">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="2d644-793">Delete length characters from start.</span></span>  <span data-ttu-id="2d644-794">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="2d644-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="2d644-795">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="2d644-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="2d644-796">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="2d644-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="2d644-797">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="2d644-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="2d644-798">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="2d644-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="2d644-799">Essa função é usada pelo Get-PSReadLineKeyHandler e provavelmente não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="2d644-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="2d644-800">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="2d644-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="2d644-801">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="2d644-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="2d644-802">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="2d644-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="2d644-803">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="2d644-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="2d644-804">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="2d644-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="2d644-805">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="2d644-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="2d644-806">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="2d644-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="2d644-807">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="2d644-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="2d644-808">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="2d644-808">Replace some of the input.</span></span> <span data-ttu-id="2d644-809">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="2d644-809">This operation supports undo/redo.</span></span> <span data-ttu-id="2d644-810">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="2d644-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="2d644-811">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="2d644-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="2d644-812">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="2d644-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="2d644-813">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="2d644-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="2d644-814">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="2d644-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="2d644-815">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="2d644-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="2d644-816">Observação</span><span class="sxs-lookup"><span data-stu-id="2d644-816">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="2d644-817">Histórico de comandos</span><span class="sxs-lookup"><span data-stu-id="2d644-817">Command History</span></span>

<span data-ttu-id="2d644-818">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2d644-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="2d644-819">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="2d644-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="2d644-820">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="2d644-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="2d644-821">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="2d644-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="2d644-822">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="2d644-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="2d644-823">Em sistemas não Windows, os arquivos de histórico são armazenados em `$env:XDG_DATA_HOME/powershell/PSReadLine` ou `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="2d644-823">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="2d644-824">Comentários & contribuindo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="2d644-824">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="2d644-825">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="2d644-825">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="2d644-826">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="2d644-826">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d644-827">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d644-827">See Also</span></span>

<span data-ttu-id="2d644-828">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="2d644-828">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
