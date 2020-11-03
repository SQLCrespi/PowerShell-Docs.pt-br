---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: 5b59ffcdfb35c2aa10f8e0caf3a3b365c5bcf93e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196257"
---
# <a name="psreadline"></a><span data-ttu-id="7dfe8-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="7dfe8-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="7dfe8-106">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="7dfe8-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="7dfe8-107">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="7dfe8-108">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="7dfe8-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="7dfe8-109">O PSReadLine 2,0 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="7dfe8-110">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="7dfe8-110">It provides:</span></span>

- <span data-ttu-id="7dfe8-111">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="7dfe8-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="7dfe8-112">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="7dfe8-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="7dfe8-113">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="7dfe8-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="7dfe8-114">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="7dfe8-114">Customizable key bindings</span></span>
- <span data-ttu-id="7dfe8-115">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="7dfe8-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="7dfe8-116">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="7dfe8-116">Many configuration options</span></span>
- <span data-ttu-id="7dfe8-117">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="7dfe8-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="7dfe8-118">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="7dfe8-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="7dfe8-119">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="7dfe8-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="7dfe8-120">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]** .</span><span class="sxs-lookup"><span data-stu-id="7dfe8-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]** .</span></span>

> [!NOTE]
> <span data-ttu-id="7dfe8-121">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="7dfe8-122">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="7dfe8-123">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="7dfe8-124">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="7dfe8-125">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="7dfe8-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="7dfe8-126">Anular</span><span class="sxs-lookup"><span data-stu-id="7dfe8-126">Abort</span></span>

<span data-ttu-id="7dfe8-127">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="7dfe8-128">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="7dfe8-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="7dfe8-129">AcceptAndGetNext</span></span>

<span data-ttu-id="7dfe8-130">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-130">Attempt to execute the current input.</span></span> <span data-ttu-id="7dfe8-131">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="7dfe8-132">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="7dfe8-133">Aceitar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-133">AcceptLine</span></span>

<span data-ttu-id="7dfe8-134">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-134">Attempt to execute the current input.</span></span> <span data-ttu-id="7dfe8-135">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="7dfe8-136">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="7dfe8-137">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="7dfe8-138">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="7dfe8-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-139">AddLine</span></span>

<span data-ttu-id="7dfe8-140">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="7dfe8-141">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="7dfe8-142">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="7dfe8-143">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="7dfe8-144">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="7dfe8-145">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="7dfe8-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-146">BackwardDeleteChar</span></span>

<span data-ttu-id="7dfe8-147">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="7dfe8-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="7dfe8-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="7dfe8-150">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="7dfe8-151">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="7dfe8-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-152">BackwardDeleteLine</span></span>

<span data-ttu-id="7dfe8-153">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-154">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="7dfe8-155">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="7dfe8-156">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="7dfe8-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-157">BackwardDeleteWord</span></span>

<span data-ttu-id="7dfe8-158">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-158">Deletes the previous word.</span></span>

- <span data-ttu-id="7dfe8-159">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="7dfe8-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-160">BackwardKillLine</span></span>

<span data-ttu-id="7dfe8-161">Limpe a entrada do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="7dfe8-162">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="7dfe8-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-164">BackwardKillWord</span></span>

<span data-ttu-id="7dfe8-165">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="7dfe8-166">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="7dfe8-167">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-168">Cmd `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-168">Cmd: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="7dfe8-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="7dfe8-170">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="7dfe8-171">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="7dfe8-172">Cancelar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-172">CancelLine</span></span>

<span data-ttu-id="7dfe8-173">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="7dfe8-174">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="7dfe8-175">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="7dfe8-176">Copiar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-176">Copy</span></span>

<span data-ttu-id="7dfe8-177">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="7dfe8-178">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="7dfe8-179">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="7dfe8-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-180">CopyOrCancelLine</span></span>

<span data-ttu-id="7dfe8-181">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="7dfe8-182">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="7dfe8-183">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="7dfe8-184">Recortar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-184">Cut</span></span>

<span data-ttu-id="7dfe8-185">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="7dfe8-186">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="7dfe8-187">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-187">DeleteChar</span></span>

<span data-ttu-id="7dfe8-188">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="7dfe8-189">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="7dfe8-190">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="7dfe8-191">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="7dfe8-192">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Space>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Space>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="7dfe8-193">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="7dfe8-193">DeleteCharOrExit</span></span>

<span data-ttu-id="7dfe8-194">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="7dfe8-195">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="7dfe8-196">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-196">DeleteEndOfWord</span></span>

<span data-ttu-id="7dfe8-197">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-197">Delete to the end of the word.</span></span>

- <span data-ttu-id="7dfe8-198">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-198">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="7dfe8-199">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-199">DeleteLine</span></span>

<span data-ttu-id="7dfe8-200">Exclui a linha atual, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-200">Deletes the current line, enabling undo.</span></span>

- <span data-ttu-id="7dfe8-201">Modo de comando vi: `<d,d>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-201">Vi command mode: `<d,d>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="7dfe8-202">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-202">DeleteLineToFirstChar</span></span>

<span data-ttu-id="7dfe8-203">Exclui o texto do cursor para o primeiro caractere que não seja em branco da linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-203">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="7dfe8-204">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-204">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="7dfe8-205">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="7dfe8-205">DeleteToEnd</span></span>

<span data-ttu-id="7dfe8-206">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-206">Delete to the end of the line.</span></span>

- <span data-ttu-id="7dfe8-207">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-207">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="7dfe8-208">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-208">DeleteWord</span></span>

<span data-ttu-id="7dfe8-209">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-209">Delete the next word.</span></span>

- <span data-ttu-id="7dfe8-210">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-210">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="7dfe8-211">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-211">ForwardDeleteLine</span></span>

<span data-ttu-id="7dfe8-212">Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-212">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-213">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-213">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="7dfe8-214">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-214">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="7dfe8-215">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-215">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="7dfe8-216">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="7dfe8-216">InsertLineAbove</span></span>

<span data-ttu-id="7dfe8-217">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-217">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="7dfe8-218">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-218">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="7dfe8-219">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-219">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="7dfe8-220">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="7dfe8-220">InsertLineBelow</span></span>

<span data-ttu-id="7dfe8-221">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-221">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="7dfe8-222">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-222">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="7dfe8-223">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-223">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="7dfe8-224">InvertCase</span><span class="sxs-lookup"><span data-stu-id="7dfe8-224">InvertCase</span></span>

<span data-ttu-id="7dfe8-225">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-225">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="7dfe8-226">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-226">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="7dfe8-227">Finalizar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-227">KillLine</span></span>

<span data-ttu-id="7dfe8-228">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-228">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="7dfe8-229">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-229">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-230">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-230">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="7dfe8-231">KillRegion</span><span class="sxs-lookup"><span data-stu-id="7dfe8-231">KillRegion</span></span>

<span data-ttu-id="7dfe8-232">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-232">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="7dfe8-233">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-233">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="7dfe8-234">KillWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-234">KillWord</span></span>

<span data-ttu-id="7dfe8-235">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-235">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="7dfe8-236">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-236">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="7dfe8-237">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-237">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-238">Cmd `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-238">Cmd: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="7dfe8-239">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-239">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="7dfe8-240">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-240">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="7dfe8-241">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-241">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="7dfe8-242">Colar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-242">Paste</span></span>

<span data-ttu-id="7dfe8-243">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-243">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="7dfe8-244">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-244">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="7dfe8-245">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-245">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="7dfe8-246">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-246">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dfe8-247">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-247">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="7dfe8-248">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-248">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="7dfe8-249">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-249">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="7dfe8-250">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-250">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="7dfe8-251">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-251">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="7dfe8-252">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-252">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="7dfe8-253">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="7dfe8-253">PasteAfter</span></span>

<span data-ttu-id="7dfe8-254">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-254">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="7dfe8-255">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-255">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="7dfe8-256">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="7dfe8-256">PasteBefore</span></span>

<span data-ttu-id="7dfe8-257">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-257">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="7dfe8-258">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-258">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="7dfe8-259">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="7dfe8-259">PrependAndAccept</span></span>

<span data-ttu-id="7dfe8-260">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-260">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="7dfe8-261">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-261">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="7dfe8-262">Refazer</span><span class="sxs-lookup"><span data-stu-id="7dfe8-262">Redo</span></span>

<span data-ttu-id="7dfe8-263">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-263">Undo an undo.</span></span>

- <span data-ttu-id="7dfe8-264">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-264">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="7dfe8-265">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-265">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="7dfe8-266">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-266">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="7dfe8-267">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="7dfe8-267">RepeatLastCommand</span></span>

<span data-ttu-id="7dfe8-268">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-268">Repeat the last text modification.</span></span>

- <span data-ttu-id="7dfe8-269">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-269">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="7dfe8-270">Reverter</span><span class="sxs-lookup"><span data-stu-id="7dfe8-270">RevertLine</span></span>

<span data-ttu-id="7dfe8-271">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-271">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="7dfe8-272">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-272">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="7dfe8-273">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-273">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="7dfe8-274">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-274">ShellBackwardKillWord</span></span>

<span data-ttu-id="7dfe8-275">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-275">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="7dfe8-276">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-276">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="7dfe8-277">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-277">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="7dfe8-278">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-278">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="7dfe8-279">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-279">ShellKillWord</span></span>

<span data-ttu-id="7dfe8-280">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-280">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="7dfe8-281">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-281">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="7dfe8-282">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-282">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="7dfe8-283">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-283">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="7dfe8-284">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="7dfe8-284">SwapCharacters</span></span>

<span data-ttu-id="7dfe8-285">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-285">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="7dfe8-286">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-286">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="7dfe8-287">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-287">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="7dfe8-288">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-288">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="7dfe8-289">Desfazer</span><span class="sxs-lookup"><span data-stu-id="7dfe8-289">Undo</span></span>

<span data-ttu-id="7dfe8-290">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-290">Undo a previous edit.</span></span>

- <span data-ttu-id="7dfe8-291">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-291">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="7dfe8-292">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-292">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="7dfe8-293">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-293">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="7dfe8-294">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-294">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="7dfe8-295">UndoAll</span><span class="sxs-lookup"><span data-stu-id="7dfe8-295">UndoAll</span></span>

<span data-ttu-id="7dfe8-296">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-296">Undo all previous edits for line.</span></span>

- <span data-ttu-id="7dfe8-297">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-297">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="7dfe8-298">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="7dfe8-298">UnixWordRubout</span></span>

<span data-ttu-id="7dfe8-299">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-299">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="7dfe8-300">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-300">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="7dfe8-301">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-301">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-302">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-302">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="7dfe8-303">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-303">ValidateAndAcceptLine</span></span>

<span data-ttu-id="7dfe8-304">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-304">Attempt to execute the current input.</span></span> <span data-ttu-id="7dfe8-305">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-305">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="7dfe8-306">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-306">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="7dfe8-307">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-307">ViAcceptLine</span></span>

<span data-ttu-id="7dfe8-308">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-308">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="7dfe8-309">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-309">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="7dfe8-310">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="7dfe8-310">ViAcceptLineOrExit</span></span>

<span data-ttu-id="7dfe8-311">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-311">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="7dfe8-312">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-312">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="7dfe8-313">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-313">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="7dfe8-314">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-314">ViAppendLine</span></span>

<span data-ttu-id="7dfe8-315">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-315">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="7dfe8-316">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-316">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="7dfe8-317">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-317">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="7dfe8-318">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-318">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="7dfe8-319">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-319">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="7dfe8-320">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-320">ViBackwardGlob</span></span>

<span data-ttu-id="7dfe8-321">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-321">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="7dfe8-322">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-322">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="7dfe8-323">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="7dfe8-323">ViDeleteBrace</span></span>

<span data-ttu-id="7dfe8-324">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-324">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="7dfe8-325">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-325">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="7dfe8-326">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-326">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="7dfe8-327">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-327">Delete to the end of the word.</span></span>

- <span data-ttu-id="7dfe8-328">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-328">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="7dfe8-329">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-329">ViDeleteGlob</span></span>

<span data-ttu-id="7dfe8-330">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="7dfe8-330">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="7dfe8-331">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-331">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="7dfe8-332">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-332">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="7dfe8-333">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-333">Deletes until given character.</span></span>

- <span data-ttu-id="7dfe8-334">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-334">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="7dfe8-335">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-335">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="7dfe8-336">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-336">Deletes until given character.</span></span>

- <span data-ttu-id="7dfe8-337">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-337">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="7dfe8-338">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-338">ViDeleteToChar</span></span>

<span data-ttu-id="7dfe8-339">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-339">Deletes until given character.</span></span>

- <span data-ttu-id="7dfe8-340">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-340">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="7dfe8-341">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-341">ViDeleteToCharBackward</span></span>

<span data-ttu-id="7dfe8-342">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-342">Deletes backwards until given character.</span></span>

- <span data-ttu-id="7dfe8-343">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-343">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="7dfe8-344">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="7dfe8-344">ViInsertAtBegining</span></span>

<span data-ttu-id="7dfe8-345">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-345">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="7dfe8-346">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-346">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="7dfe8-347">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="7dfe8-347">ViInsertAtEnd</span></span>

<span data-ttu-id="7dfe8-348">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-348">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="7dfe8-349">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-349">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="7dfe8-350">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-350">ViInsertLine</span></span>

<span data-ttu-id="7dfe8-351">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-351">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="7dfe8-352">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-352">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="7dfe8-353">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="7dfe8-353">ViInsertWithAppend</span></span>

<span data-ttu-id="7dfe8-354">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-354">Append from the current line position.</span></span>

- <span data-ttu-id="7dfe8-355">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-355">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="7dfe8-356">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="7dfe8-356">ViInsertWithDelete</span></span>

<span data-ttu-id="7dfe8-357">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-357">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="7dfe8-358">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-358">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="7dfe8-359">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="7dfe8-359">ViJoinLines</span></span>

<span data-ttu-id="7dfe8-360">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-360">Joins the current line and the next line.</span></span>

- <span data-ttu-id="7dfe8-361">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-361">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="7dfe8-362">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-362">ViReplaceLine</span></span>

<span data-ttu-id="7dfe8-363">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-363">Erase the entire command line.</span></span>

- <span data-ttu-id="7dfe8-364">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-364">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="7dfe8-365">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-365">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="7dfe8-366">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-366">Replaces until given character.</span></span>

- <span data-ttu-id="7dfe8-367">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-367">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="7dfe8-368">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-368">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="7dfe8-369">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-369">Replaces until given character.</span></span>

- <span data-ttu-id="7dfe8-370">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-370">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="7dfe8-371">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-371">ViReplaceToChar</span></span>

<span data-ttu-id="7dfe8-372">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-372">Deletes until given character.</span></span>

- <span data-ttu-id="7dfe8-373">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-373">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="7dfe8-374">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-374">ViReplaceToCharBackward</span></span>

<span data-ttu-id="7dfe8-375">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-375">Replaces until given character.</span></span>

- <span data-ttu-id="7dfe8-376">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-376">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="7dfe8-377">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-377">ViYankBeginningOfLine</span></span>

<span data-ttu-id="7dfe8-378">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-378">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="7dfe8-379">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-379">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="7dfe8-380">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-380">ViYankEndOfGlob</span></span>

<span data-ttu-id="7dfe8-381">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-381">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="7dfe8-382">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-382">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="7dfe8-383">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-383">ViYankEndOfWord</span></span>

<span data-ttu-id="7dfe8-384">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-384">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="7dfe8-385">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-385">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="7dfe8-386">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="7dfe8-386">ViYankLeft</span></span>

<span data-ttu-id="7dfe8-387">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-387">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="7dfe8-388">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-388">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="7dfe8-389">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-389">ViYankLine</span></span>

<span data-ttu-id="7dfe8-390">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-390">Yank the entire buffer.</span></span>

- <span data-ttu-id="7dfe8-391">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-391">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="7dfe8-392">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-392">ViYankNextGlob</span></span>

<span data-ttu-id="7dfe8-393">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="7dfe8-393">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="7dfe8-394">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-394">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="7dfe8-395">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-395">ViYankNextWord</span></span>

<span data-ttu-id="7dfe8-396">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-396">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="7dfe8-397">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-397">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="7dfe8-398">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="7dfe8-398">ViYankPercent</span></span>

<span data-ttu-id="7dfe8-399">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-399">Yank to/from matching brace.</span></span>

- <span data-ttu-id="7dfe8-400">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-400">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="7dfe8-401">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-401">ViYankPreviousGlob</span></span>

<span data-ttu-id="7dfe8-402">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-402">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="7dfe8-403">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-403">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="7dfe8-404">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-404">ViYankPreviousWord</span></span>

<span data-ttu-id="7dfe8-405">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-405">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="7dfe8-406">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-406">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="7dfe8-407">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="7dfe8-407">ViYankRight</span></span>

<span data-ttu-id="7dfe8-408">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-408">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="7dfe8-409">Modo de comando vi: `<y,l>` , `<y,Space>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-409">Vi command mode: `<y,l>`, `<y,Space>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="7dfe8-410">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-410">ViYankToEndOfLine</span></span>

<span data-ttu-id="7dfe8-411">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-411">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="7dfe8-412">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-412">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="7dfe8-413">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-413">ViYankToFirstChar</span></span>

<span data-ttu-id="7dfe8-414">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-414">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="7dfe8-415">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-415">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="7dfe8-416">Yank</span><span class="sxs-lookup"><span data-stu-id="7dfe8-416">Yank</span></span>

<span data-ttu-id="7dfe8-417">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-417">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="7dfe8-418">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-418">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="7dfe8-419">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="7dfe8-419">YankLastArg</span></span>

<span data-ttu-id="7dfe8-420">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-420">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="7dfe8-421">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-421">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="7dfe8-422">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="7dfe8-422">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="7dfe8-423">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-423">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="7dfe8-424">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-424">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="7dfe8-425">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="7dfe8-425">YankNthArg</span></span>

<span data-ttu-id="7dfe8-426">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-426">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="7dfe8-427">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-427">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="7dfe8-428">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-428">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="7dfe8-429">YankPop</span><span class="sxs-lookup"><span data-stu-id="7dfe8-429">YankPop</span></span>

<span data-ttu-id="7dfe8-430">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-430">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="7dfe8-431">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-431">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="7dfe8-432">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="7dfe8-432">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="7dfe8-433">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-433">BackwardChar</span></span>

<span data-ttu-id="7dfe8-434">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-434">Move the cursor one character to the left.</span></span> <span data-ttu-id="7dfe8-435">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-435">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="7dfe8-436">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-436">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="7dfe8-437">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-437">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>
- <span data-ttu-id="7dfe8-438">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-438">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="7dfe8-439">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-439">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="7dfe8-440">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-440">BackwardWord</span></span>

<span data-ttu-id="7dfe8-441">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-441">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="7dfe8-442">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-442">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7dfe8-443">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-443">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="7dfe8-444">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-444">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="7dfe8-445">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-445">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="7dfe8-446">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-446">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="7dfe8-447">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-447">BeginningOfLine</span></span>

<span data-ttu-id="7dfe8-448">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-448">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="7dfe8-449">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-449">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="7dfe8-450">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-450">Cmd: `<Home>`</span></span>
- <span data-ttu-id="7dfe8-451">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-451">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="7dfe8-452">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-452">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="7dfe8-453">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-453">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="7dfe8-454">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-454">EndOfLine</span></span>

<span data-ttu-id="7dfe8-455">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-455">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="7dfe8-456">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-456">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="7dfe8-457">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-457">Cmd: `<End>`</span></span>
- <span data-ttu-id="7dfe8-458">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-458">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="7dfe8-459">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-459">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="7dfe8-460">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-460">ForwardChar</span></span>

<span data-ttu-id="7dfe8-461">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-461">Move the cursor one character to the right.</span></span> <span data-ttu-id="7dfe8-462">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-462">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="7dfe8-463">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-463">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="7dfe8-464">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-464">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>
- <span data-ttu-id="7dfe8-465">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-465">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="7dfe8-466">Modo de comando vi: `<RightArrow>` , `<Space>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-466">Vi command mode: `<RightArrow>`, `<Space>`, `<l>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="7dfe8-467">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-467">ForwardWord</span></span>

<span data-ttu-id="7dfe8-468">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-468">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="7dfe8-469">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-469">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7dfe8-470">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-470">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="7dfe8-471">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="7dfe8-471">GotoBrace</span></span>

<span data-ttu-id="7dfe8-472">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-472">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="7dfe8-473">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-473">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="7dfe8-474">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-474">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="7dfe8-475">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-475">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="7dfe8-476">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="7dfe8-476">GotoColumn</span></span>

<span data-ttu-id="7dfe8-477">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-477">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="7dfe8-478">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-478">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="7dfe8-479">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-479">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="7dfe8-480">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-480">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="7dfe8-481">Modo de comando vi: `<^>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-481">Vi command mode: `<^>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="7dfe8-482">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-482">MoveToEndOfLine</span></span>

<span data-ttu-id="7dfe8-483">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-483">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="7dfe8-484">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-484">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="7dfe8-485">Próxima</span><span class="sxs-lookup"><span data-stu-id="7dfe8-485">NextLine</span></span>

<span data-ttu-id="7dfe8-486">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-486">Move the cursor to the next line.</span></span>

- <span data-ttu-id="7dfe8-487">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-487">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="7dfe8-488">NextWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-488">NextWord</span></span>

<span data-ttu-id="7dfe8-489">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-489">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="7dfe8-490">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-490">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7dfe8-491">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-491">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="7dfe8-492">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-492">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="7dfe8-493">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-493">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="7dfe8-494">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="7dfe8-494">NextWordEnd</span></span>

<span data-ttu-id="7dfe8-495">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="7dfe8-496">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7dfe8-497">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-497">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="7dfe8-498">Anterior</span><span class="sxs-lookup"><span data-stu-id="7dfe8-498">PreviousLine</span></span>

<span data-ttu-id="7dfe8-499">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-499">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="7dfe8-500">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-500">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="7dfe8-501">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-501">ShellBackwardWord</span></span>

<span data-ttu-id="7dfe8-502">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-502">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="7dfe8-503">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-503">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="7dfe8-504">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-504">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="7dfe8-505">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-505">ShellForwardWord</span></span>

<span data-ttu-id="7dfe8-506">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-506">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="7dfe8-507">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-507">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="7dfe8-508">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-508">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="7dfe8-509">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-509">ShellNextWord</span></span>

<span data-ttu-id="7dfe8-510">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-510">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="7dfe8-511">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-511">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="7dfe8-512">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-512">Function is unbound.</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="7dfe8-513">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-513">ViBackwardWord</span></span>

<span data-ttu-id="7dfe8-514">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="7dfe8-515">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-515">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7dfe8-516">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-516">Vi command mode: `<b>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="7dfe8-517">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-517">ViEndOfGlob</span></span>

<span data-ttu-id="7dfe8-518">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-518">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="7dfe8-519">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-519">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="7dfe8-520">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-520">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="7dfe8-521">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-521">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="7dfe8-522">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-522">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="7dfe8-523">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="7dfe8-523">ViGotoBrace</span></span>

<span data-ttu-id="7dfe8-524">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-524">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="7dfe8-525">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-525">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="7dfe8-526">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="7dfe8-526">ViNextGlob</span></span>

<span data-ttu-id="7dfe8-527">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-527">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="7dfe8-528">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-528">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="7dfe8-529">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-529">ViNextWord</span></span>

<span data-ttu-id="7dfe8-530">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-530">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="7dfe8-531">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-531">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="7dfe8-532">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-532">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="7dfe8-533">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="7dfe8-533">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="7dfe8-534">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="7dfe8-534">BeginningOfHistory</span></span>

<span data-ttu-id="7dfe8-535">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-535">Move to the first item in the history.</span></span>

- <span data-ttu-id="7dfe8-536">Emacs `<Alt+`<>\`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-536">Emacs: `<Alt+`<>\`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="7dfe8-537">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="7dfe8-537">ClearHistory</span></span>

<span data-ttu-id="7dfe8-538">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-538">Clears history in PSReadLine.</span></span> <span data-ttu-id="7dfe8-539">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-539">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="7dfe8-540">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-540">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="7dfe8-541">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="7dfe8-541">EndOfHistory</span></span>

<span data-ttu-id="7dfe8-542">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-542">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="7dfe8-543">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-543">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="7dfe8-544">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="7dfe8-544">ForwardSearchHistory</span></span>

<span data-ttu-id="7dfe8-545">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-545">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="7dfe8-546">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-546">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="7dfe8-547">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-547">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="7dfe8-548">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-548">HistorySearchBackward</span></span>

<span data-ttu-id="7dfe8-549">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-549">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="7dfe8-550">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-550">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="7dfe8-551">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-551">HistorySearchForward</span></span>

<span data-ttu-id="7dfe8-552">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-552">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="7dfe8-553">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-553">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="7dfe8-554">NextHistory</span><span class="sxs-lookup"><span data-stu-id="7dfe8-554">NextHistory</span></span>

<span data-ttu-id="7dfe8-555">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-555">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="7dfe8-556">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-556">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="7dfe8-557">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-557">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="7dfe8-558">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-558">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="7dfe8-559">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-559">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="7dfe8-560">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="7dfe8-560">PreviousHistory</span></span>

<span data-ttu-id="7dfe8-561">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-561">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="7dfe8-562">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-562">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="7dfe8-563">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-563">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="7dfe8-564">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-564">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="7dfe8-565">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-565">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="7dfe8-566">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="7dfe8-566">ReverseSearchHistory</span></span>

<span data-ttu-id="7dfe8-567">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-567">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="7dfe8-568">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-568">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="7dfe8-569">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-569">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="7dfe8-570">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-570">ViSearchHistoryBackward</span></span>

<span data-ttu-id="7dfe8-571">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-571">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="7dfe8-572">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-572">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="7dfe8-573">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-573">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="7dfe8-574">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="7dfe8-574">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="7dfe8-575">Concluir</span><span class="sxs-lookup"><span data-stu-id="7dfe8-575">Complete</span></span>

<span data-ttu-id="7dfe8-576">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-576">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="7dfe8-577">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-577">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="7dfe8-578">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-578">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="7dfe8-579">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-579">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="7dfe8-580">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="7dfe8-580">MenuComplete</span></span>

<span data-ttu-id="7dfe8-581">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-581">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="7dfe8-582">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-582">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="7dfe8-583">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-583">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="7dfe8-584">Cmd `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-584">Cmd: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="7dfe8-585">Emacs `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-585">Emacs: `<Ctrl+Space>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="7dfe8-586">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="7dfe8-586">PossibleCompletions</span></span>

<span data-ttu-id="7dfe8-587">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-587">Display the list of possible completions.</span></span>

- <span data-ttu-id="7dfe8-588">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-588">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="7dfe8-589">Modo de inserção de vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-589">Vi insert mode: `<Ctrl+Space>`</span></span>
- <span data-ttu-id="7dfe8-590">Modo de comando vi: `<Ctrl+Space>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-590">Vi command mode: `<Ctrl+Space>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="7dfe8-591">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="7dfe8-591">TabCompleteNext</span></span>

<span data-ttu-id="7dfe8-592">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-592">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="7dfe8-593">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-593">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="7dfe8-594">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-594">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="7dfe8-595">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="7dfe8-595">TabCompletePrevious</span></span>

<span data-ttu-id="7dfe8-596">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-596">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="7dfe8-597">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-597">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="7dfe8-598">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-598">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="7dfe8-599">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="7dfe8-599">ViTabCompleteNext</span></span>

<span data-ttu-id="7dfe8-600">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-600">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="7dfe8-601">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-601">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="7dfe8-602">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="7dfe8-602">ViTabCompletePrevious</span></span>

<span data-ttu-id="7dfe8-603">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-603">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="7dfe8-604">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-604">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="7dfe8-605">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="7dfe8-605">Miscellaneous functions</span></span>

### <a name="capturescreen"></a><span data-ttu-id="7dfe8-606">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="7dfe8-606">CaptureScreen</span></span>

<span data-ttu-id="7dfe8-607">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-607">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="7dfe8-608">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-608">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="7dfe8-609">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="7dfe8-609">ClearScreen</span></span>

<span data-ttu-id="7dfe8-610">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-610">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="7dfe8-611">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-611">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="7dfe8-612">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-612">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="7dfe8-613">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-613">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="7dfe8-614">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-614">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="7dfe8-615">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="7dfe8-615">DigitArgument</span></span>

<span data-ttu-id="7dfe8-616">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-616">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="7dfe8-617">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-617">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="7dfe8-618">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-618">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="7dfe8-619">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-619">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="7dfe8-620">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="7dfe8-620">InvokePrompt</span></span>

<span data-ttu-id="7dfe8-621">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-621">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="7dfe8-622">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-622">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="7dfe8-623">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-623">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="7dfe8-624">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="7dfe8-624">ScrollDisplayDown</span></span>

<span data-ttu-id="7dfe8-625">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-625">Scroll the display down one screen.</span></span>

- <span data-ttu-id="7dfe8-626">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-626">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="7dfe8-627">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-627">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="7dfe8-628">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-628">ScrollDisplayDownLine</span></span>

<span data-ttu-id="7dfe8-629">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-629">Scroll the display down one line.</span></span>

- <span data-ttu-id="7dfe8-630">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-630">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="7dfe8-631">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-631">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="7dfe8-632">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="7dfe8-632">ScrollDisplayToCursor</span></span>

<span data-ttu-id="7dfe8-633">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-633">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="7dfe8-634">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-634">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="7dfe8-635">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="7dfe8-635">ScrollDisplayTop</span></span>

<span data-ttu-id="7dfe8-636">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-636">Scroll the display to the top.</span></span>

- <span data-ttu-id="7dfe8-637">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-637">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="7dfe8-638">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="7dfe8-638">ScrollDisplayUp</span></span>

<span data-ttu-id="7dfe8-639">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-639">Scroll the display up one screen.</span></span>

- <span data-ttu-id="7dfe8-640">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-640">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="7dfe8-641">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-641">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="7dfe8-642">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-642">ScrollDisplayUpLine</span></span>

<span data-ttu-id="7dfe8-643">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-643">Scroll the display up one line.</span></span>

- <span data-ttu-id="7dfe8-644">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-644">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="7dfe8-645">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-645">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="7dfe8-646">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="7dfe8-646">SelfInsert</span></span>

<span data-ttu-id="7dfe8-647">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-647">Insert the key.</span></span>

- <span data-ttu-id="7dfe8-648">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-648">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="7dfe8-649">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="7dfe8-649">ShowKeyBindings</span></span>

<span data-ttu-id="7dfe8-650">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-650">Show all bound keys.</span></span>

- <span data-ttu-id="7dfe8-651">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-651">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="7dfe8-652">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-652">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="7dfe8-653">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-653">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="7dfe8-654">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="7dfe8-654">ViCommandMode</span></span>

<span data-ttu-id="7dfe8-655">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-655">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="7dfe8-656">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-656">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="7dfe8-657">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-657">ViDigitArgumentInChord</span></span>

<span data-ttu-id="7dfe8-658">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-658">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="7dfe8-659">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-659">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="7dfe8-660">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="7dfe8-660">ViEditVisually</span></span>

<span data-ttu-id="7dfe8-661">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-661">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="7dfe8-662">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-662">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="7dfe8-663">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-663">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="7dfe8-664">ViExit</span><span class="sxs-lookup"><span data-stu-id="7dfe8-664">ViExit</span></span>

<span data-ttu-id="7dfe8-665">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-665">Exits the shell.</span></span>

- <span data-ttu-id="7dfe8-666">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-666">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="7dfe8-667">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="7dfe8-667">ViInsertMode</span></span>

<span data-ttu-id="7dfe8-668">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-668">Switch to Insert mode.</span></span>

- <span data-ttu-id="7dfe8-669">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-669">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="7dfe8-670">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="7dfe8-670">WhatIsKey</span></span>

<span data-ttu-id="7dfe8-671">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-671">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="7dfe8-672">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-672">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="7dfe8-673">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-673">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="7dfe8-674">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="7dfe8-674">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="7dfe8-675">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="7dfe8-675">ExchangePointAndMark</span></span>

<span data-ttu-id="7dfe8-676">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-676">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="7dfe8-677">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-677">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="7dfe8-678">SelectAll</span><span class="sxs-lookup"><span data-stu-id="7dfe8-678">SelectAll</span></span>

<span data-ttu-id="7dfe8-679">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-679">Select the entire line.</span></span>

- <span data-ttu-id="7dfe8-680">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-680">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="7dfe8-681">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-681">SelectBackwardChar</span></span>

<span data-ttu-id="7dfe8-682">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-682">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="7dfe8-683">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-683">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="7dfe8-684">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-684">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="7dfe8-685">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-685">SelectBackwardsLine</span></span>

<span data-ttu-id="7dfe8-686">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-686">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="7dfe8-687">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-687">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="7dfe8-688">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-688">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="7dfe8-689">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-689">SelectBackwardWord</span></span>

<span data-ttu-id="7dfe8-690">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-690">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="7dfe8-691">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-691">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="7dfe8-692">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-692">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="7dfe8-693">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-693">SelectForwardChar</span></span>

<span data-ttu-id="7dfe8-694">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-694">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="7dfe8-695">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-695">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="7dfe8-696">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-696">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="7dfe8-697">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-697">SelectForwardWord</span></span>

<span data-ttu-id="7dfe8-698">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-698">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="7dfe8-699">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-699">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="7dfe8-700">Seleção</span><span class="sxs-lookup"><span data-stu-id="7dfe8-700">SelectLine</span></span>

<span data-ttu-id="7dfe8-701">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-701">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="7dfe8-702">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-702">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="7dfe8-703">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-703">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="7dfe8-704">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-704">SelectNextWord</span></span>

<span data-ttu-id="7dfe8-705">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-705">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="7dfe8-706">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-706">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="7dfe8-707">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-707">SelectShellBackwardWord</span></span>

<span data-ttu-id="7dfe8-708">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-708">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="7dfe8-709">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-709">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="7dfe8-710">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-710">SelectShellForwardWord</span></span>

<span data-ttu-id="7dfe8-711">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-711">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="7dfe8-712">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-712">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="7dfe8-713">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="7dfe8-713">SelectShellNextWord</span></span>

<span data-ttu-id="7dfe8-714">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-714">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="7dfe8-715">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-715">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="7dfe8-716">Definir marca</span><span class="sxs-lookup"><span data-stu-id="7dfe8-716">SetMark</span></span>

<span data-ttu-id="7dfe8-717">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-717">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="7dfe8-718">Emacs `<Ctrl+`>\`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-718">Emacs: `<Ctrl+`>\`</span></span>

## <a name="search-functions"></a><span data-ttu-id="7dfe8-719">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="7dfe8-719">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="7dfe8-720">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="7dfe8-720">CharacterSearch</span></span>

<span data-ttu-id="7dfe8-721">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-721">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="7dfe8-722">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-722">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="7dfe8-723">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-723">Cmd: `<F3>`</span></span>
- <span data-ttu-id="7dfe8-724">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-724">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="7dfe8-725">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-725">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="7dfe8-726">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-726">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="7dfe8-727">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-727">CharacterSearchBackward</span></span>

<span data-ttu-id="7dfe8-728">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-728">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="7dfe8-729">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-729">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="7dfe8-730">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-730">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="7dfe8-731">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-731">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="7dfe8-732">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-732">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="7dfe8-733">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-733">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="7dfe8-734">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="7dfe8-734">RepeatLastCharSearch</span></span>

<span data-ttu-id="7dfe8-735">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-735">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="7dfe8-736">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-736">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="7dfe8-737">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="7dfe8-737">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="7dfe8-738">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-738">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="7dfe8-739">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-739">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="7dfe8-740">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="7dfe8-740">RepeatSearch</span></span>

<span data-ttu-id="7dfe8-741">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-741">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="7dfe8-742">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-742">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="7dfe8-743">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-743">RepeatSearchBackward</span></span>

<span data-ttu-id="7dfe8-744">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-744">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="7dfe8-745">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-745">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="7dfe8-746">SearchChar</span><span class="sxs-lookup"><span data-stu-id="7dfe8-746">SearchChar</span></span>

<span data-ttu-id="7dfe8-747">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-747">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="7dfe8-748">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-748">This is for 't' functionality.</span></span>

- <span data-ttu-id="7dfe8-749">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-749">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="7dfe8-750">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-750">SearchCharBackward</span></span>

<span data-ttu-id="7dfe8-751">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-751">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="7dfe8-752">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-752">This is for 'T' functionality.</span></span>

- <span data-ttu-id="7dfe8-753">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-753">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="7dfe8-754">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="7dfe8-754">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="7dfe8-755">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-755">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="7dfe8-756">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-756">This is for 'T' functionality.</span></span>

- <span data-ttu-id="7dfe8-757">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-757">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="7dfe8-758">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="7dfe8-758">SearchCharWithBackoff</span></span>

<span data-ttu-id="7dfe8-759">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-759">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="7dfe8-760">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-760">This is for 't' functionality.</span></span>

- <span data-ttu-id="7dfe8-761">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-761">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="7dfe8-762">SearchForward</span><span class="sxs-lookup"><span data-stu-id="7dfe8-762">SearchForward</span></span>

<span data-ttu-id="7dfe8-763">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-763">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="7dfe8-764">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-764">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="7dfe8-765">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="7dfe8-765">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="7dfe8-766">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="7dfe8-766">Custom Key Bindings</span></span>

<span data-ttu-id="7dfe8-767">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="7dfe8-767">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="7dfe8-768">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="7dfe8-768">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="7dfe8-769">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-769">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="7dfe8-770">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-770">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="7dfe8-771">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="7dfe8-771">Some useful examples include</span></span>

- <span data-ttu-id="7dfe8-772">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="7dfe8-772">edit the command line</span></span>
- <span data-ttu-id="7dfe8-773">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="7dfe8-773">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="7dfe8-774">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="7dfe8-774">change directories without changing the command line</span></span>

<span data-ttu-id="7dfe8-775">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="7dfe8-775">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="7dfe8-776">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-776">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="7dfe8-777">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-777">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="7dfe8-778">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-778">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="7dfe8-779">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-779">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="7dfe8-780">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-780">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="7dfe8-781">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-781">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="7dfe8-782">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-782">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="7dfe8-783">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-783">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="7dfe8-784">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-784">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="7dfe8-785">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-785">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="7dfe8-786">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-786">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="7dfe8-787">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="7dfe8-787">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="7dfe8-788">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-788">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="7dfe8-789">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-789">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="7dfe8-790">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-790">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="7dfe8-791">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-791">Clear the kill-ring.</span></span>  <span data-ttu-id="7dfe8-792">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-792">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="7dfe8-793">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-793">Delete length characters from start.</span></span>  <span data-ttu-id="7dfe8-794">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-794">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="7dfe8-795">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-795">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="7dfe8-796">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-796">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="7dfe8-797">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-797">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="7dfe8-798">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-798">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

<span data-ttu-id="7dfe8-799">Essa função é usada pelo Get-PSReadLineKeyHandler e provavelmente não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-799">This function is used by Get-PSReadLineKeyHandler and probably isn't useful in a custom key binding.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="7dfe8-800">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-800">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="7dfe8-801">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-801">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="7dfe8-802">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-802">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="7dfe8-803">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-803">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="7dfe8-804">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-804">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="7dfe8-805">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-805">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="7dfe8-806">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-806">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="7dfe8-807">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-807">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="7dfe8-808">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-808">Replace some of the input.</span></span> <span data-ttu-id="7dfe8-809">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-809">This operation supports undo/redo.</span></span> <span data-ttu-id="7dfe8-810">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-810">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="7dfe8-811">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-811">Move the cursor to the given offset.</span></span> <span data-ttu-id="7dfe8-812">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-812">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="7dfe8-813">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-813">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="7dfe8-814">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-814">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="7dfe8-815">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="7dfe8-815">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="7dfe8-816">OBSERVAÇÃO</span><span class="sxs-lookup"><span data-stu-id="7dfe8-816">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="7dfe8-817">COMPATIBILIDADE DO POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="7dfe8-817">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="7dfe8-818">O PSReadLine requer o PowerShell 3,0 ou mais recente e o host do console.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-818">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="7dfe8-819">Ele não funciona no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-819">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="7dfe8-820">Ele funciona no console do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-820">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="7dfe8-821">HISTÓRICO DE COMANDOS</span><span class="sxs-lookup"><span data-stu-id="7dfe8-821">COMMAND HISTORY</span></span>

<span data-ttu-id="7dfe8-822">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-822">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="7dfe8-823">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-823">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="7dfe8-824">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-824">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="7dfe8-825">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="7dfe8-825">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="7dfe8-826">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="7dfe8-826">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="7dfe8-827">Em sistemas não Windows, os arquivos de histórico são armazenados em `$env:XDG_DATA_HOME/powershell/PSReadLine` ou `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="7dfe8-827">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="7dfe8-828">Comentários & CONTRIBUIndo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="7dfe8-828">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="7dfe8-829">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="7dfe8-829">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="7dfe8-830">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="7dfe8-830">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dfe8-831">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="7dfe8-831">SEE ALSO</span></span>

<span data-ttu-id="7dfe8-832">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="7dfe8-832">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
