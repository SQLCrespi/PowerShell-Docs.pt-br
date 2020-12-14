---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: 25fc3a9a814728057b1ebc7e721d3fba84ae72c2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692302"
---
# <a name="psreadline"></a><span data-ttu-id="eb84b-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="eb84b-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="eb84b-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="eb84b-106">Short Description</span></span>

<span data-ttu-id="eb84b-107">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="eb84b-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="eb84b-108">Long Description</span></span>

<span data-ttu-id="eb84b-109">O PSReadLine 2,0 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="eb84b-110">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="eb84b-110">It provides:</span></span>

- <span data-ttu-id="eb84b-111">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="eb84b-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="eb84b-112">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="eb84b-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="eb84b-113">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="eb84b-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="eb84b-114">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="eb84b-114">Customizable key bindings</span></span>
- <span data-ttu-id="eb84b-115">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="eb84b-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="eb84b-116">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="eb84b-116">Many configuration options</span></span>
- <span data-ttu-id="eb84b-117">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="eb84b-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="eb84b-118">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="eb84b-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="eb84b-119">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="eb84b-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="eb84b-120">O PSReadLine requer o PowerShell 3,0 ou mais recente e o host do console.</span><span class="sxs-lookup"><span data-stu-id="eb84b-120">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="eb84b-121">Ele não funciona no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-121">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="eb84b-122">Ele funciona no console do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="eb84b-122">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="eb84b-123">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]**.</span><span class="sxs-lookup"><span data-stu-id="eb84b-123">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="eb84b-124">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="eb84b-124">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="eb84b-125">Anular</span><span class="sxs-lookup"><span data-stu-id="eb84b-125">Abort</span></span>

<span data-ttu-id="eb84b-126">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="eb84b-126">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="eb84b-127">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-127">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="eb84b-128">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="eb84b-128">AcceptAndGetNext</span></span>

<span data-ttu-id="eb84b-129">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-129">Attempt to execute the current input.</span></span> <span data-ttu-id="eb84b-130">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-130">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="eb84b-131">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-131">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="eb84b-132">Aceitar</span><span class="sxs-lookup"><span data-stu-id="eb84b-132">AcceptLine</span></span>

<span data-ttu-id="eb84b-133">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-133">Attempt to execute the current input.</span></span> <span data-ttu-id="eb84b-134">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-134">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="eb84b-135">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-135">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="eb84b-136">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-136">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="eb84b-137">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-137">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="eb84b-138">AddLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-138">AddLine</span></span>

<span data-ttu-id="eb84b-139">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-139">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="eb84b-140">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="eb84b-140">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="eb84b-141">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-141">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="eb84b-142">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-142">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="eb84b-143">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-143">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="eb84b-144">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-144">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="eb84b-145">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-145">BackwardDeleteChar</span></span>

<span data-ttu-id="eb84b-146">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-146">Delete the character before the cursor.</span></span>

- <span data-ttu-id="eb84b-147">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-147">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="eb84b-148">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-148">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="eb84b-149">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-149">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="eb84b-150">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-150">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="eb84b-151">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-151">BackwardDeleteLine</span></span>

<span data-ttu-id="eb84b-152">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-152">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="eb84b-153">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-153">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="eb84b-154">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-154">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="eb84b-155">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-155">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="eb84b-156">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-156">BackwardDeleteWord</span></span>

<span data-ttu-id="eb84b-157">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-157">Deletes the previous word.</span></span>

- <span data-ttu-id="eb84b-158">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-158">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="eb84b-159">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-159">BackwardKillLine</span></span>

<span data-ttu-id="eb84b-160">Limpe a entrada do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-160">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="eb84b-161">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-161">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb84b-162">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-162">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="eb84b-163">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-163">BackwardKillWord</span></span>

<span data-ttu-id="eb84b-164">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-164">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="eb84b-165">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-165">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="eb84b-166">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-166">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb84b-167">Cmd `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-167">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="eb84b-168">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-168">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="eb84b-169">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-169">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="eb84b-170">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-170">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="eb84b-171">Cancelar</span><span class="sxs-lookup"><span data-stu-id="eb84b-171">CancelLine</span></span>

<span data-ttu-id="eb84b-172">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="eb84b-172">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="eb84b-173">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-173">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="eb84b-174">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-174">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="eb84b-175">Copiar</span><span class="sxs-lookup"><span data-stu-id="eb84b-175">Copy</span></span>

<span data-ttu-id="eb84b-176">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="eb84b-176">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="eb84b-177">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="eb84b-177">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="eb84b-178">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-178">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="eb84b-179">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-179">CopyOrCancelLine</span></span>

<span data-ttu-id="eb84b-180">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-180">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="eb84b-181">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-181">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="eb84b-182">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-182">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="eb84b-183">Recortar</span><span class="sxs-lookup"><span data-stu-id="eb84b-183">Cut</span></span>

<span data-ttu-id="eb84b-184">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="eb84b-184">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="eb84b-185">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-185">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="eb84b-186">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-186">DeleteChar</span></span>

<span data-ttu-id="eb84b-187">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-187">Delete the character under the cursor.</span></span>

- <span data-ttu-id="eb84b-188">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-188">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="eb84b-189">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-189">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="eb84b-190">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-190">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="eb84b-191">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-191">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="eb84b-192">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="eb84b-192">DeleteCharOrExit</span></span>

<span data-ttu-id="eb84b-193">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="eb84b-193">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="eb84b-194">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-194">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="eb84b-195">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-195">DeleteEndOfWord</span></span>

<span data-ttu-id="eb84b-196">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-196">Delete to the end of the word.</span></span>

- <span data-ttu-id="eb84b-197">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-197">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="eb84b-198">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-198">DeleteLine</span></span>

<span data-ttu-id="eb84b-199">Exclui a linha atual, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-199">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="eb84b-200">Modo de comando vi: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-200">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="eb84b-201">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-201">DeleteLineToFirstChar</span></span>

<span data-ttu-id="eb84b-202">Exclui o texto do cursor para o primeiro caractere que não seja em branco da linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-202">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="eb84b-203">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-203">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="eb84b-204">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="eb84b-204">DeleteToEnd</span></span>

<span data-ttu-id="eb84b-205">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-205">Delete to the end of the line.</span></span>

- <span data-ttu-id="eb84b-206">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-206">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="eb84b-207">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-207">DeleteWord</span></span>

<span data-ttu-id="eb84b-208">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-208">Delete the next word.</span></span>

- <span data-ttu-id="eb84b-209">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-209">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="eb84b-210">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-210">ForwardDeleteLine</span></span>

<span data-ttu-id="eb84b-211">Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-211">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="eb84b-212">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-212">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="eb84b-213">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-213">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="eb84b-214">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-214">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="eb84b-215">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="eb84b-215">InsertLineAbove</span></span>

<span data-ttu-id="eb84b-216">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-216">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="eb84b-217">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-217">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="eb84b-218">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-218">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="eb84b-219">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="eb84b-219">InsertLineBelow</span></span>

<span data-ttu-id="eb84b-220">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-220">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="eb84b-221">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-221">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="eb84b-222">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-222">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="eb84b-223">InvertCase</span><span class="sxs-lookup"><span data-stu-id="eb84b-223">InvertCase</span></span>

<span data-ttu-id="eb84b-224">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="eb84b-224">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="eb84b-225">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-225">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="eb84b-226">Finalizar</span><span class="sxs-lookup"><span data-stu-id="eb84b-226">KillLine</span></span>

<span data-ttu-id="eb84b-227">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-227">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="eb84b-228">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-228">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb84b-229">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-229">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="eb84b-230">KillRegion</span><span class="sxs-lookup"><span data-stu-id="eb84b-230">KillRegion</span></span>

<span data-ttu-id="eb84b-231">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="eb84b-231">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="eb84b-232">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-232">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="eb84b-233">KillWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-233">KillWord</span></span>

<span data-ttu-id="eb84b-234">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-234">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="eb84b-235">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-235">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="eb84b-236">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-236">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb84b-237">Cmd `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-237">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="eb84b-238">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-238">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="eb84b-239">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-239">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="eb84b-240">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-240">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="eb84b-241">Colar</span><span class="sxs-lookup"><span data-stu-id="eb84b-241">Paste</span></span>

<span data-ttu-id="eb84b-242">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="eb84b-242">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="eb84b-243">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-243">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="eb84b-244">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-244">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="eb84b-245">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-245">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb84b-246">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="eb84b-246">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="eb84b-247">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-247">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="eb84b-248">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="eb84b-248">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="eb84b-249">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-249">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="eb84b-250">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="eb84b-250">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="eb84b-251">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="eb84b-251">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="eb84b-252">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="eb84b-252">PasteAfter</span></span>

<span data-ttu-id="eb84b-253">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-253">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="eb84b-254">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-254">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="eb84b-255">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="eb84b-255">PasteBefore</span></span>

<span data-ttu-id="eb84b-256">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-256">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="eb84b-257">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-257">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="eb84b-258">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="eb84b-258">PrependAndAccept</span></span>

<span data-ttu-id="eb84b-259">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-259">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="eb84b-260">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-260">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="eb84b-261">Refaz</span><span class="sxs-lookup"><span data-stu-id="eb84b-261">Redo</span></span>

<span data-ttu-id="eb84b-262">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-262">Undo an undo.</span></span>

- <span data-ttu-id="eb84b-263">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-263">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="eb84b-264">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-264">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="eb84b-265">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-265">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="eb84b-266">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="eb84b-266">RepeatLastCommand</span></span>

<span data-ttu-id="eb84b-267">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="eb84b-267">Repeat the last text modification.</span></span>

- <span data-ttu-id="eb84b-268">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-268">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="eb84b-269">Reverter</span><span class="sxs-lookup"><span data-stu-id="eb84b-269">RevertLine</span></span>

<span data-ttu-id="eb84b-270">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-270">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="eb84b-271">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-271">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="eb84b-272">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-272">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="eb84b-273">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-273">ShellBackwardKillWord</span></span>

<span data-ttu-id="eb84b-274">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-274">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="eb84b-275">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-275">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="eb84b-276">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-276">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="eb84b-277">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-277">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="eb84b-278">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-278">ShellKillWord</span></span>

<span data-ttu-id="eb84b-279">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-279">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="eb84b-280">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-280">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="eb84b-281">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-281">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="eb84b-282">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-282">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="eb84b-283">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="eb84b-283">SwapCharacters</span></span>

<span data-ttu-id="eb84b-284">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-284">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="eb84b-285">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-285">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="eb84b-286">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-286">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="eb84b-287">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-287">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="eb84b-288">Desfazer</span><span class="sxs-lookup"><span data-stu-id="eb84b-288">Undo</span></span>

<span data-ttu-id="eb84b-289">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-289">Undo a previous edit.</span></span>

- <span data-ttu-id="eb84b-290">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-290">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="eb84b-291">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-291">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="eb84b-292">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-292">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="eb84b-293">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-293">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="eb84b-294">UndoAll</span><span class="sxs-lookup"><span data-stu-id="eb84b-294">UndoAll</span></span>

<span data-ttu-id="eb84b-295">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-295">Undo all previous edits for line.</span></span>

- <span data-ttu-id="eb84b-296">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-296">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="eb84b-297">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="eb84b-297">UnixWordRubout</span></span>

<span data-ttu-id="eb84b-298">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-298">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="eb84b-299">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-299">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="eb84b-300">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-300">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="eb84b-301">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-301">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="eb84b-302">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-302">ValidateAndAcceptLine</span></span>

<span data-ttu-id="eb84b-303">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-303">Attempt to execute the current input.</span></span> <span data-ttu-id="eb84b-304">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-304">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="eb84b-305">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-305">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="eb84b-306">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-306">ViAcceptLine</span></span>

<span data-ttu-id="eb84b-307">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="eb84b-307">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="eb84b-308">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-308">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="eb84b-309">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="eb84b-309">ViAcceptLineOrExit</span></span>

<span data-ttu-id="eb84b-310">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-310">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="eb84b-311">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-311">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="eb84b-312">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-312">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="eb84b-313">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-313">ViAppendLine</span></span>

<span data-ttu-id="eb84b-314">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-314">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="eb84b-315">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-315">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="eb84b-316">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-316">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="eb84b-317">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-317">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="eb84b-318">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-318">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="eb84b-319">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-319">ViBackwardGlob</span></span>

<span data-ttu-id="eb84b-320">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="eb84b-320">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="eb84b-321">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-321">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="eb84b-322">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="eb84b-322">ViDeleteBrace</span></span>

<span data-ttu-id="eb84b-323">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="eb84b-323">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="eb84b-324">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-324">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="eb84b-325">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-325">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="eb84b-326">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-326">Delete to the end of the word.</span></span>

- <span data-ttu-id="eb84b-327">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-327">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="eb84b-328">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-328">ViDeleteGlob</span></span>

<span data-ttu-id="eb84b-329">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="eb84b-329">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="eb84b-330">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-330">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="eb84b-331">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-331">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="eb84b-332">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-332">Deletes until given character.</span></span>

- <span data-ttu-id="eb84b-333">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-333">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="eb84b-334">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-334">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="eb84b-335">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-335">Deletes until given character.</span></span>

- <span data-ttu-id="eb84b-336">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-336">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="eb84b-337">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-337">ViDeleteToChar</span></span>

<span data-ttu-id="eb84b-338">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-338">Deletes until given character.</span></span>

- <span data-ttu-id="eb84b-339">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-339">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="eb84b-340">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-340">ViDeleteToCharBackward</span></span>

<span data-ttu-id="eb84b-341">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-341">Deletes backwards until given character.</span></span>

- <span data-ttu-id="eb84b-342">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-342">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="eb84b-343">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="eb84b-343">ViInsertAtBegining</span></span>

<span data-ttu-id="eb84b-344">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-344">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="eb84b-345">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-345">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="eb84b-346">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="eb84b-346">ViInsertAtEnd</span></span>

<span data-ttu-id="eb84b-347">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-347">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="eb84b-348">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-348">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="eb84b-349">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-349">ViInsertLine</span></span>

<span data-ttu-id="eb84b-350">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-350">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="eb84b-351">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-351">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="eb84b-352">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="eb84b-352">ViInsertWithAppend</span></span>

<span data-ttu-id="eb84b-353">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-353">Append from the current line position.</span></span>

- <span data-ttu-id="eb84b-354">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-354">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="eb84b-355">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="eb84b-355">ViInsertWithDelete</span></span>

<span data-ttu-id="eb84b-356">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="eb84b-356">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="eb84b-357">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-357">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="eb84b-358">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="eb84b-358">ViJoinLines</span></span>

<span data-ttu-id="eb84b-359">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-359">Joins the current line and the next line.</span></span>

- <span data-ttu-id="eb84b-360">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-360">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="eb84b-361">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-361">ViReplaceLine</span></span>

<span data-ttu-id="eb84b-362">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="eb84b-362">Erase the entire command line.</span></span>

- <span data-ttu-id="eb84b-363">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-363">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="eb84b-364">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-364">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="eb84b-365">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-365">Replaces until given character.</span></span>

- <span data-ttu-id="eb84b-366">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-366">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="eb84b-367">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-367">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="eb84b-368">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-368">Replaces until given character.</span></span>

- <span data-ttu-id="eb84b-369">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-369">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="eb84b-370">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-370">ViReplaceToChar</span></span>

<span data-ttu-id="eb84b-371">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-371">Deletes until given character.</span></span>

- <span data-ttu-id="eb84b-372">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-372">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="eb84b-373">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-373">ViReplaceToCharBackward</span></span>

<span data-ttu-id="eb84b-374">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="eb84b-374">Replaces until given character.</span></span>

- <span data-ttu-id="eb84b-375">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-375">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="eb84b-376">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-376">ViYankBeginningOfLine</span></span>

<span data-ttu-id="eb84b-377">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-377">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="eb84b-378">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-378">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="eb84b-379">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-379">ViYankEndOfGlob</span></span>

<span data-ttu-id="eb84b-380">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="eb84b-380">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="eb84b-381">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-381">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="eb84b-382">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-382">ViYankEndOfWord</span></span>

<span data-ttu-id="eb84b-383">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="eb84b-383">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="eb84b-384">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-384">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="eb84b-385">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="eb84b-385">ViYankLeft</span></span>

<span data-ttu-id="eb84b-386">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-386">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="eb84b-387">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-387">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="eb84b-388">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-388">ViYankLine</span></span>

<span data-ttu-id="eb84b-389">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-389">Yank the entire buffer.</span></span>

- <span data-ttu-id="eb84b-390">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-390">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="eb84b-391">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-391">ViYankNextGlob</span></span>

<span data-ttu-id="eb84b-392">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="eb84b-392">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="eb84b-393">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-393">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="eb84b-394">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-394">ViYankNextWord</span></span>

<span data-ttu-id="eb84b-395">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-395">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="eb84b-396">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-396">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="eb84b-397">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="eb84b-397">ViYankPercent</span></span>

<span data-ttu-id="eb84b-398">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="eb84b-398">Yank to/from matching brace.</span></span>

- <span data-ttu-id="eb84b-399">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-399">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="eb84b-400">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-400">ViYankPreviousGlob</span></span>

<span data-ttu-id="eb84b-401">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-401">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="eb84b-402">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-402">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="eb84b-403">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-403">ViYankPreviousWord</span></span>

<span data-ttu-id="eb84b-404">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-404">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="eb84b-405">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-405">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="eb84b-406">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="eb84b-406">ViYankRight</span></span>

<span data-ttu-id="eb84b-407">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-407">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="eb84b-408">Modo de comando vi: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-408">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="eb84b-409">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-409">ViYankToEndOfLine</span></span>

<span data-ttu-id="eb84b-410">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-410">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="eb84b-411">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-411">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="eb84b-412">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-412">ViYankToFirstChar</span></span>

<span data-ttu-id="eb84b-413">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-413">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="eb84b-414">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-414">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="eb84b-415">Yank</span><span class="sxs-lookup"><span data-stu-id="eb84b-415">Yank</span></span>

<span data-ttu-id="eb84b-416">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-416">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="eb84b-417">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-417">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="eb84b-418">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="eb84b-418">YankLastArg</span></span>

<span data-ttu-id="eb84b-419">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-419">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="eb84b-420">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="eb84b-420">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="eb84b-421">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="eb84b-421">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="eb84b-422">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-422">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="eb84b-423">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-423">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="eb84b-424">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="eb84b-424">YankNthArg</span></span>

<span data-ttu-id="eb84b-425">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-425">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="eb84b-426">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="eb84b-426">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="eb84b-427">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-427">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="eb84b-428">YankPop</span><span class="sxs-lookup"><span data-stu-id="eb84b-428">YankPop</span></span>

<span data-ttu-id="eb84b-429">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-429">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="eb84b-430">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-430">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="eb84b-431">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="eb84b-431">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="eb84b-432">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-432">BackwardChar</span></span>

<span data-ttu-id="eb84b-433">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="eb84b-433">Move the cursor one character to the left.</span></span> <span data-ttu-id="eb84b-434">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="eb84b-434">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="eb84b-435">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-435">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="eb84b-436">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-436">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="eb84b-437">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-437">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="eb84b-438">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-438">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="eb84b-439">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-439">BackwardWord</span></span>

<span data-ttu-id="eb84b-440">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-440">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="eb84b-441">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb84b-441">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb84b-442">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-442">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="eb84b-443">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-443">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="eb84b-444">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-444">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="eb84b-445">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-445">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="eb84b-446">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-446">BeginningOfLine</span></span>

<span data-ttu-id="eb84b-447">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-447">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="eb84b-448">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-448">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="eb84b-449">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-449">Cmd: `<Home>`</span></span>
- <span data-ttu-id="eb84b-450">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-450">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="eb84b-451">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-451">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="eb84b-452">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-452">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="eb84b-453">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-453">EndOfLine</span></span>

<span data-ttu-id="eb84b-454">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-454">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="eb84b-455">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-455">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="eb84b-456">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-456">Cmd: `<End>`</span></span>
- <span data-ttu-id="eb84b-457">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-457">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="eb84b-458">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-458">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="eb84b-459">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-459">ForwardChar</span></span>

<span data-ttu-id="eb84b-460">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="eb84b-460">Move the cursor one character to the right.</span></span> <span data-ttu-id="eb84b-461">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="eb84b-461">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="eb84b-462">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-462">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="eb84b-463">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-463">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="eb84b-464">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-464">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="eb84b-465">Modo de comando vi: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-465">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="eb84b-466">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-466">ForwardWord</span></span>

<span data-ttu-id="eb84b-467">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-467">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="eb84b-468">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb84b-468">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb84b-469">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-469">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="eb84b-470">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="eb84b-470">GotoBrace</span></span>

<span data-ttu-id="eb84b-471">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="eb84b-471">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="eb84b-472">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-472">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="eb84b-473">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-473">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="eb84b-474">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-474">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="eb84b-475">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="eb84b-475">GotoColumn</span></span>

<span data-ttu-id="eb84b-476">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="eb84b-476">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="eb84b-477">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-477">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="eb84b-478">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-478">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="eb84b-479">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-479">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="eb84b-480">Modo de comando vi: `<^>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-480">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="eb84b-481">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-481">MoveToEndOfLine</span></span>

<span data-ttu-id="eb84b-482">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-482">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="eb84b-483">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-483">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="eb84b-484">Próxima</span><span class="sxs-lookup"><span data-stu-id="eb84b-484">NextLine</span></span>

<span data-ttu-id="eb84b-485">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-485">Move the cursor to the next line.</span></span>

- <span data-ttu-id="eb84b-486">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-486">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="eb84b-487">NextWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-487">NextWord</span></span>

<span data-ttu-id="eb84b-488">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-488">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="eb84b-489">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb84b-489">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb84b-490">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-490">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="eb84b-491">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-491">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="eb84b-492">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-492">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="eb84b-493">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="eb84b-493">NextWordEnd</span></span>

<span data-ttu-id="eb84b-494">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-494">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="eb84b-495">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb84b-495">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb84b-496">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-496">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="eb84b-497">Anterior</span><span class="sxs-lookup"><span data-stu-id="eb84b-497">PreviousLine</span></span>

<span data-ttu-id="eb84b-498">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-498">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="eb84b-499">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-499">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="eb84b-500">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-500">ShellBackwardWord</span></span>

<span data-ttu-id="eb84b-501">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-501">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="eb84b-502">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-502">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="eb84b-503">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-503">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="eb84b-504">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-504">ShellForwardWord</span></span>

<span data-ttu-id="eb84b-505">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-505">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="eb84b-506">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-506">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="eb84b-507">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-507">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="eb84b-508">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-508">ShellNextWord</span></span>

<span data-ttu-id="eb84b-509">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-509">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="eb84b-510">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-510">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="eb84b-511">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-511">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="eb84b-512">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-512">ViBackwardWord</span></span>

<span data-ttu-id="eb84b-513">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-513">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="eb84b-514">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb84b-514">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb84b-515">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-515">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="eb84b-516">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-516">ViEndOfGlob</span></span>

<span data-ttu-id="eb84b-517">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="eb84b-517">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="eb84b-518">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-518">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="eb84b-519">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-519">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="eb84b-520">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-520">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="eb84b-521">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-521">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="eb84b-522">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="eb84b-522">ViGotoBrace</span></span>

<span data-ttu-id="eb84b-523">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="eb84b-523">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="eb84b-524">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-524">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="eb84b-525">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="eb84b-525">ViNextGlob</span></span>

<span data-ttu-id="eb84b-526">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-526">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="eb84b-527">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-527">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="eb84b-528">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-528">ViNextWord</span></span>

<span data-ttu-id="eb84b-529">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-529">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="eb84b-530">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb84b-530">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="eb84b-531">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-531">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="eb84b-532">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="eb84b-532">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="eb84b-533">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="eb84b-533">BeginningOfHistory</span></span>

<span data-ttu-id="eb84b-534">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="eb84b-534">Move to the first item in the history.</span></span>

- <span data-ttu-id="eb84b-535">Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="eb84b-535">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="eb84b-536">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="eb84b-536">ClearHistory</span></span>

<span data-ttu-id="eb84b-537">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="eb84b-537">Clears history in PSReadLine.</span></span> <span data-ttu-id="eb84b-538">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-538">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="eb84b-539">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-539">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="eb84b-540">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="eb84b-540">EndOfHistory</span></span>

<span data-ttu-id="eb84b-541">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="eb84b-541">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="eb84b-542">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-542">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="eb84b-543">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="eb84b-543">ForwardSearchHistory</span></span>

<span data-ttu-id="eb84b-544">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="eb84b-544">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="eb84b-545">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-545">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="eb84b-546">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-546">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="eb84b-547">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-547">HistorySearchBackward</span></span>

<span data-ttu-id="eb84b-548">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-548">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="eb84b-549">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-549">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="eb84b-550">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="eb84b-550">HistorySearchForward</span></span>

<span data-ttu-id="eb84b-551">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-551">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="eb84b-552">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-552">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="eb84b-553">NextHistory</span><span class="sxs-lookup"><span data-stu-id="eb84b-553">NextHistory</span></span>

<span data-ttu-id="eb84b-554">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="eb84b-554">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="eb84b-555">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-555">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="eb84b-556">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-556">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="eb84b-557">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-557">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="eb84b-558">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-558">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="eb84b-559">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="eb84b-559">PreviousHistory</span></span>

<span data-ttu-id="eb84b-560">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="eb84b-560">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="eb84b-561">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-561">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="eb84b-562">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-562">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="eb84b-563">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-563">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="eb84b-564">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="eb84b-564">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="eb84b-565">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="eb84b-565">ReverseSearchHistory</span></span>

<span data-ttu-id="eb84b-566">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="eb84b-566">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="eb84b-567">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-567">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="eb84b-568">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-568">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="eb84b-569">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-569">ViSearchHistoryBackward</span></span>

<span data-ttu-id="eb84b-570">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="eb84b-570">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="eb84b-571">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-571">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="eb84b-572">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-572">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="eb84b-573">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="eb84b-573">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="eb84b-574">Concluir</span><span class="sxs-lookup"><span data-stu-id="eb84b-574">Complete</span></span>

<span data-ttu-id="eb84b-575">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-575">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="eb84b-576">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="eb84b-576">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="eb84b-577">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="eb84b-577">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="eb84b-578">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-578">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="eb84b-579">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="eb84b-579">MenuComplete</span></span>

<span data-ttu-id="eb84b-580">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-580">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="eb84b-581">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="eb84b-581">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="eb84b-582">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="eb84b-582">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="eb84b-583">Cmd `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-583">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="eb84b-584">Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-584">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="eb84b-585">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="eb84b-585">PossibleCompletions</span></span>

<span data-ttu-id="eb84b-586">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="eb84b-586">Display the list of possible completions.</span></span>

- <span data-ttu-id="eb84b-587">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-587">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="eb84b-588">Modo de inserção de vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-588">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="eb84b-589">Modo de comando vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-589">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="eb84b-590">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="eb84b-590">TabCompleteNext</span></span>

<span data-ttu-id="eb84b-591">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="eb84b-591">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="eb84b-592">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-592">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="eb84b-593">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-593">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="eb84b-594">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="eb84b-594">TabCompletePrevious</span></span>

<span data-ttu-id="eb84b-595">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-595">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="eb84b-596">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-596">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="eb84b-597">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-597">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="eb84b-598">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="eb84b-598">ViTabCompleteNext</span></span>

<span data-ttu-id="eb84b-599">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="eb84b-599">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="eb84b-600">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-600">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="eb84b-601">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="eb84b-601">ViTabCompletePrevious</span></span>

<span data-ttu-id="eb84b-602">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="eb84b-602">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="eb84b-603">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-603">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="eb84b-604">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="eb84b-604">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="eb84b-605">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="eb84b-605">CaptureScreen</span></span>

<span data-ttu-id="eb84b-606">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="eb84b-606">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="eb84b-607">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-607">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="eb84b-608">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="eb84b-608">ClearScreen</span></span>

<span data-ttu-id="eb84b-609">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="eb84b-609">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="eb84b-610">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-610">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="eb84b-611">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-611">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="eb84b-612">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-612">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="eb84b-613">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-613">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="eb84b-614">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="eb84b-614">DigitArgument</span></span>

<span data-ttu-id="eb84b-615">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="eb84b-615">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="eb84b-616">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="eb84b-616">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="eb84b-617">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="eb84b-617">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="eb84b-618">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-618">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="eb84b-619">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="eb84b-619">InvokePrompt</span></span>

<span data-ttu-id="eb84b-620">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="eb84b-620">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="eb84b-621">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="eb84b-621">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="eb84b-622">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-622">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="eb84b-623">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="eb84b-623">ScrollDisplayDown</span></span>

<span data-ttu-id="eb84b-624">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="eb84b-624">Scroll the display down one screen.</span></span>

- <span data-ttu-id="eb84b-625">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-625">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="eb84b-626">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-626">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="eb84b-627">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-627">ScrollDisplayDownLine</span></span>

<span data-ttu-id="eb84b-628">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="eb84b-628">Scroll the display down one line.</span></span>

- <span data-ttu-id="eb84b-629">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-629">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="eb84b-630">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-630">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="eb84b-631">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="eb84b-631">ScrollDisplayToCursor</span></span>

<span data-ttu-id="eb84b-632">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-632">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="eb84b-633">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-633">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="eb84b-634">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="eb84b-634">ScrollDisplayTop</span></span>

<span data-ttu-id="eb84b-635">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-635">Scroll the display to the top.</span></span>

- <span data-ttu-id="eb84b-636">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-636">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="eb84b-637">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="eb84b-637">ScrollDisplayUp</span></span>

<span data-ttu-id="eb84b-638">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="eb84b-638">Scroll the display up one screen.</span></span>

- <span data-ttu-id="eb84b-639">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-639">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="eb84b-640">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-640">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="eb84b-641">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-641">ScrollDisplayUpLine</span></span>

<span data-ttu-id="eb84b-642">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="eb84b-642">Scroll the display up one line.</span></span>

- <span data-ttu-id="eb84b-643">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-643">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="eb84b-644">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-644">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="eb84b-645">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="eb84b-645">SelfInsert</span></span>

<span data-ttu-id="eb84b-646">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="eb84b-646">Insert the key.</span></span>

- <span data-ttu-id="eb84b-647">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-647">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="eb84b-648">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="eb84b-648">ShowKeyBindings</span></span>

<span data-ttu-id="eb84b-649">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="eb84b-649">Show all bound keys.</span></span>

- <span data-ttu-id="eb84b-650">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-650">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="eb84b-651">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-651">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="eb84b-652">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-652">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="eb84b-653">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="eb84b-653">ViCommandMode</span></span>

<span data-ttu-id="eb84b-654">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="eb84b-654">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="eb84b-655">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-655">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="eb84b-656">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="eb84b-656">ViDigitArgumentInChord</span></span>

<span data-ttu-id="eb84b-657">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="eb84b-657">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="eb84b-658">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-658">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="eb84b-659">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="eb84b-659">ViEditVisually</span></span>

<span data-ttu-id="eb84b-660">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="eb84b-660">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="eb84b-661">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-661">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="eb84b-662">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-662">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="eb84b-663">ViExit</span><span class="sxs-lookup"><span data-stu-id="eb84b-663">ViExit</span></span>

<span data-ttu-id="eb84b-664">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="eb84b-664">Exits the shell.</span></span>

- <span data-ttu-id="eb84b-665">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-665">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="eb84b-666">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="eb84b-666">ViInsertMode</span></span>

<span data-ttu-id="eb84b-667">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="eb84b-667">Switch to Insert mode.</span></span>

- <span data-ttu-id="eb84b-668">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-668">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="eb84b-669">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="eb84b-669">WhatIsKey</span></span>

<span data-ttu-id="eb84b-670">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-670">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="eb84b-671">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-671">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="eb84b-672">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-672">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="eb84b-673">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="eb84b-673">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="eb84b-674">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="eb84b-674">ExchangePointAndMark</span></span>

<span data-ttu-id="eb84b-675">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-675">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="eb84b-676">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-676">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="eb84b-677">SelectAll</span><span class="sxs-lookup"><span data-stu-id="eb84b-677">SelectAll</span></span>

<span data-ttu-id="eb84b-678">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="eb84b-678">Select the entire line.</span></span>

- <span data-ttu-id="eb84b-679">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-679">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="eb84b-680">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-680">SelectBackwardChar</span></span>

<span data-ttu-id="eb84b-681">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-681">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="eb84b-682">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-682">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="eb84b-683">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-683">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="eb84b-684">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-684">SelectBackwardsLine</span></span>

<span data-ttu-id="eb84b-685">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-685">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="eb84b-686">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-686">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="eb84b-687">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-687">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="eb84b-688">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-688">SelectBackwardWord</span></span>

<span data-ttu-id="eb84b-689">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="eb84b-689">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="eb84b-690">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-690">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="eb84b-691">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-691">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="eb84b-692">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-692">SelectForwardChar</span></span>

<span data-ttu-id="eb84b-693">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-693">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="eb84b-694">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-694">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="eb84b-695">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-695">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="eb84b-696">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-696">SelectForwardWord</span></span>

<span data-ttu-id="eb84b-697">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="eb84b-697">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="eb84b-698">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-698">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="eb84b-699">Seleção</span><span class="sxs-lookup"><span data-stu-id="eb84b-699">SelectLine</span></span>

<span data-ttu-id="eb84b-700">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="eb84b-700">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="eb84b-701">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-701">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="eb84b-702">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-702">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="eb84b-703">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-703">SelectNextWord</span></span>

<span data-ttu-id="eb84b-704">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="eb84b-704">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="eb84b-705">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-705">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="eb84b-706">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-706">SelectShellBackwardWord</span></span>

<span data-ttu-id="eb84b-707">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="eb84b-707">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="eb84b-708">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-708">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="eb84b-709">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-709">SelectShellForwardWord</span></span>

<span data-ttu-id="eb84b-710">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="eb84b-710">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="eb84b-711">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-711">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="eb84b-712">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="eb84b-712">SelectShellNextWord</span></span>

<span data-ttu-id="eb84b-713">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="eb84b-713">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="eb84b-714">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-714">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="eb84b-715">Definir marca</span><span class="sxs-lookup"><span data-stu-id="eb84b-715">SetMark</span></span>

<span data-ttu-id="eb84b-716">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="eb84b-716">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="eb84b-717">Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="eb84b-717">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="eb84b-718">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="eb84b-718">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="eb84b-719">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="eb84b-719">CharacterSearch</span></span>

<span data-ttu-id="eb84b-720">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-720">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="eb84b-721">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="eb84b-721">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="eb84b-722">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-722">Cmd: `<F3>`</span></span>
- <span data-ttu-id="eb84b-723">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-723">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="eb84b-724">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-724">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="eb84b-725">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-725">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="eb84b-726">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-726">CharacterSearchBackward</span></span>

<span data-ttu-id="eb84b-727">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-727">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="eb84b-728">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="eb84b-728">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="eb84b-729">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-729">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="eb84b-730">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-730">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="eb84b-731">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-731">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="eb84b-732">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-732">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="eb84b-733">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="eb84b-733">RepeatLastCharSearch</span></span>

<span data-ttu-id="eb84b-734">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-734">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="eb84b-735">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-735">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="eb84b-736">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="eb84b-736">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="eb84b-737">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="eb84b-737">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="eb84b-738">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-738">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="eb84b-739">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="eb84b-739">RepeatSearch</span></span>

<span data-ttu-id="eb84b-740">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="eb84b-740">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="eb84b-741">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-741">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="eb84b-742">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-742">RepeatSearchBackward</span></span>

<span data-ttu-id="eb84b-743">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="eb84b-743">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="eb84b-744">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-744">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="eb84b-745">SearchChar</span><span class="sxs-lookup"><span data-stu-id="eb84b-745">SearchChar</span></span>

<span data-ttu-id="eb84b-746">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-746">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="eb84b-747">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="eb84b-747">This is for 't' functionality.</span></span>

- <span data-ttu-id="eb84b-748">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-748">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="eb84b-749">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="eb84b-749">SearchCharBackward</span></span>

<span data-ttu-id="eb84b-750">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-750">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="eb84b-751">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="eb84b-751">This is for 'T' functionality.</span></span>

- <span data-ttu-id="eb84b-752">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-752">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="eb84b-753">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="eb84b-753">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="eb84b-754">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-754">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="eb84b-755">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="eb84b-755">This is for 'T' functionality.</span></span>

- <span data-ttu-id="eb84b-756">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-756">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="eb84b-757">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="eb84b-757">SearchCharWithBackoff</span></span>

<span data-ttu-id="eb84b-758">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="eb84b-758">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="eb84b-759">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="eb84b-759">This is for 't' functionality.</span></span>

- <span data-ttu-id="eb84b-760">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-760">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="eb84b-761">SearchForward</span><span class="sxs-lookup"><span data-stu-id="eb84b-761">SearchForward</span></span>

<span data-ttu-id="eb84b-762">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="eb84b-762">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="eb84b-763">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-763">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="eb84b-764">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="eb84b-764">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="eb84b-765">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="eb84b-765">Custom Key Bindings</span></span>

<span data-ttu-id="eb84b-766">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="eb84b-766">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="eb84b-767">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="eb84b-767">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="eb84b-768">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="eb84b-768">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="eb84b-769">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="eb84b-769">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="eb84b-770">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="eb84b-770">Some useful examples include</span></span>

- <span data-ttu-id="eb84b-771">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="eb84b-771">edit the command line</span></span>
- <span data-ttu-id="eb84b-772">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="eb84b-772">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="eb84b-773">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="eb84b-773">change directories without changing the command line</span></span>

<span data-ttu-id="eb84b-774">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="eb84b-774">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="eb84b-775">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-775">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="eb84b-776">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="eb84b-776">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="eb84b-777">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="eb84b-777">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="eb84b-778">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="eb84b-778">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="eb84b-779">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="eb84b-779">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="eb84b-780">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="eb84b-780">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="eb84b-781">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="eb84b-781">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="eb84b-782">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="eb84b-782">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="eb84b-783">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="eb84b-783">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="eb84b-784">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="eb84b-784">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="eb84b-785">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="eb84b-785">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="eb84b-786">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="eb84b-786">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="eb84b-787">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="eb84b-787">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="eb84b-788">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="eb84b-788">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="eb84b-789">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="eb84b-789">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="eb84b-790">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="eb84b-790">Clear the kill-ring.</span></span>  <span data-ttu-id="eb84b-791">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="eb84b-791">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="eb84b-792">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="eb84b-792">Delete length characters from start.</span></span>  <span data-ttu-id="eb84b-793">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-793">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="eb84b-794">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="eb84b-794">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="eb84b-795">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-795">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="eb84b-796">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="eb84b-796">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="eb84b-797">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="eb84b-797">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="eb84b-798">Essa função é usada pelo Get-PSReadLineKeyHandler e provavelmente não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-798">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="eb84b-799">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-799">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="eb84b-800">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="eb84b-800">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="eb84b-801">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="eb84b-801">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="eb84b-802">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="eb84b-802">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="eb84b-803">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-803">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="eb84b-804">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="eb84b-804">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="eb84b-805">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-805">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="eb84b-806">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="eb84b-806">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="eb84b-807">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="eb84b-807">Replace some of the input.</span></span> <span data-ttu-id="eb84b-808">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-808">This operation supports undo/redo.</span></span> <span data-ttu-id="eb84b-809">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-809">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="eb84b-810">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="eb84b-810">Move the cursor to the given offset.</span></span> <span data-ttu-id="eb84b-811">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="eb84b-811">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="eb84b-812">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="eb84b-812">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="eb84b-813">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="eb84b-813">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="eb84b-814">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="eb84b-814">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="eb84b-815">Observação</span><span class="sxs-lookup"><span data-stu-id="eb84b-815">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="eb84b-816">Histórico de comandos</span><span class="sxs-lookup"><span data-stu-id="eb84b-816">Command History</span></span>

<span data-ttu-id="eb84b-817">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="eb84b-817">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="eb84b-818">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="eb84b-818">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="eb84b-819">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="eb84b-819">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="eb84b-820">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="eb84b-820">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="eb84b-821">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="eb84b-821">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="eb84b-822">Comentários & contribuindo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="eb84b-822">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="eb84b-823">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="eb84b-823">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="eb84b-824">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="eb84b-824">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb84b-825">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb84b-825">See Also</span></span>

<span data-ttu-id="eb84b-826">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="eb84b-826">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
