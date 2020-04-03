---
title: Uso do Visual Studio Code para desenvolvimento do PowerShell
description: Uso do Visual Studio Code para desenvolvimento do PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 8644aa7c648d649651ca679238e0b79ff35ac579
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500905"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="236e9-103">Uso do Visual Studio Code para desenvolvimento do PowerShell</span><span class="sxs-lookup"><span data-stu-id="236e9-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="236e9-104">O [Visual Studio Code](https://code.visualstudio.com/) é um editor de scripts multiplataforma (Windows, macOS e Linux) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="236e9-104">[Visual Studio Code](https://code.visualstudio.com/) is a cross-platform (Windows, macOS, and Linux) script editor by Microsoft.</span></span> <span data-ttu-id="236e9-105">Junto com a [extensão do PowerShell](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell), ele fornece uma experiência rica e interativa de edição de scripts, facilitando a criação de scripts confiáveis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-105">Together with the [the PowerShell extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell), it provides a rich and interactive script editing experience, making it easier to write reliable PowerShell scripts.</span></span>

<span data-ttu-id="236e9-106">O Visual Studio Code com a extensão do PowerShell é o editor recomendado para escrever scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-106">Visual Studio Code with the PowerShell extension is the recommended editor for writing PowerShell scripts.</span></span>
<span data-ttu-id="236e9-107">Ele dá suporte às seguintes versões do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="236e9-107">It supports the following PowerShell versions:</span></span>

- <span data-ttu-id="236e9-108">PowerShell 7 e posterior</span><span class="sxs-lookup"><span data-stu-id="236e9-108">PowerShell 7 and up</span></span>
- <span data-ttu-id="236e9-109">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="236e9-109">PowerShell Core 6</span></span>
- <span data-ttu-id="236e9-110">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="236e9-110">Windows PowerShell 5.1</span></span>

<span data-ttu-id="236e9-111">Antes de começar, verifique se o PowerShell existe no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="236e9-111">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="236e9-112">Para cargas de trabalho modernas no Windows, macOS e Linux, confira os seguintes links:</span><span class="sxs-lookup"><span data-stu-id="236e9-112">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="236e9-113">[Instalar o PowerShell no Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="236e9-113">[Installing PowerShell on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="236e9-114">[Instalar o PowerShell no macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="236e9-114">[Installing PowerShell on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="236e9-115">[Instalar o PowerShell no Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="236e9-115">[Installing PowerShell on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="236e9-116">Para cargas de trabalho tradicionais do Windows PowerShell, confira [Como instalar o Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="236e9-116">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

> [!NOTE]
> <span data-ttu-id="236e9-117">Visual Studio Code não é o mesmo que [Visual Studio](https://visualstudio.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="236e9-117">Visual Studio Code is not the same as [Visual Studio](https://visualstudio.microsoft.com/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="236e9-118">O [ISE do Windows PowerShell][ise] ainda está disponível para o Windows, no entanto, ele não está mais no desenvolvimento ativo de recursos e não funciona com o PowerShell 7 e posteriores ou com o PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="236e9-118">The [Windows PowerShell ISE][ise] is also still available for Windows, however, it is no longer in active feature development and does not work with PowerShell 7 and up or PowerShell Core 6.</span></span>
> <span data-ttu-id="236e9-119">Como componente de remessa do Windows, ele continua com suporte oficial para correções de segurança e serviços de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="236e9-119">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span> <span data-ttu-id="236e9-120">No momento, não há planos de remover o ISE do Windows.</span><span class="sxs-lookup"><span data-stu-id="236e9-120">We currently have no plans to remove the ISE from Windows.</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="236e9-121">Edição com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="236e9-121">Editing with Visual Studio Code</span></span>

1. <span data-ttu-id="236e9-122">Instale o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="236e9-122">Install Visual Studio Code.</span></span> <span data-ttu-id="236e9-123">Para obter mais informações, confira a visão geral [Configurar o Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span><span class="sxs-lookup"><span data-stu-id="236e9-123">For more information, see the overview [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span></span>

    <span data-ttu-id="236e9-124">Há instruções de instalação para cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="236e9-124">There are installation instructions for each platform:</span></span>

    - <span data-ttu-id="236e9-125">**Windows**: siga as instruções de instalação na página [Executar o Visual Studio Code no Windows](https://code.visualstudio.com/docs/setup/windows).</span><span class="sxs-lookup"><span data-stu-id="236e9-125">**Windows**: follow the installation instructions on the [Running Visual Studio Code on Windows](https://code.visualstudio.com/docs/setup/windows) page.</span></span>
    - <span data-ttu-id="236e9-126">**macOS**: siga as instruções de instalação na página [Executar o Visual Studio Code no macOS](https://code.visualstudio.com/docs/setup/mac).</span><span class="sxs-lookup"><span data-stu-id="236e9-126">**macOS**: follow the installation instructions on the [Running Visual Studio Code on macOS](https://code.visualstudio.com/docs/setup/mac) page.</span></span>
    - <span data-ttu-id="236e9-127">**Linux**: siga as instruções de instalação na página [Executar o Visual Studio Code no Linux](https://code.visualstudio.com/docs/setup/linux).</span><span class="sxs-lookup"><span data-stu-id="236e9-127">**Linux**: follow the installation instructions on the [Running Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux) page.</span></span>

1. <span data-ttu-id="236e9-128">Instale a extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-128">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="236e9-129">Inicie o aplicativo do Visual Studio Code digitando `code` em um console ou `code-insiders` se você instalou o Visual Studio Code Insiders.</span><span class="sxs-lookup"><span data-stu-id="236e9-129">Launch the Visual Studio Code app by typing `code` in a console or `code-insiders` if you installed Visual Studio Code Insiders.</span></span>
   1. <span data-ttu-id="236e9-130">Inicie o **Abertura rápida** no Windows ou no Linux pressionando <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="236e9-130">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="236e9-131">No macOS, pressione <kbd>Cmd</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="236e9-131">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="236e9-132">Em Abertura rápida, digite `ext install powershell` e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="236e9-132">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="236e9-133">A exibição **Extensões** será aberta na barra lateral.</span><span class="sxs-lookup"><span data-stu-id="236e9-133">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="236e9-134">Selecione a extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="236e9-134">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="236e9-135">Você deverá ver uma tela do Visual Studio Code semelhante à seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="236e9-135">You should see a Visual Studio Code screen similar to the following image:</span></span>

      ![Visual Studio Code](media/using-vscode/vscode.png)

   1. <span data-ttu-id="236e9-137">Clique no botão **Instalar** na extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="236e9-137">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="236e9-138">Após a instalação, se o botão **Instalar** mudar para **Recarregar**, clique em **Recarregar**.</span><span class="sxs-lookup"><span data-stu-id="236e9-138">After the install, if you see the **Install** button turn into **Reload**, Click on **Reload**.</span></span>
   1. <span data-ttu-id="236e9-139">Depois que o Visual Studio Code for recarregado, você estará pronto para a edição.</span><span class="sxs-lookup"><span data-stu-id="236e9-139">After Visual Studio Code has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="236e9-140">Por exemplo, para criar um novo arquivo, clique em **Arquivo > Novo**.</span><span class="sxs-lookup"><span data-stu-id="236e9-140">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="236e9-141">Para salvá-lo, clique em **Arquivo > Salvar** e forneça um nome de arquivo, como `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="236e9-141">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="236e9-142">Para fechar o arquivo, clique no `X` ao lado do nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="236e9-142">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="236e9-143">Para sair do Visual Studio Code, **Arquivo > Sair**.</span><span class="sxs-lookup"><span data-stu-id="236e9-143">To exit Visual Studio Code, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="236e9-144">Instalando a extensão do PowerShell em sistemas restritos</span><span class="sxs-lookup"><span data-stu-id="236e9-144">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="236e9-145">Alguns sistemas são configurados de forma a exigir que todas as assinaturas de código sejam verificadas e exigem que os Serviços do Editor do PowerShell sejam aprovados manualmente para serem executados no sistema.</span><span class="sxs-lookup"><span data-stu-id="236e9-145">Some systems are set up in a way that requires all code signatures to be checked and requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="236e9-146">Uma atualização da Política de Grupo que altera a política de execução é uma causa provável caso tenha instalado a extensão do PowerShell, mas está recebendo um erro como:</span><span class="sxs-lookup"><span data-stu-id="236e9-146">A Group Policy update that changes execution policy is a likely cause if you've installed the PowerShell extension but are receiving an error such as:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="236e9-147">Para aprovar manualmente os Serviços do Editor do PowerShell e a extensão do PowerShell para o Visual Studio Code, abra um prompt do PowerShell e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="236e9-147">To manually approve PowerShell Editor Services and the PowerShell extension for Visual Studio Code, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="236e9-148">O sistema mostrará a mensagem **Você deseja executar o software desse editor não confiável?**</span><span class="sxs-lookup"><span data-stu-id="236e9-148">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span>
<span data-ttu-id="236e9-149">Digite `A` para executar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="236e9-149">Type `A` to run the file.</span></span> <span data-ttu-id="236e9-150">Em seguida, abra o Visual Studio Code e verifique se a extensão do PowerShell está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="236e9-150">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="236e9-151">Se você ainda tiver problemas para começar, fale conosco no [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span><span class="sxs-lookup"><span data-stu-id="236e9-151">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

> [!NOTE]
> <span data-ttu-id="236e9-152">A extensão do PowerShell para o Visual Studio Code não dá suporte à execução no modo de linguagem restrita.</span><span class="sxs-lookup"><span data-stu-id="236e9-152">The PowerShell extension for Visual Studio Code does not support running in constrained language mode.</span></span> <span data-ttu-id="236e9-153">Para obter mais informações, confira o [problema do GitHub que acompanha esse suporte](https://github.com/PowerShell/vscode-powershell/issues/606).</span><span class="sxs-lookup"><span data-stu-id="236e9-153">Please see the [GitHub issue tracking that support](https://github.com/PowerShell/vscode-powershell/issues/606) for more information.</span></span>

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a><span data-ttu-id="236e9-154">Usar uma versão mais antiga da extensão do PowerShell para Windows PowerShell v3 e v4</span><span class="sxs-lookup"><span data-stu-id="236e9-154">Using an older version of the PowerShell Extension for Windows PowerShell v3 and v4</span></span>

<span data-ttu-id="236e9-155">Embora a extensão atual do PowerShell [tenha interrompido o suporte ao v3 e v4](https://github.com/PowerShell/vscode-powershell/issues/1310), você ainda pode usar a última versão da extensão que oferecia suporte.</span><span class="sxs-lookup"><span data-stu-id="236e9-155">Although the current PowerShell extension [stopped supporting v3 and v4](https://github.com/PowerShell/vscode-powershell/issues/1310), you can still use the last version of the extension that did.</span></span>

> [!NOTE]
> <span data-ttu-id="236e9-156">Não haverá correções adicionais para essa versão mais antiga da extensão.</span><span class="sxs-lookup"><span data-stu-id="236e9-156">There will be no additional fixes to this older version of the extension.</span></span> <span data-ttu-id="236e9-157">Ela é fornecida "no estado em que se encontra", mas estará disponível para você caso ainda esteja usando o Windows PowerShell v3 e v4.</span><span class="sxs-lookup"><span data-stu-id="236e9-157">It's provided "AS IS" but is available for you if you are still using Windows PowerShell v3 and Windows PowerShell v4.</span></span>

<span data-ttu-id="236e9-158">Primeiro, abra o painel Extensão e pesquise por `PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="236e9-158">First, open the Extension pane and search for `PowerShell`.</span></span> <span data-ttu-id="236e9-159">Em seguida, clique na engrenagem e selecione **Instalar outra versão...** .</span><span class="sxs-lookup"><span data-stu-id="236e9-159">Then click the gear and select **Install another version...**.</span></span>

![Instalar outra versão...](media/using-vscode/install-another-version.png)

<span data-ttu-id="236e9-161">Depois, selecione a versão **`2020.1.0`** .</span><span class="sxs-lookup"><span data-stu-id="236e9-161">Then select the **`2020.1.0`** version.</span></span> <span data-ttu-id="236e9-162">Essa versão da extensão foi a última com suporte ao v3 e v4.</span><span class="sxs-lookup"><span data-stu-id="236e9-162">This version of the extension was the last version to support v3 and v4.</span></span>

<span data-ttu-id="236e9-163">Além disso, adicione a seguinte configuração para que a versão da extensão não seja atualizada automaticamente:</span><span class="sxs-lookup"><span data-stu-id="236e9-163">Also, add the following setting so that your extension version doesn't update automatically:</span></span>

```json
{
    "extensions.autoUpdate": false
}
```

<span data-ttu-id="236e9-164">Isso funcionará no futuro próximo, mas o Visual Studio Code pode implementar uma alteração que interrompa essa versão da extensão.</span><span class="sxs-lookup"><span data-stu-id="236e9-164">Although this will work in the forseeable future, Visual Studio Code could implement a change that breaks this version of the extension.</span></span>
<span data-ttu-id="236e9-165">Devido a isso e à falta de suporte, nós recomendamos:</span><span class="sxs-lookup"><span data-stu-id="236e9-165">Because of this, and lack of support, we highly recommend either:</span></span>

- <span data-ttu-id="236e9-166">Baixar o PowerShell 7 – que é uma instalação lado a lado do Windows PowerShell e funciona melhor com a extensão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="236e9-166">Downloading PowerShell 7 - which is a side-by-side install to Windows PowerShell and works the best with the PowerShell extension</span></span>
- <span data-ttu-id="236e9-167">Atualizar para o Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="236e9-167">Upgrading to Windows PowerShell 5.1</span></span>

<span data-ttu-id="236e9-168">A seção [Editar com o Visual Studio Code](#editing-with-visual-studio-code) neste artigo contém links sobre onde instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="236e9-168">The [Editing with Visual Studio Code](#editing-with-visual-studio-code) section in this article links to where to install these.</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="236e9-169">Escolha de uma versão do PowerShell para ser usada com a extensão</span><span class="sxs-lookup"><span data-stu-id="236e9-169">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="236e9-170">Com o PowerShell Core instalado com o Windows PowerShell, agora é possível usar uma versão específica do PowerShell com a extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-170">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="236e9-171">Siga as etapas a seguir para escolher a versão:</span><span class="sxs-lookup"><span data-stu-id="236e9-171">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="236e9-172">Abra a **Paleta de comandos** no Windows ou Linux com <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="236e9-172">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="236e9-173">No macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="236e9-173">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="236e9-174">Pesquise por **Sessão**.</span><span class="sxs-lookup"><span data-stu-id="236e9-174">Search for **Session**.</span></span>
1. <span data-ttu-id="236e9-175">Clique em **PowerShell: mostrar menu de sessão**.</span><span class="sxs-lookup"><span data-stu-id="236e9-175">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="236e9-176">Na lista, escolha a versão do PowerShell que deseja usar, por exemplo: **PowerShell Core**.</span><span class="sxs-lookup"><span data-stu-id="236e9-176">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="236e9-177">Esse recurso analisa alguns caminhos conhecidos em diferentes sistemas operacionais para descobrir locais de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-177">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="236e9-178">Se você instalou o PowerShell em um local não típico, talvez ele não apareça inicialmente no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="236e9-178">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="236e9-179">Você pode estender o menu de sessão [adicionando seus próprios caminhos personalizados](#adding-your-own-powershell-paths-to-the-session-menu) conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="236e9-179">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="236e9-180">Há outra maneira de acessar o menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="236e9-180">There's another way to get to the session menu.</span></span> <span data-ttu-id="236e9-181">Quando um arquivo do PowerShell é aberto no editor, um número de versão em verde aparece no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="236e9-181">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="236e9-182">Clicar nesse número de versão levará ao menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="236e9-182">Clicking this version number will bring you to the session menu.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="236e9-183">Adição dos seus caminhos do PowerShell ao menu de sessão</span><span class="sxs-lookup"><span data-stu-id="236e9-183">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="236e9-184">É possível adicionar outros caminhos executáveis do PowerShell ao menu de sessão por meio de uma [configuração do Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span><span class="sxs-lookup"><span data-stu-id="236e9-184">You can add other PowerShell executable paths to the session menu through the [Visual Studio Code setting](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span></span>

<span data-ttu-id="236e9-185">Adicione um item à lista `powershell.powerShellAdditionalExePaths` ou crie a lista se ela não estiver em `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="236e9-185">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    // other settings...
}
```

<span data-ttu-id="236e9-186">Cada item precisa ter:</span><span class="sxs-lookup"><span data-stu-id="236e9-186">Each item must have:</span></span>

- <span data-ttu-id="236e9-187">`exePath`: o caminho para o executável `pwsh` ou `powershell`.</span><span class="sxs-lookup"><span data-stu-id="236e9-187">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
- <span data-ttu-id="236e9-188">`versionName`: o texto que aparece no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="236e9-188">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="236e9-189">É possível definir a versão padrão do PowerShell para usar a configuração `powershell.powerShellDefaultVersion` definindo-a como o texto exibido no menu de sessão (também conhecido como `versionName` na última configuração):</span><span class="sxs-lookup"><span data-stu-id="236e9-189">You can set the default PowerShell version to use the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (also known as the `versionName` in the last setting):</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    "powershell.powerShellDefaultVersion": "Downloaded PowerShell",

    // other settings...
}
```

<span data-ttu-id="236e9-190">Depois de definir essa configuração, reinicie o Visual Studio Code ou, para recarregar a janela atual do Visual Studio Code na **Paleta de Comandos**, digite **Developer: Reload Window**.</span><span class="sxs-lookup"><span data-stu-id="236e9-190">After you've configured this setting, restart Visual Studio Code or to reload the current Visual Studio Code window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="236e9-191">Se você abrir o menu de sessão, agora verá versões adicionais do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-191">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="236e9-192">Compilar o PowerShell na origem é uma ótima maneira de testar sua compilação local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-192">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="236e9-193">Definições de configuração para o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="236e9-193">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="236e9-194">Primeiro, se você não estiver familiarizado com a maneira de alterar as configurações no Visual Studio Code, recomendamos ler a [documentação de configurações do Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings).</span><span class="sxs-lookup"><span data-stu-id="236e9-194">First, if you're not familiar with how to change settings in Visual Studio Code, we recommend looking at [Visual Studio Code's settings documentation](https://code.visualstudio.com/docs/getstarted/settings).</span></span>

<span data-ttu-id="236e9-195">Usando as etapas no parágrafo anterior, você pode adicionar configurações no `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="236e9-195">By using the steps in the previous paragraph, you can add configuration settings in `settings.json`.</span></span>

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="236e9-196">Caso você não queira que essas configurações afetem todos os tipos de arquivos, o Visual Studio Code também permite configurações por idioma.</span><span class="sxs-lookup"><span data-stu-id="236e9-196">If you don't want these settings to affect all files types, Visual Studio Code also allows per-language configurations.</span></span> <span data-ttu-id="236e9-197">Crie uma configuração específica a um idioma colocando as configurações em um campo `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="236e9-197">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="236e9-198">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="236e9-198">For example:</span></span>

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> <span data-ttu-id="236e9-199">Para saber mais sobre a codificação de arquivo no Visual Studio Code, confira [Noções básicas sobre codificação de arquivo](understanding-file-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="236e9-199">For more information about file encoding in Visual Studio Code, see [Understanding file encoding](understanding-file-encoding.md).</span></span>
>
> <span data-ttu-id="236e9-200">Confira também [Como replicar a experiência do ISE no Visual Studio Code](How-To-Replicate-the-ISE-Experience-In-VSCode.md) para obter outras dicas sobre como configurar o Visual Studio Code para edição no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-200">Also check out the [How to replicate the ISE experience in Visual Studio Code](How-To-Replicate-the-ISE-Experience-In-VSCode.md) for other tips on how to configure Visual Studio Code for PowerShell editing.</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="236e9-201">Depuração com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="236e9-201">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="236e9-202">Depuração sem espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="236e9-202">No-workspace debugging</span></span>

<span data-ttu-id="236e9-203">A partir da versão 1.9 do Visual Studio Code, é possível depurar scripts do PowerShell sem abrir a pasta que contém o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-203">As of Visual Studio Code version 1.9 you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span> <span data-ttu-id="236e9-204">Abra o arquivo de script do PowerShell usando **Arquivo > Abrir Arquivo…** , defina um ponto de interrupção em uma linha, pressione <kbd>F9</kbd> e <kbd>F5</kbd> para iniciar a depuração.</span><span class="sxs-lookup"><span data-stu-id="236e9-204">Open the PowerShell script file with **File > Open File...**, set a breakpoint on a line, press <kbd>F9</kbd>, and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="236e9-205">Será exibido o painel de ações de depuração, que permite que você interrompa o depurador, execute em etapas, retome e pare a depuração.</span><span class="sxs-lookup"><span data-stu-id="236e9-205">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="236e9-206">Depuração do workspace</span><span class="sxs-lookup"><span data-stu-id="236e9-206">Workspace debugging</span></span>

<span data-ttu-id="236e9-207">A depuração do workspace refere-se a depuração no contexto de uma pasta que você abriu no Visual Studio Code a partir do menu **Arquivo** usando **Abrir Pasta...** . A pasta que você abrir normalmente é a pasta do projeto do PowerShell e/ou a raiz do repositório Git.</span><span class="sxs-lookup"><span data-stu-id="236e9-207">Workspace debugging refers to debugging in the context of a folder that you've opened in Visual Studio Code from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="236e9-208">Mesmo nesse modo, é possível iniciar a depuração de script do PowerShell selecionado no momento pressionando <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="236e9-208">Even in this mode, you can start debugging the currently selected PowerShell script by pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="236e9-209">No entanto, a depuração do workspace permite definir várias configurações de depuração diferentes de depurar apenas o arquivo aberto no momento.</span><span class="sxs-lookup"><span data-stu-id="236e9-209">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="236e9-210">Abordaremos isso em um momento.</span><span class="sxs-lookup"><span data-stu-id="236e9-210">We'll get to those in a moment.</span></span>

<span data-ttu-id="236e9-211">Siga estas etapas para criar o arquivo de configuração de depuração:</span><span class="sxs-lookup"><span data-stu-id="236e9-211">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="236e9-212">Abra a exibição **Depurar** no Windows ou Linux pressionando <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="236e9-212">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="236e9-213">No macOS, pressione <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="236e9-213">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
  1. <span data-ttu-id="236e9-214">Clique no link "criar um arquivo launch.json".</span><span class="sxs-lookup"><span data-stu-id="236e9-214">Click the "create a launch.json file" link.</span></span>
  1. <span data-ttu-id="236e9-215">O Visual Studio Code solicitará que você **Selecione o Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="236e9-215">Visual Studio Code prompts you to **Select Environment**.</span></span> <span data-ttu-id="236e9-216">Escolha **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="236e9-216">Choose **PowerShell**.</span></span>
  1. <span data-ttu-id="236e9-217">Por fim, escolha o tipo de depuração que deseja usar:</span><span class="sxs-lookup"><span data-stu-id="236e9-217">Lastly, choose the type of debugging you'd like to use:</span></span>

- <span data-ttu-id="236e9-218">**Iniciar o Arquivo Atual** – inicie e depure o arquivo na janela do editor atualmente ativa</span><span class="sxs-lookup"><span data-stu-id="236e9-218">**Launch Current File** - Launch and debug the file in the currently active editor window</span></span>
- <span data-ttu-id="236e9-219">**Iniciar Script** – inicie e depure o arquivo ou comando especificado</span><span class="sxs-lookup"><span data-stu-id="236e9-219">**Launch Script** - Launch and debug the specified file or command</span></span>
- <span data-ttu-id="236e9-220">**Sessão Interativa** – depure os comandos executados no Console Integrado</span><span class="sxs-lookup"><span data-stu-id="236e9-220">**Interactive Session** - Debug commands executed from the Integrated Console</span></span>
- <span data-ttu-id="236e9-221">**Anexar** – anexe o depurador a um processo de host do PowerShell em execução</span><span class="sxs-lookup"><span data-stu-id="236e9-221">**Attach** - Attach the debugger to a running PowerShell Host Process</span></span>

<span data-ttu-id="236e9-222">O resultado é que o Visual Studio Code cria um diretório e um arquivo `.vscode\launch.json` na raiz da sua pasta do espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="236e9-222">The result is that Visual Studio Code creates a directory and a file `.vscode\launch.json` in the root of your workspace folder.</span></span> <span data-ttu-id="236e9-223">A configuração de depuração é armazenada nesse local.</span><span class="sxs-lookup"><span data-stu-id="236e9-223">This location is where your debug configuration is stored.</span></span> <span data-ttu-id="236e9-224">Se os arquivos estiverem em um repositório Git, normalmente você desejará confirmar o arquivo `launch.json`.</span><span class="sxs-lookup"><span data-stu-id="236e9-224">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="236e9-225">O conteúdo do arquivo `launch.json` e:</span><span class="sxs-lookup"><span data-stu-id="236e9-225">The contents of the `launch.json` file are:</span></span>

```json
{
  "version": "0.2.0",
  "configurations": [
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Launch (current file)",
          "script": "${file}",
          "args": [],
          "cwd": "${file}"
      },
      {
          "type": "PowerShell",
          "request": "attach",
          "name": "PowerShell Attach to Host Process",
          "processId": "${command.PickPSHostProcess}",
          "runspaceId": 1
      },
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Interactive Session",
          "cwd": "${workspaceRoot}"
      }
  ]
}
```

<span data-ttu-id="236e9-226">Esse arquivo representa os cenários comuns de depuração.</span><span class="sxs-lookup"><span data-stu-id="236e9-226">This file represents the common debug scenarios.</span></span> <span data-ttu-id="236e9-227">Ao abrir este arquivo no editor, você vê um botão **Adicionar configuração...** .</span><span class="sxs-lookup"><span data-stu-id="236e9-227">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="236e9-228">É possível clicar nesse botão para adicionar mais configurações de depuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="236e9-228">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="236e9-229">Uma configuração útil a adicionar é **PowerShell: Iniciar Script**.</span><span class="sxs-lookup"><span data-stu-id="236e9-229">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="236e9-230">Com essa configuração, é possível especificar um arquivo com argumentos opcionais que devem ser iniciados sempre que você pressionar <kbd>F5</kbd>, não importa qual arquivo está ativo no momento no editor.</span><span class="sxs-lookup"><span data-stu-id="236e9-230">With this configuration, you can specify a file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

<span data-ttu-id="236e9-231">Depois que a configuração de depuração for estabelecida, você poderá selecionar qual configuração deseja usar durante uma sessão de depuração.</span><span class="sxs-lookup"><span data-stu-id="236e9-231">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="236e9-232">Selecione uma configuração na lista suspensa de configuração de depuração, na barra de ferramentas da exibição **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="236e9-232">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

## <a name="useful-resources"></a><span data-ttu-id="236e9-233">Recursos úteis</span><span class="sxs-lookup"><span data-stu-id="236e9-233">Useful resources</span></span>

<span data-ttu-id="236e9-234">Há alguns vídeos e postagens no blog que podem ser úteis para você começar a usar a extensão do PowerShell para o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="236e9-234">There are a few videos and blog posts that may be helpful to get you started using the PowerShell extension for Visual Studio Code:</span></span>

### <a name="videos"></a><span data-ttu-id="236e9-235">vídeos</span><span class="sxs-lookup"><span data-stu-id="236e9-235">Videos</span></span>

- [<span data-ttu-id="236e9-236">Usar o Visual Studio Code como seu editor padrão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="236e9-236">Using Visual Studio Code as Your Default PowerShell Editor</span></span>](https://youtu.be/bGn45vIeAMM)
- [<span data-ttu-id="236e9-237">Visual Studio Code: análise aprofundada sobre a depuração de scripts do PowerShell</span><span class="sxs-lookup"><span data-stu-id="236e9-237">Visual Studio Code: deep dive into debugging your PowerShell scripts</span></span>](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a><span data-ttu-id="236e9-238">Postagens no blog</span><span class="sxs-lookup"><span data-stu-id="236e9-238">Blog posts</span></span>

- <span data-ttu-id="236e9-239">[Extensão do PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="236e9-239">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="236e9-240">[Gravar e depurar scripts do PowerShell no Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="236e9-240">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="236e9-241">[Diretrizes sobre depuração no Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="236e9-241">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="236e9-242">[Depuração do PowerShell no Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="236e9-242">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="236e9-243">[Introdução ao desenvolvimento do PowerShell no Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="236e9-243">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="236e9-244">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="236e9-244">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="236e9-245">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="236e9-245">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="236e9-246">[Depuração de script do PowerShell no Visual Studio Code– parte 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="236e9-246">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="236e9-247">[Depuração de script do PowerShell no Visual Studio Code– parte 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="236e9-247">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

## <a name="powershell-extension-for-visual-studio-code"></a><span data-ttu-id="236e9-248">Extensão do PowerShell para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="236e9-248">PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="236e9-249">O código-fonte da extensão do PowerShell pode ser encontrado no [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="236e9-249">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>

<span data-ttu-id="236e9-250">Se você tem interesse em contribuir, a solicitação de pull é uma ótima opção.</span><span class="sxs-lookup"><span data-stu-id="236e9-250">If you're interested in contributing, Pull Request are greatly appreciated.</span></span> <span data-ttu-id="236e9-251">Siga a [documentação de desenvolvedor no GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="236e9-251">Follow along with the [developer documentation on GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md) to get started.</span></span>

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a><span data-ttu-id="236e9-252">Solucionar problemas na extensão do PowerShell para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="236e9-252">Troubleshooting the PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="236e9-253">Se você tiver problemas ao usar o Visual Studio Code para desenvolver scripts do PowerShell, confira o [guia de solução de problemas no GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="236e9-253">If you experience any issues using Visual Studio Code for PowerShell script development, please take a look at the [troubleshooting guide on GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)</span></span>

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../install/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/
