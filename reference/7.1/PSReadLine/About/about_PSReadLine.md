---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
keywords: powershell
Locale: en-US
ms.date: 11/16/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: 6d52bb04118914a9ccca5d3442a9d1915c1c2818
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94692268"
---
# <a name="psreadline"></a><span data-ttu-id="d6da5-104">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-104">PSReadLine</span></span>

## <a name="about_psreadline"></a><span data-ttu-id="d6da5-105">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-105">about_PSReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="d6da5-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="d6da5-106">Short Description</span></span>

<span data-ttu-id="d6da5-107">O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-107">PSReadLine provides an improved command-line editing experience in the PowerShell console.</span></span>

## <a name="long-description"></a><span data-ttu-id="d6da5-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="d6da5-108">Long Description</span></span>

<span data-ttu-id="d6da5-109">O PSReadLine 2,1 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-109">PSReadLine 2.1 provides a powerful command-line editing experience for the PowerShell console.</span></span> <span data-ttu-id="d6da5-110">Ele fornece:</span><span class="sxs-lookup"><span data-stu-id="d6da5-110">It provides:</span></span>

- <span data-ttu-id="d6da5-111">Cor da sintaxe da linha de comando</span><span class="sxs-lookup"><span data-stu-id="d6da5-111">Syntax coloring of the command line</span></span>
- <span data-ttu-id="d6da5-112">Uma indicação visual de erros de sintaxe</span><span class="sxs-lookup"><span data-stu-id="d6da5-112">A visual indication of syntax errors</span></span>
- <span data-ttu-id="d6da5-113">Uma experiência de várias linhas melhor (edição e histórico)</span><span class="sxs-lookup"><span data-stu-id="d6da5-113">A better multi-line experience (both editing and history)</span></span>
- <span data-ttu-id="d6da5-114">Associações de chave personalizáveis</span><span class="sxs-lookup"><span data-stu-id="d6da5-114">Customizable key bindings</span></span>
- <span data-ttu-id="d6da5-115">Modos cmd e Emacs</span><span class="sxs-lookup"><span data-stu-id="d6da5-115">Cmd and Emacs modes</span></span>
- <span data-ttu-id="d6da5-116">Muitas opções de configuração</span><span class="sxs-lookup"><span data-stu-id="d6da5-116">Many configuration options</span></span>
- <span data-ttu-id="d6da5-117">Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)</span><span class="sxs-lookup"><span data-stu-id="d6da5-117">Bash style completion (optional in Cmd mode, default in Emacs mode)</span></span>
- <span data-ttu-id="d6da5-118">Emacs Yank/Kill-Ring</span><span class="sxs-lookup"><span data-stu-id="d6da5-118">Emacs yank/kill-ring</span></span>
- <span data-ttu-id="d6da5-119">"Word" com base no token do PowerShell movimentação e eliminação</span><span class="sxs-lookup"><span data-stu-id="d6da5-119">PowerShell token based "word" movement and kill</span></span>
- <span data-ttu-id="d6da5-120">IntelliSense preditiva</span><span class="sxs-lookup"><span data-stu-id="d6da5-120">Predictive IntelliSense</span></span>

<span data-ttu-id="d6da5-121">O PSReadLine requer o PowerShell 3,0 ou mais recente e o host do console.</span><span class="sxs-lookup"><span data-stu-id="d6da5-121">PSReadLine requires PowerShell 3.0, or newer, and the console host.</span></span> <span data-ttu-id="d6da5-122">Ele não funciona no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-122">It does not work in PowerShell ISE.</span></span> <span data-ttu-id="d6da5-123">Ele funciona no console do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="d6da5-123">It does work in the console of Visual Studio Code.</span></span>

<span data-ttu-id="d6da5-124">O PSReadLine 2.1.0 é fornecido com o PowerShell 7,1 e tem suporte em todas as versões com suporte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-124">PSReadLine 2.1.0 ships with PowerShell 7.1 and is supported in all supported versions of PowerShell.</span></span> <span data-ttu-id="d6da5-125">Ele está disponível para instalação do Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-125">It is available to install from the PowerShell Gallery.</span></span>
<span data-ttu-id="d6da5-126">Para instalar o PSReadLine 2.1.0 em uma versão com suporte do PowerShell, execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6da5-126">To install PSReadLine 2.1.0 in a supported version of PowerShell run the following command.</span></span>

```powershell
Install-Module -Name PSReadLine -RequiredVersion 2.1.0
```

> [!NOTE]
> <span data-ttu-id="d6da5-127">A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-127">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="d6da5-128">Atualmente, o PSReadLine não funciona bem com os leitores de tela.</span><span class="sxs-lookup"><span data-stu-id="d6da5-128">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="d6da5-129">A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="d6da5-129">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="d6da5-130">Você pode carregar o módulo manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d6da5-130">You can manually load the module if necessary.</span></span>

## <a name="predictive-intellisense"></a><span data-ttu-id="d6da5-131">IntelliSense preditiva</span><span class="sxs-lookup"><span data-stu-id="d6da5-131">Predictive IntelliSense</span></span>

<span data-ttu-id="d6da5-132">O IntelliSense preditiva é uma adição ao conceito de preenchimento com Tab que ajuda o usuário a concluir comandos com êxito.</span><span class="sxs-lookup"><span data-stu-id="d6da5-132">Predictive IntelliSense is an addition to the concept of tab completion that assists the user in successfully completing commands.</span></span> <span data-ttu-id="d6da5-133">Ele permite que os usuários descubram, editem e executem comandos completos com base em previsões correspondentes do histórico do usuário e de plugins específicos de domínio adicionais.</span><span class="sxs-lookup"><span data-stu-id="d6da5-133">It enables users to discover, edit, and execute full commands based on matching predictions from the user's history and additional domain specific plugins.</span></span>

### <a name="enable-predictive-intellisense"></a><span data-ttu-id="d6da5-134">Habilitar IntelliSense Preditivo</span><span class="sxs-lookup"><span data-stu-id="d6da5-134">Enable Predictive IntelliSense</span></span>

<span data-ttu-id="d6da5-135">O IntelliSense preditiva é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="d6da5-135">Predictive IntelliSense is disabled by default.</span></span> <span data-ttu-id="d6da5-136">Para habilitar previsões, basta executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d6da5-136">To enable predictions, just run the following command:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource History
```

<span data-ttu-id="d6da5-137">O parâmetro **PredictionSource** também pode aceitar plug-ins para requisitos personalizados e específicos de domínio.</span><span class="sxs-lookup"><span data-stu-id="d6da5-137">The **PredictionSource** parameter can also accept plugins for domain specific and custom requirements.</span></span>

<span data-ttu-id="d6da5-138">Para desabilitar o IntelliSense preditiva, basta executar:</span><span class="sxs-lookup"><span data-stu-id="d6da5-138">To disable Predictive IntelliSense, just run:</span></span>

```powershell
Set-PSReadLineOption -PredictionSource None
```

<span data-ttu-id="d6da5-139">As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]**.</span><span class="sxs-lookup"><span data-stu-id="d6da5-139">The following functions are available in the class **[Microsoft.PowerShell.PSConsoleReadLine]**.</span></span>

## <a name="basic-editing-functions"></a><span data-ttu-id="d6da5-140">Funções de edição básicas</span><span class="sxs-lookup"><span data-stu-id="d6da5-140">Basic editing functions</span></span>

### <a name="abort"></a><span data-ttu-id="d6da5-141">Anular</span><span class="sxs-lookup"><span data-stu-id="d6da5-141">Abort</span></span>

<span data-ttu-id="d6da5-142">Anular a ação atual, por exemplo, pesquisa de histórico incremental.</span><span class="sxs-lookup"><span data-stu-id="d6da5-142">Abort current action, e.g. incremental history search.</span></span>

- <span data-ttu-id="d6da5-143">Emacs `<Ctrl+g>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-143">Emacs: `<Ctrl+g>`</span></span>

### <a name="acceptandgetnext"></a><span data-ttu-id="d6da5-144">AcceptAndGetNext</span><span class="sxs-lookup"><span data-stu-id="d6da5-144">AcceptAndGetNext</span></span>

<span data-ttu-id="d6da5-145">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-145">Attempt to execute the current input.</span></span> <span data-ttu-id="d6da5-146">Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-146">If it can be executed (like AcceptLine), then recall the next item from history the next time ReadLine is called.</span></span>

- <span data-ttu-id="d6da5-147">Emacs `<Ctrl+o>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-147">Emacs: `<Ctrl+o>`</span></span>

### <a name="acceptline"></a><span data-ttu-id="d6da5-148">Aceitar</span><span class="sxs-lookup"><span data-stu-id="d6da5-148">AcceptLine</span></span>

<span data-ttu-id="d6da5-149">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-149">Attempt to execute the current input.</span></span> <span data-ttu-id="d6da5-150">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-150">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="d6da5-151">Cmd `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-151">Cmd: `<Enter>`</span></span>
- <span data-ttu-id="d6da5-152">Emacs `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-152">Emacs: `<Enter>`</span></span>
- <span data-ttu-id="d6da5-153">Modo de inserção de vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-153">Vi insert mode: `<Enter>`</span></span>

### <a name="addline"></a><span data-ttu-id="d6da5-154">AddLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-154">AddLine</span></span>

<span data-ttu-id="d6da5-155">O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-155">The continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span> <span data-ttu-id="d6da5-156">Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.</span><span class="sxs-lookup"><span data-stu-id="d6da5-156">This is useful to enter multi-line input as a single command even when a single line is complete input by itself.</span></span>

- <span data-ttu-id="d6da5-157">Cmd `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-157">Cmd: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d6da5-158">Emacs `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-158">Emacs: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d6da5-159">Modo de inserção de vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-159">Vi insert mode: `<Shift+Enter>`</span></span>
- <span data-ttu-id="d6da5-160">Modo de comando vi: `<Shift+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-160">Vi command mode: `<Shift+Enter>`</span></span>

### <a name="backwarddeletechar"></a><span data-ttu-id="d6da5-161">BackwardDeleteChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-161">BackwardDeleteChar</span></span>

<span data-ttu-id="d6da5-162">Exclua o caractere antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-162">Delete the character before the cursor.</span></span>

- <span data-ttu-id="d6da5-163">Cmd: `<Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-163">Cmd: `<Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="d6da5-164">Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-164">Emacs: `<Backspace>`, `<Ctrl+Backspace>`, `<Ctrl+h>`</span></span>
- <span data-ttu-id="d6da5-165">Modo de inserção de vi: `<Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-165">Vi insert mode: `<Backspace>`</span></span>
- <span data-ttu-id="d6da5-166">Modo de comando vi: `<X>` , `<d,h>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-166">Vi command mode: `<X>`, `<d,h>`</span></span>

### <a name="backwarddeleteline"></a><span data-ttu-id="d6da5-167">BackwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-167">BackwardDeleteLine</span></span>

<span data-ttu-id="d6da5-168">Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-168">Like BackwardKillLine - deletes text from the point to the start of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="d6da5-169">Cmd `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-169">Cmd: `<Ctrl+Home>`</span></span>
- <span data-ttu-id="d6da5-170">Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-170">Vi insert mode: `<Ctrl+u>`, `<Ctrl+Home>`</span></span>
- <span data-ttu-id="d6da5-171">Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-171">Vi command mode: `<Ctrl+u>`, `<Ctrl+Home>`, `<d,0>`</span></span>

### <a name="backwarddeleteword"></a><span data-ttu-id="d6da5-172">BackwardDeleteWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-172">BackwardDeleteWord</span></span>

<span data-ttu-id="d6da5-173">Exclui a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-173">Deletes the previous word.</span></span>

- <span data-ttu-id="d6da5-174">Modo de comando vi: `<Ctrl+w>` , `<d,b>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-174">Vi command mode: `<Ctrl+w>`, `<d,b>`</span></span>

### <a name="backwardkillline"></a><span data-ttu-id="d6da5-175">BackwardKillLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-175">BackwardKillLine</span></span>

<span data-ttu-id="d6da5-176">Limpe a entrada do início da entrada para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-176">Clear the input from the start of the input to the cursor.</span></span> <span data-ttu-id="d6da5-177">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-177">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6da5-178">Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-178">Emacs: `<Ctrl+u>`, `<Ctrl+x,Backspace>`</span></span>

### <a name="backwardkillword"></a><span data-ttu-id="d6da5-179">BackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-179">BackwardKillWord</span></span>

<span data-ttu-id="d6da5-180">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-180">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d6da5-181">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-181">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d6da5-182">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-182">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6da5-183">Cmd: `<Ctrl+Backspace>` , `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-183">Cmd: `<Ctrl+Backspace>`, `<Ctrl+w>`</span></span>
- <span data-ttu-id="d6da5-184">Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-184">Emacs: `<Alt+Backspace>`, `<Escape,Backspace>`</span></span>
- <span data-ttu-id="d6da5-185">Modo de inserção de vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-185">Vi insert mode: `<Ctrl+Backspace>`</span></span>
- <span data-ttu-id="d6da5-186">Modo de comando vi: `<Ctrl+Backspace>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-186">Vi command mode: `<Ctrl+Backspace>`</span></span>

### <a name="cancelline"></a><span data-ttu-id="d6da5-187">Cancelar</span><span class="sxs-lookup"><span data-stu-id="d6da5-187">CancelLine</span></span>

<span data-ttu-id="d6da5-188">Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.</span><span class="sxs-lookup"><span data-stu-id="d6da5-188">Cancel the current input, leaving the input on the screen, but returns back to the host so the prompt is evaluated again.</span></span>

- <span data-ttu-id="d6da5-189">Modo de inserção de vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-189">Vi insert mode: `<Ctrl+c>`</span></span>
- <span data-ttu-id="d6da5-190">Modo de comando vi: `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-190">Vi command mode: `<Ctrl+c>`</span></span>

### <a name="copy"></a><span data-ttu-id="d6da5-191">Copiar</span><span class="sxs-lookup"><span data-stu-id="d6da5-191">Copy</span></span>

<span data-ttu-id="d6da5-192">Copie a região selecionada para a área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="d6da5-192">Copy selected region to the system clipboard.</span></span> <span data-ttu-id="d6da5-193">Se nenhuma região for selecionada, copie a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="d6da5-193">If no region is selected, copy the whole line.</span></span>

- <span data-ttu-id="d6da5-194">Cmd `<Ctrl+C>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-194">Cmd: `<Ctrl+C>`</span></span>

### <a name="copyorcancelline"></a><span data-ttu-id="d6da5-195">CopyOrCancelLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-195">CopyOrCancelLine</span></span>

<span data-ttu-id="d6da5-196">Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-196">If text is selected, copy to the clipboard, otherwise cancel the line.</span></span>

- <span data-ttu-id="d6da5-197">Cmd `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-197">Cmd: `<Ctrl+c>`</span></span>
- <span data-ttu-id="d6da5-198">Emacs `<Ctrl+c>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-198">Emacs: `<Ctrl+c>`</span></span>

### <a name="cut"></a><span data-ttu-id="d6da5-199">Recortar</span><span class="sxs-lookup"><span data-stu-id="d6da5-199">Cut</span></span>

<span data-ttu-id="d6da5-200">Excluir região selecionada colocando texto excluído na área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="d6da5-200">Delete selected region placing deleted text in the system clipboard.</span></span>

- <span data-ttu-id="d6da5-201">Cmd `<Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-201">Cmd: `<Ctrl+x>`</span></span>

### <a name="deletechar"></a><span data-ttu-id="d6da5-202">DeleteChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-202">DeleteChar</span></span>

<span data-ttu-id="d6da5-203">Exclua o caractere sob o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-203">Delete the character under the cursor.</span></span>

- <span data-ttu-id="d6da5-204">Cmd `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-204">Cmd: `<Delete>`</span></span>
- <span data-ttu-id="d6da5-205">Emacs `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-205">Emacs: `<Delete>`</span></span>
- <span data-ttu-id="d6da5-206">Modo de inserção de vi: `<Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-206">Vi insert mode: `<Delete>`</span></span>
- <span data-ttu-id="d6da5-207">Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-207">Vi command mode: `<Delete>`, `<x>`, `<d,l>`, `<d,Spacebar>`</span></span>

### <a name="deletecharorexit"></a><span data-ttu-id="d6da5-208">DeleteCharOrExit</span><span class="sxs-lookup"><span data-stu-id="d6da5-208">DeleteCharOrExit</span></span>

<span data-ttu-id="d6da5-209">Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.</span><span class="sxs-lookup"><span data-stu-id="d6da5-209">Delete the character under the cursor, or if the line is empty, exit the process.</span></span>

- <span data-ttu-id="d6da5-210">Emacs `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-210">Emacs: `<Ctrl+d>`</span></span>

### <a name="deleteendofbuffer"></a><span data-ttu-id="d6da5-211">DeleteEndOfBuffer</span><span class="sxs-lookup"><span data-stu-id="d6da5-211">DeleteEndOfBuffer</span></span>

<span data-ttu-id="d6da5-212">Exclui para o final do buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-212">Deletes to the end of the multiline buffer.</span></span>

- <span data-ttu-id="d6da5-213">Modo de comando vi: `<d,G>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-213">Vi command mode: `<d,G>`</span></span>

### <a name="deleteendofword"></a><span data-ttu-id="d6da5-214">DeleteEndOfWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-214">DeleteEndOfWord</span></span>

<span data-ttu-id="d6da5-215">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-215">Delete to the end of the word.</span></span>

- <span data-ttu-id="d6da5-216">Modo de comando vi: `<d,e>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-216">Vi command mode: `<d,e>`</span></span>

### <a name="deleteline"></a><span data-ttu-id="d6da5-217">DeleteLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-217">DeleteLine</span></span>

<span data-ttu-id="d6da5-218">Exclui a linha lógica atual de um buffer de várias linhas, habilitando desfazer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-218">Deletes the current logical line of a multiline buffer, enabling undo.</span></span>

- <span data-ttu-id="d6da5-219">Modo de comando vi: `<d,d>` , `<d,_>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-219">Vi command mode: `<d,d>`, `<d,_>`</span></span>

### <a name="deletepreviouslines"></a><span data-ttu-id="d6da5-220">DeletePreviousLines</span><span class="sxs-lookup"><span data-stu-id="d6da5-220">DeletePreviousLines</span></span>

<span data-ttu-id="d6da5-221">Exclui as linhas lógicas solicitadas anteriores e a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-221">Deletes the previous requested logical lines and the current logical line in a multiline buffer.</span></span>

- <span data-ttu-id="d6da5-222">Modo de comando vi: `<d,k>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-222">Vi command mode: `<d,k>`</span></span>

### <a name="deleterelativelines"></a><span data-ttu-id="d6da5-223">DeleteRelativeLines</span><span class="sxs-lookup"><span data-stu-id="d6da5-223">DeleteRelativeLines</span></span>

<span data-ttu-id="d6da5-224">Exclui desde o início do buffer até a linha lógica atual em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-224">Deletes from the beginning of the buffer to the current logical line in a multiline buffer.</span></span>

<span data-ttu-id="d6da5-225">Como a maioria dos comandos vi, o `<d,g,g>` comando pode ser anexado com um argumento numérico que especifica um número de linha absoluto, que, junto com o número de linha atual, compõem um intervalo de linhas a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="d6da5-225">As most Vi commands, the `<d,g,g>` command can be prepended with a numeric argument that specifies an absolute line number, which, together with the current line number, make up a range of lines to be deleted.</span></span>
<span data-ttu-id="d6da5-226">Se não for especificado, o argumento numérico usa como padrão 1, que se refere à primeira linha lógica em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-226">If not specified, the numeric argument defaults to 1, which refers to the first logical line in a multiline buffer.</span></span>

<span data-ttu-id="d6da5-227">O número real de linhas a serem excluídas da multilinha é calculado como a diferença entre o número da linha lógica atual e o argumento numérico especificado, que pode ser, portanto, negativo.</span><span class="sxs-lookup"><span data-stu-id="d6da5-227">The actual number of lines to be deleted from the multiline is computed as the difference between the current logical line number and the specified numeric argument, which can thus be negative.</span></span> <span data-ttu-id="d6da5-228">Portanto, a parte _relativa_ do nome do método.</span><span class="sxs-lookup"><span data-stu-id="d6da5-228">Hence the _relative_ part of method name.</span></span>

- <span data-ttu-id="d6da5-229">Modo de comando vi: `<d,g,g>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-229">Vi command mode: `<d,g,g>`</span></span>

### <a name="deletenextlines"></a><span data-ttu-id="d6da5-230">DeleteNextLines</span><span class="sxs-lookup"><span data-stu-id="d6da5-230">DeleteNextLines</span></span>

<span data-ttu-id="d6da5-231">Exclui a linha lógica atual e as próximas linhas lógicas solicitadas em um buffer de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-231">Deletes the current logical line and the next requested logical lines in a multiline buffer.</span></span>

- <span data-ttu-id="d6da5-232">Modo de comando vi: `<d,j>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-232">Vi command mode: `<d,j>`</span></span>

### <a name="deletelinetofirstchar"></a><span data-ttu-id="d6da5-233">DeleteLineToFirstChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-233">DeleteLineToFirstChar</span></span>

<span data-ttu-id="d6da5-234">Exclui o texto do cursor para o primeiro caractere que não seja em branco da linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-234">Deletes text from the cursor to the first non-blank character of the line.</span></span>

- <span data-ttu-id="d6da5-235">Modo de comando vi: `<d,^>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-235">Vi command mode: `<d,^>`</span></span>

### <a name="deletetoend"></a><span data-ttu-id="d6da5-236">DeleteToEnd</span><span class="sxs-lookup"><span data-stu-id="d6da5-236">DeleteToEnd</span></span>

<span data-ttu-id="d6da5-237">Excluir até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-237">Delete to the end of the line.</span></span>

- <span data-ttu-id="d6da5-238">Modo de comando vi: `<D>` , `<d,$>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-238">Vi command mode: `<D>`, `<d,$>`</span></span>

### <a name="deleteword"></a><span data-ttu-id="d6da5-239">DeleteWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-239">DeleteWord</span></span>

<span data-ttu-id="d6da5-240">Excluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-240">Delete the next word.</span></span>

- <span data-ttu-id="d6da5-241">Modo de comando vi: `<d,w>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-241">Vi command mode: `<d,w>`</span></span>

### <a name="forwarddeleteline"></a><span data-ttu-id="d6da5-242">ForwardDeleteLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-242">ForwardDeleteLine</span></span>

<span data-ttu-id="d6da5-243">Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-243">Like ForwardKillLine - deletes text from the point to the end of the line, but does not put the deleted text in the kill-ring.</span></span>

- <span data-ttu-id="d6da5-244">Cmd `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-244">Cmd: `<Ctrl+End>`</span></span>
- <span data-ttu-id="d6da5-245">Modo de inserção de vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-245">Vi insert mode: `<Ctrl+End>`</span></span>
- <span data-ttu-id="d6da5-246">Modo de comando vi: `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-246">Vi command mode: `<Ctrl+End>`</span></span>

### <a name="insertlineabove"></a><span data-ttu-id="d6da5-247">InsertLineAbove</span><span class="sxs-lookup"><span data-stu-id="d6da5-247">InsertLineAbove</span></span>

<span data-ttu-id="d6da5-248">Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-248">A new empty line is created above the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="d6da5-249">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-249">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="d6da5-250">Cmd `<Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-250">Cmd: `<Ctrl+Enter>`</span></span>

### <a name="insertlinebelow"></a><span data-ttu-id="d6da5-251">InsertLineBelow</span><span class="sxs-lookup"><span data-stu-id="d6da5-251">InsertLineBelow</span></span>

<span data-ttu-id="d6da5-252">Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-252">A new empty line is created below the current line regardless of where the cursor is on the current line.</span></span> <span data-ttu-id="d6da5-253">O cursor se move para o início da nova linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-253">The cursor moves to the beginning of the new line.</span></span>

- <span data-ttu-id="d6da5-254">Cmd `<Shift+Ctrl+Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-254">Cmd: `<Shift+Ctrl+Enter>`</span></span>

### <a name="invertcase"></a><span data-ttu-id="d6da5-255">InvertCase</span><span class="sxs-lookup"><span data-stu-id="d6da5-255">InvertCase</span></span>

<span data-ttu-id="d6da5-256">Inverta o caso do caractere atual e mova para o próximo.</span><span class="sxs-lookup"><span data-stu-id="d6da5-256">Invert the case of the current character and move to the next one.</span></span>

- <span data-ttu-id="d6da5-257">Modo de comando vi: `<~>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-257">Vi command mode: `<~>`</span></span>

### <a name="killline"></a><span data-ttu-id="d6da5-258">Finalizar</span><span class="sxs-lookup"><span data-stu-id="d6da5-258">KillLine</span></span>

<span data-ttu-id="d6da5-259">Limpe a entrada do cursor até o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-259">Clear the input from the cursor to the end of the input.</span></span> <span data-ttu-id="d6da5-260">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-260">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6da5-261">Emacs `<Ctrl+k>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-261">Emacs: `<Ctrl+k>`</span></span>

### <a name="killregion"></a><span data-ttu-id="d6da5-262">KillRegion</span><span class="sxs-lookup"><span data-stu-id="d6da5-262">KillRegion</span></span>

<span data-ttu-id="d6da5-263">Elimine o texto entre o cursor e a marca.</span><span class="sxs-lookup"><span data-stu-id="d6da5-263">Kill the text between the cursor and the mark.</span></span>

- <span data-ttu-id="d6da5-264">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-264">Function is unbound.</span></span>

### <a name="killword"></a><span data-ttu-id="d6da5-265">KillWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-265">KillWord</span></span>

<span data-ttu-id="d6da5-266">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-266">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="d6da5-267">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-267">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="d6da5-268">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-268">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6da5-269">Cmd: `<Alt+d>` , `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-269">Cmd: `<Alt+d>`, `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="d6da5-270">Emacs: `<Alt+d>` , `<Escape,d>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-270">Emacs: `<Alt+d>`, `<Escape,d>`</span></span>
- <span data-ttu-id="d6da5-271">Modo de inserção de vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-271">Vi insert mode: `<Ctrl+Delete>`</span></span>
- <span data-ttu-id="d6da5-272">Modo de comando vi: `<Ctrl+Delete>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-272">Vi command mode: `<Ctrl+Delete>`</span></span>

### <a name="paste"></a><span data-ttu-id="d6da5-273">Colar</span><span class="sxs-lookup"><span data-stu-id="d6da5-273">Paste</span></span>

<span data-ttu-id="d6da5-274">Cole o texto da área de transferência do sistema.</span><span class="sxs-lookup"><span data-stu-id="d6da5-274">Paste text from the system clipboard.</span></span>

- <span data-ttu-id="d6da5-275">Cmd: `<Ctrl+v>` , `<Shift+Insert>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-275">Cmd: `<Ctrl+v>`, `<Shift+Insert>`</span></span>
- <span data-ttu-id="d6da5-276">Modo de inserção de vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-276">Vi insert mode: `<Ctrl+v>`</span></span>
- <span data-ttu-id="d6da5-277">Modo de comando vi: `<Ctrl+v>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-277">Vi command mode: `<Ctrl+v>`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6da5-278">Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d6da5-278">When using the **Paste** function, the entire contents of the clipboard buffer is pasted into the input buffer of PSReadLine.</span></span> <span data-ttu-id="d6da5-279">O buffer de entrada é passado para o analisador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-279">The input buffer is then passed to the PowerShell parser.</span></span> <span data-ttu-id="d6da5-280">A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="d6da5-280">Input pasted using the console application's **right-click** paste method is copied to the input buffer one character at a time.</span></span> <span data-ttu-id="d6da5-281">O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-281">The input buffer is passed to the parser when a newline character is copied.</span></span> <span data-ttu-id="d6da5-282">Portanto, a entrada é analisada uma linha por vez.</span><span class="sxs-lookup"><span data-stu-id="d6da5-282">Therefore, the input is parsed one line at a time.</span></span> <span data-ttu-id="d6da5-283">A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.</span><span class="sxs-lookup"><span data-stu-id="d6da5-283">The difference between paste methods results in different execution behavior.</span></span>

### <a name="pasteafter"></a><span data-ttu-id="d6da5-284">PasteAfter</span><span class="sxs-lookup"><span data-stu-id="d6da5-284">PasteAfter</span></span>

<span data-ttu-id="d6da5-285">Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-285">Paste the clipboard after the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="d6da5-286">Modo de comando vi: `<p>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-286">Vi command mode: `<p>`</span></span>

### <a name="pastebefore"></a><span data-ttu-id="d6da5-287">PasteBefore</span><span class="sxs-lookup"><span data-stu-id="d6da5-287">PasteBefore</span></span>

<span data-ttu-id="d6da5-288">Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-288">Paste the clipboard before the cursor, moving the cursor to the end of the pasted text.</span></span>

- <span data-ttu-id="d6da5-289">Modo de comando vi: `<P>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-289">Vi command mode: `<P>`</span></span>

### <a name="prependandaccept"></a><span data-ttu-id="d6da5-290">PrependAndAccept</span><span class="sxs-lookup"><span data-stu-id="d6da5-290">PrependAndAccept</span></span>

<span data-ttu-id="d6da5-291">Preceda um ' # ' e aceite a linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-291">Prepend a '#' and accept the line.</span></span>

- <span data-ttu-id="d6da5-292">Modo de comando vi: `<#>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-292">Vi command mode: `<#>`</span></span>

### <a name="redo"></a><span data-ttu-id="d6da5-293">Refaz</span><span class="sxs-lookup"><span data-stu-id="d6da5-293">Redo</span></span>

<span data-ttu-id="d6da5-294">Desfazer um desfazer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-294">Undo an undo.</span></span>

- <span data-ttu-id="d6da5-295">Cmd `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-295">Cmd: `<Ctrl+y>`</span></span>
- <span data-ttu-id="d6da5-296">Modo de inserção de vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-296">Vi insert mode: `<Ctrl+y>`</span></span>
- <span data-ttu-id="d6da5-297">Modo de comando vi: `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-297">Vi command mode: `<Ctrl+y>`</span></span>

### <a name="repeatlastcommand"></a><span data-ttu-id="d6da5-298">RepeatLastCommand</span><span class="sxs-lookup"><span data-stu-id="d6da5-298">RepeatLastCommand</span></span>

<span data-ttu-id="d6da5-299">Repita a última modificação de texto.</span><span class="sxs-lookup"><span data-stu-id="d6da5-299">Repeat the last text modification.</span></span>

- <span data-ttu-id="d6da5-300">Modo de comando vi: `<.>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-300">Vi command mode: `<.>`</span></span>

### <a name="revertline"></a><span data-ttu-id="d6da5-301">Reverter</span><span class="sxs-lookup"><span data-stu-id="d6da5-301">RevertLine</span></span>

<span data-ttu-id="d6da5-302">Reverte todas as entradas para a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-302">Reverts all of the input to the current input.</span></span>

- <span data-ttu-id="d6da5-303">Cmd `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-303">Cmd: `<Escape>`</span></span>
- <span data-ttu-id="d6da5-304">Emacs: `<Alt+r>` , `<Escape,r>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-304">Emacs: `<Alt+r>`, `<Escape,r>`</span></span>

### <a name="shellbackwardkillword"></a><span data-ttu-id="d6da5-305">ShellBackwardKillWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-305">ShellBackwardKillWord</span></span>

<span data-ttu-id="d6da5-306">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-306">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d6da5-307">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-307">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d6da5-308">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-308">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="d6da5-309">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-309">Function is unbound.</span></span>

### <a name="shellkillword"></a><span data-ttu-id="d6da5-310">ShellKillWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-310">ShellKillWord</span></span>

<span data-ttu-id="d6da5-311">Limpe a entrada do cursor até o fim da palavra atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-311">Clear the input from the cursor to the end of the current word.</span></span> <span data-ttu-id="d6da5-312">Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-312">If the cursor is between words, the input is cleared from the cursor to the end of the next word.</span></span> <span data-ttu-id="d6da5-313">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-313">The cleared text is placed in the kill-ring.</span></span>

<span data-ttu-id="d6da5-314">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-314">Function is unbound.</span></span>

### <a name="swapcharacters"></a><span data-ttu-id="d6da5-315">SwapCharacters</span><span class="sxs-lookup"><span data-stu-id="d6da5-315">SwapCharacters</span></span>

<span data-ttu-id="d6da5-316">Troque o caractere atual e aquele anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-316">Swap the current character and the one before it.</span></span>

- <span data-ttu-id="d6da5-317">Emacs `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-317">Emacs: `<Ctrl+t>`</span></span>
- <span data-ttu-id="d6da5-318">Modo de inserção de vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-318">Vi insert mode: `<Ctrl+t>`</span></span>
- <span data-ttu-id="d6da5-319">Modo de comando vi: `<Ctrl+t>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-319">Vi command mode: `<Ctrl+t>`</span></span>

### <a name="undo"></a><span data-ttu-id="d6da5-320">Desfazer</span><span class="sxs-lookup"><span data-stu-id="d6da5-320">Undo</span></span>

<span data-ttu-id="d6da5-321">Desfazer uma edição anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-321">Undo a previous edit.</span></span>

- <span data-ttu-id="d6da5-322">Cmd `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-322">Cmd: `<Ctrl+z>`</span></span>
- <span data-ttu-id="d6da5-323">Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-323">Emacs: `<Ctrl+_>`, `<Ctrl+x,Ctrl+u>`</span></span>
- <span data-ttu-id="d6da5-324">Modo de inserção de vi: `<Ctrl+z>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-324">Vi insert mode: `<Ctrl+z>`</span></span>
- <span data-ttu-id="d6da5-325">Modo de comando vi: `<Ctrl+z>` , `<u>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-325">Vi command mode: `<Ctrl+z>`, `<u>`</span></span>

### <a name="undoall"></a><span data-ttu-id="d6da5-326">UndoAll</span><span class="sxs-lookup"><span data-stu-id="d6da5-326">UndoAll</span></span>

<span data-ttu-id="d6da5-327">Desfazer todas as edições anteriores para a linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-327">Undo all previous edits for line.</span></span>

- <span data-ttu-id="d6da5-328">Modo de comando vi: `<U>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-328">Vi command mode: `<U>`</span></span>

### <a name="unixwordrubout"></a><span data-ttu-id="d6da5-329">UnixWordRubout</span><span class="sxs-lookup"><span data-stu-id="d6da5-329">UnixWordRubout</span></span>

<span data-ttu-id="d6da5-330">Limpe a entrada do início da palavra atual para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-330">Clear the input from the start of the current word to the cursor.</span></span> <span data-ttu-id="d6da5-331">Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-331">If the cursor is between words, the input is cleared from the start of the previous word to the cursor.</span></span> <span data-ttu-id="d6da5-332">O texto limpo é colocado no Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-332">The cleared text is placed in the kill-ring.</span></span>

- <span data-ttu-id="d6da5-333">Emacs `<Ctrl+w>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-333">Emacs: `<Ctrl+w>`</span></span>

### <a name="validateandacceptline"></a><span data-ttu-id="d6da5-334">ValidateAndAcceptLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-334">ValidateAndAcceptLine</span></span>

<span data-ttu-id="d6da5-335">Tentativa de executar a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-335">Attempt to execute the current input.</span></span> <span data-ttu-id="d6da5-336">Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-336">If the current input is incomplete (for example there is a missing closing parenthesis, bracket, or quote, then the continuation prompt is displayed on the next line and PSReadLine waits for keys to edit the current input.</span></span>

- <span data-ttu-id="d6da5-337">Emacs `<Ctrl+m>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-337">Emacs: `<Ctrl+m>`</span></span>

### <a name="viacceptline"></a><span data-ttu-id="d6da5-338">ViAcceptLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-338">ViAcceptLine</span></span>

<span data-ttu-id="d6da5-339">Aceite a linha e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="d6da5-339">Accept the line and switch to Insert mode.</span></span>

- <span data-ttu-id="d6da5-340">Modo de comando vi: `<Enter>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-340">Vi command mode: `<Enter>`</span></span>

### <a name="viacceptlineorexit"></a><span data-ttu-id="d6da5-341">ViAcceptLineOrExit</span><span class="sxs-lookup"><span data-stu-id="d6da5-341">ViAcceptLineOrExit</span></span>

<span data-ttu-id="d6da5-342">Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-342">Like DeleteCharOrExit in Emacs mode, but accepts the line instead of deleting a character.</span></span>

- <span data-ttu-id="d6da5-343">Modo de inserção de vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-343">Vi insert mode: `<Ctrl+d>`</span></span>
- <span data-ttu-id="d6da5-344">Modo de comando vi: `<Ctrl+d>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-344">Vi command mode: `<Ctrl+d>`</span></span>

### <a name="viappendline"></a><span data-ttu-id="d6da5-345">ViAppendLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-345">ViAppendLine</span></span>

<span data-ttu-id="d6da5-346">Uma nova linha é inserida abaixo da linha atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-346">A new line is inserted below the current line.</span></span>

- <span data-ttu-id="d6da5-347">Modo de comando vi: `<o>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-347">Vi command mode: `<o>`</span></span>

### <a name="vibackwarddeleteglob"></a><span data-ttu-id="d6da5-348">ViBackwardDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-348">ViBackwardDeleteGlob</span></span>

<span data-ttu-id="d6da5-349">Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-349">Deletes the previous word, using only white space as the word delimiter.</span></span>

- <span data-ttu-id="d6da5-350">Modo de comando vi: `<d,B>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-350">Vi command mode: `<d,B>`</span></span>

### <a name="vibackwardglob"></a><span data-ttu-id="d6da5-351">ViBackwardGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-351">ViBackwardGlob</span></span>

<span data-ttu-id="d6da5-352">Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="d6da5-352">Moves the cursor back to the beginning of the previous word, using only white space as delimiters.</span></span>

- <span data-ttu-id="d6da5-353">Modo de comando vi: `<B>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-353">Vi command mode: `<B>`</span></span>

### <a name="videletebrace"></a><span data-ttu-id="d6da5-354">ViDeleteBrace</span><span class="sxs-lookup"><span data-stu-id="d6da5-354">ViDeleteBrace</span></span>

<span data-ttu-id="d6da5-355">Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.</span><span class="sxs-lookup"><span data-stu-id="d6da5-355">Find the matching brace, parenthesis, or square bracket and delete all contents within, including the brace.</span></span>

- <span data-ttu-id="d6da5-356">Modo de comando vi: `<d,%>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-356">Vi command mode: `<d,%>`</span></span>

### <a name="videleteendofglob"></a><span data-ttu-id="d6da5-357">ViDeleteEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-357">ViDeleteEndOfGlob</span></span>

<span data-ttu-id="d6da5-358">Excluir até o final da palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-358">Delete to the end of the word.</span></span>

- <span data-ttu-id="d6da5-359">Modo de comando vi: `<d,E>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-359">Vi command mode: `<d,E>`</span></span>

### <a name="videleteglob"></a><span data-ttu-id="d6da5-360">ViDeleteGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-360">ViDeleteGlob</span></span>

<span data-ttu-id="d6da5-361">Exclua a próxima glob (palavra delimitada por espaço em branco).</span><span class="sxs-lookup"><span data-stu-id="d6da5-361">Delete the next glob (white space delimited word).</span></span>

- <span data-ttu-id="d6da5-362">Modo de comando vi: `<d,W>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-362">Vi command mode: `<d,W>`</span></span>

### <a name="videletetobeforechar"></a><span data-ttu-id="d6da5-363">ViDeleteToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-363">ViDeleteToBeforeChar</span></span>

<span data-ttu-id="d6da5-364">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-364">Deletes until given character.</span></span>

- <span data-ttu-id="d6da5-365">Modo de comando vi: `<d,t>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-365">Vi command mode: `<d,t>`</span></span>

### <a name="videletetobeforecharbackward"></a><span data-ttu-id="d6da5-366">ViDeleteToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-366">ViDeleteToBeforeCharBackward</span></span>

<span data-ttu-id="d6da5-367">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-367">Deletes until given character.</span></span>

- <span data-ttu-id="d6da5-368">Modo de comando vi: `<d,T>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-368">Vi command mode: `<d,T>`</span></span>

### <a name="videletetochar"></a><span data-ttu-id="d6da5-369">ViDeleteToChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-369">ViDeleteToChar</span></span>

<span data-ttu-id="d6da5-370">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-370">Deletes until given character.</span></span>

- <span data-ttu-id="d6da5-371">Modo de comando vi: `<d,f>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-371">Vi command mode: `<d,f>`</span></span>

### <a name="videletetocharbackward"></a><span data-ttu-id="d6da5-372">ViDeleteToCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-372">ViDeleteToCharBackward</span></span>

<span data-ttu-id="d6da5-373">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-373">Deletes backwards until given character.</span></span>

- <span data-ttu-id="d6da5-374">Modo de comando vi: `<d,F>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-374">Vi command mode: `<d,F>`</span></span>

### <a name="viinsertatbegining"></a><span data-ttu-id="d6da5-375">ViInsertAtBegining</span><span class="sxs-lookup"><span data-stu-id="d6da5-375">ViInsertAtBegining</span></span>

<span data-ttu-id="d6da5-376">Alterne para o modo de inserção e posicione o cursor no início da linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-376">Switch to Insert mode and position the cursor at the beginning of the line.</span></span>

- <span data-ttu-id="d6da5-377">Modo de comando vi: `<I>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-377">Vi command mode: `<I>`</span></span>

### <a name="viinsertatend"></a><span data-ttu-id="d6da5-378">ViInsertAtEnd</span><span class="sxs-lookup"><span data-stu-id="d6da5-378">ViInsertAtEnd</span></span>

<span data-ttu-id="d6da5-379">Alterne para o modo de inserção e posicione o cursor no final da linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-379">Switch to Insert mode and position the cursor at the end of the line.</span></span>

- <span data-ttu-id="d6da5-380">Modo de comando vi: `<A>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-380">Vi command mode: `<A>`</span></span>

### <a name="viinsertline"></a><span data-ttu-id="d6da5-381">ViInsertLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-381">ViInsertLine</span></span>

<span data-ttu-id="d6da5-382">Uma nova linha é inserida acima da linha atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-382">A new line is inserted above the current line.</span></span>

- <span data-ttu-id="d6da5-383">Modo de comando vi: `<O>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-383">Vi command mode: `<O>`</span></span>

### <a name="viinsertwithappend"></a><span data-ttu-id="d6da5-384">ViInsertWithAppend</span><span class="sxs-lookup"><span data-stu-id="d6da5-384">ViInsertWithAppend</span></span>

<span data-ttu-id="d6da5-385">Anexar da posição da linha atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-385">Append from the current line position.</span></span>

- <span data-ttu-id="d6da5-386">Modo de comando vi: `<a>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-386">Vi command mode: `<a>`</span></span>

### <a name="viinsertwithdelete"></a><span data-ttu-id="d6da5-387">ViInsertWithDelete</span><span class="sxs-lookup"><span data-stu-id="d6da5-387">ViInsertWithDelete</span></span>

<span data-ttu-id="d6da5-388">Exclua o caractere atual e alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="d6da5-388">Delete the current character and switch to Insert mode.</span></span>

- <span data-ttu-id="d6da5-389">Modo de comando vi: `<s>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-389">Vi command mode: `<s>`</span></span>

### <a name="vijoinlines"></a><span data-ttu-id="d6da5-390">ViJoinLines</span><span class="sxs-lookup"><span data-stu-id="d6da5-390">ViJoinLines</span></span>

<span data-ttu-id="d6da5-391">Une a linha atual e a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-391">Joins the current line and the next line.</span></span>

- <span data-ttu-id="d6da5-392">Modo de comando vi: `<J>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-392">Vi command mode: `<J>`</span></span>

### <a name="vireplaceline"></a><span data-ttu-id="d6da5-393">ViReplaceLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-393">ViReplaceLine</span></span>

<span data-ttu-id="d6da5-394">Apague a linha de comando inteira.</span><span class="sxs-lookup"><span data-stu-id="d6da5-394">Erase the entire command line.</span></span>

- <span data-ttu-id="d6da5-395">Modo de comando vi: `<S>` , `<c,c>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-395">Vi command mode: `<S>`, `<c,c>`</span></span>

### <a name="vireplacetobeforechar"></a><span data-ttu-id="d6da5-396">ViReplaceToBeforeChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-396">ViReplaceToBeforeChar</span></span>

<span data-ttu-id="d6da5-397">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-397">Replaces until given character.</span></span>

- <span data-ttu-id="d6da5-398">Modo de comando vi: `<c,t>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-398">Vi command mode: `<c,t>`</span></span>

### <a name="vireplacetobeforecharbackward"></a><span data-ttu-id="d6da5-399">ViReplaceToBeforeCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-399">ViReplaceToBeforeCharBackward</span></span>

<span data-ttu-id="d6da5-400">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-400">Replaces until given character.</span></span>

- <span data-ttu-id="d6da5-401">Modo de comando vi: `<c,T>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-401">Vi command mode: `<c,T>`</span></span>

### <a name="vireplacetochar"></a><span data-ttu-id="d6da5-402">ViReplaceToChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-402">ViReplaceToChar</span></span>

<span data-ttu-id="d6da5-403">Exclui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-403">Deletes until given character.</span></span>

- <span data-ttu-id="d6da5-404">Modo de comando vi: `<c,f>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-404">Vi command mode: `<c,f>`</span></span>

### <a name="vireplacetocharbackward"></a><span data-ttu-id="d6da5-405">ViReplaceToCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-405">ViReplaceToCharBackward</span></span>

<span data-ttu-id="d6da5-406">Substitui até o caractere especificado.</span><span class="sxs-lookup"><span data-stu-id="d6da5-406">Replaces until given character.</span></span>

- <span data-ttu-id="d6da5-407">Modo de comando vi: `<c,F>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-407">Vi command mode: `<c,F>`</span></span>

### <a name="viyankbeginningofline"></a><span data-ttu-id="d6da5-408">ViYankBeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-408">ViYankBeginningOfLine</span></span>

<span data-ttu-id="d6da5-409">Yank desde o início do buffer até o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-409">Yank from the beginning of the buffer to the cursor.</span></span>

- <span data-ttu-id="d6da5-410">Modo de comando vi: `<y,0>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-410">Vi command mode: `<y,0>`</span></span>

### <a name="viyankendofglob"></a><span data-ttu-id="d6da5-411">ViYankEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-411">ViYankEndOfGlob</span></span>

<span data-ttu-id="d6da5-412">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="d6da5-412">Yank from the cursor to the end of the WORD(s).</span></span>

- <span data-ttu-id="d6da5-413">Modo de comando vi: `<y,E>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-413">Vi command mode: `<y,E>`</span></span>

### <a name="viyankendofword"></a><span data-ttu-id="d6da5-414">ViYankEndOfWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-414">ViYankEndOfWord</span></span>

<span data-ttu-id="d6da5-415">Yank do cursor até o fim das palavras.</span><span class="sxs-lookup"><span data-stu-id="d6da5-415">Yank from the cursor to the end of the word(s).</span></span>

- <span data-ttu-id="d6da5-416">Modo de comando vi: `<y,e>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-416">Vi command mode: `<y,e>`</span></span>

### <a name="viyankleft"></a><span data-ttu-id="d6da5-417">ViYankLeft</span><span class="sxs-lookup"><span data-stu-id="d6da5-417">ViYankLeft</span></span>

<span data-ttu-id="d6da5-418">Yank caractere (s) à esquerda do cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-418">Yank character(s) to the left of the cursor.</span></span>

- <span data-ttu-id="d6da5-419">Modo de comando vi: `<y,h>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-419">Vi command mode: `<y,h>`</span></span>

### <a name="viyankline"></a><span data-ttu-id="d6da5-420">ViYankLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-420">ViYankLine</span></span>

<span data-ttu-id="d6da5-421">Yank todo o buffer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-421">Yank the entire buffer.</span></span>

- <span data-ttu-id="d6da5-422">Modo de comando vi: `<y,y>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-422">Vi command mode: `<y,y>`</span></span>

### <a name="viyanknextglob"></a><span data-ttu-id="d6da5-423">ViYankNextGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-423">ViYankNextGlob</span></span>

<span data-ttu-id="d6da5-424">Yank do cursor até o início da próxima palavra (s).</span><span class="sxs-lookup"><span data-stu-id="d6da5-424">Yank from cursor to the start of the next WORD(s).</span></span>

- <span data-ttu-id="d6da5-425">Modo de comando vi: `<y,W>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-425">Vi command mode: `<y,W>`</span></span>

### <a name="viyanknextword"></a><span data-ttu-id="d6da5-426">ViYankNextWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-426">ViYankNextWord</span></span>

<span data-ttu-id="d6da5-427">Yank as palavras após o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-427">Yank the word(s) after the cursor.</span></span>

- <span data-ttu-id="d6da5-428">Modo de comando vi: `<y,w>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-428">Vi command mode: `<y,w>`</span></span>

### <a name="viyankpercent"></a><span data-ttu-id="d6da5-429">ViYankPercent</span><span class="sxs-lookup"><span data-stu-id="d6da5-429">ViYankPercent</span></span>

<span data-ttu-id="d6da5-430">Yank de/para a chave correspondente.</span><span class="sxs-lookup"><span data-stu-id="d6da5-430">Yank to/from matching brace.</span></span>

- <span data-ttu-id="d6da5-431">Modo de comando vi: `<y,%>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-431">Vi command mode: `<y,%>`</span></span>

### <a name="viyankpreviousglob"></a><span data-ttu-id="d6da5-432">ViYankPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-432">ViYankPreviousGlob</span></span>

<span data-ttu-id="d6da5-433">Yank do início das palavras ao cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-433">Yank from beginning of the WORD(s) to cursor.</span></span>

- <span data-ttu-id="d6da5-434">Modo de comando vi: `<y,B>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-434">Vi command mode: `<y,B>`</span></span>

### <a name="viyankpreviousword"></a><span data-ttu-id="d6da5-435">ViYankPreviousWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-435">ViYankPreviousWord</span></span>

<span data-ttu-id="d6da5-436">Yank as palavras antes do cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-436">Yank the word(s) before the cursor.</span></span>

- <span data-ttu-id="d6da5-437">Modo de comando vi: `<y,b>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-437">Vi command mode: `<y,b>`</span></span>

### <a name="viyankright"></a><span data-ttu-id="d6da5-438">ViYankRight</span><span class="sxs-lookup"><span data-stu-id="d6da5-438">ViYankRight</span></span>

<span data-ttu-id="d6da5-439">Yank caractere (s) em e à direita do cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-439">Yank character(s) under and to the right of the cursor.</span></span>

- <span data-ttu-id="d6da5-440">Modo de comando vi: `<y,l>` , `<y,Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-440">Vi command mode: `<y,l>`, `<y,Spacebar>`</span></span>

### <a name="viyanktoendofline"></a><span data-ttu-id="d6da5-441">ViYankToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-441">ViYankToEndOfLine</span></span>

<span data-ttu-id="d6da5-442">Yank do cursor até o final do buffer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-442">Yank from the cursor to the end of the buffer.</span></span>

- <span data-ttu-id="d6da5-443">Modo de comando vi: `<y,$>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-443">Vi command mode: `<y,$>`</span></span>

### <a name="viyanktofirstchar"></a><span data-ttu-id="d6da5-444">ViYankToFirstChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-444">ViYankToFirstChar</span></span>

<span data-ttu-id="d6da5-445">Yank do primeiro caractere que não seja espaço em branco para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-445">Yank from the first non-whitespace character to the cursor.</span></span>

- <span data-ttu-id="d6da5-446">Modo de comando vi: `<y,^>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-446">Vi command mode: `<y,^>`</span></span>

### <a name="yank"></a><span data-ttu-id="d6da5-447">Yank</span><span class="sxs-lookup"><span data-stu-id="d6da5-447">Yank</span></span>

<span data-ttu-id="d6da5-448">Adicione o texto eliminado mais recentemente à entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-448">Add the most recently killed text to the input.</span></span>

- <span data-ttu-id="d6da5-449">Emacs `<Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-449">Emacs: `<Ctrl+y>`</span></span>

### <a name="yanklastarg"></a><span data-ttu-id="d6da5-450">YankLastArg</span><span class="sxs-lookup"><span data-stu-id="d6da5-450">YankLastArg</span></span>

<span data-ttu-id="d6da5-451">Yank o último argumento da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-451">Yank the last argument from the previous history line.</span></span> <span data-ttu-id="d6da5-452">Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg.</span><span class="sxs-lookup"><span data-stu-id="d6da5-452">With an argument, the first time it is invoked, behaves just like YankNthArg.</span></span> <span data-ttu-id="d6da5-453">Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)</span><span class="sxs-lookup"><span data-stu-id="d6da5-453">If invoked multiple times, instead it iterates through history and arg sets the direction (negative reverses the direction.)</span></span>

- <span data-ttu-id="d6da5-454">Cmd `<Alt+.>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-454">Cmd: `<Alt+.>`</span></span>
- <span data-ttu-id="d6da5-455">Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-455">Emacs: `<Alt+.>`, `<Alt+_>`, `<Escape,.>`, `<Escape,_>`</span></span>

### <a name="yankntharg"></a><span data-ttu-id="d6da5-456">YankNthArg</span><span class="sxs-lookup"><span data-stu-id="d6da5-456">YankNthArg</span></span>

<span data-ttu-id="d6da5-457">Yank o primeiro argumento (após o comando) da linha do histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-457">Yank the first argument (after the command) from the previous history line.</span></span>
<span data-ttu-id="d6da5-458">Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.</span><span class="sxs-lookup"><span data-stu-id="d6da5-458">With an argument, yank the nth argument (starting from 0), if the argument is negative, start from the last argument.</span></span>

- <span data-ttu-id="d6da5-459">Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-459">Emacs: `<Ctrl+Alt+y>`, `<Escape,Ctrl+y>`</span></span>

### <a name="yankpop"></a><span data-ttu-id="d6da5-460">YankPop</span><span class="sxs-lookup"><span data-stu-id="d6da5-460">YankPop</span></span>

<span data-ttu-id="d6da5-461">Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-461">If the previous operation was Yank or YankPop, replace the previously yanked text with the next killed text from the kill-ring.</span></span>

- <span data-ttu-id="d6da5-462">Emacs: `<Alt+y>` , `<Escape,y>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-462">Emacs: `<Alt+y>`, `<Escape,y>`</span></span>

## <a name="cursor-movement-functions"></a><span data-ttu-id="d6da5-463">Funções de movimento do cursor</span><span class="sxs-lookup"><span data-stu-id="d6da5-463">Cursor movement functions</span></span>

### <a name="backwardchar"></a><span data-ttu-id="d6da5-464">BackwardChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-464">BackwardChar</span></span>

<span data-ttu-id="d6da5-465">Mover o cursor um caractere para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="d6da5-465">Move the cursor one character to the left.</span></span> <span data-ttu-id="d6da5-466">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-466">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="d6da5-467">Cmd `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-467">Cmd: `<LeftArrow>`</span></span>
- <span data-ttu-id="d6da5-468">Emacs: `<LeftArrow>` , `<Ctrl+b>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-468">Emacs: `<LeftArrow>`, `<Ctrl+b>`</span></span>

### <a name="backwardword"></a><span data-ttu-id="d6da5-469">BackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-469">BackwardWord</span></span>

<span data-ttu-id="d6da5-470">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-470">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d6da5-471">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6da5-471">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6da5-472">Cmd `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-472">Cmd: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d6da5-473">Emacs: `<Alt+b>` , `<Escape,b>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-473">Emacs: `<Alt+b>`, `<Escape,b>`</span></span>
- <span data-ttu-id="d6da5-474">Modo de inserção de vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-474">Vi insert mode: `<Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d6da5-475">Modo de comando vi: `<Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-475">Vi command mode: `<Ctrl+LeftArrow>`</span></span>

### <a name="beginningofline"></a><span data-ttu-id="d6da5-476">BeginningOfLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-476">BeginningOfLine</span></span>

<span data-ttu-id="d6da5-477">Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-477">If the input has multiple lines, move to the start of the current line, or if already at the start of the line, move to the start of the input.</span></span> <span data-ttu-id="d6da5-478">Se a entrada tiver uma única linha, vá para o início da entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-478">If the input has a single line, move to the start of the input.</span></span>

- <span data-ttu-id="d6da5-479">Cmd `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-479">Cmd: `<Home>`</span></span>
- <span data-ttu-id="d6da5-480">Emacs: `<Home>` , `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-480">Emacs: `<Home>`, `<Ctrl+a>`</span></span>
- <span data-ttu-id="d6da5-481">Modo de inserção de vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-481">Vi insert mode: `<Home>`</span></span>
- <span data-ttu-id="d6da5-482">Modo de comando vi: `<Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-482">Vi command mode: `<Home>`</span></span>

### <a name="endofline"></a><span data-ttu-id="d6da5-483">EndOfLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-483">EndOfLine</span></span>

<span data-ttu-id="d6da5-484">Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-484">If the input has multiple lines, move to the end of the current line, or if already at the end of the line, move to the end of the input.</span></span> <span data-ttu-id="d6da5-485">Se a entrada tiver uma única linha, vá para o final da entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-485">If the input has a single line, move to the end of the input.</span></span>

- <span data-ttu-id="d6da5-486">Cmd `<End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-486">Cmd: `<End>`</span></span>
- <span data-ttu-id="d6da5-487">Emacs: `<End>` , `<Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-487">Emacs: `<End>`, `<Ctrl+e>`</span></span>
- <span data-ttu-id="d6da5-488">Modo de inserção de vi: `<End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-488">Vi insert mode: `<End>`</span></span>

### <a name="forwardchar"></a><span data-ttu-id="d6da5-489">ForwardChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-489">ForwardChar</span></span>

<span data-ttu-id="d6da5-490">Mover o cursor um caractere para a direita.</span><span class="sxs-lookup"><span data-stu-id="d6da5-490">Move the cursor one character to the right.</span></span> <span data-ttu-id="d6da5-491">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-491">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="d6da5-492">Cmd `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-492">Cmd: `<RightArrow>`</span></span>
- <span data-ttu-id="d6da5-493">Emacs: `<RightArrow>` , `<Ctrl+f>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-493">Emacs: `<RightArrow>`, `<Ctrl+f>`</span></span>

### <a name="forwardword"></a><span data-ttu-id="d6da5-494">ForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-494">ForwardWord</span></span>

<span data-ttu-id="d6da5-495">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-495">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d6da5-496">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6da5-496">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6da5-497">Emacs: `<Alt+f>` , `<Escape,f>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-497">Emacs: `<Alt+f>`, `<Escape,f>`</span></span>

### <a name="gotobrace"></a><span data-ttu-id="d6da5-498">GotoBrace</span><span class="sxs-lookup"><span data-stu-id="d6da5-498">GotoBrace</span></span>

<span data-ttu-id="d6da5-499">Vá para a chave correspondente, parêntese ou colchete.</span><span class="sxs-lookup"><span data-stu-id="d6da5-499">Go to the matching brace, parenthesis, or square bracket.</span></span>

- <span data-ttu-id="d6da5-500">Cmd `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-500">Cmd: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d6da5-501">Modo de inserção de vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-501">Vi insert mode: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d6da5-502">Modo de comando vi: `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-502">Vi command mode: `<Ctrl+]>`</span></span>

### <a name="gotocolumn"></a><span data-ttu-id="d6da5-503">GotoColumn</span><span class="sxs-lookup"><span data-stu-id="d6da5-503">GotoColumn</span></span>

<span data-ttu-id="d6da5-504">Mova para a coluna indicada por ARG.</span><span class="sxs-lookup"><span data-stu-id="d6da5-504">Move to the column indicated by arg.</span></span>

- <span data-ttu-id="d6da5-505">Modo de comando vi: `<|>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-505">Vi command mode: `<|>`</span></span>

### <a name="gotofirstnonblankofline"></a><span data-ttu-id="d6da5-506">GotoFirstNonBlankOfLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-506">GotoFirstNonBlankOfLine</span></span>

<span data-ttu-id="d6da5-507">Mover o cursor para o primeiro caractere que não esteja em branco na linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-507">Move the cursor to the first non-blank character in the line.</span></span>

- <span data-ttu-id="d6da5-508">Modo de comando vi: `<^>` , `<_>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-508">Vi command mode: `<^>`, `<_>`</span></span>

### <a name="movetoendofline"></a><span data-ttu-id="d6da5-509">MoveToEndOfLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-509">MoveToEndOfLine</span></span>

<span data-ttu-id="d6da5-510">Mover o cursor para o fim da entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-510">Move the cursor to the end of the input.</span></span>

- <span data-ttu-id="d6da5-511">Modo de comando vi: `<End>` , `<$>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-511">Vi command mode: `<End>`, `<$>`</span></span>

### <a name="nextline"></a><span data-ttu-id="d6da5-512">Próxima</span><span class="sxs-lookup"><span data-stu-id="d6da5-512">NextLine</span></span>

<span data-ttu-id="d6da5-513">Mover o cursor para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-513">Move the cursor to the next line.</span></span>

- <span data-ttu-id="d6da5-514">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-514">Function is unbound.</span></span>

### <a name="nextword"></a><span data-ttu-id="d6da5-515">NextWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-515">NextWord</span></span>

<span data-ttu-id="d6da5-516">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-516">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d6da5-517">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6da5-517">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6da5-518">Cmd `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-518">Cmd: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="d6da5-519">Modo de inserção de vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-519">Vi insert mode: `<Ctrl+RightArrow>`</span></span>
- <span data-ttu-id="d6da5-520">Modo de comando vi: `<Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-520">Vi command mode: `<Ctrl+RightArrow>`</span></span>

### <a name="nextwordend"></a><span data-ttu-id="d6da5-521">NextWordEnd</span><span class="sxs-lookup"><span data-stu-id="d6da5-521">NextWordEnd</span></span>

<span data-ttu-id="d6da5-522">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-522">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d6da5-523">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6da5-523">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6da5-524">Modo de comando vi: `<e>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-524">Vi command mode: `<e>`</span></span>

### <a name="previousline"></a><span data-ttu-id="d6da5-525">Anterior</span><span class="sxs-lookup"><span data-stu-id="d6da5-525">PreviousLine</span></span>

<span data-ttu-id="d6da5-526">Mover o cursor para a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-526">Move the cursor to the previous line.</span></span>

- <span data-ttu-id="d6da5-527">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-527">Function is unbound.</span></span>

### <a name="shellbackwardword"></a><span data-ttu-id="d6da5-528">ShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-528">ShellBackwardWord</span></span>

<span data-ttu-id="d6da5-529">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-529">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d6da5-530">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-530">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d6da5-531">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-531">Function is unbound.</span></span>

### <a name="shellforwardword"></a><span data-ttu-id="d6da5-532">ShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-532">ShellForwardWord</span></span>

<span data-ttu-id="d6da5-533">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-533">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d6da5-534">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-534">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d6da5-535">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-535">Function is unbound.</span></span>

### <a name="shellnextword"></a><span data-ttu-id="d6da5-536">ShellNextWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-536">ShellNextWord</span></span>

<span data-ttu-id="d6da5-537">Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-537">Move the cursor forward to the end of the current word, or if between words, to the end of the next word.</span></span> <span data-ttu-id="d6da5-538">Os limites de palavras são definidos por tokens do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-538">Word boundaries are defined by PowerShell tokens.</span></span>

- <span data-ttu-id="d6da5-539">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-539">Function is unbound.</span></span>

### <a name="vibackwardchar"></a><span data-ttu-id="d6da5-540">ViBackwardChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-540">ViBackwardChar</span></span>

<span data-ttu-id="d6da5-541">Mover o cursor um caractere para a esquerda no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="d6da5-541">Move the cursor one character to the left in the Vi edit mode.</span></span> <span data-ttu-id="d6da5-542">Isso pode mover o cursor para a linha anterior de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-542">This may move the cursor to the previous line of multi-line input.</span></span>

- <span data-ttu-id="d6da5-543">Modo de inserção de vi: `<LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-543">Vi insert mode: `<LeftArrow>`</span></span>
- <span data-ttu-id="d6da5-544">Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-544">Vi command mode: `<LeftArrow>`, `<Backspace>`, `<h>`</span></span>

### <a name="vibackwardword"></a><span data-ttu-id="d6da5-545">ViBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-545">ViBackwardWord</span></span>

<span data-ttu-id="d6da5-546">Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-546">Move the cursor back to the start of the current word, or if between words, the start of the previous word.</span></span> <span data-ttu-id="d6da5-547">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6da5-547">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6da5-548">Modo de comando vi: `<b>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-548">Vi command mode: `<b>`</span></span>

### <a name="viforwardchar"></a><span data-ttu-id="d6da5-549">ViForwardChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-549">ViForwardChar</span></span>

<span data-ttu-id="d6da5-550">Mover o cursor um caractere para a direita no modo de edição vi.</span><span class="sxs-lookup"><span data-stu-id="d6da5-550">Move the cursor one character to the right in the Vi edit mode.</span></span> <span data-ttu-id="d6da5-551">Isso pode mover o cursor para a próxima linha de entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-551">This may move the cursor to the next line of multi-line input.</span></span>

- <span data-ttu-id="d6da5-552">Modo de inserção de vi: `<RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-552">Vi insert mode: `<RightArrow>`</span></span>
- <span data-ttu-id="d6da5-553">Modo de comando vi: `<RightArrow>` , `<Spacebar>` , `<l>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-553">Vi command mode: `<RightArrow>`, `<Spacebar>`, `<l>`</span></span>

### <a name="viendofglob"></a><span data-ttu-id="d6da5-554">ViEndOfGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-554">ViEndOfGlob</span></span>

<span data-ttu-id="d6da5-555">Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="d6da5-555">Moves the cursor to the end of the word, using only white space as delimiters.</span></span>

- <span data-ttu-id="d6da5-556">Modo de comando vi: `<E>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-556">Vi command mode: `<E>`</span></span>

### <a name="viendofpreviousglob"></a><span data-ttu-id="d6da5-557">ViEndOfPreviousGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-557">ViEndOfPreviousGlob</span></span>

<span data-ttu-id="d6da5-558">Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-558">Moves to the end of the previous word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="d6da5-559">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-559">Function is unbound.</span></span>

### <a name="vigotobrace"></a><span data-ttu-id="d6da5-560">ViGotoBrace</span><span class="sxs-lookup"><span data-stu-id="d6da5-560">ViGotoBrace</span></span>

<span data-ttu-id="d6da5-561">Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.</span><span class="sxs-lookup"><span data-stu-id="d6da5-561">Similar to GotoBrace, but is character based instead of token based.</span></span>

- <span data-ttu-id="d6da5-562">Modo de comando vi: `<%>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-562">Vi command mode: `<%>`</span></span>

### <a name="vinextglob"></a><span data-ttu-id="d6da5-563">ViNextGlob</span><span class="sxs-lookup"><span data-stu-id="d6da5-563">ViNextGlob</span></span>

<span data-ttu-id="d6da5-564">Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-564">Moves to the next word, using only white space as a word delimiter.</span></span>

- <span data-ttu-id="d6da5-565">Modo de comando vi: `<W>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-565">Vi command mode: `<W>`</span></span>

### <a name="vinextword"></a><span data-ttu-id="d6da5-566">ViNextWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-566">ViNextWord</span></span>

<span data-ttu-id="d6da5-567">Mover o cursor para frente até o início da próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-567">Move the cursor forward to the start of the next word.</span></span> <span data-ttu-id="d6da5-568">Os limites de palavras são definidos por um conjunto configurável de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d6da5-568">Word boundaries are defined by a configurable set of characters.</span></span>

- <span data-ttu-id="d6da5-569">Modo de comando vi: `<w>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-569">Vi command mode: `<w>`</span></span>

## <a name="history-functions"></a><span data-ttu-id="d6da5-570">Funções de histórico</span><span class="sxs-lookup"><span data-stu-id="d6da5-570">History functions</span></span>

### <a name="beginningofhistory"></a><span data-ttu-id="d6da5-571">BeginningOfHistory</span><span class="sxs-lookup"><span data-stu-id="d6da5-571">BeginningOfHistory</span></span>

<span data-ttu-id="d6da5-572">Mover para o primeiro item no histórico.</span><span class="sxs-lookup"><span data-stu-id="d6da5-572">Move to the first item in the history.</span></span>

- <span data-ttu-id="d6da5-573">Emacs `<Alt+<>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-573">Emacs: `<Alt+<>`</span></span>

### <a name="clearhistory"></a><span data-ttu-id="d6da5-574">ClearHistory</span><span class="sxs-lookup"><span data-stu-id="d6da5-574">ClearHistory</span></span>

<span data-ttu-id="d6da5-575">Limpa o histórico em PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d6da5-575">Clears history in PSReadLine.</span></span> <span data-ttu-id="d6da5-576">Isso não afeta o histórico do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-576">This does not affect PowerShell history.</span></span>

- <span data-ttu-id="d6da5-577">Cmd `<Alt+F7>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-577">Cmd: `<Alt+F7>`</span></span>

### <a name="endofhistory"></a><span data-ttu-id="d6da5-578">EndOfHistory</span><span class="sxs-lookup"><span data-stu-id="d6da5-578">EndOfHistory</span></span>

<span data-ttu-id="d6da5-579">Mover para o último item (a entrada atual) no histórico.</span><span class="sxs-lookup"><span data-stu-id="d6da5-579">Move to the last item (the current input) in the history.</span></span>

- <span data-ttu-id="d6da5-580">Emacs `<Alt+>>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-580">Emacs: `<Alt+>>`</span></span>

### <a name="forwardsearchhistory"></a><span data-ttu-id="d6da5-581">ForwardSearchHistory</span><span class="sxs-lookup"><span data-stu-id="d6da5-581">ForwardSearchHistory</span></span>

<span data-ttu-id="d6da5-582">Execute uma pesquisa de encaminhamento incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="d6da5-582">Perform an incremental forward search through history.</span></span>

- <span data-ttu-id="d6da5-583">Cmd `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-583">Cmd: `<Ctrl+s>`</span></span>
- <span data-ttu-id="d6da5-584">Emacs `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-584">Emacs: `<Ctrl+s>`</span></span>

### <a name="historysearchbackward"></a><span data-ttu-id="d6da5-585">HistorySearchBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-585">HistorySearchBackward</span></span>

<span data-ttu-id="d6da5-586">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-586">Replace the current input with the 'previous' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="d6da5-587">Cmd `<F8>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-587">Cmd: `<F8>`</span></span>

### <a name="historysearchforward"></a><span data-ttu-id="d6da5-588">HistorySearchForward</span><span class="sxs-lookup"><span data-stu-id="d6da5-588">HistorySearchForward</span></span>

<span data-ttu-id="d6da5-589">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-589">Replace the current input with the 'next' item from PSReadLine history that matches the characters between the start and the input and the cursor.</span></span>

- <span data-ttu-id="d6da5-590">Cmd `<Shift+F8>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-590">Cmd: `<Shift+F8>`</span></span>

### <a name="nexthistory"></a><span data-ttu-id="d6da5-591">NextHistory</span><span class="sxs-lookup"><span data-stu-id="d6da5-591">NextHistory</span></span>

<span data-ttu-id="d6da5-592">Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d6da5-592">Replace the current input with the 'next' item from PSReadLine history.</span></span>

- <span data-ttu-id="d6da5-593">Cmd `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-593">Cmd: `<DownArrow>`</span></span>
- <span data-ttu-id="d6da5-594">Emacs: `<DownArrow>` , `<Ctrl+n>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-594">Emacs: `<DownArrow>`, `<Ctrl+n>`</span></span>
- <span data-ttu-id="d6da5-595">Modo de inserção de vi: `<DownArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-595">Vi insert mode: `<DownArrow>`</span></span>
- <span data-ttu-id="d6da5-596">Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-596">Vi command mode: `<DownArrow>`, `<j>`, `<+>`</span></span>

### <a name="previoushistory"></a><span data-ttu-id="d6da5-597">PreviousHistory</span><span class="sxs-lookup"><span data-stu-id="d6da5-597">PreviousHistory</span></span>

<span data-ttu-id="d6da5-598">Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d6da5-598">Replace the current input with the 'previous' item from PSReadLine history.</span></span>

- <span data-ttu-id="d6da5-599">Cmd `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-599">Cmd: `<UpArrow>`</span></span>
- <span data-ttu-id="d6da5-600">Emacs: `<UpArrow>` , `<Ctrl+p>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-600">Emacs: `<UpArrow>`, `<Ctrl+p>`</span></span>
- <span data-ttu-id="d6da5-601">Modo de inserção de vi: `<UpArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-601">Vi insert mode: `<UpArrow>`</span></span>
- <span data-ttu-id="d6da5-602">Modo de comando vi: `<UpArrow>` , `<k>` , `<->`</span><span class="sxs-lookup"><span data-stu-id="d6da5-602">Vi command mode: `<UpArrow>`, `<k>`, `<->`</span></span>

### <a name="reversesearchhistory"></a><span data-ttu-id="d6da5-603">ReverseSearchHistory</span><span class="sxs-lookup"><span data-stu-id="d6da5-603">ReverseSearchHistory</span></span>

<span data-ttu-id="d6da5-604">Execute uma pesquisa regressiva incremental por meio do histórico.</span><span class="sxs-lookup"><span data-stu-id="d6da5-604">Perform an incremental backward search through history.</span></span>

- <span data-ttu-id="d6da5-605">Cmd `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-605">Cmd: `<Ctrl+r>`</span></span>
- <span data-ttu-id="d6da5-606">Emacs `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-606">Emacs: `<Ctrl+r>`</span></span>

### <a name="visearchhistorybackward"></a><span data-ttu-id="d6da5-607">ViSearchHistoryBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-607">ViSearchHistoryBackward</span></span>

<span data-ttu-id="d6da5-608">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="d6da5-608">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="d6da5-609">Modo de inserção de vi: `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-609">Vi insert mode: `<Ctrl+r>`</span></span>
- <span data-ttu-id="d6da5-610">Modo de comando vi: `</>` , `<Ctrl+r>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-610">Vi command mode: `</>`, `<Ctrl+r>`</span></span>

## <a name="completion-functions"></a><span data-ttu-id="d6da5-611">Funções de conclusão</span><span class="sxs-lookup"><span data-stu-id="d6da5-611">Completion functions</span></span>

### <a name="complete"></a><span data-ttu-id="d6da5-612">Concluir</span><span class="sxs-lookup"><span data-stu-id="d6da5-612">Complete</span></span>

<span data-ttu-id="d6da5-613">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-613">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="d6da5-614">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="d6da5-614">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="d6da5-615">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="d6da5-615">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="d6da5-616">Emacs `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-616">Emacs: `<Tab>`</span></span>

### <a name="menucomplete"></a><span data-ttu-id="d6da5-617">MenuComplete</span><span class="sxs-lookup"><span data-stu-id="d6da5-617">MenuComplete</span></span>

<span data-ttu-id="d6da5-618">Tentativa de executar a conclusão no texto ao redor do cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-618">Attempt to perform completion on the text surrounding the cursor.</span></span> <span data-ttu-id="d6da5-619">Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="d6da5-619">If there are multiple possible completions, the longest unambiguous prefix is used for completion.</span></span> <span data-ttu-id="d6da5-620">Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.</span><span class="sxs-lookup"><span data-stu-id="d6da5-620">If trying to complete the longest unambiguous completion, a list of possible completions is displayed.</span></span>

- <span data-ttu-id="d6da5-621">Cmd: `<Ctrl+@>` , `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-621">Cmd: `<Ctrl+@>`, `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="d6da5-622">Emacs `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-622">Emacs: `<Ctrl+Spacebar>`</span></span>

### <a name="possiblecompletions"></a><span data-ttu-id="d6da5-623">PossibleCompletions</span><span class="sxs-lookup"><span data-stu-id="d6da5-623">PossibleCompletions</span></span>

<span data-ttu-id="d6da5-624">Exiba a lista de conclusões possíveis.</span><span class="sxs-lookup"><span data-stu-id="d6da5-624">Display the list of possible completions.</span></span>

- <span data-ttu-id="d6da5-625">Emacs `<Alt+=>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-625">Emacs: `<Alt+=>`</span></span>
- <span data-ttu-id="d6da5-626">Modo de inserção de vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-626">Vi insert mode: `<Ctrl+Spacebar>`</span></span>
- <span data-ttu-id="d6da5-627">Modo de comando vi: `<Ctrl+Spacebar>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-627">Vi command mode: `<Ctrl+Spacebar>`</span></span>

### <a name="tabcompletenext"></a><span data-ttu-id="d6da5-628">TabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="d6da5-628">TabCompleteNext</span></span>

<span data-ttu-id="d6da5-629">Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="d6da5-629">Attempt to complete the text surrounding the cursor with the next available completion.</span></span>

- <span data-ttu-id="d6da5-630">Cmd `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-630">Cmd: `<Tab>`</span></span>
- <span data-ttu-id="d6da5-631">Modo de comando vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-631">Vi command mode: `<Tab>`</span></span>

### <a name="tabcompleteprevious"></a><span data-ttu-id="d6da5-632">TabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="d6da5-632">TabCompletePrevious</span></span>

<span data-ttu-id="d6da5-633">Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-633">Attempt to complete the text surrounding the cursor with the previous available completion.</span></span>

- <span data-ttu-id="d6da5-634">Cmd `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-634">Cmd: `<Shift+Tab>`</span></span>
- <span data-ttu-id="d6da5-635">Modo de comando vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-635">Vi command mode: `<Shift+Tab>`</span></span>

### <a name="vitabcompletenext"></a><span data-ttu-id="d6da5-636">ViTabCompleteNext</span><span class="sxs-lookup"><span data-stu-id="d6da5-636">ViTabCompleteNext</span></span>

<span data-ttu-id="d6da5-637">Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.</span><span class="sxs-lookup"><span data-stu-id="d6da5-637">Ends the current edit group, if needed, and invokes TabCompleteNext.</span></span>

- <span data-ttu-id="d6da5-638">Modo de inserção de vi: `<Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-638">Vi insert mode: `<Tab>`</span></span>

### <a name="vitabcompleteprevious"></a><span data-ttu-id="d6da5-639">ViTabCompletePrevious</span><span class="sxs-lookup"><span data-stu-id="d6da5-639">ViTabCompletePrevious</span></span>

<span data-ttu-id="d6da5-640">Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.</span><span class="sxs-lookup"><span data-stu-id="d6da5-640">Ends the current edit group, if needed, and invokes TabCompletePrevious.</span></span>

- <span data-ttu-id="d6da5-641">Modo de inserção de vi: `<Shift+Tab>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-641">Vi insert mode: `<Shift+Tab>`</span></span>

## <a name="miscellaneous-functions"></a><span data-ttu-id="d6da5-642">Funções diversas</span><span class="sxs-lookup"><span data-stu-id="d6da5-642">Miscellaneous functions</span></span>

### <a name="acceptnextsuggestionword"></a><span data-ttu-id="d6da5-643">AcceptNextSuggestionWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-643">AcceptNextSuggestionWord</span></span>

<span data-ttu-id="d6da5-644">Aceite a próxima palavra da sugestão embutida ou selecionada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-644">Accept the next word of the inline or selected suggestion.</span></span>

- <span data-ttu-id="d6da5-645">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-645">Function is unbound.</span></span>

### <a name="acceptsuggestion"></a><span data-ttu-id="d6da5-646">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="d6da5-646">AcceptSuggestion</span></span>

<span data-ttu-id="d6da5-647">Aceite a sugestão embutida ou selecionada atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-647">Accept the current inline or selected suggestion.</span></span>

- <span data-ttu-id="d6da5-648">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-648">Function is unbound.</span></span>

### <a name="capturescreen"></a><span data-ttu-id="d6da5-649">CaptureScreen</span><span class="sxs-lookup"><span data-stu-id="d6da5-649">CaptureScreen</span></span>

<span data-ttu-id="d6da5-650">Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.</span><span class="sxs-lookup"><span data-stu-id="d6da5-650">Start interactive screen capture - up/down arrows select lines, enter copies selected text to clipboard as text and html.</span></span>

- <span data-ttu-id="d6da5-651">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-651">Function is unbound.</span></span>

### <a name="clearscreen"></a><span data-ttu-id="d6da5-652">ClearScreen</span><span class="sxs-lookup"><span data-stu-id="d6da5-652">ClearScreen</span></span>

<span data-ttu-id="d6da5-653">Limpe a tela e desenhe a linha atual na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="d6da5-653">Clear the screen and draw the current line at the top of the screen.</span></span>

- <span data-ttu-id="d6da5-654">Cmd `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-654">Cmd: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d6da5-655">Emacs `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-655">Emacs: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d6da5-656">Modo de inserção de vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-656">Vi insert mode: `<Ctrl+l>`</span></span>
- <span data-ttu-id="d6da5-657">Modo de comando vi: `<Ctrl+l>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-657">Vi command mode: `<Ctrl+l>`</span></span>

### <a name="digitargument"></a><span data-ttu-id="d6da5-658">DigitArgument</span><span class="sxs-lookup"><span data-stu-id="d6da5-658">DigitArgument</span></span>

<span data-ttu-id="d6da5-659">Inicie um novo argumento de dígito para passar para outras funções.</span><span class="sxs-lookup"><span data-stu-id="d6da5-659">Start a new digit argument to pass to other functions.</span></span>

- <span data-ttu-id="d6da5-660">Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="d6da5-660">Cmd: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="d6da5-661">Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`</span><span class="sxs-lookup"><span data-stu-id="d6da5-661">Emacs: `<Alt+0>`, `<Alt+1>`, `<Alt+2>`, `<Alt+3>`, `<Alt+4>`, `<Alt+5>`, `<Alt+6>`, `<Alt+7>`, `<Alt+8>`, `<Alt+9>`, `<Alt+->`</span></span>
- <span data-ttu-id="d6da5-662">Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-662">Vi command mode: `<0>`, `<1>`, `<2>`, `<3>`, `<4>`, `<5>`, `<6>`, `<7>`, `<8>`, `<9>`</span></span>

### <a name="invokeprompt"></a><span data-ttu-id="d6da5-663">InvokePrompt</span><span class="sxs-lookup"><span data-stu-id="d6da5-663">InvokePrompt</span></span>

<span data-ttu-id="d6da5-664">Apaga o prompt atual e chama a função prompt para exibir novamente o prompt.</span><span class="sxs-lookup"><span data-stu-id="d6da5-664">Erases the current prompt and calls the prompt function to redisplay the prompt.</span></span> <span data-ttu-id="d6da5-665">Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-665">Useful for custom key handlers that change state, e.g. change the current directory.</span></span>

- <span data-ttu-id="d6da5-666">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-666">Function is unbound.</span></span>

### <a name="scrolldisplaydown"></a><span data-ttu-id="d6da5-667">ScrollDisplayDown</span><span class="sxs-lookup"><span data-stu-id="d6da5-667">ScrollDisplayDown</span></span>

<span data-ttu-id="d6da5-668">Rolar a exibição uma tela para baixo.</span><span class="sxs-lookup"><span data-stu-id="d6da5-668">Scroll the display down one screen.</span></span>

- <span data-ttu-id="d6da5-669">Cmd `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-669">Cmd: `<PageDown>`</span></span>
- <span data-ttu-id="d6da5-670">Emacs `<PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-670">Emacs: `<PageDown>`</span></span>

### <a name="scrolldisplaydownline"></a><span data-ttu-id="d6da5-671">ScrollDisplayDownLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-671">ScrollDisplayDownLine</span></span>

<span data-ttu-id="d6da5-672">Rolar a exibição uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="d6da5-672">Scroll the display down one line.</span></span>

- <span data-ttu-id="d6da5-673">Cmd `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-673">Cmd: `<Ctrl+PageDown>`</span></span>
- <span data-ttu-id="d6da5-674">Emacs `<Ctrl+PageDown>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-674">Emacs: `<Ctrl+PageDown>`</span></span>

### <a name="scrolldisplaytocursor"></a><span data-ttu-id="d6da5-675">ScrollDisplayToCursor</span><span class="sxs-lookup"><span data-stu-id="d6da5-675">ScrollDisplayToCursor</span></span>

<span data-ttu-id="d6da5-676">Rolar a exibição para o cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-676">Scroll the display to the cursor.</span></span>

- <span data-ttu-id="d6da5-677">Emacs `<Ctrl+End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-677">Emacs: `<Ctrl+End>`</span></span>

### <a name="scrolldisplaytop"></a><span data-ttu-id="d6da5-678">ScrollDisplayTop</span><span class="sxs-lookup"><span data-stu-id="d6da5-678">ScrollDisplayTop</span></span>

<span data-ttu-id="d6da5-679">Role a exibição para a parte superior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-679">Scroll the display to the top.</span></span>

- <span data-ttu-id="d6da5-680">Emacs `<Ctrl+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-680">Emacs: `<Ctrl+Home>`</span></span>

### <a name="scrolldisplayup"></a><span data-ttu-id="d6da5-681">ScrollDisplayUp</span><span class="sxs-lookup"><span data-stu-id="d6da5-681">ScrollDisplayUp</span></span>

<span data-ttu-id="d6da5-682">Rolar a exibição uma tela para cima.</span><span class="sxs-lookup"><span data-stu-id="d6da5-682">Scroll the display up one screen.</span></span>

- <span data-ttu-id="d6da5-683">Cmd `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-683">Cmd: `<PageUp>`</span></span>
- <span data-ttu-id="d6da5-684">Emacs `<PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-684">Emacs: `<PageUp>`</span></span>

### <a name="scrolldisplayupline"></a><span data-ttu-id="d6da5-685">ScrollDisplayUpLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-685">ScrollDisplayUpLine</span></span>

<span data-ttu-id="d6da5-686">Rolar a exibição uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="d6da5-686">Scroll the display up one line.</span></span>

- <span data-ttu-id="d6da5-687">Cmd `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-687">Cmd: `<Ctrl+PageUp>`</span></span>
- <span data-ttu-id="d6da5-688">Emacs `<Ctrl+PageUp>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-688">Emacs: `<Ctrl+PageUp>`</span></span>

### <a name="selfinsert"></a><span data-ttu-id="d6da5-689">SelfInsert</span><span class="sxs-lookup"><span data-stu-id="d6da5-689">SelfInsert</span></span>

<span data-ttu-id="d6da5-690">Insira a chave.</span><span class="sxs-lookup"><span data-stu-id="d6da5-690">Insert the key.</span></span>

- <span data-ttu-id="d6da5-691">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-691">Function is unbound.</span></span>

### <a name="showkeybindings"></a><span data-ttu-id="d6da5-692">ShowKeyBindings</span><span class="sxs-lookup"><span data-stu-id="d6da5-692">ShowKeyBindings</span></span>

<span data-ttu-id="d6da5-693">Mostrar todas as chaves associadas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-693">Show all bound keys.</span></span>

- <span data-ttu-id="d6da5-694">Cmd `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-694">Cmd: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="d6da5-695">Emacs `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-695">Emacs: `<Ctrl+Alt+?>`</span></span>
- <span data-ttu-id="d6da5-696">Modo de inserção de vi: `<Ctrl+Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-696">Vi insert mode: `<Ctrl+Alt+?>`</span></span>

### <a name="vicommandmode"></a><span data-ttu-id="d6da5-697">ViCommandMode</span><span class="sxs-lookup"><span data-stu-id="d6da5-697">ViCommandMode</span></span>

<span data-ttu-id="d6da5-698">Alterne o modo de operação atual de Vi-Insert para vi-Command.</span><span class="sxs-lookup"><span data-stu-id="d6da5-698">Switch the current operating mode from Vi-Insert to Vi-Command.</span></span>

- <span data-ttu-id="d6da5-699">Modo de inserção de vi: `<Escape>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-699">Vi insert mode: `<Escape>`</span></span>

### <a name="vidigitargumentinchord"></a><span data-ttu-id="d6da5-700">ViDigitArgumentInChord</span><span class="sxs-lookup"><span data-stu-id="d6da5-700">ViDigitArgumentInChord</span></span>

<span data-ttu-id="d6da5-701">Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.</span><span class="sxs-lookup"><span data-stu-id="d6da5-701">Start a new digit argument to pass to other functions while in one of vi's chords.</span></span>

- <span data-ttu-id="d6da5-702">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-702">Function is unbound.</span></span>

### <a name="vieditvisually"></a><span data-ttu-id="d6da5-703">ViEditVisually</span><span class="sxs-lookup"><span data-stu-id="d6da5-703">ViEditVisually</span></span>

<span data-ttu-id="d6da5-704">Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.</span><span class="sxs-lookup"><span data-stu-id="d6da5-704">Edit the command line in a text editor specified by $env:EDITOR or $env:VISUAL.</span></span>

- <span data-ttu-id="d6da5-705">Emacs `<Ctrl+x,Ctrl+e>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-705">Emacs: `<Ctrl+x,Ctrl+e>`</span></span>
- <span data-ttu-id="d6da5-706">Modo de comando vi: `<v>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-706">Vi command mode: `<v>`</span></span>

### <a name="viexit"></a><span data-ttu-id="d6da5-707">ViExit</span><span class="sxs-lookup"><span data-stu-id="d6da5-707">ViExit</span></span>

<span data-ttu-id="d6da5-708">Sai do Shell.</span><span class="sxs-lookup"><span data-stu-id="d6da5-708">Exits the shell.</span></span>

- <span data-ttu-id="d6da5-709">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-709">Function is unbound.</span></span>

### <a name="viinsertmode"></a><span data-ttu-id="d6da5-710">ViInsertMode</span><span class="sxs-lookup"><span data-stu-id="d6da5-710">ViInsertMode</span></span>

<span data-ttu-id="d6da5-711">Alterne para o modo de inserção.</span><span class="sxs-lookup"><span data-stu-id="d6da5-711">Switch to Insert mode.</span></span>

- <span data-ttu-id="d6da5-712">Modo de comando vi: `<i>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-712">Vi command mode: `<i>`</span></span>

### <a name="whatiskey"></a><span data-ttu-id="d6da5-713">WhatIsKey</span><span class="sxs-lookup"><span data-stu-id="d6da5-713">WhatIsKey</span></span>

<span data-ttu-id="d6da5-714">Leia uma chave e diga-me a que a chave está associada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-714">Read a key and tell me what the key is bound to.</span></span>

- <span data-ttu-id="d6da5-715">Cmd `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-715">Cmd: `<Alt+?>`</span></span>
- <span data-ttu-id="d6da5-716">Emacs `<Alt+?>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-716">Emacs: `<Alt+?>`</span></span>

## <a name="selection-functions"></a><span data-ttu-id="d6da5-717">Funções de seleção</span><span class="sxs-lookup"><span data-stu-id="d6da5-717">Selection functions</span></span>

### <a name="exchangepointandmark"></a><span data-ttu-id="d6da5-718">ExchangePointAndMark</span><span class="sxs-lookup"><span data-stu-id="d6da5-718">ExchangePointAndMark</span></span>

<span data-ttu-id="d6da5-719">O cursor é colocado no local da marca e a marca é movida para o local do cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-719">The cursor is placed at the location of the mark and the mark is moved to the location of the cursor.</span></span>

- <span data-ttu-id="d6da5-720">Emacs `<Ctrl+x,Ctrl+x>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-720">Emacs: `<Ctrl+x,Ctrl+x>`</span></span>

### <a name="selectall"></a><span data-ttu-id="d6da5-721">SelectAll</span><span class="sxs-lookup"><span data-stu-id="d6da5-721">SelectAll</span></span>

<span data-ttu-id="d6da5-722">Selecione a linha inteira.</span><span class="sxs-lookup"><span data-stu-id="d6da5-722">Select the entire line.</span></span>

- <span data-ttu-id="d6da5-723">Cmd `<Ctrl+a>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-723">Cmd: `<Ctrl+a>`</span></span>

### <a name="selectbackwardchar"></a><span data-ttu-id="d6da5-724">SelectBackwardChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-724">SelectBackwardChar</span></span>

<span data-ttu-id="d6da5-725">Ajuste a seleção atual para incluir o caractere anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-725">Adjust the current selection to include the previous character.</span></span>

- <span data-ttu-id="d6da5-726">Cmd `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-726">Cmd: `<Shift+LeftArrow>`</span></span>
- <span data-ttu-id="d6da5-727">Emacs `<Shift+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-727">Emacs: `<Shift+LeftArrow>`</span></span>

### <a name="selectbackwardsline"></a><span data-ttu-id="d6da5-728">SelectBackwardsLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-728">SelectBackwardsLine</span></span>

<span data-ttu-id="d6da5-729">Ajuste a seleção atual para incluir do cursor até o início da linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-729">Adjust the current selection to include from the cursor to the start of the line.</span></span>

- <span data-ttu-id="d6da5-730">Cmd `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-730">Cmd: `<Shift+Home>`</span></span>
- <span data-ttu-id="d6da5-731">Emacs `<Shift+Home>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-731">Emacs: `<Shift+Home>`</span></span>

### <a name="selectbackwardword"></a><span data-ttu-id="d6da5-732">SelectBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-732">SelectBackwardWord</span></span>

<span data-ttu-id="d6da5-733">Ajuste a seleção atual para incluir a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="d6da5-733">Adjust the current selection to include the previous word.</span></span>

- <span data-ttu-id="d6da5-734">Cmd `<Shift+Ctrl+LeftArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-734">Cmd: `<Shift+Ctrl+LeftArrow>`</span></span>
- <span data-ttu-id="d6da5-735">Emacs `<Alt+B>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-735">Emacs: `<Alt+B>`</span></span>

### <a name="selectforwardchar"></a><span data-ttu-id="d6da5-736">SelectForwardChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-736">SelectForwardChar</span></span>

<span data-ttu-id="d6da5-737">Ajuste a seleção atual para incluir o próximo caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-737">Adjust the current selection to include the next character.</span></span>

- <span data-ttu-id="d6da5-738">Cmd `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-738">Cmd: `<Shift+RightArrow>`</span></span>
- <span data-ttu-id="d6da5-739">Emacs `<Shift+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-739">Emacs: `<Shift+RightArrow>`</span></span>

### <a name="selectforwardword"></a><span data-ttu-id="d6da5-740">SelectForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-740">SelectForwardWord</span></span>

<span data-ttu-id="d6da5-741">Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.</span><span class="sxs-lookup"><span data-stu-id="d6da5-741">Adjust the current selection to include the next word using ForwardWord.</span></span>

- <span data-ttu-id="d6da5-742">Emacs `<Alt+F>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-742">Emacs: `<Alt+F>`</span></span>

### <a name="selectline"></a><span data-ttu-id="d6da5-743">Seleção</span><span class="sxs-lookup"><span data-stu-id="d6da5-743">SelectLine</span></span>

<span data-ttu-id="d6da5-744">Ajuste a seleção atual para incluir do cursor até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="d6da5-744">Adjust the current selection to include from the cursor to the end of the line.</span></span>

- <span data-ttu-id="d6da5-745">Cmd `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-745">Cmd: `<Shift+End>`</span></span>
- <span data-ttu-id="d6da5-746">Emacs `<Shift+End>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-746">Emacs: `<Shift+End>`</span></span>

### <a name="selectnextword"></a><span data-ttu-id="d6da5-747">SelectNextWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-747">SelectNextWord</span></span>

<span data-ttu-id="d6da5-748">Ajuste a seleção atual para incluir a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="d6da5-748">Adjust the current selection to include the next word.</span></span>

- <span data-ttu-id="d6da5-749">Cmd `<Shift+Ctrl+RightArrow>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-749">Cmd: `<Shift+Ctrl+RightArrow>`</span></span>

### <a name="selectshellbackwardword"></a><span data-ttu-id="d6da5-750">SelectShellBackwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-750">SelectShellBackwardWord</span></span>

<span data-ttu-id="d6da5-751">Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.</span><span class="sxs-lookup"><span data-stu-id="d6da5-751">Adjust the current selection to include the previous word using ShellBackwardWord.</span></span>

- <span data-ttu-id="d6da5-752">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-752">Function is unbound.</span></span>

### <a name="selectshellforwardword"></a><span data-ttu-id="d6da5-753">SelectShellForwardWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-753">SelectShellForwardWord</span></span>

<span data-ttu-id="d6da5-754">Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.</span><span class="sxs-lookup"><span data-stu-id="d6da5-754">Adjust the current selection to include the next word using ShellForwardWord.</span></span>

- <span data-ttu-id="d6da5-755">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-755">Function is unbound.</span></span>

### <a name="selectshellnextword"></a><span data-ttu-id="d6da5-756">SelectShellNextWord</span><span class="sxs-lookup"><span data-stu-id="d6da5-756">SelectShellNextWord</span></span>

<span data-ttu-id="d6da5-757">Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.</span><span class="sxs-lookup"><span data-stu-id="d6da5-757">Adjust the current selection to include the next word using ShellNextWord.</span></span>

- <span data-ttu-id="d6da5-758">A função está desassociada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-758">Function is unbound.</span></span>

### <a name="setmark"></a><span data-ttu-id="d6da5-759">Definir marca</span><span class="sxs-lookup"><span data-stu-id="d6da5-759">SetMark</span></span>

<span data-ttu-id="d6da5-760">Marque o local atual do cursor para uso em um comando de edição subsequente.</span><span class="sxs-lookup"><span data-stu-id="d6da5-760">Mark the current location of the cursor for use in a subsequent editing command.</span></span>

- <span data-ttu-id="d6da5-761">Emacs `<Ctrl+@>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-761">Emacs: `<Ctrl+@>`</span></span>

## <a name="predictive-intellisense-functions"></a><span data-ttu-id="d6da5-762">Funções IntelliSense preditivas</span><span class="sxs-lookup"><span data-stu-id="d6da5-762">Predictive IntelliSense functions</span></span>

> [!NOTE]
> <span data-ttu-id="d6da5-763">O IntelliSense preditiva precisa ser habilitado para usar essas funções.</span><span class="sxs-lookup"><span data-stu-id="d6da5-763">Predictive IntelliSense needs to be enabled to use these functions.</span></span>

### <a name="acceptnextwordsuggestion"></a><span data-ttu-id="d6da5-764">AcceptNextWordSuggestion</span><span class="sxs-lookup"><span data-stu-id="d6da5-764">AcceptNextWordSuggestion</span></span>

<span data-ttu-id="d6da5-765">Aceita a próxima palavra da sugestão embutida do IntelliSense preditiva.</span><span class="sxs-lookup"><span data-stu-id="d6da5-765">Accepts the next word of the inline suggestion from Predictive IntelliSense.</span></span>
<span data-ttu-id="d6da5-766">Essa função pode ser associada com <kbd>Ctrl</kbd> + <kbd>F</kbd> executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6da5-766">This function can be bound with <kbd>Ctrl</kbd>+<kbd>F</kbd> by running the following command.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord "Ctrl+f" -Function ForwardWord
```

### <a name="acceptsuggestion"></a><span data-ttu-id="d6da5-767">AcceptSuggestion</span><span class="sxs-lookup"><span data-stu-id="d6da5-767">AcceptSuggestion</span></span>

<span data-ttu-id="d6da5-768">Aceita a sugestão embutida atual do IntelliSense preditiva pressionando <kbd>RIGHTARROW</kbd> quando o cursor está no final da linha atual.</span><span class="sxs-lookup"><span data-stu-id="d6da5-768">Accepts the current inline suggestion from Predictive IntelliSense by pressing <kbd>RightArrow</kbd> when the cursor is at the end of the current line.</span></span>

## <a name="search-functions"></a><span data-ttu-id="d6da5-769">Funções de pesquisa</span><span class="sxs-lookup"><span data-stu-id="d6da5-769">Search functions</span></span>

### <a name="charactersearch"></a><span data-ttu-id="d6da5-770">CharacterSearch</span><span class="sxs-lookup"><span data-stu-id="d6da5-770">CharacterSearch</span></span>

<span data-ttu-id="d6da5-771">Ler um caractere e pesquisar a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-771">Read a character and search forward for the next occurrence of that character.</span></span>
<span data-ttu-id="d6da5-772">Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="d6da5-772">If an argument is specified, search forward (or backward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="d6da5-773">Cmd `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-773">Cmd: `<F3>`</span></span>
- <span data-ttu-id="d6da5-774">Emacs `<Ctrl+]>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-774">Emacs: `<Ctrl+]>`</span></span>
- <span data-ttu-id="d6da5-775">Modo de inserção de vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-775">Vi insert mode: `<F3>`</span></span>
- <span data-ttu-id="d6da5-776">Modo de comando vi: `<F3>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-776">Vi command mode: `<F3>`</span></span>

### <a name="charactersearchbackward"></a><span data-ttu-id="d6da5-777">CharacterSearchBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-777">CharacterSearchBackward</span></span>

<span data-ttu-id="d6da5-778">Ler um caractere e Pesquisar para a próxima ocorrência desse caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-778">Read a character and search backward for the next occurrence of that character.</span></span> <span data-ttu-id="d6da5-779">Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.</span><span class="sxs-lookup"><span data-stu-id="d6da5-779">If an argument is specified, search backward (or forward if negative) for the nth occurrence.</span></span>

- <span data-ttu-id="d6da5-780">Cmd `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-780">Cmd: `<Shift+F3>`</span></span>
- <span data-ttu-id="d6da5-781">Emacs `<Ctrl+Alt+]>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-781">Emacs: `<Ctrl+Alt+]>`</span></span>
- <span data-ttu-id="d6da5-782">Modo de inserção de vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-782">Vi insert mode: `<Shift+F3>`</span></span>
- <span data-ttu-id="d6da5-783">Modo de comando vi: `<Shift+F3>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-783">Vi command mode: `<Shift+F3>`</span></span>

### <a name="repeatlastcharsearch"></a><span data-ttu-id="d6da5-784">RepeatLastCharSearch</span><span class="sxs-lookup"><span data-stu-id="d6da5-784">RepeatLastCharSearch</span></span>

<span data-ttu-id="d6da5-785">Repita a última pesquisa de caractere gravada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-785">Repeat the last recorded character search.</span></span>

- <span data-ttu-id="d6da5-786">Modo de comando vi: `<;>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-786">Vi command mode: `<;>`</span></span>

### <a name="repeatlastcharsearchbackwards"></a><span data-ttu-id="d6da5-787">RepeatLastCharSearchBackwards</span><span class="sxs-lookup"><span data-stu-id="d6da5-787">RepeatLastCharSearchBackwards</span></span>

<span data-ttu-id="d6da5-788">Repita a última pesquisa de caractere gravada, mas na direção oposta.</span><span class="sxs-lookup"><span data-stu-id="d6da5-788">Repeat the last recorded character search, but in the opposite direction.</span></span>

- <span data-ttu-id="d6da5-789">Modo de comando vi: `<,>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-789">Vi command mode: `<,>`</span></span>

### <a name="repeatsearch"></a><span data-ttu-id="d6da5-790">RepeatSearch</span><span class="sxs-lookup"><span data-stu-id="d6da5-790">RepeatSearch</span></span>

<span data-ttu-id="d6da5-791">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="d6da5-791">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="d6da5-792">Modo de comando vi: `<n>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-792">Vi command mode: `<n>`</span></span>

### <a name="repeatsearchbackward"></a><span data-ttu-id="d6da5-793">RepeatSearchBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-793">RepeatSearchBackward</span></span>

<span data-ttu-id="d6da5-794">Repita a última pesquisa na mesma direção que antes.</span><span class="sxs-lookup"><span data-stu-id="d6da5-794">Repeat the last search in the same direction as before.</span></span>

- <span data-ttu-id="d6da5-795">Modo de comando vi: `<N>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-795">Vi command mode: `<N>`</span></span>

### <a name="searchchar"></a><span data-ttu-id="d6da5-796">SearchChar</span><span class="sxs-lookup"><span data-stu-id="d6da5-796">SearchChar</span></span>

<span data-ttu-id="d6da5-797">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-797">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="d6da5-798">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="d6da5-798">This is for 't' functionality.</span></span>

- <span data-ttu-id="d6da5-799">Modo de comando vi: `<f>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-799">Vi command mode: `<f>`</span></span>

### <a name="searchcharbackward"></a><span data-ttu-id="d6da5-800">SearchCharBackward</span><span class="sxs-lookup"><span data-stu-id="d6da5-800">SearchCharBackward</span></span>

<span data-ttu-id="d6da5-801">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-801">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="d6da5-802">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="d6da5-802">This is for 'T' functionality.</span></span>

- <span data-ttu-id="d6da5-803">Modo de comando vi: `<F>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-803">Vi command mode: `<F>`</span></span>

### <a name="searchcharbackwardwithbackoff"></a><span data-ttu-id="d6da5-804">SearchCharBackwardWithBackoff</span><span class="sxs-lookup"><span data-stu-id="d6da5-804">SearchCharBackwardWithBackoff</span></span>

<span data-ttu-id="d6da5-805">Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-805">Read the next character and then find it, going backward, and then back off a character.</span></span> <span data-ttu-id="d6da5-806">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="d6da5-806">This is for 'T' functionality.</span></span>

- <span data-ttu-id="d6da5-807">Modo de comando vi: `<T>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-807">Vi command mode: `<T>`</span></span>

### <a name="searchcharwithbackoff"></a><span data-ttu-id="d6da5-808">SearchCharWithBackoff</span><span class="sxs-lookup"><span data-stu-id="d6da5-808">SearchCharWithBackoff</span></span>

<span data-ttu-id="d6da5-809">Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere.</span><span class="sxs-lookup"><span data-stu-id="d6da5-809">Read the next character and then find it, going forward, and then back off a character.</span></span> <span data-ttu-id="d6da5-810">Isso é para a funcionalidade ' T'.</span><span class="sxs-lookup"><span data-stu-id="d6da5-810">This is for 't' functionality.</span></span>

- <span data-ttu-id="d6da5-811">Modo de comando vi: `<t>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-811">Vi command mode: `<t>`</span></span>

### <a name="searchforward"></a><span data-ttu-id="d6da5-812">SearchForward</span><span class="sxs-lookup"><span data-stu-id="d6da5-812">SearchForward</span></span>

<span data-ttu-id="d6da5-813">Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.</span><span class="sxs-lookup"><span data-stu-id="d6da5-813">Prompts for a search string and initiates search upon AcceptLine.</span></span>

- <span data-ttu-id="d6da5-814">Modo de inserção de vi: `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-814">Vi insert mode: `<Ctrl+s>`</span></span>
- <span data-ttu-id="d6da5-815">Modo de comando vi: `<?>` , `<Ctrl+s>`</span><span class="sxs-lookup"><span data-stu-id="d6da5-815">Vi command mode: `<?>`, `<Ctrl+s>`</span></span>

## <a name="custom-key-bindings"></a><span data-ttu-id="d6da5-816">Associações de chave personalizadas</span><span class="sxs-lookup"><span data-stu-id="d6da5-816">Custom Key Bindings</span></span>

<span data-ttu-id="d6da5-817">O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="d6da5-817">PSReadLine supports custom key bindings using the cmdlet `Set-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="d6da5-818">A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo</span><span class="sxs-lookup"><span data-stu-id="d6da5-818">Most custom key bindings call one of the above functions, for example</span></span>

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

<span data-ttu-id="d6da5-819">Você pode associar um ScriptBlock a uma chave.</span><span class="sxs-lookup"><span data-stu-id="d6da5-819">You can bind a ScriptBlock to a key.</span></span> <span data-ttu-id="d6da5-820">O ScriptBlock pode fazer praticamente qualquer coisa que você desejar.</span><span class="sxs-lookup"><span data-stu-id="d6da5-820">The ScriptBlock can do pretty much anything you want.</span></span> <span data-ttu-id="d6da5-821">Alguns exemplos úteis incluem</span><span class="sxs-lookup"><span data-stu-id="d6da5-821">Some useful examples include</span></span>

- <span data-ttu-id="d6da5-822">editar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="d6da5-822">edit the command line</span></span>
- <span data-ttu-id="d6da5-823">abrindo uma nova janela (por exemplo, ajuda)</span><span class="sxs-lookup"><span data-stu-id="d6da5-823">opening a new window (e.g. help)</span></span>
- <span data-ttu-id="d6da5-824">alterar os diretórios sem alterar a linha de comando</span><span class="sxs-lookup"><span data-stu-id="d6da5-824">change directories without changing the command line</span></span>

<span data-ttu-id="d6da5-825">O ScriptBlock recebe dois argumentos:</span><span class="sxs-lookup"><span data-stu-id="d6da5-825">The ScriptBlock receives two arguments:</span></span>

- <span data-ttu-id="d6da5-826">`$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-826">`$key` - A **[ConsoleKeyInfo]** object that is the key that triggered the custom binding.</span></span> <span data-ttu-id="d6da5-827">Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key.</span><span class="sxs-lookup"><span data-stu-id="d6da5-827">If you bind the same ScriptBlock to multiple keys and need to perform different actions depending on the key, you can check $key.</span></span> <span data-ttu-id="d6da5-828">Muitas associações personalizadas ignoram esse argumento.</span><span class="sxs-lookup"><span data-stu-id="d6da5-828">Many custom bindings ignore this argument.</span></span>

- <span data-ttu-id="d6da5-829">`$arg` -Um argumento arbitrário.</span><span class="sxs-lookup"><span data-stu-id="d6da5-829">`$arg` - An arbitrary argument.</span></span> <span data-ttu-id="d6da5-830">Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="d6da5-830">Most often, this would be an integer argument that the user passes from the key bindings DigitArgument.</span></span> <span data-ttu-id="d6da5-831">Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.</span><span class="sxs-lookup"><span data-stu-id="d6da5-831">If your binding doesn't accept arguments, it's reasonable to ignore this argument.</span></span>

<span data-ttu-id="d6da5-832">Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="d6da5-832">Let's take a look at an example that adds a command line to history without executing it.</span></span> <span data-ttu-id="d6da5-833">Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.</span><span class="sxs-lookup"><span data-stu-id="d6da5-833">This is useful when you realize you forgot to do something, but don't want to re-enter the command line you've already entered.</span></span>

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

<span data-ttu-id="d6da5-834">Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d6da5-834">You can see many more examples in the file `SamplePSReadLineProfile.ps1` which is installed in the PSReadLine module folder.</span></span>

<span data-ttu-id="d6da5-835">A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d6da5-835">Most key bindings use some helper functions for editing the command line.</span></span>
<span data-ttu-id="d6da5-836">Essas APIs são documentadas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="d6da5-836">Those APIs are documented in the next section.</span></span>

## <a name="custom-key-binding-support-apis"></a><span data-ttu-id="d6da5-837">APIs de suporte de associação de chave personalizada</span><span class="sxs-lookup"><span data-stu-id="d6da5-837">Custom Key Binding Support APIs</span></span>

<span data-ttu-id="d6da5-838">As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave.</span><span class="sxs-lookup"><span data-stu-id="d6da5-838">The following functions are public in Microsoft.PowerShell.PSConsoleReadLine, but cannot be directly bound to a key.</span></span> <span data-ttu-id="d6da5-839">A maioria é útil em associações de chave personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-839">Most are useful in custom key bindings.</span></span>

```csharp
void AddToHistory(string command)
```

<span data-ttu-id="d6da5-840">Adicione uma linha de comando ao histórico sem executá-lo.</span><span class="sxs-lookup"><span data-stu-id="d6da5-840">Add a command line to history without executing it.</span></span>

```csharp
void ClearKillRing()
```

<span data-ttu-id="d6da5-841">Limpe o Kill-Ring.</span><span class="sxs-lookup"><span data-stu-id="d6da5-841">Clear the kill-ring.</span></span>  <span data-ttu-id="d6da5-842">Isso é usado principalmente para teste.</span><span class="sxs-lookup"><span data-stu-id="d6da5-842">This is mostly used for testing.</span></span>

```csharp
void Delete(int start, int length)
```

<span data-ttu-id="d6da5-843">Exclua os caracteres de comprimento do início.</span><span class="sxs-lookup"><span data-stu-id="d6da5-843">Delete length characters from start.</span></span>  <span data-ttu-id="d6da5-844">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-844">This operation supports undo/redo.</span></span>

```csharp
void Ding()
```

<span data-ttu-id="d6da5-845">Execute a ação de-Ding com base na preferência dos usuários.</span><span class="sxs-lookup"><span data-stu-id="d6da5-845">Perform the Ding action based on the users preference.</span></span>

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

<span data-ttu-id="d6da5-846">Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-846">These two functions retrieve useful information about the current state of the input buffer.</span></span>  <span data-ttu-id="d6da5-847">A primeira é mais comumente usada para casos simples.</span><span class="sxs-lookup"><span data-stu-id="d6da5-847">The first is more commonly used for simple cases.</span></span>  <span data-ttu-id="d6da5-848">O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.</span><span class="sxs-lookup"><span data-stu-id="d6da5-848">The second is used if your binding is doing something more advanced with the Ast.</span></span>

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(string[] Chord)
```

<span data-ttu-id="d6da5-849">Essas duas funções são usadas pelo `Get-PSReadLineKeyHandler` .</span><span class="sxs-lookup"><span data-stu-id="d6da5-849">These two functions are used by `Get-PSReadLineKeyHandler`.</span></span> <span data-ttu-id="d6da5-850">O primeiro é usado para obter todas as associações de chave.</span><span class="sxs-lookup"><span data-stu-id="d6da5-850">The first is used to get all key bindings.</span></span> <span data-ttu-id="d6da5-851">O segundo é usado para obter associações de chave específicas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-851">The second is used to get specific key bindings.</span></span>

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

<span data-ttu-id="d6da5-852">Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-852">This function is used by Get-PSReadLineOption and probably isn't too useful in a custom key binding.</span></span>

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

<span data-ttu-id="d6da5-853">Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento.</span><span class="sxs-lookup"><span data-stu-id="d6da5-853">If there is no selection on the command line, -1 will be returned in both start and length.</span></span> <span data-ttu-id="d6da5-854">Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.</span><span class="sxs-lookup"><span data-stu-id="d6da5-854">If there is a selection on the command line, the start and length of the selection are returned.</span></span>

```csharp
void Insert(char c)
void Insert(string s)
```

<span data-ttu-id="d6da5-855">Inserir um caractere ou uma cadeia de caracteres no cursor.</span><span class="sxs-lookup"><span data-stu-id="d6da5-855">Insert a character or string at the cursor.</span></span>  <span data-ttu-id="d6da5-856">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-856">This operation supports undo/redo.</span></span>

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

<span data-ttu-id="d6da5-857">Esse é o ponto de entrada principal para PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d6da5-857">This is the main entry point to PSReadLine.</span></span> <span data-ttu-id="d6da5-858">Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-858">It does not support recursion, so is not useful in a custom key binding.</span></span>

```csharp
void RemoveKeyHandler(string[] key)
```

<span data-ttu-id="d6da5-859">Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6da5-859">This function is used by Remove-PSReadLineKeyHandler and probably isn't too useful in a custom key binding.</span></span>

```csharp
void Replace(int start, int length, string replacement)
```

<span data-ttu-id="d6da5-860">Substitua algumas das entradas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-860">Replace some of the input.</span></span> <span data-ttu-id="d6da5-861">Esta operação dá suporte a desfazer/refazer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-861">This operation supports undo/redo.</span></span> <span data-ttu-id="d6da5-862">Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-862">This is preferred over Delete followed by Insert because it is treated as a single action for undo.</span></span>

```csharp
void SetCursorPosition(int cursor)
```

<span data-ttu-id="d6da5-863">Mover o cursor para o deslocamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="d6da5-863">Move the cursor to the given offset.</span></span> <span data-ttu-id="d6da5-864">O movimento do cursor não é rastreado para desfazer.</span><span class="sxs-lookup"><span data-stu-id="d6da5-864">Cursor movement is not tracked for undo.</span></span>

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

<span data-ttu-id="d6da5-865">Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.</span><span class="sxs-lookup"><span data-stu-id="d6da5-865">This function is a helper method used by the cmdlet Set-PSReadLineOption, but might be useful to a custom key binding that wants to temporarily change a setting.</span></span>

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

<span data-ttu-id="d6da5-866">Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument.</span><span class="sxs-lookup"><span data-stu-id="d6da5-866">This helper method is used for custom bindings that honor DigitArgument.</span></span> <span data-ttu-id="d6da5-867">Uma chamada típica é parecida com</span><span class="sxs-lookup"><span data-stu-id="d6da5-867">A typical call looks like</span></span>

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a><span data-ttu-id="d6da5-868">Observação</span><span class="sxs-lookup"><span data-stu-id="d6da5-868">Note</span></span>

### <a name="command-history"></a><span data-ttu-id="d6da5-869">Histórico de comandos</span><span class="sxs-lookup"><span data-stu-id="d6da5-869">Command History</span></span>

<span data-ttu-id="d6da5-870">PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d6da5-870">PSReadLine maintains a history file containing all the commands and data you have entered from the command line.</span></span> <span data-ttu-id="d6da5-871">Isso pode conter dados confidenciais, incluindo senhas.</span><span class="sxs-lookup"><span data-stu-id="d6da5-871">This may contain sensitive data including passwords.</span></span> <span data-ttu-id="d6da5-872">Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="d6da5-872">For example, if you use the `ConvertTo-SecureString` cmdlet the password is logged in the history file as plain text.</span></span> <span data-ttu-id="d6da5-873">Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` .</span><span class="sxs-lookup"><span data-stu-id="d6da5-873">The history files is a file named `$($host.Name)_history.txt`.</span></span> <span data-ttu-id="d6da5-874">Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="d6da5-874">On Windows systems the history file is stored at `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine`.</span></span> <span data-ttu-id="d6da5-875">Em sistemas não Windows, os arquivos de histórico são armazenados em `$env:XDG_DATA_HOME/powershell/PSReadLine` ou `$env:HOME/.local/share/powershell/PSReadLine` .</span><span class="sxs-lookup"><span data-stu-id="d6da5-875">On non-Windows systems, the history files is stored at `$env:XDG_DATA_HOME/powershell/PSReadLine` or `$env:HOME/.local/share/powershell/PSReadLine`.</span></span>

### <a name="feedback--contributing-to-psreadline"></a><span data-ttu-id="d6da5-876">Comentários & contribuindo para o PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d6da5-876">Feedback & Contributing To PSReadLine</span></span>

[<span data-ttu-id="d6da5-877">PSReadLine no GitHub</span><span class="sxs-lookup"><span data-stu-id="d6da5-877">PSReadLine on GitHub</span></span>](https://github.com/PowerShell/PSReadLine)

<span data-ttu-id="d6da5-878">Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.</span><span class="sxs-lookup"><span data-stu-id="d6da5-878">Feel free to submit a pull request or submit feedback on the GitHub page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6da5-879">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d6da5-879">See Also</span></span>

<span data-ttu-id="d6da5-880">O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .</span><span class="sxs-lookup"><span data-stu-id="d6da5-880">PSReadLine is heavily influenced by the GNU [readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library.</span></span>
