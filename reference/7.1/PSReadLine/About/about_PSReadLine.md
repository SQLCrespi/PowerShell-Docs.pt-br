---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: 1188b8dc0b4099a7c1dcc472e3b02c2d4fa908bc
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195536"
---
# <a name="psreadline"></a><span data-ttu-id="a9f62-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="a9f62-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="a9f62-106">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="a9f62-106">SHORT DESCRIPTION</span></span>

<span data-ttu-id="a9f62-107">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="a9f62-108">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="a9f62-108">LONG DESCRIPTION</span></span>

<span data-ttu-id="a9f62-109">O PSReadLine 2,0 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-109">PSReadLine 2.0 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="a9f62-110">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="a9f62-110">It provides:</span></span>

- <span data-ttu-id="a9f62-111">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="a9f62-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="a9f62-112">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="a9f62-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="a9f62-113">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="a9f62-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="a9f62-114">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="a9f62-114">Customizable key bindings</span></span>
- <span data-ttu-id="a9f62-115">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="a9f62-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="a9f62-116">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="a9f62-116">Many configuration options</span></span>
- <span data-ttu-id="a9f62-117">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="a9f62-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="a9f62-118">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="a9f62-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="a9f62-119">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="a9f62-119">PowerShell token based "word" movement and kill</span></span>

<span data-ttu-id="a9f62-120">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]** .</span><span class="sxs-lookup"><span data-stu-id="a9f62-120">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]** .</span></span>

> [!NOTE]
> <span data-ttu-id="a9f62-121">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-121">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="a9f62-122">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="a9f62-122">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="a9f62-123">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="a9f62-123">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="a9f62-124">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a9f62-124">You can manually load the module if necessary.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="a9f62-125">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="a9f62-125">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="a9f62-126">Anular</span><span class="sxs-lookup"><span data-stu-id="a9f62-126">Abort</span></span>

<span data-ttu-id="a9f62-127">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="a9f62-127">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="a9f62-128">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-128">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="a9f62-129">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="a9f62-129">AcceptAndGetNext</span></span>

<span data-ttu-id="a9f62-130">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-130">Attempt to execute the current input.</span></span> <span data-ttu-id="a9f62-131">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-131">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="a9f62-132">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-132">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="a9f62-133">Aceitar</span><span class="sxs-lookup"><span data-stu-id="a9f62-133">AcceptLine</span></span>

<span data-ttu-id="a9f62-134">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-134">Attempt to execute the current input.</span></span> <span data-ttu-id="a9f62-135">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-135">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="a9f62-136">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-136">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="a9f62-137">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-137">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="a9f62-138">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-138">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="a9f62-139">AddLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-139">AddLine</span></span>

<span data-ttu-id="a9f62-140">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-140">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="a9f62-141">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="a9f62-141">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="a9f62-142">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-142">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="a9f62-143">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-143">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="a9f62-144">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-144">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="a9f62-145">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-145">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="a9f62-146">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-146">BackwardDeleteChar</span></span>

<span data-ttu-id="a9f62-147">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-147">Delete the character before the cursor.</span></span>

- <span data-ttu-id="a9f62-148">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-148">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="a9f62-149">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-149">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="a9f62-150">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-150">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="a9f62-151">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-151">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="a9f62-152">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-152">BackwardDeleteLine</span></span>

<span data-ttu-id="a9f62-153">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-153">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="a9f62-154">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-154">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="a9f62-155">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-155">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="a9f62-156">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-156">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="a9f62-157">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-157">BackwardDeleteWord</span></span>

<span data-ttu-id="a9f62-158">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-158">Deletes the previous word.</span></span>

- <span data-ttu-id="a9f62-159">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-159">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="a9f62-160">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-160">BackwardKillLine</span></span>

<span data-ttu-id="a9f62-161">Limpe a entrada do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-161">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="a9f62-162">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-162">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a9f62-163">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-163">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="a9f62-164">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-164">BackwardKillWord</span></span>

<span data-ttu-id="a9f62-165">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-165">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="a9f62-166">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-166">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="a9f62-167">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-167">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a9f62-168">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-168">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="a9f62-169">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-169">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="a9f62-170">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-170">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="a9f62-171">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-171">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="a9f62-172">Cancelar</span><span class="sxs-lookup"><span data-stu-id="a9f62-172">CancelLine</span></span>

<span data-ttu-id="a9f62-173">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="a9f62-173">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="a9f62-174">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-174">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="a9f62-175">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-175">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="a9f62-176">Copiar</span><span class="sxs-lookup"><span data-stu-id="a9f62-176">Copy</span></span>

<span data-ttu-id="a9f62-177">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="a9f62-177">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="a9f62-178">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="a9f62-178">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="a9f62-179">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-179">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="a9f62-180">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-180">CopyOrCancelLine</span></span>

<span data-ttu-id="a9f62-181">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-181">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="a9f62-182">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-182">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="a9f62-183">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-183">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="a9f62-184">Recortar</span><span class="sxs-lookup"><span data-stu-id="a9f62-184">Cut</span></span>

<span data-ttu-id="a9f62-185">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="a9f62-185">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="a9f62-186">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-186">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="a9f62-187">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-187">DeleteChar</span></span>

<span data-ttu-id="a9f62-188">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-188">Delete the character under the cursor.</span></span>

- <span data-ttu-id="a9f62-189">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-189">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="a9f62-190">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-190">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="a9f62-191">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-191">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="a9f62-192">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-192">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="a9f62-193">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="a9f62-193">DeleteCharOrExit</span></span>

<span data-ttu-id="a9f62-194">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="a9f62-194">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="a9f62-195">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-195">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="a9f62-196">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="a9f62-196">DeleteEndOfBuffer</span></span>

<span data-ttu-id="a9f62-197">Exclui para o final do buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-197">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="a9f62-198">Modo de comando vi: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-198">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="a9f62-199">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-199">DeleteEndOfWord</span></span>

<span data-ttu-id="a9f62-200">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-200">Delete to the end of the word.</span></span>

- <span data-ttu-id="a9f62-201">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-201">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="a9f62-202">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-202">DeleteLine</span></span>

<span data-ttu-id="a9f62-203">Exclui a linha lógica atual de um buffer de várias linhas, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-203">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="a9f62-204">Modo de comando vi: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-204">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="a9f62-205">DeletePreviousLines</span><span class="sxs-lookup"><span data-stu-id="a9f62-205">DeletePreviousLines</span></span>

<span data-ttu-id="a9f62-206">Exclui as linhas lógicas solicitadas anteriores e a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-206">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="a9f62-207">Modo de comando vi: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-207">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="a9f62-208">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="a9f62-208">DeleteRelativeLines</span></span>

<span data-ttu-id="a9f62-209">Exclui desde o início do buffer até a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-209">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="a9f62-210">Como a maioria dos comandos vi, o `<d,g,g>` comando pode ser anexado com um argumento numérico que especifica um número de linha absoluto, que, junto com o número de linha atual, compõem um intervalo de linhas a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="a9f62-210">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="a9f62-211">Se não for especificado, o argumento numérico usa como padrão 1, que se refere à primeira linha lógica em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-211">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="a9f62-212">O número real de linhas a serem excluídas da multilinha é calculado como a diferença entre o número da linha lógica atual e o argumento numérico especificado, que pode ser, portanto, negativo.</span><span class="sxs-lookup"><span data-stu-id="a9f62-212">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="a9f62-213">Portanto, a parte _relativa_ do nome do método.</span><span class="sxs-lookup"><span data-stu-id="a9f62-213">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="a9f62-214">Modo de comando vi: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-214">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="a9f62-215">DeleteNextLines</span><span class="sxs-lookup"><span data-stu-id="a9f62-215">DeleteNextLines</span></span>

<span data-ttu-id="a9f62-216">Exclui a linha lógica atual e as próximas linhas lógicas solicitadas em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-216">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="a9f62-217">Modo de comando vi: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-217">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="a9f62-218">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-218">DeleteLineToFirstChar</span></span>

<span data-ttu-id="a9f62-219">Exclui o texto do cursor para o primeiro caractere que não seja em branco da linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-219">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="a9f62-220">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-220">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="a9f62-221">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="a9f62-221">DeleteToEnd</span></span>

<span data-ttu-id="a9f62-222">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-222">Delete to the end of the line.</span></span>

- <span data-ttu-id="a9f62-223">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-223">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="a9f62-224">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-224">DeleteWord</span></span>

<span data-ttu-id="a9f62-225">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-225">Delete the next word.</span></span>

- <span data-ttu-id="a9f62-226">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-226">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="a9f62-227">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-227">ForwardDeleteLine</span></span>

<span data-ttu-id="a9f62-228">Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-228">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="a9f62-229">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-229">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="a9f62-230">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-230">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="a9f62-231">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-231">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="a9f62-232">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="a9f62-232">InsertLineAbove</span></span>

<span data-ttu-id="a9f62-233">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-233">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="a9f62-234">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-234">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="a9f62-235">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-235">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="a9f62-236">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="a9f62-236">InsertLineBelow</span></span>

<span data-ttu-id="a9f62-237">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-237">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="a9f62-238">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-238">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="a9f62-239">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-239">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="a9f62-240">InvertCase</span><span class="sxs-lookup"><span data-stu-id="a9f62-240">InvertCase</span></span>

<span data-ttu-id="a9f62-241">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="a9f62-241">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="a9f62-242">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-242">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="a9f62-243">Finalizar</span><span class="sxs-lookup"><span data-stu-id="a9f62-243">KillLine</span></span>

<span data-ttu-id="a9f62-244">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-244">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="a9f62-245">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-245">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a9f62-246">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-246">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="a9f62-247">KillRegion</span><span class="sxs-lookup"><span data-stu-id="a9f62-247">KillRegion</span></span>

<span data-ttu-id="a9f62-248">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="a9f62-248">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="a9f62-249">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-249">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="a9f62-250">KillWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-250">KillWord</span></span>

<span data-ttu-id="a9f62-251">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-251">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="a9f62-252">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-252">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="a9f62-253">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-253">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a9f62-254">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-254">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="a9f62-255">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-255">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="a9f62-256">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-256">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="a9f62-257">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-257">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="a9f62-258">Colar</span><span class="sxs-lookup"><span data-stu-id="a9f62-258">Paste</span></span>

<span data-ttu-id="a9f62-259">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="a9f62-259">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="a9f62-260">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-260">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="a9f62-261">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-261">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="a9f62-262">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-262">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9f62-263">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="a9f62-263">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="a9f62-264">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-264">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="a9f62-265">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="a9f62-265">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="a9f62-266">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-266">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="a9f62-267">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="a9f62-267">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="a9f62-268">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="a9f62-268">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="a9f62-269">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="a9f62-269">PasteAfter</span></span>

<span data-ttu-id="a9f62-270">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-270">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="a9f62-271">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-271">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="a9f62-272">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="a9f62-272">PasteBefore</span></span>

<span data-ttu-id="a9f62-273">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-273">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="a9f62-274">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-274">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="a9f62-275">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="a9f62-275">PrependAndAccept</span></span>

<span data-ttu-id="a9f62-276">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-276">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="a9f62-277">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-277">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="a9f62-278">Refazer</span><span class="sxs-lookup"><span data-stu-id="a9f62-278">Redo</span></span>

<span data-ttu-id="a9f62-279">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-279">Undo an undo.</span></span>

- <span data-ttu-id="a9f62-280">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-280">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="a9f62-281">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-281">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="a9f62-282">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-282">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="a9f62-283">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="a9f62-283">RepeatLastCommand</span></span>

<span data-ttu-id="a9f62-284">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="a9f62-284">Repeat the last text modification.</span></span>

- <span data-ttu-id="a9f62-285">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-285">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="a9f62-286">Reverter</span><span class="sxs-lookup"><span data-stu-id="a9f62-286">RevertLine</span></span>

<span data-ttu-id="a9f62-287">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-287">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="a9f62-288">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-288">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="a9f62-289">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-289">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="a9f62-290">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-290">ShellBackwardKillWord</span></span>

<span data-ttu-id="a9f62-291">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-291">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="a9f62-292">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-292">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="a9f62-293">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-293">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="a9f62-294">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-294">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="a9f62-295">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-295">ShellKillWord</span></span>

<span data-ttu-id="a9f62-296">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-296">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="a9f62-297">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-297">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="a9f62-298">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-298">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="a9f62-299">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-299">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="a9f62-300">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="a9f62-300">SwapCharacters</span></span>

<span data-ttu-id="a9f62-301">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-301">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="a9f62-302">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-302">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="a9f62-303">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-303">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="a9f62-304">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-304">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="a9f62-305">Desfazer</span><span class="sxs-lookup"><span data-stu-id="a9f62-305">Undo</span></span>

<span data-ttu-id="a9f62-306">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-306">Undo a previous edit.</span></span>

- <span data-ttu-id="a9f62-307">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-307">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="a9f62-308">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-308">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="a9f62-309">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-309">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="a9f62-310">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-310">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="a9f62-311">UndoAll</span><span class="sxs-lookup"><span data-stu-id="a9f62-311">UndoAll</span></span>

<span data-ttu-id="a9f62-312">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-312">Undo all previous edits for line.</span></span>

- <span data-ttu-id="a9f62-313">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-313">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="a9f62-314">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="a9f62-314">UnixWordRubout</span></span>

<span data-ttu-id="a9f62-315">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-315">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="a9f62-316">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-316">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="a9f62-317">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-317">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="a9f62-318">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-318">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="a9f62-319">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-319">ValidateAndAcceptLine</span></span>

<span data-ttu-id="a9f62-320">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-320">Attempt to execute the current input.</span></span> <span data-ttu-id="a9f62-321">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-321">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="a9f62-322">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-322">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="a9f62-323">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-323">ViAcceptLine</span></span>

<span data-ttu-id="a9f62-324">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="a9f62-324">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="a9f62-325">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-325">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="a9f62-326">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="a9f62-326">ViAcceptLineOrExit</span></span>

<span data-ttu-id="a9f62-327">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-327">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="a9f62-328">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-328">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="a9f62-329">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-329">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="a9f62-330">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-330">ViAppendLine</span></span>

<span data-ttu-id="a9f62-331">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-331">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="a9f62-332">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-332">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="a9f62-333">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-333">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="a9f62-334">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-334">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="a9f62-335">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-335">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="a9f62-336">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-336">ViBackwardGlob</span></span>

<span data-ttu-id="a9f62-337">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="a9f62-337">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="a9f62-338">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-338">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="a9f62-339">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="a9f62-339">ViDeleteBrace</span></span>

<span data-ttu-id="a9f62-340">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="a9f62-340">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="a9f62-341">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-341">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="a9f62-342">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-342">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="a9f62-343">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-343">Delete to the end of the word.</span></span>

- <span data-ttu-id="a9f62-344">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-344">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="a9f62-345">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-345">ViDeleteGlob</span></span>

<span data-ttu-id="a9f62-346">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="a9f62-346">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="a9f62-347">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-347">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="a9f62-348">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-348">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="a9f62-349">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-349">Deletes until given character.</span></span>

- <span data-ttu-id="a9f62-350">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-350">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="a9f62-351">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-351">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="a9f62-352">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-352">Deletes until given character.</span></span>

- <span data-ttu-id="a9f62-353">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-353">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="a9f62-354">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-354">ViDeleteToChar</span></span>

<span data-ttu-id="a9f62-355">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-355">Deletes until given character.</span></span>

- <span data-ttu-id="a9f62-356">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-356">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="a9f62-357">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-357">ViDeleteToCharBackward</span></span>

<span data-ttu-id="a9f62-358">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-358">Deletes backwards until given character.</span></span>

- <span data-ttu-id="a9f62-359">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-359">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="a9f62-360">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="a9f62-360">ViInsertAtBegining</span></span>

<span data-ttu-id="a9f62-361">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-361">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="a9f62-362">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-362">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="a9f62-363">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="a9f62-363">ViInsertAtEnd</span></span>

<span data-ttu-id="a9f62-364">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-364">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="a9f62-365">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-365">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="a9f62-366">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-366">ViInsertLine</span></span>

<span data-ttu-id="a9f62-367">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-367">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="a9f62-368">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-368">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="a9f62-369">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="a9f62-369">ViInsertWithAppend</span></span>

<span data-ttu-id="a9f62-370">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-370">Append from the current line position.</span></span>

- <span data-ttu-id="a9f62-371">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-371">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="a9f62-372">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="a9f62-372">ViInsertWithDelete</span></span>

<span data-ttu-id="a9f62-373">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="a9f62-373">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="a9f62-374">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-374">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="a9f62-375">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="a9f62-375">ViJoinLines</span></span>

<span data-ttu-id="a9f62-376">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-376">Joins the current line and the next line.</span></span>

- <span data-ttu-id="a9f62-377">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-377">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="a9f62-378">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-378">ViReplaceLine</span></span>

<span data-ttu-id="a9f62-379">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="a9f62-379">Erase the entire command line.</span></span>

- <span data-ttu-id="a9f62-380">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-380">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="a9f62-381">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-381">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="a9f62-382">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-382">Replaces until given character.</span></span>

- <span data-ttu-id="a9f62-383">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-383">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="a9f62-384">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-384">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="a9f62-385">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-385">Replaces until given character.</span></span>

- <span data-ttu-id="a9f62-386">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-386">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="a9f62-387">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-387">ViReplaceToChar</span></span>

<span data-ttu-id="a9f62-388">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-388">Deletes until given character.</span></span>

- <span data-ttu-id="a9f62-389">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-389">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="a9f62-390">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-390">ViReplaceToCharBackward</span></span>

<span data-ttu-id="a9f62-391">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="a9f62-391">Replaces until given character.</span></span>

- <span data-ttu-id="a9f62-392">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-392">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="a9f62-393">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-393">ViYankBeginningOfLine</span></span>

<span data-ttu-id="a9f62-394">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-394">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="a9f62-395">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-395">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="a9f62-396">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-396">ViYankEndOfGlob</span></span>

<span data-ttu-id="a9f62-397">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="a9f62-397">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="a9f62-398">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-398">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="a9f62-399">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-399">ViYankEndOfWord</span></span>

<span data-ttu-id="a9f62-400">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="a9f62-400">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="a9f62-401">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-401">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="a9f62-402">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="a9f62-402">ViYankLeft</span></span>

<span data-ttu-id="a9f62-403">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-403">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="a9f62-404">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-404">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="a9f62-405">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-405">ViYankLine</span></span>

<span data-ttu-id="a9f62-406">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-406">Yank the entire buffer.</span></span>

- <span data-ttu-id="a9f62-407">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-407">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="a9f62-408">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-408">ViYankNextGlob</span></span>

<span data-ttu-id="a9f62-409">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="a9f62-409">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="a9f62-410">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-410">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="a9f62-411">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-411">ViYankNextWord</span></span>

<span data-ttu-id="a9f62-412">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-412">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="a9f62-413">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-413">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="a9f62-414">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="a9f62-414">ViYankPercent</span></span>

<span data-ttu-id="a9f62-415">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="a9f62-415">Yank to/from matching brace.</span></span>

- <span data-ttu-id="a9f62-416">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-416">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="a9f62-417">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-417">ViYankPreviousGlob</span></span>

<span data-ttu-id="a9f62-418">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-418">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="a9f62-419">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-419">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="a9f62-420">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-420">ViYankPreviousWord</span></span>

<span data-ttu-id="a9f62-421">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-421">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="a9f62-422">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-422">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="a9f62-423">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="a9f62-423">ViYankRight</span></span>

<span data-ttu-id="a9f62-424">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-424">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="a9f62-425">Modo de comando vi: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-425">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="a9f62-426">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-426">ViYankToEndOfLine</span></span>

<span data-ttu-id="a9f62-427">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-427">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="a9f62-428">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-428">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="a9f62-429">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-429">ViYankToFirstChar</span></span>

<span data-ttu-id="a9f62-430">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-430">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="a9f62-431">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-431">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="a9f62-432">Yank</span><span class="sxs-lookup"><span data-stu-id="a9f62-432">Yank</span></span>

<span data-ttu-id="a9f62-433">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-433">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="a9f62-434">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-434">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="a9f62-435">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="a9f62-435">YankLastArg</span></span>

<span data-ttu-id="a9f62-436">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-436">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="a9f62-437">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="a9f62-437">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="a9f62-438">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="a9f62-438">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="a9f62-439">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-439">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="a9f62-440">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-440">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="a9f62-441">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="a9f62-441">YankNthArg</span></span>

<span data-ttu-id="a9f62-442">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-442">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="a9f62-443">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="a9f62-443">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="a9f62-444">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-444">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="a9f62-445">YankPop</span><span class="sxs-lookup"><span data-stu-id="a9f62-445">YankPop</span></span>

<span data-ttu-id="a9f62-446">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-446">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="a9f62-447">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-447">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="a9f62-448">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="a9f62-448">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="a9f62-449">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-449">BackwardChar</span></span>

<span data-ttu-id="a9f62-450">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="a9f62-450">Move the cursor one character to the left.</span></span> <span data-ttu-id="a9f62-451">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-451">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="a9f62-452">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-452">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="a9f62-453">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-453">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="a9f62-454">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-454">BackwardWord</span></span>

<span data-ttu-id="a9f62-455">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-455">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="a9f62-456">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a9f62-456">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a9f62-457">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-457">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="a9f62-458">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-458">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="a9f62-459">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-459">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="a9f62-460">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-460">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="a9f62-461">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-461">BeginningOfLine</span></span>

<span data-ttu-id="a9f62-462">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-462">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="a9f62-463">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-463">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="a9f62-464">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-464">Cmd: `<Home>`</span></span>
- <span data-ttu-id="a9f62-465">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-465">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="a9f62-466">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-466">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="a9f62-467">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-467">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="a9f62-468">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-468">EndOfLine</span></span>

<span data-ttu-id="a9f62-469">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-469">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="a9f62-470">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-470">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="a9f62-471">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-471">Cmd: `<End>`</span></span>
- <span data-ttu-id="a9f62-472">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-472">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="a9f62-473">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-473">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="a9f62-474">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-474">ForwardChar</span></span>

<span data-ttu-id="a9f62-475">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="a9f62-475">Move the cursor one character to the right.</span></span> <span data-ttu-id="a9f62-476">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-476">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="a9f62-477">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-477">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="a9f62-478">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-478">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="a9f62-479">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-479">ForwardWord</span></span>

<span data-ttu-id="a9f62-480">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-480">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="a9f62-481">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a9f62-481">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a9f62-482">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-482">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="a9f62-483">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="a9f62-483">GotoBrace</span></span>

<span data-ttu-id="a9f62-484">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="a9f62-484">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="a9f62-485">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-485">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="a9f62-486">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-486">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="a9f62-487">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-487">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="a9f62-488">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="a9f62-488">GotoColumn</span></span>

<span data-ttu-id="a9f62-489">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="a9f62-489">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="a9f62-490">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-490">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="a9f62-491">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-491">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="a9f62-492">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-492">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="a9f62-493">Modo de comando vi: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-493">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="a9f62-494">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-494">MoveToEndOfLine</span></span>

<span data-ttu-id="a9f62-495">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-495">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="a9f62-496">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-496">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="a9f62-497">Próxima</span><span class="sxs-lookup"><span data-stu-id="a9f62-497">NextLine</span></span>

<span data-ttu-id="a9f62-498">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-498">Move the cursor to the next line.</span></span>

- <span data-ttu-id="a9f62-499">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-499">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="a9f62-500">NextWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-500">NextWord</span></span>

<span data-ttu-id="a9f62-501">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-501">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="a9f62-502">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a9f62-502">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a9f62-503">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-503">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="a9f62-504">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-504">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="a9f62-505">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-505">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="a9f62-506">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="a9f62-506">NextWordEnd</span></span>

<span data-ttu-id="a9f62-507">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-507">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="a9f62-508">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a9f62-508">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a9f62-509">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-509">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="a9f62-510">Anterior</span><span class="sxs-lookup"><span data-stu-id="a9f62-510">PreviousLine</span></span>

<span data-ttu-id="a9f62-511">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-511">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="a9f62-512">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-512">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="a9f62-513">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-513">ShellBackwardWord</span></span>

<span data-ttu-id="a9f62-514">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-514">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="a9f62-515">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-515">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="a9f62-516">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-516">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="a9f62-517">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-517">ShellForwardWord</span></span>

<span data-ttu-id="a9f62-518">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-518">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="a9f62-519">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-519">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="a9f62-520">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-520">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="a9f62-521">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-521">ShellNextWord</span></span>

<span data-ttu-id="a9f62-522">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="a9f62-523">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-523">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="a9f62-524">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-524">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="a9f62-525">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-525">ViBackwardChar</span></span>

<span data-ttu-id="a9f62-526">Mover o cursor um caractere para a esquerda no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="a9f62-526">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="a9f62-527">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-527">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="a9f62-528">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-528">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="a9f62-529">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-529">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="a9f62-530">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-530">ViBackwardWord</span></span>

<span data-ttu-id="a9f62-531">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-531">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="a9f62-532">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a9f62-532">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a9f62-533">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-533">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="a9f62-534">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-534">ViForwardChar</span></span>

<span data-ttu-id="a9f62-535">Mover o cursor um caractere para a direita no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="a9f62-535">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="a9f62-536">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-536">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="a9f62-537">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-537">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="a9f62-538">Modo de comando vi: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-538">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="a9f62-539">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-539">ViEndOfGlob</span></span>

<span data-ttu-id="a9f62-540">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="a9f62-540">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="a9f62-541">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-541">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="a9f62-542">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-542">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="a9f62-543">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-543">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="a9f62-544">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-544">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="a9f62-545">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="a9f62-545">ViGotoBrace</span></span>

<span data-ttu-id="a9f62-546">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="a9f62-546">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="a9f62-547">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-547">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="a9f62-548">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="a9f62-548">ViNextGlob</span></span>

<span data-ttu-id="a9f62-549">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-549">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="a9f62-550">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-550">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="a9f62-551">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-551">ViNextWord</span></span>

<span data-ttu-id="a9f62-552">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-552">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="a9f62-553">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a9f62-553">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="a9f62-554">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-554">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="a9f62-555">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="a9f62-555">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="a9f62-556">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="a9f62-556">BeginningOfHistory</span></span>

<span data-ttu-id="a9f62-557">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="a9f62-557">Move to the first item in the history.</span></span>

- <span data-ttu-id="a9f62-558">Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-558">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="a9f62-559">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="a9f62-559">ClearHistory</span></span>

<span data-ttu-id="a9f62-560">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="a9f62-560">Clears history in PSReadLine.</span></span> <span data-ttu-id="a9f62-561">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-561">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="a9f62-562">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-562">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="a9f62-563">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="a9f62-563">EndOfHistory</span></span>

<span data-ttu-id="a9f62-564">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="a9f62-564">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="a9f62-565">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-565">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="a9f62-566">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="a9f62-566">ForwardSearchHistory</span></span>

<span data-ttu-id="a9f62-567">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="a9f62-567">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="a9f62-568">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-568">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="a9f62-569">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-569">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="a9f62-570">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-570">HistorySearchBackward</span></span>

<span data-ttu-id="a9f62-571">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-571">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="a9f62-572">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-572">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="a9f62-573">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="a9f62-573">HistorySearchForward</span></span>

<span data-ttu-id="a9f62-574">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-574">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="a9f62-575">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-575">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="a9f62-576">NextHistory</span><span class="sxs-lookup"><span data-stu-id="a9f62-576">NextHistory</span></span>

<span data-ttu-id="a9f62-577">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="a9f62-577">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="a9f62-578">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-578">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="a9f62-579">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-579">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="a9f62-580">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-580">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="a9f62-581">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-581">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="a9f62-582">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="a9f62-582">PreviousHistory</span></span>

<span data-ttu-id="a9f62-583">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="a9f62-583">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="a9f62-584">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-584">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="a9f62-585">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-585">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="a9f62-586">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-586">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="a9f62-587">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="a9f62-587">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="a9f62-588">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="a9f62-588">ReverseSearchHistory</span></span>

<span data-ttu-id="a9f62-589">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="a9f62-589">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="a9f62-590">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-590">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="a9f62-591">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-591">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="a9f62-592">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-592">ViSearchHistoryBackward</span></span>

<span data-ttu-id="a9f62-593">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="a9f62-593">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="a9f62-594">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-594">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="a9f62-595">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-595">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="a9f62-596">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="a9f62-596">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="a9f62-597">Concluir</span><span class="sxs-lookup"><span data-stu-id="a9f62-597">Complete</span></span>

<span data-ttu-id="a9f62-598">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-598">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="a9f62-599">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="a9f62-599">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="a9f62-600">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="a9f62-600">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="a9f62-601">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-601">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="a9f62-602">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="a9f62-602">MenuComplete</span></span>

<span data-ttu-id="a9f62-603">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-603">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="a9f62-604">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="a9f62-604">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="a9f62-605">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="a9f62-605">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="a9f62-606">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-606">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="a9f62-607">Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-607">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="a9f62-608">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="a9f62-608">PossibleCompletions</span></span>

<span data-ttu-id="a9f62-609">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="a9f62-609">Display the list of possible completions.</span></span>

- <span data-ttu-id="a9f62-610">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-610">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="a9f62-611">Modo de inserção de vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-611">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="a9f62-612">Modo de comando vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-612">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="a9f62-613">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="a9f62-613">TabCompleteNext</span></span>

<span data-ttu-id="a9f62-614">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="a9f62-614">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="a9f62-615">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-615">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="a9f62-616">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-616">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="a9f62-617">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="a9f62-617">TabCompletePrevious</span></span>

<span data-ttu-id="a9f62-618">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-618">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="a9f62-619">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-619">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="a9f62-620">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-620">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="a9f62-621">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="a9f62-621">ViTabCompleteNext</span></span>

<span data-ttu-id="a9f62-622">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="a9f62-622">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="a9f62-623">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-623">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="a9f62-624">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="a9f62-624">ViTabCompletePrevious</span></span>

<span data-ttu-id="a9f62-625">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="a9f62-625">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="a9f62-626">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-626">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="a9f62-627">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="a9f62-627">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="a9f62-628">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-628">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="a9f62-629">Aceite a próxima palavra da sugestão embutida ou selecionada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-629">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="a9f62-630">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-630">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="a9f62-631">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="a9f62-631">AcceptSuggestion</span></span>

<span data-ttu-id="a9f62-632">Aceite a sugestão embutida ou selecionada atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-632">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="a9f62-633">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-633">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="a9f62-634">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="a9f62-634">CaptureScreen</span></span>

<span data-ttu-id="a9f62-635">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="a9f62-635">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="a9f62-636">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-636">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="a9f62-637">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="a9f62-637">ClearScreen</span></span>

<span data-ttu-id="a9f62-638">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="a9f62-638">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="a9f62-639">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-639">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="a9f62-640">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-640">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="a9f62-641">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-641">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="a9f62-642">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-642">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="a9f62-643">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="a9f62-643">DigitArgument</span></span>

<span data-ttu-id="a9f62-644">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="a9f62-644">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="a9f62-645">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="a9f62-645">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="a9f62-646">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="a9f62-646">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="a9f62-647">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-647">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="a9f62-648">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="a9f62-648">InvokePrompt</span></span>

<span data-ttu-id="a9f62-649">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="a9f62-649">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="a9f62-650">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a9f62-650">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="a9f62-651">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-651">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="a9f62-652">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="a9f62-652">ScrollDisplayDown</span></span>

<span data-ttu-id="a9f62-653">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="a9f62-653">Scroll the display down one screen.</span></span>

- <span data-ttu-id="a9f62-654">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-654">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="a9f62-655">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-655">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="a9f62-656">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-656">ScrollDisplayDownLine</span></span>

<span data-ttu-id="a9f62-657">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="a9f62-657">Scroll the display down one line.</span></span>

- <span data-ttu-id="a9f62-658">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-658">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="a9f62-659">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-659">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="a9f62-660">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="a9f62-660">ScrollDisplayToCursor</span></span>

<span data-ttu-id="a9f62-661">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-661">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="a9f62-662">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-662">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="a9f62-663">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="a9f62-663">ScrollDisplayTop</span></span>

<span data-ttu-id="a9f62-664">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-664">Scroll the display to the top.</span></span>

- <span data-ttu-id="a9f62-665">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-665">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="a9f62-666">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="a9f62-666">ScrollDisplayUp</span></span>

<span data-ttu-id="a9f62-667">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="a9f62-667">Scroll the display up one screen.</span></span>

- <span data-ttu-id="a9f62-668">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-668">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="a9f62-669">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-669">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="a9f62-670">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-670">ScrollDisplayUpLine</span></span>

<span data-ttu-id="a9f62-671">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="a9f62-671">Scroll the display up one line.</span></span>

- <span data-ttu-id="a9f62-672">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-672">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="a9f62-673">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-673">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="a9f62-674">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="a9f62-674">SelfInsert</span></span>

<span data-ttu-id="a9f62-675">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="a9f62-675">Insert the key.</span></span>

- <span data-ttu-id="a9f62-676">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-676">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="a9f62-677">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="a9f62-677">ShowKeyBindings</span></span>

<span data-ttu-id="a9f62-678">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-678">Show all bound keys.</span></span>

- <span data-ttu-id="a9f62-679">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-679">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="a9f62-680">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-680">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="a9f62-681">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-681">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="a9f62-682">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="a9f62-682">ViCommandMode</span></span>

<span data-ttu-id="a9f62-683">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="a9f62-683">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="a9f62-684">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-684">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="a9f62-685">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="a9f62-685">ViDigitArgumentInChord</span></span>

<span data-ttu-id="a9f62-686">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="a9f62-686">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="a9f62-687">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-687">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="a9f62-688">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="a9f62-688">ViEditVisually</span></span>

<span data-ttu-id="a9f62-689">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="a9f62-689">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="a9f62-690">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-690">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="a9f62-691">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-691">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="a9f62-692">ViExit</span><span class="sxs-lookup"><span data-stu-id="a9f62-692">ViExit</span></span>

<span data-ttu-id="a9f62-693">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-693">Exits the shell.</span></span>

- <span data-ttu-id="a9f62-694">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-694">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="a9f62-695">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="a9f62-695">ViInsertMode</span></span>

<span data-ttu-id="a9f62-696">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="a9f62-696">Switch to Insert mode.</span></span>

- <span data-ttu-id="a9f62-697">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-697">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="a9f62-698">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="a9f62-698">WhatIsKey</span></span>

<span data-ttu-id="a9f62-699">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-699">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="a9f62-700">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-700">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="a9f62-701">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-701">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="a9f62-702">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="a9f62-702">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="a9f62-703">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="a9f62-703">ExchangePointAndMark</span></span>

<span data-ttu-id="a9f62-704">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-704">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="a9f62-705">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-705">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="a9f62-706">SelectAll</span><span class="sxs-lookup"><span data-stu-id="a9f62-706">SelectAll</span></span>

<span data-ttu-id="a9f62-707">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="a9f62-707">Select the entire line.</span></span>

- <span data-ttu-id="a9f62-708">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-708">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="a9f62-709">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-709">SelectBackwardChar</span></span>

<span data-ttu-id="a9f62-710">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-710">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="a9f62-711">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-711">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="a9f62-712">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-712">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="a9f62-713">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-713">SelectBackwardsLine</span></span>

<span data-ttu-id="a9f62-714">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-714">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="a9f62-715">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-715">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="a9f62-716">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-716">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="a9f62-717">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-717">SelectBackwardWord</span></span>

<span data-ttu-id="a9f62-718">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="a9f62-718">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="a9f62-719">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-719">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="a9f62-720">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-720">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="a9f62-721">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-721">SelectForwardChar</span></span>

<span data-ttu-id="a9f62-722">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-722">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="a9f62-723">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-723">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="a9f62-724">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-724">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="a9f62-725">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-725">SelectForwardWord</span></span>

<span data-ttu-id="a9f62-726">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="a9f62-726">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="a9f62-727">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-727">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="a9f62-728">Seleção</span><span class="sxs-lookup"><span data-stu-id="a9f62-728">SelectLine</span></span>

<span data-ttu-id="a9f62-729">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="a9f62-729">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="a9f62-730">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-730">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="a9f62-731">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-731">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="a9f62-732">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-732">SelectNextWord</span></span>

<span data-ttu-id="a9f62-733">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="a9f62-733">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="a9f62-734">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-734">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="a9f62-735">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-735">SelectShellBackwardWord</span></span>

<span data-ttu-id="a9f62-736">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="a9f62-736">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="a9f62-737">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-737">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="a9f62-738">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-738">SelectShellForwardWord</span></span>

<span data-ttu-id="a9f62-739">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="a9f62-739">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="a9f62-740">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-740">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="a9f62-741">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="a9f62-741">SelectShellNextWord</span></span>

<span data-ttu-id="a9f62-742">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="a9f62-742">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="a9f62-743">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-743">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="a9f62-744">Definir marca</span><span class="sxs-lookup"><span data-stu-id="a9f62-744">SetMark</span></span>

<span data-ttu-id="a9f62-745">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="a9f62-745">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="a9f62-746">Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-746">Emacs: `<Ctrl+@>`</span></span>

## <a name="search-functions"></a><span data-ttu-id="a9f62-747">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="a9f62-747">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="a9f62-748">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="a9f62-748">CharacterSearch</span></span>

<span data-ttu-id="a9f62-749">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-749">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="a9f62-750">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="a9f62-750">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="a9f62-751">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-751">Cmd: `<F3>`</span></span>
- <span data-ttu-id="a9f62-752">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-752">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="a9f62-753">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-753">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="a9f62-754">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-754">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="a9f62-755">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-755">CharacterSearchBackward</span></span>

<span data-ttu-id="a9f62-756">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-756">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="a9f62-757">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="a9f62-757">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="a9f62-758">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-758">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="a9f62-759">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-759">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="a9f62-760">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-760">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="a9f62-761">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-761">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="a9f62-762">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="a9f62-762">RepeatLastCharSearch</span></span>

<span data-ttu-id="a9f62-763">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-763">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="a9f62-764">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-764">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="a9f62-765">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="a9f62-765">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="a9f62-766">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="a9f62-766">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="a9f62-767">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-767">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="a9f62-768">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="a9f62-768">RepeatSearch</span></span>

<span data-ttu-id="a9f62-769">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="a9f62-769">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="a9f62-770">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-770">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="a9f62-771">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-771">RepeatSearchBackward</span></span>

<span data-ttu-id="a9f62-772">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="a9f62-772">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="a9f62-773">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-773">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="a9f62-774">SearchChar</span><span class="sxs-lookup"><span data-stu-id="a9f62-774">SearchChar</span></span>

<span data-ttu-id="a9f62-775">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-775">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="a9f62-776">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="a9f62-776">This is for 't' functionality.</span></span>

- <span data-ttu-id="a9f62-777">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-777">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="a9f62-778">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="a9f62-778">SearchCharBackward</span></span>

<span data-ttu-id="a9f62-779">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-779">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="a9f62-780">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="a9f62-780">This is for 'T' functionality.</span></span>

- <span data-ttu-id="a9f62-781">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-781">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="a9f62-782">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="a9f62-782">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="a9f62-783">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-783">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="a9f62-784">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="a9f62-784">This is for 'T' functionality.</span></span>

- <span data-ttu-id="a9f62-785">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-785">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="a9f62-786">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="a9f62-786">SearchCharWithBackoff</span></span>

<span data-ttu-id="a9f62-787">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="a9f62-787">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="a9f62-788">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="a9f62-788">This is for 't' functionality.</span></span>

- <span data-ttu-id="a9f62-789">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-789">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="a9f62-790">SearchForward</span><span class="sxs-lookup"><span data-stu-id="a9f62-790">SearchForward</span></span>

<span data-ttu-id="a9f62-791">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="a9f62-791">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="a9f62-792">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-792">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="a9f62-793">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="a9f62-793">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="a9f62-794">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="a9f62-794">Custom Key Bindings</span></span>

<span data-ttu-id="a9f62-795">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="a9f62-795">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="a9f62-796">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="a9f62-796">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="a9f62-797">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="a9f62-797">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="a9f62-798">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="a9f62-798">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="a9f62-799">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="a9f62-799">Some useful examples include</span></span>

- <span data-ttu-id="a9f62-800">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="a9f62-800">edit the command line</span></span>
- <span data-ttu-id="a9f62-801">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="a9f62-801">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="a9f62-802">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="a9f62-802">change directories without changing the command line</span></span>

<span data-ttu-id="a9f62-803">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="a9f62-803">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="a9f62-804">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-804">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="a9f62-805">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="a9f62-805">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="a9f62-806">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="a9f62-806">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="a9f62-807">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="a9f62-807">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="a9f62-808">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="a9f62-808">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="a9f62-809">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="a9f62-809">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="a9f62-810">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="a9f62-810">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="a9f62-811">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="a9f62-811">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="a9f62-812">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="a9f62-812">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="a9f62-813">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a9f62-813">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="a9f62-814">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="a9f62-814">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="a9f62-815">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="a9f62-815">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="a9f62-816">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="a9f62-816">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="a9f62-817">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-817">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="a9f62-818">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="a9f62-818">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="a9f62-819">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="a9f62-819">Clear the kill-ring.</span></span>  <span data-ttu-id="a9f62-820">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="a9f62-820">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="a9f62-821">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="a9f62-821">Delete length characters from start.</span></span>  <span data-ttu-id="a9f62-822">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-822">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="a9f62-823">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="a9f62-823">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="a9f62-824">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-824">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="a9f62-825">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="a9f62-825">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="a9f62-826">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="a9f62-826">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="a9f62-827">Essas duas funções são usadas pelo `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="a9f62-827">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="a9f62-828">O primeiro é usado para obter todas as associações de chave.</span><span class="sxs-lookup"><span data-stu-id="a9f62-828">The first is used to get all key bindings.</span></span> <span data-ttu-id="a9f62-829">O segundo é usado para obter associações de chave específicas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-829">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="a9f62-830">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-830">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="a9f62-831">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="a9f62-831">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="a9f62-832">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="a9f62-832">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="a9f62-833">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="a9f62-833">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="a9f62-834">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-834">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="a9f62-835">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="a9f62-835">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="a9f62-836">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-836">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="a9f62-837">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="a9f62-837">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="a9f62-838">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-838">Replace some of the input.</span></span> <span data-ttu-id="a9f62-839">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-839">This operation supports undo/redo.</span></span> <span data-ttu-id="a9f62-840">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-840">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="a9f62-841">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="a9f62-841">Move the cursor to the given offset.</span></span> <span data-ttu-id="a9f62-842">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="a9f62-842">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="a9f62-843">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="a9f62-843">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="a9f62-844">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="a9f62-844">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="a9f62-845">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="a9f62-845">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="a9f62-846">OBSERVAÇÃO</span><span class="sxs-lookup"><span data-stu-id="a9f62-846">NOTE</span></span>

### <a name="powershell-compatibility"></a><span data-ttu-id="a9f62-847">COMPATIBILIDADE DO POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="a9f62-847">POWERSHELL COMPATIBILITY</span></span>

<span data-ttu-id="a9f62-848">O PSReadLine requer o PowerShell 3,0 ou mais recente e o host do console.</span><span class="sxs-lookup"><span data-stu-id="a9f62-848">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="a9f62-849">Ele não funciona no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9f62-849">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="a9f62-850">Ele funciona no console do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a9f62-850">It does work in the console of Visual Studio Code.</span></span>

### <a name="command-history"></a><span data-ttu-id="a9f62-851">HISTÓRICO DE COMANDOS</span><span class="sxs-lookup"><span data-stu-id="a9f62-851">COMMAND HISTORY</span></span>

<span data-ttu-id="a9f62-852">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a9f62-852">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="a9f62-853">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="a9f62-853">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="a9f62-854">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="a9f62-854">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="a9f62-855">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="a9f62-855">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="a9f62-856">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="a9f62-856">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="a9f62-857">Em sistemas não Windows, os arquivos de histórico são armazenados em `$env:XDG_DATA_HOME/powershell/PSReadLine` ou `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="a9f62-857">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="a9f62-858">Comentários & CONTRIBUIndo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="a9f62-858">FEEDBACK & CONTRIBUTING TO PSReadLine</span></span>

[<span data-ttu-id="a9f62-859">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="a9f62-859">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="a9f62-860">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="a9f62-860">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9f62-861">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="a9f62-861">SEE ALSO</span></span>

<span data-ttu-id="a9f62-862">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="a9f62-862">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>

