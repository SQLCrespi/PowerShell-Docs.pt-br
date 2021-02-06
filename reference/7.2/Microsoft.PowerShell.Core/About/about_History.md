---
description: Descreve como obter e executar comandos no histórico de comandos.
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_History
ms.openlocfilehash: 44e03bd37b0b2c5928fb3aa850f3f5b554ccf123
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598844"
---
# <a name="about-history"></a><span data-ttu-id="8e194-103">Sobre o histórico</span><span class="sxs-lookup"><span data-stu-id="8e194-103">About History</span></span>

## <a name="short-description"></a><span data-ttu-id="8e194-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="8e194-104">Short Description</span></span>
<span data-ttu-id="8e194-105">Descreve como obter e executar comandos no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-105">Describes how to get and run commands in the command history.</span></span>

## <a name="long-description"></a><span data-ttu-id="8e194-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="8e194-106">Long Description</span></span>

<span data-ttu-id="8e194-107">Quando você insere um comando no prompt de comando, o PowerShell salva o comando no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-107">When you enter a command at the command prompt, PowerShell saves the command in the command history.</span></span> <span data-ttu-id="8e194-108">Você pode usar os comandos no histórico como um registro do seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="8e194-108">You can use the commands in the history as a record of your work.</span></span> <span data-ttu-id="8e194-109">E, você pode recuperar e executar os comandos no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-109">And, you can recall and run the commands from the command history.</span></span>

<span data-ttu-id="8e194-110">O PowerShell tem dois provedores de histórico diferentes: o histórico interno e o histórico gerenciado pelo módulo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="8e194-110">PowerShell has two different history providers: the built-in history and the history managed by the **PSReadLine** module.</span></span> <span data-ttu-id="8e194-111">Os históricos são gerenciados separadamente, mas ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.</span><span class="sxs-lookup"><span data-stu-id="8e194-111">The histories are managed separately, but both histories are available in sessions where **PSReadLine** is loaded.</span></span>

## <a name="using-the-psreadline-history"></a><span data-ttu-id="8e194-112">Usando o histórico de PSReadLine</span><span class="sxs-lookup"><span data-stu-id="8e194-112">Using the PSReadLine history</span></span>

<span data-ttu-id="8e194-113">O histórico de PSReadLine controla os comandos usados em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e194-113">The PSReadLine history tracks the commands used in all PowerShell sessions.</span></span>
<span data-ttu-id="8e194-114">O histórico é gravado em um arquivo central por host.</span><span class="sxs-lookup"><span data-stu-id="8e194-114">The history is written to a central file per host.</span></span> <span data-ttu-id="8e194-115">Esse arquivo de histórico está disponível para todas as sessões e contém todo o histórico anterior.</span><span class="sxs-lookup"><span data-stu-id="8e194-115">That history file is available to all sessions and contains all past history.</span></span> <span data-ttu-id="8e194-116">O histórico não é excluído quando a sessão termina.</span><span class="sxs-lookup"><span data-stu-id="8e194-116">The history is not deleted when the session ends.</span></span> <span data-ttu-id="8e194-117">Além disso, esse histórico não pode ser gerenciado pelos `*-History` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="8e194-117">Also, that history cannot be managed by the `*-History` cmdlets.</span></span> <span data-ttu-id="8e194-118">Para obter mais informações, consulte [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="8e194-118">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

## <a name="using-the-built-in-session-history"></a><span data-ttu-id="8e194-119">Usando o histórico de sessões internas</span><span class="sxs-lookup"><span data-stu-id="8e194-119">Using the built-in session history</span></span>

<span data-ttu-id="8e194-120">O histórico interno controla apenas os comandos usados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="8e194-120">The built-in history only tracks the commands used in the current session.</span></span> <span data-ttu-id="8e194-121">O histórico não está disponível para outras sessões e é excluído quando a sessão termina.</span><span class="sxs-lookup"><span data-stu-id="8e194-121">The history is not available to other sessions and is deleted when the session ends.</span></span>

### <a name="history-cmdlets"></a><span data-ttu-id="8e194-122">Cmdlets de histórico</span><span class="sxs-lookup"><span data-stu-id="8e194-122">History Cmdlets</span></span>

<span data-ttu-id="8e194-123">O PowerShell tem um conjunto de cmdlets que gerenciam o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-123">PowerShell has a set of cmdlets that manage the command history.</span></span>

| <span data-ttu-id="8e194-124">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8e194-124">Cmdlet</span></span>           | <span data-ttu-id="8e194-125">Alias</span><span class="sxs-lookup"><span data-stu-id="8e194-125">Alias</span></span>  | <span data-ttu-id="8e194-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e194-126">Description</span></span>                                |
| ---------------- | ------ | ------------------------------------------ |
| `Get-History`    | `h`    | <span data-ttu-id="8e194-127">Obtém o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-127">Gets the command history.</span></span>                  |
| `Invoke-History` | `r`    | <span data-ttu-id="8e194-128">Executa um comando no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-128">Runs a command in the command history.</span></span>     |
| `Add-History`    |        | <span data-ttu-id="8e194-129">Adiciona um comando ao histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-129">Adds a command to the command history.</span></span>     |
| `Clear-History`  | `clhy` | <span data-ttu-id="8e194-130">Exclui comandos do histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-130">Deletes commands from the command history.</span></span> |

### <a name="keyboard-shortcuts-for-managing-history"></a><span data-ttu-id="8e194-131">Atalhos de teclado para gerenciamento de histórico</span><span class="sxs-lookup"><span data-stu-id="8e194-131">Keyboard Shortcuts for Managing History</span></span>

<span data-ttu-id="8e194-132">No console do PowerShell, você pode usar os seguintes atalhos para gerenciar o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-132">In the PowerShell console, you can use the following shortcuts to manage the command history.</span></span>

- <span data-ttu-id="8e194-133"><kbd>Upseta</kbd> – exibe o comando anterior.</span><span class="sxs-lookup"><span data-stu-id="8e194-133"><kbd>UpArrow</kbd> - Displays the previous command.</span></span>
- <span data-ttu-id="8e194-134"><kbd>Seta</kbd> -exibe o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="8e194-134"><kbd>DownArrow</kbd> - Displays the next command.</span></span>
- <span data-ttu-id="8e194-135"><kbd>F7</kbd> -exibe o histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-135"><kbd>F7</kbd> - Displays the command history.</span></span>
- <span data-ttu-id="8e194-136"><kbd>ESC</kbd> – para ocultar o histórico.</span><span class="sxs-lookup"><span data-stu-id="8e194-136"><kbd>ESC</kbd> - To hide the history.</span></span>
- <span data-ttu-id="8e194-137"><kbd>F8</kbd> -localiza um comando.</span><span class="sxs-lookup"><span data-stu-id="8e194-137"><kbd>F8</kbd> - Finds a command.</span></span> <span data-ttu-id="8e194-138">Digite um ou mais caracteres e pressione <kbd>F8</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8e194-138">Type one or more characters then press <kbd>F8</kbd>.</span></span> <span data-ttu-id="8e194-139">Pressione <kbd>F8</kbd> novamente na próxima instância.</span><span class="sxs-lookup"><span data-stu-id="8e194-139">Press <kbd>F8</kbd> again the next instance.</span></span>
- <span data-ttu-id="8e194-140"><kbd>F9</kbd> -localizar um comando por ID do histórico.</span><span class="sxs-lookup"><span data-stu-id="8e194-140"><kbd>F9</kbd> - Find a command by history ID.</span></span> <span data-ttu-id="8e194-141">Digite a ID do histórico e pressione <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="8e194-141">Type the history ID then press <kbd>F9</kbd>.</span></span> <span data-ttu-id="8e194-142">Pressione <kbd>F7</kbd> para localizar a ID.</span><span class="sxs-lookup"><span data-stu-id="8e194-142">Press <kbd>F7</kbd> to find the ID.</span></span>
- <span data-ttu-id="8e194-143"><kbd>#</kbd>`<string>`</kbd><kbd>Guia</kbd> – pesquise o histórico para `*<string>*` e retorna a correspondência mais recente.</span><span class="sxs-lookup"><span data-stu-id="8e194-143"><kbd>#</kbd>`<string>`</kbd><kbd>Tab</kbd> - Search the history for `*<string>*` and returns the most recent match.</span></span> <span data-ttu-id="8e194-144">Se você pressionar <kbd>Tab</kbd> repetidamente, ela percorrerá os itens correspondentes em seu histórico.</span><span class="sxs-lookup"><span data-stu-id="8e194-144">If you press <kbd>Tab</kbd> repeatedly, it cycles through the matching items in your history.</span></span>

> [!NOTE]
> <span data-ttu-id="8e194-145">Essas associações de chave são implementadas pelo aplicativo host do console.</span><span class="sxs-lookup"><span data-stu-id="8e194-145">These key bindings are implemented by the console host application.</span></span> <span data-ttu-id="8e194-146">Outros aplicativos, como Visual Studio Code ou terminal do Windows, podem ter diferentes associações de chave.</span><span class="sxs-lookup"><span data-stu-id="8e194-146">Other applications, such as Visual Studio Code or Windows Terminal, can have different key bindings.</span></span> <span data-ttu-id="8e194-147">As associações podem ser substituídas pelo módulo PSReadLine.</span><span class="sxs-lookup"><span data-stu-id="8e194-147">The bindings can be overridden by the PSReadLine module.</span></span> <span data-ttu-id="8e194-148">O PSReadLine é carregado automaticamente quando você inicia uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e194-148">PSReadLine loads automatically when you start a PowerShell session.</span></span>
> <span data-ttu-id="8e194-149">Com PSReadLine carregado, <kbd>F7</kbd> e <kbd>F9</kbd> não são associados a nenhuma função.</span><span class="sxs-lookup"><span data-stu-id="8e194-149">With PSReadLine loaded, <kbd>F7</kbd> and <kbd>F9</kbd> are not bound to any function.</span></span> <span data-ttu-id="8e194-150">PSReadLine não fornece funcionalidade equivalente.</span><span class="sxs-lookup"><span data-stu-id="8e194-150">PSReadLine does not provide equivalent functionality.</span></span> <span data-ttu-id="8e194-151">Para obter mais informações, consulte [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="8e194-151">For more information, see [about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="8e194-152">MaximumHistoryCount</span><span class="sxs-lookup"><span data-stu-id="8e194-152">MaximumHistoryCount</span></span>

<span data-ttu-id="8e194-153">A `$MaximumHistoryCount` variável de preferência determina o número máximo de comandos que o PowerShell salva no histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="8e194-153">The `$MaximumHistoryCount` preference variable determines the maximum number of commands that PowerShell saves in the command history.</span></span> <span data-ttu-id="8e194-154">O valor padrão é</span><span class="sxs-lookup"><span data-stu-id="8e194-154">The default value is</span></span>
4096.

<span data-ttu-id="8e194-155">Por exemplo, o comando a seguir reduz os `$MaximumHistoryCount` comandos para 100:</span><span class="sxs-lookup"><span data-stu-id="8e194-155">For example, the following command lowers the `$MaximumHistoryCount` to 100 commands:</span></span>

```powershell
$MaximumHistoryCount = 100
```

<span data-ttu-id="8e194-156">Para aplicar a configuração, reinicie o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e194-156">To apply the setting, restart PowerShell.</span></span>

<span data-ttu-id="8e194-157">Para salvar o novo valor de variável para todas as sessões do PowerShell, adicione a instrução de atribuição a um perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e194-157">To save the new variable value for all your PowerShell sessions, add the assignment statement to a PowerShell profile.</span></span> <span data-ttu-id="8e194-158">Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8e194-158">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="8e194-159">Para obter mais informações sobre a `$MaximumHistoryCount` variável de preferência, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8e194-159">For more information about the `$MaximumHistoryCount` preference variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="order-of-commands-in-the-history"></a><span data-ttu-id="8e194-160">Ordem dos comandos no histórico</span><span class="sxs-lookup"><span data-stu-id="8e194-160">Order of Commands in the History</span></span>

<span data-ttu-id="8e194-161">Os comandos são adicionados ao histórico quando o comando termina a execução, não quando o comando é inserido.</span><span class="sxs-lookup"><span data-stu-id="8e194-161">Commands are added to the history when the command finishes executing, not when the command is entered.</span></span> <span data-ttu-id="8e194-162">Se os comandos levar algum tempo para serem concluídos ou se os comandos estiverem sendo executados em um prompt aninhado, os comandos poderão parecer estar fora de ordem no histórico.</span><span class="sxs-lookup"><span data-stu-id="8e194-162">If commands take some time to be completed, or if the commands are executing in a nested prompt, the commands might appear to be out of order in the history.</span></span> <span data-ttu-id="8e194-163">Os comandos que estão sendo executados em um prompt aninhado são concluídos somente quando você sai do nível do prompt.</span><span class="sxs-lookup"><span data-stu-id="8e194-163">Commands that are executing in a nested prompt are completed only when you exit the prompt level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e194-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e194-164">See Also</span></span>

- [<span data-ttu-id="8e194-165">about_Line_Editing</span><span class="sxs-lookup"><span data-stu-id="8e194-165">about_Line_Editing</span></span>](about_Line_Editing.md)
- [<span data-ttu-id="8e194-166">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="8e194-166">about_Preference_Variables</span></span>](about_Preference_Variables.md)
- [<span data-ttu-id="8e194-167">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="8e194-167">about_Profiles</span></span>](about_Profiles.md)
- [<span data-ttu-id="8e194-168">about_Variables</span><span class="sxs-lookup"><span data-stu-id="8e194-168">about_Variables</span></span>](about_Variables.md)
- [<span data-ttu-id="8e194-169">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="8e194-169">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)

