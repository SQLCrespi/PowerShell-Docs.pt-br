---
description: Descreve como obter e executar comandos no histórico de comandos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: 64a8fac4f25ac60be58aca8549748b9e4dde6c3b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196198"
---
# <a name="about-history"></a><span data-ttu-id="d84aa-104">Sobre o histórico</span><span class="sxs-lookup"><span data-stu-id="d84aa-104">About History</span></span>

## <a name="short-description"></a><span data-ttu-id="d84aa-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="d84aa-105">Short Description</span></span>
<span data-ttu-id="d84aa-106">Descreve como obter e executar comandos no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-106">Describes how to get and run commands in the command history.</span></span>

## <a name="long-description"></a><span data-ttu-id="d84aa-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="d84aa-107">Long Description</span></span>

<span data-ttu-id="d84aa-108">Quando você insere um comando no prompt de comando, o PowerShell salva o comando no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-108">When you enter a command at the command prompt, PowerShell saves the command in the command history.</span></span> <span data-ttu-id="d84aa-109">Você pode usar os comandos no histórico como um registro do seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="d84aa-109">You can use the commands in the history as a record of your work.</span></span> <span data-ttu-id="d84aa-110">E, você pode recuperar e executar os comandos no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-110">And, you can recall and run the commands from the command history.</span></span>

<span data-ttu-id="d84aa-111">O PowerShell tem dois provedores de histórico diferentes: o histórico interno e o histórico gerenciado pelo módulo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="d84aa-111">PowerShell has two different history providers: the built-in history and the history managed by the **PSReadLine** module.</span></span> <span data-ttu-id="d84aa-112">Os históricos são gerenciados separadamente, mas ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.</span><span class="sxs-lookup"><span data-stu-id="d84aa-112">The histories are managed separately, but both histories are available in sessions where **PSReadLine** is loaded.</span></span>

## <a name="using-the-psreadline-history"></a><span data-ttu-id="d84aa-113">Usando o histórico de PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d84aa-113">Using the PSReadLine history</span></span>

<span data-ttu-id="d84aa-114">O histórico de PSReadLine controla os comandos usados em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d84aa-114">The PSReadLine history tracks the commands used in all PowerShell sessions.</span></span>
<span data-ttu-id="d84aa-115">O histórico é gravado em um arquivo central por host.</span><span class="sxs-lookup"><span data-stu-id="d84aa-115">The history is written to a central file per host.</span></span> <span data-ttu-id="d84aa-116">Esse arquivo de histórico está disponível para todas as sessões e contém todo o histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="d84aa-116">That history file is available to all sessions and contains all past history.</span></span> <span data-ttu-id="d84aa-117">O histórico não é excluído quando a sessão termina.</span><span class="sxs-lookup"><span data-stu-id="d84aa-117">The history is not deleted when the session ends.</span></span> <span data-ttu-id="d84aa-118">Além disso, esse histórico não pode ser gerenciado pelos `*-History` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d84aa-118">Also, that history cannot be managed by the `*-History` cmdlets.</span></span> <span data-ttu-id="d84aa-119">Para obter mais informações, consulte [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="d84aa-119">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

## <a name="using-the-built-in-session-history"></a><span data-ttu-id="d84aa-120">Usando o histórico de sessões internas</span><span class="sxs-lookup"><span data-stu-id="d84aa-120">Using the built-in session history</span></span>

<span data-ttu-id="d84aa-121">O histórico interno controla apenas os comandos usados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d84aa-121">The built-in history only tracks the commands used in the current session.</span></span> <span data-ttu-id="d84aa-122">O histórico não está disponível para outras sessões e é excluído quando a sessão termina.</span><span class="sxs-lookup"><span data-stu-id="d84aa-122">The history is not available to other sessions and is deleted when the session ends.</span></span>

### <a name="history-cmdlets"></a><span data-ttu-id="d84aa-123">Cmdlets de histórico</span><span class="sxs-lookup"><span data-stu-id="d84aa-123">History Cmdlets</span></span>

<span data-ttu-id="d84aa-124">O PowerShell tem um conjunto de cmdlets que gerenciam o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-124">PowerShell has a set of cmdlets that manage the command history.</span></span>

| <span data-ttu-id="d84aa-125">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d84aa-125">Cmdlet</span></span>           | <span data-ttu-id="d84aa-126">Alias</span><span class="sxs-lookup"><span data-stu-id="d84aa-126">Alias</span></span>  | <span data-ttu-id="d84aa-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="d84aa-127">Description</span></span>                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | <span data-ttu-id="d84aa-128">Obtém o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-128">Gets the command history.</span></span>                  |
| `Invoke-History` | `r`    | <span data-ttu-id="d84aa-129">Executa um comando no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-129">Runs a command in the command history.</span></span>     |
| `Add-History`    |        | <span data-ttu-id="d84aa-130">Adiciona um comando ao histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-130">Adds a command to the command history.</span></span>     |
| `Clear-History`  | `clhy` | <span data-ttu-id="d84aa-131">Exclui comandos do histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-131">Deletes commands from the command history.</span></span> |

### <a name="keyboard-shortcuts-for-managing-history"></a><span data-ttu-id="d84aa-132">Atalhos de teclado para gerenciamento de histórico</span><span class="sxs-lookup"><span data-stu-id="d84aa-132">Keyboard Shortcuts for Managing History</span></span>

<span data-ttu-id="d84aa-133">No console do PowerShell, você pode usar os seguintes atalhos para gerenciar o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-133">In the PowerShell console, you can use the following shortcuts to manage the command history.</span></span>

- <span data-ttu-id="d84aa-134"><kbd>Upseta</kbd> – exibe o comando anterior.</span><span class="sxs-lookup"><span data-stu-id="d84aa-134"><kbd>UpArrow</kbd> - Displays the previous command.</span></span>
- <span data-ttu-id="d84aa-135"><kbd>Seta</kbd> -exibe o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="d84aa-135"><kbd>DownArrow</kbd> - Displays the next command.</span></span>
- <span data-ttu-id="d84aa-136"><kbd>F7</kbd> -exibe o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-136"><kbd>F7</kbd> - Displays the command history.</span></span>
- <span data-ttu-id="d84aa-137"><kbd>ESC</kbd> – para ocultar o histórico.</span><span class="sxs-lookup"><span data-stu-id="d84aa-137"><kbd>ESC</kbd> - To hide the history.</span></span>
- <span data-ttu-id="d84aa-138"><kbd>F8</kbd> -localiza um comando.</span><span class="sxs-lookup"><span data-stu-id="d84aa-138"><kbd>F8</kbd> - Finds a command.</span></span> <span data-ttu-id="d84aa-139">Digite um ou mais caracteres e pressione <kbd>F8</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d84aa-139">Type one or more characters then press <kbd>F8</kbd>.</span></span> <span data-ttu-id="d84aa-140">Pressione <kbd>F8</kbd> novamente na próxima instância.</span><span class="sxs-lookup"><span data-stu-id="d84aa-140">Press <kbd>F8</kbd> again the next instance.</span></span>
- <span data-ttu-id="d84aa-141"><kbd>F9</kbd> -localizar um comando por ID do histórico.</span><span class="sxs-lookup"><span data-stu-id="d84aa-141"><kbd>F9</kbd> - Find a command by history ID.</span></span> <span data-ttu-id="d84aa-142">Digite a ID do histórico e pressione <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d84aa-142">Type the history ID then press <kbd>F9</kbd>.</span></span> <span data-ttu-id="d84aa-143">Pressione <kbd>F7</kbd> para localizar a ID.</span><span class="sxs-lookup"><span data-stu-id="d84aa-143">Press <kbd>F7</kbd> to find the ID.</span></span>
- <span data-ttu-id="d84aa-144"><kbd>#</kbd>`<string>`</kbd><kbd>Guia</kbd> – pesquise o histórico para `*<string>*` e retorna a correspondência mais recente.</span><span class="sxs-lookup"><span data-stu-id="d84aa-144"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> - Search the history for `*<string>*` and returns the most recent match.</span></span> <span data-ttu-id="d84aa-145">Se você pressionar <kbd>Tab</kbd> repetidamente, ela percorrerá os itens correspondentes em seu histórico.</span><span class="sxs-lookup"><span data-stu-id="d84aa-145">If you press <kbd>Tab</kbd> repeatedly, it cycles through the matching items in your history.</span></span>

> [!NOTE]
> <span data-ttu-id="d84aa-146">Essas associações de chave são implementadas pelo aplicativo host do console.</span><span class="sxs-lookup"><span data-stu-id="d84aa-146">These key bindings are implemented by the console host application.</span></span> <span data-ttu-id="d84aa-147">Outros aplicativos, como Visual Studio Code ou terminal do Windows, podem ter diferentes associações de chave.</span><span class="sxs-lookup"><span data-stu-id="d84aa-147">Other applications, such as Visual Studio Code or Windows Terminal, can have different key bindings.</span></span> <span data-ttu-id="d84aa-148">As associações podem ser substituídas pelo módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="d84aa-148">The bindings can be overridden by the PSReadLine module.</span></span> <span data-ttu-id="d84aa-149">O PSReadLine é carregado automaticamente quando você inicia uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d84aa-149">PSReadLine loads automatically when you start a PowerShell session.</span></span>
> <span data-ttu-id="d84aa-150">Com PSReadLine carregado, <kbd>F7</kbd> e <kbd>F9</kbd> não são associados a nenhuma função.</span><span class="sxs-lookup"><span data-stu-id="d84aa-150">With PSReadLine loaded, <kbd>F7</kbd> and <kbd>F9</kbd> are not bound to any function.</span></span> <span data-ttu-id="d84aa-151">PSReadLine não fornece funcionalidade equivalente.</span><span class="sxs-lookup"><span data-stu-id="d84aa-151">PSReadLine does not provide equivalent functionality.</span></span> <span data-ttu-id="d84aa-152">Para obter mais informações, consulte [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="d84aa-152">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="d84aa-153">MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="d84aa-153">MaximumHistoryCount</span></span>

<span data-ttu-id="d84aa-154">A `$MaximumHistoryCount` variável de preferência determina o número máximo de comandos que o PowerShell salva no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="d84aa-154">The `$MaximumHistoryCount` preference variable determines the maximum number of commands that PowerShell saves in the command history.</span></span> <span data-ttu-id="d84aa-155">O valor padrão é</span><span class="sxs-lookup"><span data-stu-id="d84aa-155">The default value is</span></span>
4096.

<span data-ttu-id="d84aa-156">Por exemplo, o comando a seguir reduz os `$MaximumHistoryCount` comandos para 100:</span><span class="sxs-lookup"><span data-stu-id="d84aa-156">For example, the following command lowers the `$MaximumHistoryCount` to 100 commands:</span></span>

```powershell
$MaximumHistoryCount = 100
```

<span data-ttu-id="d84aa-157">Para aplicar a configuração, reinicie o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d84aa-157">To apply the setting, restart PowerShell.</span></span>

<span data-ttu-id="d84aa-158">Para salvar o novo valor de variável para todas as sessões do PowerShell, adicione a instrução de atribuição a um perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d84aa-158">To save the new variable value for all your PowerShell sessions, add the assignment statement to a PowerShell profile.</span></span> <span data-ttu-id="d84aa-159">Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d84aa-159">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="d84aa-160">Para obter mais informações sobre a `$MaximumHistoryCount` variável de preferência, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d84aa-160">For more information about the `$MaximumHistoryCount` preference variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="order-of-commands-in-the-history"></a><span data-ttu-id="d84aa-161">Ordem dos comandos no histórico</span><span class="sxs-lookup"><span data-stu-id="d84aa-161">Order of Commands in the History</span></span>

<span data-ttu-id="d84aa-162">Os comandos são adicionados ao histórico quando o comando termina a execução, não quando o comando é inserido.</span><span class="sxs-lookup"><span data-stu-id="d84aa-162">Commands are added to the history when the command finishes executing, not when the command is entered.</span></span> <span data-ttu-id="d84aa-163">Se os comandos levar algum tempo para serem concluídos ou se os comandos estiverem sendo executados em um prompt aninhado, os comandos poderão parecer estar fora de ordem no histórico.</span><span class="sxs-lookup"><span data-stu-id="d84aa-163">If commands take some time to be completed, or if the commands are executing in a nested prompt, the commands might appear to be out of order in the history.</span></span> <span data-ttu-id="d84aa-164">Os comandos que estão sendo executados em um prompt aninhado são concluídos somente quando você sai do nível do prompt.</span><span class="sxs-lookup"><span data-stu-id="d84aa-164">Commands that are executing in a nested prompt are completed only when you exit the prompt level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d84aa-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d84aa-165">See Also</span></span>

- [<span data-ttu-id="d84aa-166">about_Line_Editing</span><span class="sxs-lookup"><span data-stu-id="d84aa-166">about_Line_Editing</span></span>](about_Line_Editing.md)
- [<span data-ttu-id="d84aa-167">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="d84aa-167">about_Preference_Variables</span></span>](about_Preference_Variables.md)
- [<span data-ttu-id="d84aa-168">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="d84aa-168">about_Profiles</span></span>](about_Profiles.md)
- [<span data-ttu-id="d84aa-169">about_Variables</span><span class="sxs-lookup"><span data-stu-id="d84aa-169">about_Variables</span></span>](about_Variables.md)
- [<span data-ttu-id="d84aa-170">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d84aa-170">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)
