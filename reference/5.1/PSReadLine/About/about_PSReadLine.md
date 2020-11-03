---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: ad6e85a30f866cb332c89a4c36f42231f511f5ae
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196564"
---
# <a name="psreadline"></a><span data-ttu-id="ed93c-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="ed93c-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="ed93c-106">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="ed93c-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ed93c-107">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="ed93c-108">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="ed93c-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="ed93c-109">O PSReadLine 2,0 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="ed93c-110">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="ed93c-110">It provides:</span></span>

- <span data-ttu-id="ed93c-111">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="ed93c-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="ed93c-112">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="ed93c-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="ed93c-113">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="ed93c-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="ed93c-114">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="ed93c-114">Customizable key bindings</span></span>
- <span data-ttu-id="ed93c-115">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="ed93c-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="ed93c-116">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="ed93c-116">Many configuration options</span></span>
- <span data-ttu-id="ed93c-117">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="ed93c-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="ed93c-118">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="ed93c-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="ed93c-119">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="ed93c-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="ed93c-120">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]** .</span><span class="sxs-lookup"><span data-stu-id="ed93c-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]** .</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="ed93c-121">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="ed93c-121">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="ed93c-122">Anular</span><span class="sxs-lookup"><span data-stu-id="ed93c-122">Abort</span></span>

<span data-ttu-id="ed93c-123">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="ed93c-123">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="ed93c-124">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-124">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="ed93c-125">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="ed93c-125">AcceptAndGetNext</span></span>

<span data-ttu-id="ed93c-126">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-126">Attempt to execute the current input.</span></span> <span data-ttu-id="ed93c-127">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-127">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="ed93c-128">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-128">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="ed93c-129">Aceitar</span><span class="sxs-lookup"><span data-stu-id="ed93c-129">AcceptLine</span></span>

<span data-ttu-id="ed93c-130">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-130">Attempt to execute the current input.</span></span> <span data-ttu-id="ed93c-131">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-131">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="ed93c-132">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-132">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="ed93c-133">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-133">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="ed93c-134">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-134">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="ed93c-135">AddLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-135">AddLine</span></span>

<span data-ttu-id="ed93c-136">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-136">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="ed93c-137">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="ed93c-137">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="ed93c-138">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-138">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="ed93c-139">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-139">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="ed93c-140">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-140">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="ed93c-141">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-141">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="ed93c-142">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-142">BackwardDeleteChar</span></span>

<span data-ttu-id="ed93c-143">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-143">Delete the character before the cursor.</span></span>

- <span data-ttu-id="ed93c-144">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-144">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="ed93c-145">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-145">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="ed93c-146">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-146">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="ed93c-147">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-147">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="ed93c-148">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-148">BackwardDeleteLine</span></span>

<span data-ttu-id="ed93c-149">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-149">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="ed93c-150">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-150">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="ed93c-151">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-151">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="ed93c-152">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-152">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="ed93c-153">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-153">BackwardDeleteWord</span></span>

<span data-ttu-id="ed93c-154">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-154">Deletes the previous word.</span></span>

- <span data-ttu-id="ed93c-155">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-155">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="ed93c-156">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-156">BackwardKillLine</span></span>

<span data-ttu-id="ed93c-157">Limpe a entrada do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-157">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="ed93c-158">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-158">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="ed93c-159">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-159">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="ed93c-160">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-160">BackwardKillWord</span></span>

<span data-ttu-id="ed93c-161">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-161">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="ed93c-162">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-162">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="ed93c-163">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-163">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="ed93c-164">Cmd `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-164">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="ed93c-165">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-165">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="ed93c-166">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-166">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="ed93c-167">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-167">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="ed93c-168">Cancelar</span><span class="sxs-lookup"><span data-stu-id="ed93c-168">CancelLine</span></span>

<span data-ttu-id="ed93c-169">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="ed93c-169">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="ed93c-170">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-170">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="ed93c-171">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-171">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="ed93c-172">Copiar</span><span class="sxs-lookup"><span data-stu-id="ed93c-172">Copy</span></span>

<span data-ttu-id="ed93c-173">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="ed93c-173">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="ed93c-174">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="ed93c-174">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="ed93c-175">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-175">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="ed93c-176">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-176">CopyOrCancelLine</span></span>

<span data-ttu-id="ed93c-177">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-177">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="ed93c-178">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-178">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="ed93c-179">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-179">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="ed93c-180">Recortar</span><span class="sxs-lookup"><span data-stu-id="ed93c-180">Cut</span></span>

<span data-ttu-id="ed93c-181">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="ed93c-181">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="ed93c-182">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-182">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="ed93c-183">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-183">DeleteChar</span></span>

<span data-ttu-id="ed93c-184">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-184">Delete the character under the cursor.</span></span>

- <span data-ttu-id="ed93c-185">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-185">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="ed93c-186">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-186">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="ed93c-187">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-187">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="ed93c-188">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-188">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="ed93c-189">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="ed93c-189">DeleteCharOrExit</span></span>

<span data-ttu-id="ed93c-190">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="ed93c-190">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="ed93c-191">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-191">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="ed93c-192">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-192">DeleteEndOfWord</span></span>

<span data-ttu-id="ed93c-193">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-193">Delete to the end of the word.</span></span>

- <span data-ttu-id="ed93c-194">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-194">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="ed93c-195">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-195">DeleteLine</span></span>

<span data-ttu-id="ed93c-196">Exclui a linha atual, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-196">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="ed93c-197">Modo de comando vi: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-197">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="ed93c-198">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-198">DeleteLineToFirstChar</span></span>

<span data-ttu-id="ed93c-199">Exclui o texto do cursor para o primeiro caractere que não seja em branco da linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-199">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="ed93c-200">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-200">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="ed93c-201">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="ed93c-201">DeleteToEnd</span></span>

<span data-ttu-id="ed93c-202">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-202">Delete to the end of the line.</span></span>

- <span data-ttu-id="ed93c-203">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-203">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="ed93c-204">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-204">DeleteWord</span></span>

<span data-ttu-id="ed93c-205">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-205">Delete the next word.</span></span>

- <span data-ttu-id="ed93c-206">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-206">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="ed93c-207">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-207">ForwardDeleteLine</span></span>

<span data-ttu-id="ed93c-208">Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-208">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="ed93c-209">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-209">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="ed93c-210">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-210">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="ed93c-211">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-211">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="ed93c-212">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="ed93c-212">InsertLineAbove</span></span>

<span data-ttu-id="ed93c-213">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-213">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="ed93c-214">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-214">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="ed93c-215">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-215">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="ed93c-216">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="ed93c-216">InsertLineBelow</span></span>

<span data-ttu-id="ed93c-217">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-217">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="ed93c-218">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="ed93c-219">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-219">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="ed93c-220">InvertCase</span><span class="sxs-lookup"><span data-stu-id="ed93c-220">InvertCase</span></span>

<span data-ttu-id="ed93c-221">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="ed93c-221">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="ed93c-222">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-222">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="ed93c-223">Finalizar</span><span class="sxs-lookup"><span data-stu-id="ed93c-223">KillLine</span></span>

<span data-ttu-id="ed93c-224">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-224">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="ed93c-225">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-225">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="ed93c-226">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-226">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="ed93c-227">KillRegion</span><span class="sxs-lookup"><span data-stu-id="ed93c-227">KillRegion</span></span>

<span data-ttu-id="ed93c-228">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="ed93c-228">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="ed93c-229">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-229">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="ed93c-230">KillWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-230">KillWord</span></span>

<span data-ttu-id="ed93c-231">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-231">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="ed93c-232">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-232">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="ed93c-233">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-233">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="ed93c-234">Cmd `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-234">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="ed93c-235">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-235">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="ed93c-236">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-236">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="ed93c-237">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-237">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="ed93c-238">Colar</span><span class="sxs-lookup"><span data-stu-id="ed93c-238">Paste</span></span>

<span data-ttu-id="ed93c-239">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="ed93c-239">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="ed93c-240">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-240">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="ed93c-241">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-241">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="ed93c-242">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-242">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed93c-243">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ed93c-243">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="ed93c-244">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-244">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="ed93c-245">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="ed93c-245">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="ed93c-246">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-246">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="ed93c-247">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="ed93c-247">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="ed93c-248">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="ed93c-248">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="ed93c-249">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="ed93c-249">PasteAfter</span></span>

<span data-ttu-id="ed93c-250">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-250">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="ed93c-251">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-251">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="ed93c-252">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="ed93c-252">PasteBefore</span></span>

<span data-ttu-id="ed93c-253">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-253">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="ed93c-254">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-254">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="ed93c-255">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="ed93c-255">PrependAndAccept</span></span>

<span data-ttu-id="ed93c-256">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-256">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="ed93c-257">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-257">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="ed93c-258">Refazer</span><span class="sxs-lookup"><span data-stu-id="ed93c-258">Redo</span></span>

<span data-ttu-id="ed93c-259">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-259">Undo an undo.</span></span>

- <span data-ttu-id="ed93c-260">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-260">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="ed93c-261">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-261">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="ed93c-262">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-262">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="ed93c-263">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="ed93c-263">RepeatLastCommand</span></span>

<span data-ttu-id="ed93c-264">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="ed93c-264">Repeat the last text modification.</span></span>

- <span data-ttu-id="ed93c-265">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-265">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="ed93c-266">Reverter</span><span class="sxs-lookup"><span data-stu-id="ed93c-266">RevertLine</span></span>

<span data-ttu-id="ed93c-267">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-267">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="ed93c-268">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-268">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="ed93c-269">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-269">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="ed93c-270">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-270">ShellBackwardKillWord</span></span>

<span data-ttu-id="ed93c-271">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-271">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="ed93c-272">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-272">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="ed93c-273">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-273">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="ed93c-274">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-274">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="ed93c-275">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-275">ShellKillWord</span></span>

<span data-ttu-id="ed93c-276">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-276">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="ed93c-277">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-277">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="ed93c-278">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-278">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="ed93c-279">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-279">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="ed93c-280">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="ed93c-280">SwapCharacters</span></span>

<span data-ttu-id="ed93c-281">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-281">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="ed93c-282">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-282">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="ed93c-283">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-283">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="ed93c-284">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-284">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="ed93c-285">Desfazer</span><span class="sxs-lookup"><span data-stu-id="ed93c-285">Undo</span></span>

<span data-ttu-id="ed93c-286">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-286">Undo a previous edit.</span></span>

- <span data-ttu-id="ed93c-287">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-287">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="ed93c-288">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-288">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="ed93c-289">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-289">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="ed93c-290">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-290">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="ed93c-291">UndoAll</span><span class="sxs-lookup"><span data-stu-id="ed93c-291">UndoAll</span></span>

<span data-ttu-id="ed93c-292">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-292">Undo all previous edits for line.</span></span>

- <span data-ttu-id="ed93c-293">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-293">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="ed93c-294">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="ed93c-294">UnixWordRubout</span></span>

<span data-ttu-id="ed93c-295">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-295">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="ed93c-296">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-296">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="ed93c-297">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-297">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="ed93c-298">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-298">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="ed93c-299">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-299">ValidateAndAcceptLine</span></span>

<span data-ttu-id="ed93c-300">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-300">Attempt to execute the current input.</span></span> <span data-ttu-id="ed93c-301">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-301">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="ed93c-302">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-302">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="ed93c-303">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-303">ViAcceptLine</span></span>

<span data-ttu-id="ed93c-304">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="ed93c-304">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="ed93c-305">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-305">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="ed93c-306">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="ed93c-306">ViAcceptLineOrExit</span></span>

<span data-ttu-id="ed93c-307">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-307">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="ed93c-308">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-308">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="ed93c-309">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-309">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="ed93c-310">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-310">ViAppendLine</span></span>

<span data-ttu-id="ed93c-311">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-311">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="ed93c-312">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-312">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="ed93c-313">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-313">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="ed93c-314">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-314">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="ed93c-315">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-315">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="ed93c-316">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-316">ViBackwardGlob</span></span>

<span data-ttu-id="ed93c-317">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="ed93c-317">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="ed93c-318">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-318">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="ed93c-319">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="ed93c-319">ViDeleteBrace</span></span>

<span data-ttu-id="ed93c-320">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="ed93c-320">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="ed93c-321">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-321">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="ed93c-322">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-322">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="ed93c-323">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-323">Delete to the end of the word.</span></span>

- <span data-ttu-id="ed93c-324">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-324">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="ed93c-325">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-325">ViDeleteGlob</span></span>

<span data-ttu-id="ed93c-326">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="ed93c-326">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="ed93c-327">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-327">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="ed93c-328">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-328">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="ed93c-329">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-329">Deletes until given character.</span></span>

- <span data-ttu-id="ed93c-330">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-330">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="ed93c-331">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-331">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="ed93c-332">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-332">Deletes until given character.</span></span>

- <span data-ttu-id="ed93c-333">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-333">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="ed93c-334">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-334">ViDeleteToChar</span></span>

<span data-ttu-id="ed93c-335">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-335">Deletes until given character.</span></span>

- <span data-ttu-id="ed93c-336">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-336">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="ed93c-337">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-337">ViDeleteToCharBackward</span></span>

<span data-ttu-id="ed93c-338">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-338">Deletes backwards until given character.</span></span>

- <span data-ttu-id="ed93c-339">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-339">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="ed93c-340">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="ed93c-340">ViInsertAtBegining</span></span>

<span data-ttu-id="ed93c-341">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-341">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="ed93c-342">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-342">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="ed93c-343">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="ed93c-343">ViInsertAtEnd</span></span>

<span data-ttu-id="ed93c-344">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-344">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="ed93c-345">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-345">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="ed93c-346">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-346">ViInsertLine</span></span>

<span data-ttu-id="ed93c-347">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-347">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="ed93c-348">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-348">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="ed93c-349">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="ed93c-349">ViInsertWithAppend</span></span>

<span data-ttu-id="ed93c-350">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-350">Append from the current line position.</span></span>

- <span data-ttu-id="ed93c-351">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-351">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="ed93c-352">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="ed93c-352">ViInsertWithDelete</span></span>

<span data-ttu-id="ed93c-353">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="ed93c-353">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="ed93c-354">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-354">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="ed93c-355">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="ed93c-355">ViJoinLines</span></span>

<span data-ttu-id="ed93c-356">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-356">Joins the current line and the next line.</span></span>

- <span data-ttu-id="ed93c-357">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-357">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="ed93c-358">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-358">ViReplaceLine</span></span>

<span data-ttu-id="ed93c-359">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="ed93c-359">Erase the entire command line.</span></span>

- <span data-ttu-id="ed93c-360">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-360">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="ed93c-361">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-361">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="ed93c-362">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-362">Replaces until given character.</span></span>

- <span data-ttu-id="ed93c-363">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-363">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="ed93c-364">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-364">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="ed93c-365">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-365">Replaces until given character.</span></span>

- <span data-ttu-id="ed93c-366">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-366">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="ed93c-367">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-367">ViReplaceToChar</span></span>

<span data-ttu-id="ed93c-368">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-368">Deletes until given character.</span></span>

- <span data-ttu-id="ed93c-369">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-369">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="ed93c-370">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-370">ViReplaceToCharBackward</span></span>

<span data-ttu-id="ed93c-371">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="ed93c-371">Replaces until given character.</span></span>

- <span data-ttu-id="ed93c-372">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-372">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="ed93c-373">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-373">ViYankBeginningOfLine</span></span>

<span data-ttu-id="ed93c-374">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-374">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="ed93c-375">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-375">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="ed93c-376">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-376">ViYankEndOfGlob</span></span>

<span data-ttu-id="ed93c-377">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="ed93c-377">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="ed93c-378">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-378">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="ed93c-379">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-379">ViYankEndOfWord</span></span>

<span data-ttu-id="ed93c-380">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="ed93c-380">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="ed93c-381">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-381">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="ed93c-382">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="ed93c-382">ViYankLeft</span></span>

<span data-ttu-id="ed93c-383">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-383">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="ed93c-384">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-384">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="ed93c-385">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-385">ViYankLine</span></span>

<span data-ttu-id="ed93c-386">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-386">Yank the entire buffer.</span></span>

- <span data-ttu-id="ed93c-387">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-387">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="ed93c-388">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-388">ViYankNextGlob</span></span>

<span data-ttu-id="ed93c-389">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="ed93c-389">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="ed93c-390">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-390">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="ed93c-391">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-391">ViYankNextWord</span></span>

<span data-ttu-id="ed93c-392">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-392">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="ed93c-393">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-393">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="ed93c-394">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="ed93c-394">ViYankPercent</span></span>

<span data-ttu-id="ed93c-395">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="ed93c-395">Yank to/from matching brace.</span></span>

- <span data-ttu-id="ed93c-396">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-396">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="ed93c-397">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-397">ViYankPreviousGlob</span></span>

<span data-ttu-id="ed93c-398">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-398">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="ed93c-399">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-399">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="ed93c-400">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-400">ViYankPreviousWord</span></span>

<span data-ttu-id="ed93c-401">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-401">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="ed93c-402">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-402">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="ed93c-403">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="ed93c-403">ViYankRight</span></span>

<span data-ttu-id="ed93c-404">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-404">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="ed93c-405">Modo de comando vi: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-405">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="ed93c-406">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-406">ViYankToEndOfLine</span></span>

<span data-ttu-id="ed93c-407">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-407">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="ed93c-408">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-408">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="ed93c-409">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-409">ViYankToFirstChar</span></span>

<span data-ttu-id="ed93c-410">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-410">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="ed93c-411">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-411">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="ed93c-412">Yank</span><span class="sxs-lookup"><span data-stu-id="ed93c-412">Yank</span></span>

<span data-ttu-id="ed93c-413">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-413">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="ed93c-414">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-414">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="ed93c-415">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="ed93c-415">YankLastArg</span></span>

<span data-ttu-id="ed93c-416">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-416">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="ed93c-417">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="ed93c-417">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="ed93c-418">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="ed93c-418">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="ed93c-419">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-419">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="ed93c-420">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-420">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="ed93c-421">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="ed93c-421">YankNthArg</span></span>

<span data-ttu-id="ed93c-422">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-422">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="ed93c-423">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="ed93c-423">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="ed93c-424">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-424">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="ed93c-425">YankPop</span><span class="sxs-lookup"><span data-stu-id="ed93c-425">YankPop</span></span>

<span data-ttu-id="ed93c-426">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-426">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="ed93c-427">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-427">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="ed93c-428">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="ed93c-428">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="ed93c-429">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-429">BackwardChar</span></span>

<span data-ttu-id="ed93c-430">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="ed93c-430">Move the cursor one character to the left.</span></span> <span data-ttu-id="ed93c-431">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="ed93c-431">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="ed93c-432">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-432">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="ed93c-433">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-433">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="ed93c-434">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-434">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="ed93c-435">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-435">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="ed93c-436">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-436">BackwardWord</span></span>

<span data-ttu-id="ed93c-437">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-437">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="ed93c-438">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed93c-438">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="ed93c-439">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-439">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="ed93c-440">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-440">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="ed93c-441">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-441">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="ed93c-442">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-442">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="ed93c-443">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-443">BeginningOfLine</span></span>

<span data-ttu-id="ed93c-444">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-444">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="ed93c-445">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-445">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="ed93c-446">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-446">Cmd: `<Home>`</span></span>
- <span data-ttu-id="ed93c-447">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-447">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="ed93c-448">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-448">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="ed93c-449">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-449">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="ed93c-450">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-450">EndOfLine</span></span>

<span data-ttu-id="ed93c-451">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-451">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="ed93c-452">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-452">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="ed93c-453">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-453">Cmd: `<End>`</span></span>
- <span data-ttu-id="ed93c-454">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-454">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="ed93c-455">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-455">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="ed93c-456">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-456">ForwardChar</span></span>

<span data-ttu-id="ed93c-457">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="ed93c-457">Move the cursor one character to the right.</span></span> <span data-ttu-id="ed93c-458">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="ed93c-458">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="ed93c-459">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-459">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="ed93c-460">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-460">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="ed93c-461">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-461">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="ed93c-462">Modo de comando vi: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-462">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="ed93c-463">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-463">ForwardWord</span></span>

<span data-ttu-id="ed93c-464">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-464">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="ed93c-465">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed93c-465">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="ed93c-466">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-466">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="ed93c-467">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="ed93c-467">GotoBrace</span></span>

<span data-ttu-id="ed93c-468">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="ed93c-468">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="ed93c-469">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-469">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="ed93c-470">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-470">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="ed93c-471">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-471">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="ed93c-472">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="ed93c-472">GotoColumn</span></span>

<span data-ttu-id="ed93c-473">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="ed93c-473">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="ed93c-474">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-474">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="ed93c-475">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-475">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="ed93c-476">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-476">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="ed93c-477">Modo de comando vi: `<^>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-477">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="ed93c-478">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-478">MoveToEndOfLine</span></span>

<span data-ttu-id="ed93c-479">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-479">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="ed93c-480">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-480">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="ed93c-481">Próxima</span><span class="sxs-lookup"><span data-stu-id="ed93c-481">NextLine</span></span>

<span data-ttu-id="ed93c-482">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-482">Move the cursor to the next line.</span></span>

- <span data-ttu-id="ed93c-483">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-483">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="ed93c-484">NextWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-484">NextWord</span></span>

<span data-ttu-id="ed93c-485">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-485">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="ed93c-486">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed93c-486">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="ed93c-487">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-487">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="ed93c-488">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-488">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="ed93c-489">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-489">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="ed93c-490">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="ed93c-490">NextWordEnd</span></span>

<span data-ttu-id="ed93c-491">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-491">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="ed93c-492">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed93c-492">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="ed93c-493">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-493">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="ed93c-494">Anterior</span><span class="sxs-lookup"><span data-stu-id="ed93c-494">PreviousLine</span></span>

<span data-ttu-id="ed93c-495">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-495">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="ed93c-496">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-496">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="ed93c-497">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-497">ShellBackwardWord</span></span>

<span data-ttu-id="ed93c-498">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-498">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="ed93c-499">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-499">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="ed93c-500">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-500">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="ed93c-501">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-501">ShellForwardWord</span></span>

<span data-ttu-id="ed93c-502">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-502">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="ed93c-503">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="ed93c-504">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-504">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="ed93c-505">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-505">ShellNextWord</span></span>

<span data-ttu-id="ed93c-506">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-506">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="ed93c-507">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="ed93c-508">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-508">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="ed93c-509">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-509">ViBackwardWord</span></span>

<span data-ttu-id="ed93c-510">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-510">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="ed93c-511">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed93c-511">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="ed93c-512">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-512">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="ed93c-513">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-513">ViEndOfGlob</span></span>

<span data-ttu-id="ed93c-514">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="ed93c-514">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="ed93c-515">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-515">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="ed93c-516">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-516">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="ed93c-517">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-517">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="ed93c-518">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-518">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="ed93c-519">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="ed93c-519">ViGotoBrace</span></span>

<span data-ttu-id="ed93c-520">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="ed93c-520">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="ed93c-521">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-521">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="ed93c-522">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="ed93c-522">ViNextGlob</span></span>

<span data-ttu-id="ed93c-523">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-523">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="ed93c-524">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-524">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="ed93c-525">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-525">ViNextWord</span></span>

<span data-ttu-id="ed93c-526">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-526">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="ed93c-527">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed93c-527">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="ed93c-528">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-528">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="ed93c-529">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="ed93c-529">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="ed93c-530">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="ed93c-530">BeginningOfHistory</span></span>

<span data-ttu-id="ed93c-531">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="ed93c-531">Move to the first item in the history.</span></span>

- <span data-ttu-id="ed93c-532">Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="ed93c-532">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="ed93c-533">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="ed93c-533">ClearHistory</span></span>

<span data-ttu-id="ed93c-534">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ed93c-534">Clears history in PSReadLine.</span></span> <span data-ttu-id="ed93c-535">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-535">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="ed93c-536">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-536">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="ed93c-537">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="ed93c-537">EndOfHistory</span></span>

<span data-ttu-id="ed93c-538">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="ed93c-538">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="ed93c-539">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-539">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="ed93c-540">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="ed93c-540">ForwardSearchHistory</span></span>

<span data-ttu-id="ed93c-541">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="ed93c-541">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="ed93c-542">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-542">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="ed93c-543">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-543">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="ed93c-544">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-544">HistorySearchBackward</span></span>

<span data-ttu-id="ed93c-545">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-545">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="ed93c-546">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-546">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="ed93c-547">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="ed93c-547">HistorySearchForward</span></span>

<span data-ttu-id="ed93c-548">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-548">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="ed93c-549">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-549">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="ed93c-550">NextHistory</span><span class="sxs-lookup"><span data-stu-id="ed93c-550">NextHistory</span></span>

<span data-ttu-id="ed93c-551">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ed93c-551">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="ed93c-552">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-552">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="ed93c-553">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-553">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="ed93c-554">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-554">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="ed93c-555">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-555">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="ed93c-556">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="ed93c-556">PreviousHistory</span></span>

<span data-ttu-id="ed93c-557">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ed93c-557">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="ed93c-558">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-558">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="ed93c-559">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-559">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="ed93c-560">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-560">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="ed93c-561">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="ed93c-561">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="ed93c-562">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="ed93c-562">ReverseSearchHistory</span></span>

<span data-ttu-id="ed93c-563">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="ed93c-563">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="ed93c-564">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-564">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="ed93c-565">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-565">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="ed93c-566">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-566">ViSearchHistoryBackward</span></span>

<span data-ttu-id="ed93c-567">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="ed93c-567">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="ed93c-568">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-568">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="ed93c-569">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-569">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="ed93c-570">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="ed93c-570">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="ed93c-571">Concluir</span><span class="sxs-lookup"><span data-stu-id="ed93c-571">Complete</span></span>

<span data-ttu-id="ed93c-572">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-572">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="ed93c-573">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="ed93c-573">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="ed93c-574">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="ed93c-574">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="ed93c-575">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-575">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="ed93c-576">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="ed93c-576">MenuComplete</span></span>

<span data-ttu-id="ed93c-577">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-577">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="ed93c-578">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="ed93c-578">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="ed93c-579">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="ed93c-579">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="ed93c-580">Cmd `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-580">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="ed93c-581">Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-581">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="ed93c-582">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="ed93c-582">PossibleCompletions</span></span>

<span data-ttu-id="ed93c-583">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="ed93c-583">Display the list of possible completions.</span></span>

- <span data-ttu-id="ed93c-584">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-584">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="ed93c-585">Modo de inserção de vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-585">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="ed93c-586">Modo de comando vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-586">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="ed93c-587">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="ed93c-587">TabCompleteNext</span></span>

<span data-ttu-id="ed93c-588">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="ed93c-588">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="ed93c-589">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-589">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="ed93c-590">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-590">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="ed93c-591">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="ed93c-591">TabCompletePrevious</span></span>

<span data-ttu-id="ed93c-592">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-592">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="ed93c-593">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-593">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="ed93c-594">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-594">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="ed93c-595">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="ed93c-595">ViTabCompleteNext</span></span>

<span data-ttu-id="ed93c-596">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="ed93c-596">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="ed93c-597">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-597">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="ed93c-598">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="ed93c-598">ViTabCompletePrevious</span></span>

<span data-ttu-id="ed93c-599">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="ed93c-599">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="ed93c-600">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-600">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="ed93c-601">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="ed93c-601">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="ed93c-602">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="ed93c-602">CaptureScreen</span></span>

<span data-ttu-id="ed93c-603">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="ed93c-603">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="ed93c-604">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-604">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="ed93c-605">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="ed93c-605">ClearScreen</span></span>

<span data-ttu-id="ed93c-606">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="ed93c-606">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="ed93c-607">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-607">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="ed93c-608">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-608">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="ed93c-609">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-609">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="ed93c-610">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-610">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="ed93c-611">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="ed93c-611">DigitArgument</span></span>

<span data-ttu-id="ed93c-612">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="ed93c-612">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="ed93c-613">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="ed93c-613">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="ed93c-614">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="ed93c-614">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="ed93c-615">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-615">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="ed93c-616">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="ed93c-616">InvokePrompt</span></span>

<span data-ttu-id="ed93c-617">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="ed93c-617">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="ed93c-618">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="ed93c-618">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="ed93c-619">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-619">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="ed93c-620">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="ed93c-620">ScrollDisplayDown</span></span>

<span data-ttu-id="ed93c-621">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="ed93c-621">Scroll the display down one screen.</span></span>

- <span data-ttu-id="ed93c-622">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-622">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="ed93c-623">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-623">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="ed93c-624">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-624">ScrollDisplayDownLine</span></span>

<span data-ttu-id="ed93c-625">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="ed93c-625">Scroll the display down one line.</span></span>

- <span data-ttu-id="ed93c-626">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-626">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="ed93c-627">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-627">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="ed93c-628">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="ed93c-628">ScrollDisplayToCursor</span></span>

<span data-ttu-id="ed93c-629">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-629">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="ed93c-630">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-630">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="ed93c-631">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="ed93c-631">ScrollDisplayTop</span></span>

<span data-ttu-id="ed93c-632">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-632">Scroll the display to the top.</span></span>

- <span data-ttu-id="ed93c-633">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-633">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="ed93c-634">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="ed93c-634">ScrollDisplayUp</span></span>

<span data-ttu-id="ed93c-635">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="ed93c-635">Scroll the display up one screen.</span></span>

- <span data-ttu-id="ed93c-636">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-636">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="ed93c-637">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-637">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="ed93c-638">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-638">ScrollDisplayUpLine</span></span>

<span data-ttu-id="ed93c-639">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="ed93c-639">Scroll the display up one line.</span></span>

- <span data-ttu-id="ed93c-640">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-640">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="ed93c-641">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-641">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="ed93c-642">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="ed93c-642">SelfInsert</span></span>

<span data-ttu-id="ed93c-643">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="ed93c-643">Insert the key.</span></span>

- <span data-ttu-id="ed93c-644">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-644">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="ed93c-645">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="ed93c-645">ShowKeyBindings</span></span>

<span data-ttu-id="ed93c-646">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="ed93c-646">Show all bound keys.</span></span>

- <span data-ttu-id="ed93c-647">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-647">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="ed93c-648">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-648">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="ed93c-649">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-649">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="ed93c-650">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="ed93c-650">ViCommandMode</span></span>

<span data-ttu-id="ed93c-651">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="ed93c-651">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="ed93c-652">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-652">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="ed93c-653">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="ed93c-653">ViDigitArgumentInChord</span></span>

<span data-ttu-id="ed93c-654">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="ed93c-654">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="ed93c-655">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-655">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="ed93c-656">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="ed93c-656">ViEditVisually</span></span>

<span data-ttu-id="ed93c-657">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="ed93c-657">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="ed93c-658">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-658">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="ed93c-659">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-659">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="ed93c-660">ViExit</span><span class="sxs-lookup"><span data-stu-id="ed93c-660">ViExit</span></span>

<span data-ttu-id="ed93c-661">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-661">Exits the shell.</span></span>

- <span data-ttu-id="ed93c-662">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-662">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="ed93c-663">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="ed93c-663">ViInsertMode</span></span>

<span data-ttu-id="ed93c-664">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="ed93c-664">Switch to Insert mode.</span></span>

- <span data-ttu-id="ed93c-665">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-665">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="ed93c-666">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="ed93c-666">WhatIsKey</span></span>

<span data-ttu-id="ed93c-667">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-667">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="ed93c-668">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-668">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="ed93c-669">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-669">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="ed93c-670">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="ed93c-670">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="ed93c-671">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="ed93c-671">ExchangePointAndMark</span></span>

<span data-ttu-id="ed93c-672">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-672">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="ed93c-673">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-673">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="ed93c-674">SelectAll</span><span class="sxs-lookup"><span data-stu-id="ed93c-674">SelectAll</span></span>

<span data-ttu-id="ed93c-675">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="ed93c-675">Select the entire line.</span></span>

- <span data-ttu-id="ed93c-676">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-676">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="ed93c-677">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-677">SelectBackwardChar</span></span>

<span data-ttu-id="ed93c-678">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-678">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="ed93c-679">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-679">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="ed93c-680">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-680">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="ed93c-681">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-681">SelectBackwardsLine</span></span>

<span data-ttu-id="ed93c-682">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-682">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="ed93c-683">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-683">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="ed93c-684">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-684">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="ed93c-685">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-685">SelectBackwardWord</span></span>

<span data-ttu-id="ed93c-686">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="ed93c-686">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="ed93c-687">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-687">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="ed93c-688">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-688">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="ed93c-689">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-689">SelectForwardChar</span></span>

<span data-ttu-id="ed93c-690">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-690">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="ed93c-691">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-691">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="ed93c-692">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-692">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="ed93c-693">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-693">SelectForwardWord</span></span>

<span data-ttu-id="ed93c-694">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="ed93c-694">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="ed93c-695">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-695">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="ed93c-696">Seleção</span><span class="sxs-lookup"><span data-stu-id="ed93c-696">SelectLine</span></span>

<span data-ttu-id="ed93c-697">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="ed93c-697">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="ed93c-698">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-698">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="ed93c-699">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-699">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="ed93c-700">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-700">SelectNextWord</span></span>

<span data-ttu-id="ed93c-701">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="ed93c-701">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="ed93c-702">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-702">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="ed93c-703">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-703">SelectShellBackwardWord</span></span>

<span data-ttu-id="ed93c-704">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="ed93c-704">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="ed93c-705">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-705">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="ed93c-706">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-706">SelectShellForwardWord</span></span>

<span data-ttu-id="ed93c-707">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="ed93c-707">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="ed93c-708">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-708">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="ed93c-709">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="ed93c-709">SelectShellNextWord</span></span>

<span data-ttu-id="ed93c-710">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="ed93c-710">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="ed93c-711">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-711">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="ed93c-712">Definir marca</span><span class="sxs-lookup"><span data-stu-id="ed93c-712">SetMark</span></span>

<span data-ttu-id="ed93c-713">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="ed93c-713">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="ed93c-714">Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="ed93c-714">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="ed93c-715">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="ed93c-715">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="ed93c-716">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="ed93c-716">CharacterSearch</span></span>

<span data-ttu-id="ed93c-717">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-717">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="ed93c-718">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="ed93c-718">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="ed93c-719">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-719">Cmd: `<F3>`</span></span>
- <span data-ttu-id="ed93c-720">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-720">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="ed93c-721">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-721">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="ed93c-722">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-722">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="ed93c-723">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-723">CharacterSearchBackward</span></span>

<span data-ttu-id="ed93c-724">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-724">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="ed93c-725">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="ed93c-725">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="ed93c-726">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-726">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="ed93c-727">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-727">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="ed93c-728">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-728">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="ed93c-729">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-729">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="ed93c-730">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="ed93c-730">RepeatLastCharSearch</span></span>

<span data-ttu-id="ed93c-731">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-731">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="ed93c-732">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-732">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="ed93c-733">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="ed93c-733">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="ed93c-734">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="ed93c-734">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="ed93c-735">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-735">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="ed93c-736">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="ed93c-736">RepeatSearch</span></span>

<span data-ttu-id="ed93c-737">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="ed93c-737">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="ed93c-738">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-738">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="ed93c-739">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-739">RepeatSearchBackward</span></span>

<span data-ttu-id="ed93c-740">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="ed93c-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="ed93c-741">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-741">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="ed93c-742">SearchChar</span><span class="sxs-lookup"><span data-stu-id="ed93c-742">SearchChar</span></span>

<span data-ttu-id="ed93c-743">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-743">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="ed93c-744">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="ed93c-744">This is for 't' functionality.</span></span>

- <span data-ttu-id="ed93c-745">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-745">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="ed93c-746">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="ed93c-746">SearchCharBackward</span></span>

<span data-ttu-id="ed93c-747">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-747">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="ed93c-748">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="ed93c-748">This is for 'T' functionality.</span></span>

- <span data-ttu-id="ed93c-749">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-749">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="ed93c-750">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="ed93c-750">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="ed93c-751">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="ed93c-752">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="ed93c-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="ed93c-753">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-753">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="ed93c-754">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="ed93c-754">SearchCharWithBackoff</span></span>

<span data-ttu-id="ed93c-755">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="ed93c-755">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="ed93c-756">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="ed93c-756">This is for 't' functionality.</span></span>

- <span data-ttu-id="ed93c-757">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-757">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="ed93c-758">SearchForward</span><span class="sxs-lookup"><span data-stu-id="ed93c-758">SearchForward</span></span>

<span data-ttu-id="ed93c-759">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="ed93c-759">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="ed93c-760">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-760">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="ed93c-761">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="ed93c-761">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="ed93c-762">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="ed93c-762">Custom Key Bindings</span></span>

<span data-ttu-id="ed93c-763">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="ed93c-763">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="ed93c-764">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="ed93c-764">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="ed93c-765">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="ed93c-765">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="ed93c-766">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="ed93c-766">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="ed93c-767">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="ed93c-767">Some useful examples include</span></span>

- <span data-ttu-id="ed93c-768">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="ed93c-768">edit the command line</span></span>
- <span data-ttu-id="ed93c-769">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="ed93c-769">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="ed93c-770">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="ed93c-770">change directories without changing the command line</span></span>

<span data-ttu-id="ed93c-771">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="ed93c-771">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="ed93c-772">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-772">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="ed93c-773">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="ed93c-773">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="ed93c-774">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="ed93c-774">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="ed93c-775">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="ed93c-775">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="ed93c-776">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="ed93c-776">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="ed93c-777">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="ed93c-777">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="ed93c-778">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed93c-778">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="ed93c-779">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="ed93c-779">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="ed93c-780">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ed93c-780">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="ed93c-781">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="ed93c-781">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="ed93c-782">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="ed93c-782">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="ed93c-783">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="ed93c-783">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="ed93c-784">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="ed93c-784">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="ed93c-785">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ed93c-785">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="ed93c-786">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed93c-786">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="ed93c-787">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="ed93c-787">Clear the kill-ring.</span></span>  <span data-ttu-id="ed93c-788">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="ed93c-788">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="ed93c-789">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="ed93c-789">Delete length characters from start.</span></span>  <span data-ttu-id="ed93c-790">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-790">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="ed93c-791">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="ed93c-791">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="ed93c-792">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-792">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="ed93c-793">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="ed93c-793">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="ed93c-794">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="ed93c-794">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="ed93c-795">Essa função é usada pelo Get-PSReadLineKeyHandler e provavelmente não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-795">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="ed93c-796">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-796">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="ed93c-797">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="ed93c-797">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="ed93c-798">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="ed93c-798">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="ed93c-799">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="ed93c-799">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="ed93c-800">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-800">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="ed93c-801">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="ed93c-801">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="ed93c-802">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-802">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="ed93c-803">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed93c-803">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="ed93c-804">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="ed93c-804">Replace some of the input.</span></span> <span data-ttu-id="ed93c-805">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-805">This operation supports undo/redo.</span></span> <span data-ttu-id="ed93c-806">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-806">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="ed93c-807">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="ed93c-807">Move the cursor to the given offset.</span></span> <span data-ttu-id="ed93c-808">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="ed93c-808">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="ed93c-809">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="ed93c-809">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="ed93c-810">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="ed93c-810">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="ed93c-811">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="ed93c-811">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="ed93c-812">OBSERVAÇÃO</span><span class="sxs-lookup"><span data-stu-id="ed93c-812">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="ed93c-813">COMPATIBILIDADE DO POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="ed93c-813">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="ed93c-814">O PSReadLine requer o PowerShell 3,0 ou mais recente e o host do console.</span><span class="sxs-lookup"><span data-stu-id="ed93c-814">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="ed93c-815">Ele não funciona no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed93c-815">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="ed93c-816">Ele funciona no console do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ed93c-816">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="ed93c-817">HISTÓRICO DE COMANDOS</span><span class="sxs-lookup"><span data-stu-id="ed93c-817">COMMAND HISTORY</span></span>

<span data-ttu-id="ed93c-818">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="ed93c-818">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="ed93c-819">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="ed93c-819">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="ed93c-820">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="ed93c-820">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="ed93c-821">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="ed93c-821">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="ed93c-822">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="ed93c-822">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="ed93c-823">Comentários & CONTRIBUIndo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="ed93c-823">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="ed93c-824">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="ed93c-824">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="ed93c-825">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="ed93c-825">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed93c-826">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="ed93c-826">SEE ALSO</span></span>

<span data-ttu-id="ed93c-827">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="ed93c-827">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
