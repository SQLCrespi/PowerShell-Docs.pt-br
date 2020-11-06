---
ms.date: 09/06/2019
keywords: powershell, cmdlet
title: Novidades no ISE do PowerShell 5.0
description: Este artigo explica os recursos novos e atualizados introduzidos na versão 5.0 do ISE (Ambiente de Script Integrado) do Windows PowerShell.
ms.openlocfilehash: 75d37d0dafe381c84898ac48343336cd525d2dd1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660830"
---
# <a name="whats-new-in-the-windows-powershell-50-ise"></a><span data-ttu-id="ca881-104">Novidades no ISE do Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ca881-104">What's New in the Windows PowerShell 5.0 ISE</span></span>

<span data-ttu-id="ca881-105">Este artigo explica os recursos novos e atualizados introduzidos na versão 5.0 do ISE (Ambiente de Script Integrado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-105">This article explains the new and updated features that have been introduced in version 5.0 of the Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

> [!NOTE]
> <span data-ttu-id="ca881-106">O ISE do PowerShell não está mais no desenvolvimento ativo de recursos.</span><span class="sxs-lookup"><span data-stu-id="ca881-106">The PowerShell ISE is no longer in active feature development.</span></span> <span data-ttu-id="ca881-107">Como componente de remessa do Windows, ele continua com suporte oficial para correções de segurança e serviços de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="ca881-107">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="ca881-108">No momento, não há planos de remover o ISE do Windows.</span><span class="sxs-lookup"><span data-stu-id="ca881-108">We currently have no plans to remove the ISE from Windows.</span></span>
>
> <span data-ttu-id="ca881-109">Não há suporte para o ISE no PowerShell v6 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="ca881-109">There is no support for the ISE in PowerShell v6 and beyond.</span></span> <span data-ttu-id="ca881-110">Os usuários que buscam substituir o ISE devem usar o [Visual Studio Code](https://code.visualstudio.com/) com o [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ca881-110">Users looking for replacement for the ISE should use [Visual Studio Code](https://code.visualstudio.com/) with the [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span></span>

## <a name="feature-description"></a><span data-ttu-id="ca881-111">Descrição do recurso</span><span class="sxs-lookup"><span data-stu-id="ca881-111">Feature description</span></span>

<span data-ttu-id="ca881-112">O ISE do Windows PowerShell é um aplicativo host que permite gravar, executar e testar scripts e módulos em um ambiente gráfico e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="ca881-112">The Windows PowerShell ISE is a host application that enables you to write, run, and test scripts and modules in a graphical and intuitive environment.</span></span> <span data-ttu-id="ca881-113">Recursos importantes como coloração de sintaxe, preenchimento de guias, depuração visual, conformidade com Unicode e Ajuda contextual permitem uma experiência avançada de script.</span><span class="sxs-lookup"><span data-stu-id="ca881-113">Key features such as syntax-coloring, tab completion, visual debugging, Unicode compliance, and context-sensitive Help provide a rich scripting experience.</span></span>

<span data-ttu-id="ca881-114">Para obter mais informações, confira [Apresentamos o ISE do Windows PowerShell](../ise/Introducing-the-Windows-PowerShell-ISE.md).</span><span class="sxs-lookup"><span data-stu-id="ca881-114">For more information, see [Introducing the Windows PowerShell ISE](../ise/Introducing-the-Windows-PowerShell-ISE.md).</span></span>

<span data-ttu-id="ca881-115">A tabela a seguir lista os recursos novos e alterados para esta versão do ISE do Windows PowerShell no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-115">The following table lists the new and changed features for this release of Windows PowerShell ISE in Windows PowerShell.</span></span>

## <a name="intellisense"></a><span data-ttu-id="ca881-116">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="ca881-116">IntelliSense</span></span>

> <span data-ttu-id="ca881-117">Adicionado no ISE 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-117">Added in ISE 3.0</span></span>

<span data-ttu-id="ca881-118">O IntelliSense é um recurso de assistência de preenchimento automático que faz parte do ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-118">IntelliSense is an automatic-completion assistance feature that is part of Windows PowerShell ISE.</span></span>
<span data-ttu-id="ca881-119">O IntelliSense exibe menus clicáveis dos cmdlets, parâmetros, valores de parâmetro, arquivos ou pastas potencialmente correspondentes conforme você digita.</span><span class="sxs-lookup"><span data-stu-id="ca881-119">IntelliSense displays clickable menus of potentially matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="ca881-120">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-120">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-121">Com a adição do IntelliSense, é mais fácil descobrir cmdlets e sintaxes ao usar o ISE do Windows PowerShell para criar scripts.</span><span class="sxs-lookup"><span data-stu-id="ca881-121">With the addition of IntelliSense, it's easier to discover cmdlets and syntax when you use Windows PowerShell ISE to create scripts.</span></span> <span data-ttu-id="ca881-122">Você também pode usar o ISE do Windows PowerShell para conhecer o Windows PowerShell enquanto cria novos scripts.</span><span class="sxs-lookup"><span data-stu-id="ca881-122">You can also use Windows PowerShell ISE to learn Windows PowerShell while you create new scripts.</span></span>

<span data-ttu-id="ca881-123">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-123">**What works differently?**</span></span>

<span data-ttu-id="ca881-124">Quando você digita cmdlets no ISE do Windows PowerShell, é exibido um menu de rolagem clicável que permite navegar e selecionar os comandos apropriados.</span><span class="sxs-lookup"><span data-stu-id="ca881-124">When you type cmdlets in the Windows PowerShell ISE, a scrollable and clickable menu displays, allowing you to browse and select the appropriate commands.</span></span>

## <a name="snippets"></a><span data-ttu-id="ca881-125">Snippets</span><span class="sxs-lookup"><span data-stu-id="ca881-125">Snippets</span></span>

> <span data-ttu-id="ca881-126">Adicionado no ISE 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-126">Added in ISE 3.0</span></span>

<span data-ttu-id="ca881-127">*Snippets de código* são sessões de código Windows PowerShell curtas que você pode inserir nos scritps que cria no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-127">*Snippets* are short sections of Windows PowerShell code that you can insert into the scripts you create in Windows PowerShell ISE.</span></span> <span data-ttu-id="ca881-128">O ISE do Windows PowerShell vem com um conjunto padrão de snippets.</span><span class="sxs-lookup"><span data-stu-id="ca881-128">Windows PowerShell ISE comes with a default set of snippets.</span></span> <span data-ttu-id="ca881-129">Você pode adicionar snippets usando o cmdlet `New-Snippet` enquanto trabalha no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-129">You can add snippets by using the `New-Snippet` cmdlet while working in Windows PowerShell ISE.</span></span>

<span data-ttu-id="ca881-130">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-130">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-131">Usando snippets, você pode montar e criar scripts para automatizar seu ambiente rapidamente.</span><span class="sxs-lookup"><span data-stu-id="ca881-131">By using snippets, you can quickly assemble and create scripts to automate your environment.</span></span>

<span data-ttu-id="ca881-132">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-132">**What works differently?**</span></span>

<span data-ttu-id="ca881-133">Para usar snippets no Windows PowerShell 3.0 ou posterior, no menu **Editar** , clique em **Iniciar Snippets** ou pressione <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ca881-133">To use snippets in Windows PowerShell 3.0 or later, on the **Edit** menu, click **Start Snippets** , or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

## <a name="add-on-tools"></a><span data-ttu-id="ca881-134">Ferramentas complementares</span><span class="sxs-lookup"><span data-stu-id="ca881-134">Add-on tools</span></span>

> <span data-ttu-id="ca881-135">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-135">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-136">Agora o ISE do Windows PowerShell dá suporte a ferramentas complementares usando o modelo de objeto.</span><span class="sxs-lookup"><span data-stu-id="ca881-136">Windows PowerShell ISE now supports add-on tools using the object model.</span></span> <span data-ttu-id="ca881-137">Esses complementos são controles do WPF (Windows Presentation Foundation), exibidos como um painel vertical ou horizontal no console.</span><span class="sxs-lookup"><span data-stu-id="ca881-137">These add-ons are Windows Presentation Foundation (WPF) controls that are displayed as a vertical or horizontal pane in the console.</span></span> <span data-ttu-id="ca881-138">Várias ferramentas complementares em um painel são exibidas como um controle com guias.</span><span class="sxs-lookup"><span data-stu-id="ca881-138">Multiple add-on tools in a pane are displayed as a tabbed control.</span></span> <span data-ttu-id="ca881-139">Você também pode adicionar ou remover ferramentas complementares produzidas por terceiros.</span><span class="sxs-lookup"><span data-stu-id="ca881-139">You can also add or remove add-on tools that are produced by non-Microsoft parties.</span></span> <span data-ttu-id="ca881-140">Para obter mais informações, confira [Objetivo do modelo de objeto de script do ISE do Windows PowerShell](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span><span class="sxs-lookup"><span data-stu-id="ca881-140">For more information, see [The Purpose of the Windows PowerShell ISE Scripting Object Model](../ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).</span></span>

<span data-ttu-id="ca881-141">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-141">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-142">Os complementos permitem estender e personalizar o ISE do Windows PowerShell com ferramentas que adicionam funcionalidades e podem melhorar sua experiência com scripts.</span><span class="sxs-lookup"><span data-stu-id="ca881-142">Add-ons allow you to extend and customize Windows PowerShell ISE with tools that add functionality and enhance your scripting experience.</span></span>

<span data-ttu-id="ca881-143">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-143">**What works differently?**</span></span>

<span data-ttu-id="ca881-144">O ISE do Windows PowerShell 3.0 e posterior vêm com o complemento **Comandos**.</span><span class="sxs-lookup"><span data-stu-id="ca881-144">Windows PowerShell ISE 3.0 and later come with the **Commands** add-on.</span></span> <span data-ttu-id="ca881-145">O complemento **Comandos** permite que você procure cmdlets e acesse a Ajuda para os cmdlets lado a lado com os Painéis de **Script** e **Console**.</span><span class="sxs-lookup"><span data-stu-id="ca881-145">The **Commands** add-on allows you to browse cmdlets, and access help about the cmdlets side-by-side with the **Script** and **Console** Panes.</span></span>

<span data-ttu-id="ca881-146">Complementos adicionais podem ser encontrados usando o comando **Abrir o Site de Ferramentas Complementares** no menu **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="ca881-146">Additional add-ons can be found by using the **Open Add-on Tools Website** command on the **Add-ons** menu.</span></span>

## <a name="restart-manager-and-auto-save"></a><span data-ttu-id="ca881-147">Gerenciador de Reinicialização e Salvamento Automático</span><span class="sxs-lookup"><span data-stu-id="ca881-147">Restart manager and auto-save</span></span>

> <span data-ttu-id="ca881-148">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-148">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-149">O ISE do Windows PowerShell agora salva automaticamente os scripts abertos a cada dois minutos em uma localização separada.</span><span class="sxs-lookup"><span data-stu-id="ca881-149">Windows PowerShell ISE now automatically saves your open scripts every two minutes, in a separate location.</span></span> <span data-ttu-id="ca881-150">Quando o ISE do Windows PowerShell é reiniciado após uma falha inesperada ou uma reinicialização, ele recupera os scripts que estavam abertos na última sessão, mesmo que os scripts não tenham sido salvos.</span><span class="sxs-lookup"><span data-stu-id="ca881-150">When Windows PowerShell ISE restarts after an unexpected crash or reboot, it recovers scripts that were open in the last session, even if the scripts weren't saved.</span></span>

<span data-ttu-id="ca881-151">Para alterar o intervalo de salvamento automático, execute o seguinte comando no painel de console: `$psise.Options.AutoSaveMinuteInterval`.</span><span class="sxs-lookup"><span data-stu-id="ca881-151">To change the automatic saving interval, run the following command in the Console pane: `$psise.Options.AutoSaveMinuteInterval`.</span></span>

<span data-ttu-id="ca881-152">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-152">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-153">Agora você pode trabalhar no ISE do Windows PowerShell sabendo que os scripts abertos são salvos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ca881-153">You can now work within Windows PowerShell ISE knowing that your open scripts are automatically saved.</span></span>

<span data-ttu-id="ca881-154">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-154">**What works differently?**</span></span>

<span data-ttu-id="ca881-155">O ISE do Windows PowerShell 2.0 não salva automaticamente os scripts.</span><span class="sxs-lookup"><span data-stu-id="ca881-155">Windows PowerShell ISE 2.0 doesn't save the scripts automatically.</span></span>

## <a name="most-recently-used-list"></a><span data-ttu-id="ca881-156">Lista de recém-usados</span><span class="sxs-lookup"><span data-stu-id="ca881-156">Most-recently used list</span></span>

> <span data-ttu-id="ca881-157">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-157">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-158">O ISE do Windows PowerShell agora tem uma lista de arquivos recém-usados.</span><span class="sxs-lookup"><span data-stu-id="ca881-158">Windows PowerShell ISE now has a most-recently used list for files.</span></span> <span data-ttu-id="ca881-159">Quando você abre um arquivo no ISE do Windows PowerShell, ele é adicionado à lista de recém-usados no menu **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="ca881-159">When you open a file in Windows PowerShell ISE, the file is added to the most-recently used list on the **File** menu.</span></span>

<span data-ttu-id="ca881-160">Para alterar o número padrão de arquivos na lista de recém-usados, execute o seguinte comando no Painel de Console: `$psise.Options.MruCount`.</span><span class="sxs-lookup"><span data-stu-id="ca881-160">To change the default number of files in the most-recently used list, run the following command in the Console Pane: `$psise.Options.MruCount`.</span></span>

<span data-ttu-id="ca881-161">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-161">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-162">Agora você pode usar a lista de recém-usados para acessar facilmente os arquivos mais usados.</span><span class="sxs-lookup"><span data-stu-id="ca881-162">You can now use the most-recently used list to easily access your frequently used files.</span></span>

<span data-ttu-id="ca881-163">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-163">**What works differently?**</span></span>

<span data-ttu-id="ca881-164">O ISE do Windows PowerShell 2.0 não tem uma lista arquivos usados recentemente.</span><span class="sxs-lookup"><span data-stu-id="ca881-164">Windows PowerShell ISE 2.0 doesn't have a most-recently used list.</span></span>

## <a name="console-pane"></a><span data-ttu-id="ca881-165">Painel de Console</span><span class="sxs-lookup"><span data-stu-id="ca881-165">Console Pane</span></span>

> <span data-ttu-id="ca881-166">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-166">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-167">Os Painéis de Comando e Saída separados que estavam disponíveis na primeira versão do ISE do Windows PowerShell foram combinados em um Painel de Console único.</span><span class="sxs-lookup"><span data-stu-id="ca881-167">The separate Command and Output Panes that were available in the first release of Windows PowerShell ISE have been combined into a single Console Pane.</span></span> <span data-ttu-id="ca881-168">O Painel do Console é semelhante, em termos de função e aparência, a um console típico do Windows PowerShell, mas inclui os aprimoramentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="ca881-168">The Console Pane is similar in function and appearance to a typical Windows PowerShell console, but it includes the following enhancements:</span></span>

- <span data-ttu-id="ca881-169">Cores de sintaxe para texto de entrada (não para texto de saída), incluindo sintaxe XML</span><span class="sxs-lookup"><span data-stu-id="ca881-169">Syntax coloring for input text (not output text), including XML syntax</span></span>
- <span data-ttu-id="ca881-170">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="ca881-170">IntelliSense</span></span>
- <span data-ttu-id="ca881-171">Correspondência de chaves</span><span class="sxs-lookup"><span data-stu-id="ca881-171">Brace matching</span></span>
- <span data-ttu-id="ca881-172">Indicação de erros</span><span class="sxs-lookup"><span data-stu-id="ca881-172">Error indication</span></span>
- <span data-ttu-id="ca881-173">Suporte total a Unicode</span><span class="sxs-lookup"><span data-stu-id="ca881-173">Full Unicode support</span></span>
- <span data-ttu-id="ca881-174">Ajuda contextual com <kbd>F1</kbd></span><span class="sxs-lookup"><span data-stu-id="ca881-174"><kbd>F1</kbd> context-sensitive help</span></span>
- <span data-ttu-id="ca881-175">Show-Command contextual com <kbd>Ctrl</kbd>+<kbd>F1</kbd></span><span class="sxs-lookup"><span data-stu-id="ca881-175"><kbd>Ctrl</kbd>+<kbd>F1</kbd> context-sensitive Show-Command</span></span>
- <span data-ttu-id="ca881-176">Suporte a scripts complexos e leitura da direita para a esquerda</span><span class="sxs-lookup"><span data-stu-id="ca881-176">Complex script and right-to-left support</span></span>
- <span data-ttu-id="ca881-177">Suporte a fontes</span><span class="sxs-lookup"><span data-stu-id="ca881-177">Font support</span></span>
- <span data-ttu-id="ca881-178">Zoom</span><span class="sxs-lookup"><span data-stu-id="ca881-178">Zoom</span></span>
- <span data-ttu-id="ca881-179">Modos de seleção de linha e seleção de blocos</span><span class="sxs-lookup"><span data-stu-id="ca881-179">Line-select and block-select modes</span></span>
- <span data-ttu-id="ca881-180">Preservação do conteúdo digitado na linha de comando quando você pressiona a <kbd>Seta para cima</kbd> para exibir o histórico no console</span><span class="sxs-lookup"><span data-stu-id="ca881-180">Preservation of typed content at the command line when you press the <kbd>UpArrow</kbd> to view history in the console</span></span>

<span data-ttu-id="ca881-181">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-181">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-182">A adição dessas alterações do Painel de Console fornece uma experiência de script que é mais consistente com a interface do console.</span><span class="sxs-lookup"><span data-stu-id="ca881-182">The addition of these Console Pane changes provides a scripting experience that is more consistent with the console interface.</span></span>

<span data-ttu-id="ca881-183">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-183">**What works differently?**</span></span>

<span data-ttu-id="ca881-184">O ISE do Windows PowerShell 2.0 tem Painéis de Comando e de Saída separados.</span><span class="sxs-lookup"><span data-stu-id="ca881-184">Windows PowerShell ISE 2.0 has separate Command and Output Panes.</span></span>

## <a name="command-line-switches"></a><span data-ttu-id="ca881-185">Opções de linha de comando</span><span class="sxs-lookup"><span data-stu-id="ca881-185">Command-line switches</span></span>

> <span data-ttu-id="ca881-186">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-186">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-187">Se você iniciar o ISE do Windows PowerShell com a linha de comando (digitando **powershell_ise.exe** ), será possível adicionar as novas opções de linha de comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="ca881-187">If you start Windows PowerShell ISE from the command line (by typing **powershell_ise.exe** ), you can add the following new command-line switches.</span></span>

- <span data-ttu-id="ca881-188">`-NoProfile`: inicia o ISE do Windows PowerShell sem executar `$profile`</span><span class="sxs-lookup"><span data-stu-id="ca881-188">`-NoProfile`: Starts Windows PowerShell ISE without running `$profile`</span></span>
- <span data-ttu-id="ca881-189">`-Help`: exibe uma janela Ajuda</span><span class="sxs-lookup"><span data-stu-id="ca881-189">`-Help`: Displays a Help window</span></span>
- <span data-ttu-id="ca881-190">`-mta`: inicia o ISE do Windows PowerShell no modo Multi-Threaded Apartment.</span><span class="sxs-lookup"><span data-stu-id="ca881-190">`-mta`: Starts Windows PowerShell ISE in multithreaded apartment mode.</span></span> <span data-ttu-id="ca881-191">O modo de operação padrão do ISE do Windows PowerShell é o modo Single-Threaded Apartment ou `-sta`.</span><span class="sxs-lookup"><span data-stu-id="ca881-191">The default operation mode for Windows PowerShell ISE is single-threaded apartment mode, or `-sta`.</span></span>

<span data-ttu-id="ca881-192">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-192">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-193">A adição dessas opções de linha de comando permite controlar o ambiente no qual o ISE do Windows PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="ca881-193">The addition of these command-line switches allows you to control the environment in which the Windows PowerShell ISE runs.</span></span>

<span data-ttu-id="ca881-194">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-194">**What works differently?**</span></span>

<span data-ttu-id="ca881-195">O ISE do Windows PowerShell 2.0 não reconhece essas opções de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="ca881-195">Windows PowerShell ISE 2.0 doesn't recognize these command-line switches.</span></span>

## <a name="new-editor-features"></a><span data-ttu-id="ca881-196">Novos recursos do editor</span><span class="sxs-lookup"><span data-stu-id="ca881-196">New editor features</span></span>

> <span data-ttu-id="ca881-197">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-197">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-198">Outros recursos de edição do ISE do Windows PowerShell incluem:</span><span class="sxs-lookup"><span data-stu-id="ca881-198">Other Windows PowerShell ISE editing features include:</span></span>

- <span data-ttu-id="ca881-199">**Cores de sintaxe de XML** – Agora o ISE do Windows PowerShell tem sintaxe XML colorida da mesma maneira que a sintaxe colorida do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-199">**XML syntax coloring** - Windows PowerShell ISE now colors XML syntax in the same way as it colors Windows PowerShell syntax.</span></span>
- <span data-ttu-id="ca881-200">**Correspondência de chaves** – O ISE do Windows PowerShell inclui o realce e a correspondência de chaves e pode ser usado das seguintes maneiras: (por exemplo, o uso do comando **Ir para Correspondência** ou <kbd>Ctrl</kbd>+<kbd>]</kbd> localizará a chave de fechamento, se você tiver selecionado uma chave de abertura).</span><span class="sxs-lookup"><span data-stu-id="ca881-200">**Brace matching** - Windows PowerShell ISE includes brace matching and highlighting, and can be used in the following ways: (for example, using the **Go to Match** command or <kbd>Ctrl</kbd>+<kbd>]</kbd> locates the closing brace, if you have an opening brace selected).</span></span>
- <span data-ttu-id="ca881-201">**Exibição de estrutura de tópicos** O Painel de Script dá suporte à exibição das estruturas de tópicos, que permitem recolher ou expandir seções de códigos com cliques nos sinais de adição ou subtração na margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="ca881-201">**Outline view** The Script Pane supports outlining, which allows collapsing or expanding sections of code by clicking plus or minus signs in the left margin.</span></span> <span data-ttu-id="ca881-202">Você pode usar chaves ou as marcas `#region` e `#endregion` para marcar o início ou o final de uma seção recolhível.</span><span class="sxs-lookup"><span data-stu-id="ca881-202">You can use braces or the `#region` and `#endregion` tags to mark the beginning or end of a collapsible section.</span></span> <span data-ttu-id="ca881-203">Para expandir ou recolher todas as regiões, pressione <kbd>Ctrl</kbd>+<kbd>M</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ca881-203">To expand or collapse all regions, press <kbd>Ctrl</kbd>+<kbd>M</kbd>.</span></span>
- <span data-ttu-id="ca881-204">**Edição de texto com arrastar e soltar** – O ISE do Windows PowerShell agora dá suporte à edição de texto ao arrastar e soltar.</span><span class="sxs-lookup"><span data-stu-id="ca881-204">**Drag and drop text editing** - Windows PowerShell ISE now supports drag and drop text editing.</span></span> <span data-ttu-id="ca881-205">Você pode selecionar qualquer bloco de texto e arrastar o texto para outro local no editor ou no console para mover o texto.</span><span class="sxs-lookup"><span data-stu-id="ca881-205">You can select any block of text and drag that text to another location in the editor or the console to move the text.</span></span> <span data-ttu-id="ca881-206">Se você mantiver a tecla <kbd>Ctrl</kbd> pressionada enquanto arrasta o texto selecionado, quando soltar o botão do mouse, o texto será copiado para o novo local.</span><span class="sxs-lookup"><span data-stu-id="ca881-206">If you hold down the <kbd>Ctrl</kbd> key while you drag the selected text, when you release the mouse button the text is copied to the new location.</span></span> <span data-ttu-id="ca881-207">Nesta versão do ISE do Windows PowerShell, quando você arrasta e solta arquivos no ISE do Windows PowerShell, ele abre o arquivo.</span><span class="sxs-lookup"><span data-stu-id="ca881-207">In this version of Windows PowerShell ISE, when you drag and drop files onto Windows PowerShell ISE, Windows PowerShell ISE opens the file.</span></span>
- <span data-ttu-id="ca881-208">**Analisar a exibição de erro** – Erros de análise são indicados com um sublinhado vermelho.</span><span class="sxs-lookup"><span data-stu-id="ca881-208">**Parse error display** - Parse errors are indicated with red underlines.</span></span> <span data-ttu-id="ca881-209">Quando você passa o cursor sobre um erro indicado, o texto da dica de ferramenta exibe o problema encontrado no código.</span><span class="sxs-lookup"><span data-stu-id="ca881-209">When you hover over an indicated error, tooltip text displays the problem that was found in the code.</span></span>
- <span data-ttu-id="ca881-210">**Zoom** – É possível definir o percentual de zoom do conteúdo do console usando o Controle Deslizante de Zoom (no canto inferior direito da janela do ISE do Windows PowerShell) ou digitando o comando `$psise.options.Zoom` no Painel de Console.</span><span class="sxs-lookup"><span data-stu-id="ca881-210">**Zoom** - The zoom percentage of the console's content can be set by using the zoom slider (in the lower right corner of Windows PowerShell ISE window), or by entering the command `$psise.options.Zoom` in the Console Pane.</span></span>
- <span data-ttu-id="ca881-211">**Copiar e colar rich text** – A cópia para a área de transferência no ISE do Windows PowerShell preserva as informações de fonte, tamanho e cor da seleção original.</span><span class="sxs-lookup"><span data-stu-id="ca881-211">**Rich text copy and paste** - Copying to the clipboard in Windows PowerShell ISE preserves the font, size, and color information of the original selection.</span></span>
- <span data-ttu-id="ca881-212">**Seleção de bloco** – Você pode selecionar um bloco de texto mantendo a tecla <kbd>ALT</kbd> pressionada enquanto seleciona o texto no Painel de Script com o mouse ou pressionando <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Seta</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ca881-212">**Block selection** - You can select a block of text by holding down the <kbd>ALT</kbd> key while selecting text in the Script Pane with your mouse, or by pressing <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Arrow</kbd>.</span></span>

<span data-ttu-id="ca881-213">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-213">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-214">Os recursos de edição adicionais fornecem um ambiente de edição mais consistente e eficiente.</span><span class="sxs-lookup"><span data-stu-id="ca881-214">The additional editing features provide a more consistent and powerful editing environment.</span></span>

<span data-ttu-id="ca881-215">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-215">**What works differently?**</span></span>

<span data-ttu-id="ca881-216">Esses aprimoramentos na edição não estavam presentes no ISE do Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca881-216">These editing enhancements weren't present in Windows PowerShell ISE 2.0.</span></span>

## <a name="new-help-viewer-window"></a><span data-ttu-id="ca881-217">Janela do novo visualizador da ajuda</span><span class="sxs-lookup"><span data-stu-id="ca881-217">New Help viewer window</span></span>

> <span data-ttu-id="ca881-218">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-218">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-219">Se você pressionar <kbd>F1</kbd> quando o cursor estiver em um cmdlet ou se parte de um cmdlet estiver realçada, o novo visualizador da Ajuda abrirá uma ajuda contextual sobre o cmdlet realçado.</span><span class="sxs-lookup"><span data-stu-id="ca881-219">If you press <kbd>F1</kbd> when your cursor is in a cmdlet, or you have part of a cmdlet highlighted, the new Help viewer opens context-sensitive Help about the highlighted cmdlet.</span></span> <span data-ttu-id="ca881-220">Para exibir a ajuda **Sobre** do Windows PowerShell, digite `operators` no painel de console e pressione <kbd>F1</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ca881-220">To display Windows PowerShell **About** help, type `operators` in the console pane, and then press <kbd>F1</kbd>.</span></span>

<span data-ttu-id="ca881-221">Antes de usar este recurso, baixe a versão mais atual dos tópicos de ajuda do Windows PowerShell do site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca881-221">Before you use this feature, download the most current version of Windows PowerShell Help topics from the Microsoft website.</span></span> <span data-ttu-id="ca881-222">O método mais simples para baixar os tópicos da Ajuda é executar o cmdlet `Update-Help` no painel de console durante a execução do ISE do Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="ca881-222">The simplest method for downloading the Help topics is to run the `Update-Help` cmdlet in the Console Pane when running Windows PowerShell ISE as administrator.</span></span>

<span data-ttu-id="ca881-223">Você pode alterar onde a tecla <kbd>F1</kbd> busca Ajuda.</span><span class="sxs-lookup"><span data-stu-id="ca881-223">You can alter where the <kbd>F1</kbd> key looks for Help.</span></span> <span data-ttu-id="ca881-224">No menu **Ferramentas**/**Opções** , na guia **Configurações Gerais** em **Outras Configurações** , você pode marcar ou desmarcar a caixa de seleção **Usar conteúdo da ajuda local em vez de conteúdo online**.</span><span class="sxs-lookup"><span data-stu-id="ca881-224">In the **Tools**/**Options** menu, on the **General Settings** tab, under **Other Settings** , you can set or clear the checkbox **Use local help content instead of online content**.</span></span> <span data-ttu-id="ca881-225">Quando marcada, o cliente procurará o cmdlet Help na Ajuda baixada que se encontra na pasta de módulos.</span><span class="sxs-lookup"><span data-stu-id="ca881-225">When checked, the client looks for the cmdlet Help in the downloaded Help found in the modules folder.</span></span> <span data-ttu-id="ca881-226">Se a caixa de seleção for desmarcada, o cliente procurará na ajuda online.</span><span class="sxs-lookup"><span data-stu-id="ca881-226">If the checkbox is cleared, the client looks for help online.</span></span>

<span data-ttu-id="ca881-227">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-227">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-228">A ajuda contextual sem deixar seu cmdlet ou script atual fornece uma experiência integrada de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="ca881-228">Context-sensitive Help without leaving your current cmdlet or script provides an integrated learning experience.</span></span>

<span data-ttu-id="ca881-229">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-229">**What works differently?**</span></span>

<span data-ttu-id="ca881-230">Pressionar <kbd>F1</kbd> em versões anteriores do ISE do Windows PowerShell abria o arquivo de ajuda no computador local.</span><span class="sxs-lookup"><span data-stu-id="ca881-230">Pressing <kbd>F1</kbd> in previous versions of Windows PowerShell ISE opened the help file on the local computer.</span></span> <span data-ttu-id="ca881-231">No ISE do Windows PowerShell 3.0 e posterior, é aberta uma janela que contém a ajuda para o cmdlet que é configurável e pesquisável.</span><span class="sxs-lookup"><span data-stu-id="ca881-231">In Windows PowerShell ISE 3.0 and later, a window opens that contains the help for the cmdlet that is searchable and configurable.</span></span> <span data-ttu-id="ca881-232">Essa experiência da ajuda é uma novidade no ISE do Windows PowerShell 3.0 e a Ajuda Atualizável é uma novidade no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ca881-232">This Help experience is new for Windows PowerShell ISE 3.0, and Updatable Help is new for Windows PowerShell 3.0.</span></span>

## <a name="show-command-cmdlet"></a><span data-ttu-id="ca881-233">Cmdlet Show-Command</span><span class="sxs-lookup"><span data-stu-id="ca881-233">Show-Command cmdlet</span></span>

> <span data-ttu-id="ca881-234">Adicionado no PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ca881-234">Added in PowerShell 3.0</span></span>

<span data-ttu-id="ca881-235">O cmdlet `Show-Command` permite compor ou executar um cmdlet ou uma função com o preenchimento de um formulário gráfico.</span><span class="sxs-lookup"><span data-stu-id="ca881-235">The `Show-Command` cmdlet enables you to compose or run a cmdlet or function by filling in a graphical form.</span></span> <span data-ttu-id="ca881-236">O formulário permite que os usuários trabalhem com o Windows PowerShell em um ambiente gráfico.</span><span class="sxs-lookup"><span data-stu-id="ca881-236">The form lets users work with Windows PowerShell in a graphical environment.</span></span>
<span data-ttu-id="ca881-237">`Show-Command` também permite que os desenvolvedores de scripts avançados criem rapidamente uma GUI baseada no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-237">`Show-Command` also enables advanced scripters to create a quick Windows PowerShell-based GUI.</span></span>

<span data-ttu-id="ca881-238">**Qual é o valor agregado desta alteração?**</span><span class="sxs-lookup"><span data-stu-id="ca881-238">**What value does this change add?**</span></span>

<span data-ttu-id="ca881-239">Usando `Show-Command` em seus scripts do Windows PowerShell, é possível fornecer aos usuários o ambiente gráfico com o qual eles estão familiarizados.</span><span class="sxs-lookup"><span data-stu-id="ca881-239">By using `Show-Command` in your Windows PowerShell scripts, you can provide your users with the graphical environment with which they're familiar.</span></span> <span data-ttu-id="ca881-240">`Show-Command` também pode ajudar os usuários iniciantes a aprender o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca881-240">`Show-Command` can also help introductory users learn Windows PowerShell.</span></span>

<span data-ttu-id="ca881-241">**O que passou a funcionar de maneira diferente?**</span><span class="sxs-lookup"><span data-stu-id="ca881-241">**What works differently?**</span></span>

<span data-ttu-id="ca881-242">`Show-Command` é o novo ISE do Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ca881-242">`Show-Command` is new Windows PowerShell ISE 3.0.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca881-243">Veja também</span><span class="sxs-lookup"><span data-stu-id="ca881-243">See also</span></span>

<span data-ttu-id="ca881-244">Para obter mais informações sobre como usar o ISE do Windows PowerShell, confira [Explorar o Ambiente de Script Integrado do Windows PowerShell](../ise/exploring-the-windows-powershell-ise.md).</span><span class="sxs-lookup"><span data-stu-id="ca881-244">For more information about using Windows PowerShell ISE, see [Exploring the Windows PowerShell Integrated Scripting Environment](../ise/exploring-the-windows-powershell-ise.md).</span></span>
