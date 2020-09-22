---
title: Uso do Visual Studio Code para desenvolvimento do PowerShell
description: Uso do Visual Studio Code para desenvolvimento do PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 181746e7d3df2880223d1f15a0c8b99b324f5b98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782524"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="844dc-103">Uso do Visual Studio Code para desenvolvimento do PowerShell</span><span class="sxs-lookup"><span data-stu-id="844dc-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="844dc-104">O [Visual Studio Code][vscode] é um editor de scripts multiplataforma da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="844dc-104">[Visual Studio Code][vscode] is a cross-platform script editor by Microsoft.</span></span> <span data-ttu-id="844dc-105">Junto com a [extensão do PowerShell][psext], ele fornece uma experiência rica e interativa de edição de scripts, facilitando a criação de scripts confiáveis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-105">Together with the [PowerShell extension][psext], it provides a rich and interactive script editing experience, making it easier to write reliable PowerShell scripts.</span></span> <span data-ttu-id="844dc-106">O Visual Studio Code com a extensão do PowerShell é o editor recomendado para escrever scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-106">Visual Studio Code with the PowerShell extension is the recommended editor for writing PowerShell scripts.</span></span>

<span data-ttu-id="844dc-107">Ele dá suporte às seguintes versões do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="844dc-107">It supports the following PowerShell versions:</span></span>

- <span data-ttu-id="844dc-108">PowerShell 7 e posterior (Windows, macOS e Linux)</span><span class="sxs-lookup"><span data-stu-id="844dc-108">PowerShell 7 and up (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="844dc-109">PowerShell Core 6 (Windows, macOS e Linux)</span><span class="sxs-lookup"><span data-stu-id="844dc-109">PowerShell Core 6 (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="844dc-110">Windows PowerShell 5.1 (apenas Windows)</span><span class="sxs-lookup"><span data-stu-id="844dc-110">Windows PowerShell 5.1 (Windows-only)</span></span>

> [!NOTE]
> <span data-ttu-id="844dc-111">Visual Studio Code não é o mesmo que [Visual Studio][].</span><span class="sxs-lookup"><span data-stu-id="844dc-111">Visual Studio Code is not the same as [Visual Studio][].</span></span>

## <a name="getting-started"></a><span data-ttu-id="844dc-112">Introdução</span><span class="sxs-lookup"><span data-stu-id="844dc-112">Getting started</span></span>

<span data-ttu-id="844dc-113">Antes de começar, verifique se o PowerShell existe no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="844dc-113">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="844dc-114">Para cargas de trabalho modernas no Windows, macOS e Linux, confira os seguintes links:</span><span class="sxs-lookup"><span data-stu-id="844dc-114">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="844dc-115">[Instalar o PowerShell no Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="844dc-115">[Installing PowerShell on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="844dc-116">[Instalar o PowerShell no macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="844dc-116">[Installing PowerShell on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="844dc-117">[Instalar o PowerShell no Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="844dc-117">[Installing PowerShell on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="844dc-118">Para cargas de trabalho tradicionais do Windows PowerShell, confira [Como instalar o Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="844dc-118">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="844dc-119">O [ISE do Windows PowerShell][ise] ainda está disponível para o Windows.</span><span class="sxs-lookup"><span data-stu-id="844dc-119">The [Windows PowerShell ISE][ise] is still available for Windows.</span></span> <span data-ttu-id="844dc-120">No entanto, não está mais no desenvolvimento ativo de recursos.</span><span class="sxs-lookup"><span data-stu-id="844dc-120">However, it is no longer in active feature development.</span></span> <span data-ttu-id="844dc-121">O ISE não funciona com o PowerShell 6 e posterior.</span><span class="sxs-lookup"><span data-stu-id="844dc-121">The ISE does not work with PowerShell 6 and higher.</span></span> <span data-ttu-id="844dc-122">Como componente do Windows, ele continua com suporte oficial para correções de segurança e serviços de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="844dc-122">As a component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="844dc-123">Não há planos de remover o ISE do Windows.</span><span class="sxs-lookup"><span data-stu-id="844dc-123">We have no plans to remove the ISE from Windows.</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="844dc-124">Edição com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="844dc-124">Editing with Visual Studio Code</span></span>

1. <span data-ttu-id="844dc-125">Instale o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="844dc-125">Install Visual Studio Code.</span></span> <span data-ttu-id="844dc-126">Para obter mais informações, confira a visão geral [Configurar o Visual Studio Code][vsc-setup].</span><span class="sxs-lookup"><span data-stu-id="844dc-126">For more information, see the overview [Setting up Visual Studio Code][vsc-setup].</span></span>

   <span data-ttu-id="844dc-127">Há instruções de instalação para cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="844dc-127">There are installation instructions for each platform:</span></span>

   - <span data-ttu-id="844dc-128">**Windows**: siga as instruções de instalação na página [Executar o Visual Studio Code no Windows][vsc-setup-win].</span><span class="sxs-lookup"><span data-stu-id="844dc-128">**Windows**: follow the installation instructions on the [Running Visual Studio Code on Windows][vsc-setup-win] page.</span></span>
   - <span data-ttu-id="844dc-129">**macOS**: siga as instruções de instalação na página [Executar o Visual Studio Code no macOS][vsc-setup-macOS].</span><span class="sxs-lookup"><span data-stu-id="844dc-129">**macOS**: follow the installation instructions on the [Running Visual Studio Code on macOS][vsc-setup-macOS] page.</span></span>
   - <span data-ttu-id="844dc-130">**Linux**: siga as instruções de instalação na página [Executar o Visual Studio Code no Linux][vsc-setup-linux].</span><span class="sxs-lookup"><span data-stu-id="844dc-130">**Linux**: follow the installation instructions on the [Running Visual Studio Code on Linux][vsc-setup-linux] page.</span></span>

1. <span data-ttu-id="844dc-131">Instale a extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-131">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="844dc-132">Inicie o aplicativo do Visual Studio Code digitando `code` em um console ou `code-insiders` se você instalou o Visual Studio Code Insiders.</span><span class="sxs-lookup"><span data-stu-id="844dc-132">Launch the Visual Studio Code app by typing `code` in a console or `code-insiders` if you installed Visual Studio Code Insiders.</span></span>
   1. <span data-ttu-id="844dc-133">Inicie o **Abertura rápida** no Windows ou no Linux pressionando <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="844dc-133">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="844dc-134">No macOS, pressione <kbd>Cmd</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="844dc-134">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="844dc-135">Em Abertura rápida, digite `ext install powershell` e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="844dc-135">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="844dc-136">A exibição **Extensões** será aberta na barra lateral.</span><span class="sxs-lookup"><span data-stu-id="844dc-136">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="844dc-137">Selecione a extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="844dc-137">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="844dc-138">Você deverá ver uma tela do Visual Studio Code semelhante à seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="844dc-138">You should see a Visual Studio Code screen similar to the following image:</span></span>

      ![Visual Studio Code – Exibição da extensão do PowerShell](media/using-vscode/vscode.png)

   1. <span data-ttu-id="844dc-140">Clique no botão **Instalar** na extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="844dc-140">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="844dc-141">Após a instalação, se o botão **Instalar** mudar para **Recarregar**, clique em **Recarregar**.</span><span class="sxs-lookup"><span data-stu-id="844dc-141">After the install, if you see the **Install** button turn into **Reload**, Click on **Reload**.</span></span>
   1. <span data-ttu-id="844dc-142">Depois que o Visual Studio Code for recarregado, você estará pronto para a edição.</span><span class="sxs-lookup"><span data-stu-id="844dc-142">After Visual Studio Code has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="844dc-143">Por exemplo, para criar um novo arquivo, clique em **Arquivo > Novo**.</span><span class="sxs-lookup"><span data-stu-id="844dc-143">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="844dc-144">Para salvá-lo, clique em **Arquivo > Salvar** e forneça um nome de arquivo, como `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="844dc-144">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="844dc-145">Para fechar o arquivo, clique no `X` ao lado do nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="844dc-145">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="844dc-146">Para sair do Visual Studio Code, **Arquivo > Sair**.</span><span class="sxs-lookup"><span data-stu-id="844dc-146">To exit Visual Studio Code, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="844dc-147">Instalando a extensão do PowerShell em sistemas restritos</span><span class="sxs-lookup"><span data-stu-id="844dc-147">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="844dc-148">Alguns sistemas são configurados para exigir a validação de todas as assinaturas de código.</span><span class="sxs-lookup"><span data-stu-id="844dc-148">Some systems are set up to require validation of all code signatures.</span></span> <span data-ttu-id="844dc-149">Você poderá receber o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="844dc-149">You may receive the following error:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="844dc-150">Esse problema pode ocorrer quando a política de execução do PowerShell é definida pela Política de Grupo do Windows.</span><span class="sxs-lookup"><span data-stu-id="844dc-150">This problem can occur when PowerShell's execution policy is set by Windows Group Policy.</span></span> <span data-ttu-id="844dc-151">Para aprovar manualmente os Serviços do Editor do PowerShell e a extensão do PowerShell para o Visual Studio Code, abra um prompt do PowerShell e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="844dc-151">To manually approve PowerShell Editor Services and the PowerShell extension for Visual Studio Code, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="844dc-152">O sistema mostrará a mensagem **Você deseja executar o software desse editor não confiável?**</span><span class="sxs-lookup"><span data-stu-id="844dc-152">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span> <span data-ttu-id="844dc-153">Digite `A` para executar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="844dc-153">Type `A` to run the file.</span></span> <span data-ttu-id="844dc-154">Em seguida, abra o Visual Studio Code e verifique se a extensão do PowerShell está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="844dc-154">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="844dc-155">Se você ainda tiver problemas para começar, fale conosco sobre [problemas do GitHub][].</span><span class="sxs-lookup"><span data-stu-id="844dc-155">If you still have problems getting started, let us know on [GitHub issues][].</span></span>

> [!NOTE]
> <span data-ttu-id="844dc-156">A extensão do PowerShell para o Visual Studio Code não dá suporte à execução no modo de linguagem restrita.</span><span class="sxs-lookup"><span data-stu-id="844dc-156">The PowerShell extension for Visual Studio Code does not support running in constrained language mode.</span></span> <span data-ttu-id="844dc-157">Para obter mais informações, confira [problema 606 do GitHub][i606].</span><span class="sxs-lookup"><span data-stu-id="844dc-157">For more information, see [GitHub issue #606][i606].</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="844dc-158">Escolha de uma versão do PowerShell para ser usada com a extensão</span><span class="sxs-lookup"><span data-stu-id="844dc-158">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="844dc-159">Com o PowerShell Core instalado com o Windows PowerShell, agora é possível usar uma versão específica do PowerShell com a extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-159">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a specific version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="844dc-160">Esse recurso analisa alguns caminhos conhecidos em diferentes sistemas operacionais para descobrir locais de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-160">This feature looks at a few well-known paths on different operating systems to discover installations of PowerShell.</span></span>

<span data-ttu-id="844dc-161">Siga as etapas a seguir para escolher a versão:</span><span class="sxs-lookup"><span data-stu-id="844dc-161">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="844dc-162">Abra a **Paleta de comandos** no Windows ou Linux com <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="844dc-162">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="844dc-163">No macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="844dc-163">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="844dc-164">Pesquise por **Sessão**.</span><span class="sxs-lookup"><span data-stu-id="844dc-164">Search for **Session**.</span></span>
1. <span data-ttu-id="844dc-165">Clique em **PowerShell: mostrar menu de sessão**.</span><span class="sxs-lookup"><span data-stu-id="844dc-165">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="844dc-166">Na lista, escolha a versão do PowerShell que deseja usar, por exemplo: **PowerShell Core**.</span><span class="sxs-lookup"><span data-stu-id="844dc-166">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

<span data-ttu-id="844dc-167">Se você instalou o PowerShell em um local não típico, talvez ele não apareça inicialmente no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="844dc-167">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="844dc-168">Você pode estender o menu de sessão [adicionando seus próprios caminhos personalizados](#adding-your-own-powershell-paths-to-the-session-menu) conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="844dc-168">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

> [!NOTE]
> <span data-ttu-id="844dc-169">O menu de sessão do PowerShell também pode ser acessado pelo número de versão verde no canto inferior direito da barra de status.</span><span class="sxs-lookup"><span data-stu-id="844dc-169">The PowerShell session menu can also be accessed from the green version number in the bottom right corner of status bar.</span></span> <span data-ttu-id="844dc-170">Clicar nesse número de versão abrirá o menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="844dc-170">Clicking this version number opens the session menu.</span></span>

## <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="844dc-171">Definições de configuração para o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="844dc-171">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="844dc-172">Primeiro, caso você não esteja familiarizado com a maneira de alterar as configurações no Visual Studio Code, recomendamos ler a [documentação de configurações do Visual Studio Code][vsc-settings].</span><span class="sxs-lookup"><span data-stu-id="844dc-172">First, if you're not familiar with how to change settings in Visual Studio Code, we recommend reading [Visual Studio Code's settings][vsc-settings] documentation.</span></span>

<span data-ttu-id="844dc-173">Depois de ler a documentação, você pode adicionar definições de configuração no `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="844dc-173">After reading the documentation, you can add configuration settings in `settings.json`.</span></span>

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="844dc-174">Caso você não queira que essas configurações afetem todos os tipos de arquivos, o Visual Studio Code também permite configurações por idioma.</span><span class="sxs-lookup"><span data-stu-id="844dc-174">If you don't want these settings to affect all files types, Visual Studio Code also allows per-language configurations.</span></span> <span data-ttu-id="844dc-175">Crie uma configuração específica a um idioma colocando as configurações em um campo `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="844dc-175">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="844dc-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="844dc-176">For example:</span></span>

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> <span data-ttu-id="844dc-177">Para saber mais sobre a codificação de arquivo no Visual Studio Code, confira [Noções básicas sobre codificação de arquivo][file-encoding].</span><span class="sxs-lookup"><span data-stu-id="844dc-177">For more information about file encoding in Visual Studio Code, see [Understanding file encoding][file-encoding].</span></span>
>
> <span data-ttu-id="844dc-178">Confira também [Como replicar a experiência do ISE no Visual Studio Code][vsc-ise] para obter outras dicas sobre como configurar o Visual Studio Code para edição no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-178">Also, check out [How to replicate the ISE experience in Visual Studio Code][vsc-ise] for other tips on how to configure Visual Studio Code for PowerShell editing.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="844dc-179">Adição dos seus caminhos do PowerShell ao menu de sessão</span><span class="sxs-lookup"><span data-stu-id="844dc-179">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="844dc-180">É possível adicionar outros caminhos executáveis do PowerShell ao menu de sessão por meio de uma [configuração do Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span><span class="sxs-lookup"><span data-stu-id="844dc-180">You can add other PowerShell executable paths to the session menu through the [Visual Studio Code setting](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span></span>

<span data-ttu-id="844dc-181">Adicione um item à lista `powershell.powerShellAdditionalExePaths` ou crie a lista se ela não estiver em `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="844dc-181">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="844dc-182">Cada item precisa ter:</span><span class="sxs-lookup"><span data-stu-id="844dc-182">Each item must have:</span></span>

- <span data-ttu-id="844dc-183">`exePath`: o caminho para o executável `pwsh` ou `powershell`.</span><span class="sxs-lookup"><span data-stu-id="844dc-183">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
- <span data-ttu-id="844dc-184">`versionName`: o texto que aparece no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="844dc-184">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="844dc-185">Para configurar a versão padrão do PowerShell, defina o valor `powershell.powerShellDefaultVersion` para o texto exibido no menu de sessão (também conhecido como `versionName`):</span><span class="sxs-lookup"><span data-stu-id="844dc-185">To set the default PowerShell version, set the value `powershell.powerShellDefaultVersion` to the text displayed in the session menu (also known as the `versionName`):</span></span>

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

<span data-ttu-id="844dc-186">Depois de definir essa configuração, reinicie o Visual Studio Code ou, para recarregar a janela atual do Visual Studio Code na **Paleta de Comandos**, digite **Developer: Reload Window**.</span><span class="sxs-lookup"><span data-stu-id="844dc-186">After you've configured this setting, restart Visual Studio Code or to reload the current Visual Studio Code window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="844dc-187">Se você abrir o menu de sessão, agora verá versões adicionais do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-187">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="844dc-188">Compilar o PowerShell na origem é uma ótima maneira de testar sua compilação local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-188">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a><span data-ttu-id="844dc-189">Usar uma versão mais antiga da extensão do PowerShell para Windows PowerShell v3 e v4</span><span class="sxs-lookup"><span data-stu-id="844dc-189">Using an older version of the PowerShell Extension for Windows PowerShell v3 and v4</span></span>

<span data-ttu-id="844dc-190">A extensão atual do PowerShell não dá suporte ao [PowerShell v3 e v4][i1310].</span><span class="sxs-lookup"><span data-stu-id="844dc-190">The current PowerShell extension doesn't support [PowerShell v3 and v4][i1310].</span></span> <span data-ttu-id="844dc-191">No entanto, você pode usar a última versão da extensão que dá suporte ao PowerShell v3 e v4.</span><span class="sxs-lookup"><span data-stu-id="844dc-191">However, you can use the last version of the extension that supports PowerShell v3 and v4.</span></span>

> [!CAUTION]
> <span data-ttu-id="844dc-192">Não haverá correções adicionais para essa versão mais antiga da extensão.</span><span class="sxs-lookup"><span data-stu-id="844dc-192">There will be no additional fixes to this older version of the extension.</span></span> <span data-ttu-id="844dc-193">Ela é fornecida "no estado em que se encontra", mas estará disponível para você caso ainda esteja usando o Windows PowerShell v3 e v4.</span><span class="sxs-lookup"><span data-stu-id="844dc-193">It's provided "AS IS" but is available for you if you are still using Windows PowerShell v3 and Windows PowerShell v4.</span></span>

<span data-ttu-id="844dc-194">Primeiro, abra o painel Extensão e pesquise por `PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="844dc-194">First, open the Extension pane and search for `PowerShell`.</span></span> <span data-ttu-id="844dc-195">Em seguida, clique na engrenagem e selecione **Instalar outra versão...** .</span><span class="sxs-lookup"><span data-stu-id="844dc-195">Then click the gear and select **Install another version...**.</span></span>

![Item de menu – Instalar outra versão…](media/using-vscode/install-another-version.png)

<span data-ttu-id="844dc-197">Selecione a versão **2020.1.0**.</span><span class="sxs-lookup"><span data-stu-id="844dc-197">Then select the **2020.1.0** version.</span></span> <span data-ttu-id="844dc-198">Essa versão da extensão foi a última com suporte ao v3 e v4.</span><span class="sxs-lookup"><span data-stu-id="844dc-198">This version of the extension was the last version to support v3 and v4.</span></span> <span data-ttu-id="844dc-199">Adicione a seguinte configuração para que a versão da extensão não seja atualizada automaticamente:</span><span class="sxs-lookup"><span data-stu-id="844dc-199">Be sure to add the following setting so that your extension version doesn't update automatically:</span></span>

```json
{
    "extensions.autoUpdate": false
}
```

<span data-ttu-id="844dc-200">A versão **2020.1.0** funcionará por um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="844dc-200">Version **2020.1.0** will work for the foreseeable future.</span></span> <span data-ttu-id="844dc-201">No entanto, o Visual Studio Code pode implementar uma alteração que interrompa essa versão da extensão.</span><span class="sxs-lookup"><span data-stu-id="844dc-201">However, Visual Studio Code could implement a change that breaks this version of the extension.</span></span> <span data-ttu-id="844dc-202">Devido a isso e à falta de suporte, recomendamos:</span><span class="sxs-lookup"><span data-stu-id="844dc-202">Because of this, and lack of support, we recommend:</span></span>

- <span data-ttu-id="844dc-203">Atualizar para o Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="844dc-203">Upgrading to Windows PowerShell 5.1</span></span>
- <span data-ttu-id="844dc-204">Instalar o PowerShell 7, que é uma instalação lado a lado do Windows PowerShell e funciona melhor com a extensão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="844dc-204">Install PowerShell 7, which is a side-by-side install to Windows PowerShell and works the best with the PowerShell extension</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="844dc-205">Depuração com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="844dc-205">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="844dc-206">Depuração sem espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="844dc-206">No-workspace debugging</span></span>

<span data-ttu-id="844dc-207">No Visual Studio Code versão 1.9 (ou posterior), é possível depurar scripts do PowerShell sem abrir a pasta que contém o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-207">In Visual Studio Code version 1.9 (or higher), you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span>

1. <span data-ttu-id="844dc-208">Abra o arquivo de script do PowerShell com **Arquivo > Abrir Arquivo...**</span><span class="sxs-lookup"><span data-stu-id="844dc-208">Open the PowerShell script file with **File > Open File...**</span></span>
1. <span data-ttu-id="844dc-209">Defina um ponto de interrupção – selecione uma linha e pressione <kbd>F9</kbd></span><span class="sxs-lookup"><span data-stu-id="844dc-209">Set a breakpoint - select a line then press <kbd>F9</kbd></span></span>
1. <span data-ttu-id="844dc-210">Pressione <kbd>F5</kbd> para iniciar a depuração</span><span class="sxs-lookup"><span data-stu-id="844dc-210">Press <kbd>F5</kbd> to start debugging</span></span>

<span data-ttu-id="844dc-211">Será exibido o painel de ações de depuração, que permite que você interrompa o depurador, execute em etapas, retome e pare a depuração.</span><span class="sxs-lookup"><span data-stu-id="844dc-211">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="844dc-212">Depuração do workspace</span><span class="sxs-lookup"><span data-stu-id="844dc-212">Workspace debugging</span></span>

<span data-ttu-id="844dc-213">A depuração do workspace refere-se à depuração no contexto de uma pasta que você abriu no menu **Arquivo** usando **Abrir Pasta...** . A pasta que você abrir normalmente é a pasta do projeto do PowerShell ou a raiz do repositório Git.</span><span class="sxs-lookup"><span data-stu-id="844dc-213">Workspace debugging refers to debugging in the context of a folder that you've opened from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder or the root of your Git repository.</span></span> <span data-ttu-id="844dc-214">A depuração do workspace permite definir várias configurações de depuração diferentes de depurar apenas o arquivo aberto no momento.</span><span class="sxs-lookup"><span data-stu-id="844dc-214">Workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>

<span data-ttu-id="844dc-215">Siga estas etapas para criar um arquivo de configuração de depuração:</span><span class="sxs-lookup"><span data-stu-id="844dc-215">Follow these steps to create a debug configuration file:</span></span>

1. <span data-ttu-id="844dc-216">Abra a exibição **Depurar** no Windows ou Linux pressionando <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="844dc-216">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="844dc-217">No macOS, pressione <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="844dc-217">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
1. <span data-ttu-id="844dc-218">Clique no link **criar um arquivo launch.json**.</span><span class="sxs-lookup"><span data-stu-id="844dc-218">Click the **create a launch.json file** link.</span></span>
1. <span data-ttu-id="844dc-219">No prompt **Selecionar Ambiente**, escolha **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="844dc-219">From the **Select Environment** prompt, choose **PowerShell**.</span></span>
1. <span data-ttu-id="844dc-220">Escolha o tipo de depuração que você deseja usar:</span><span class="sxs-lookup"><span data-stu-id="844dc-220">Choose the type of debugging you'd like to use:</span></span>

   - <span data-ttu-id="844dc-221">**Iniciar o Arquivo Atual** – inicie e depure o arquivo na janela do editor atualmente ativa</span><span class="sxs-lookup"><span data-stu-id="844dc-221">**Launch Current File** - Launch and debug the file in the currently active editor window</span></span>
   - <span data-ttu-id="844dc-222">**Iniciar Script** – inicie e depure o arquivo ou comando especificado</span><span class="sxs-lookup"><span data-stu-id="844dc-222">**Launch Script** - Launch and debug the specified file or command</span></span>
   - <span data-ttu-id="844dc-223">**Sessão Interativa** – depure os comandos executados no Console Integrado</span><span class="sxs-lookup"><span data-stu-id="844dc-223">**Interactive Session** - Debug commands executed from the Integrated Console</span></span>
   - <span data-ttu-id="844dc-224">**Anexar** – anexe o depurador a um processo de host do PowerShell em execução</span><span class="sxs-lookup"><span data-stu-id="844dc-224">**Attach** - Attach the debugger to a running PowerShell Host Process</span></span>

<span data-ttu-id="844dc-225">O Visual Studio Code cria um diretório e um arquivo `.vscode\launch.json` na raiz da sua pasta do workspace para armazenar a configuração de depuração.</span><span class="sxs-lookup"><span data-stu-id="844dc-225">Visual Studio Code creates a directory and a file `.vscode\launch.json` in the root of your workspace folder to store the debug configuration.</span></span> <span data-ttu-id="844dc-226">Se os arquivos estiverem em um repositório Git, normalmente você desejará confirmar o arquivo `launch.json`.</span><span class="sxs-lookup"><span data-stu-id="844dc-226">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="844dc-227">O conteúdo do arquivo `launch.json` e:</span><span class="sxs-lookup"><span data-stu-id="844dc-227">The contents of the `launch.json` file are:</span></span>

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

<span data-ttu-id="844dc-228">Esse arquivo representa os cenários comuns de depuração.</span><span class="sxs-lookup"><span data-stu-id="844dc-228">This file represents the common debug scenarios.</span></span> <span data-ttu-id="844dc-229">Ao abrir este arquivo no editor, você vê um botão **Adicionar configuração...** .</span><span class="sxs-lookup"><span data-stu-id="844dc-229">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="844dc-230">É possível clicar nesse botão para adicionar mais configurações de depuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844dc-230">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="844dc-231">Uma configuração útil a adicionar é **PowerShell: Iniciar Script**.</span><span class="sxs-lookup"><span data-stu-id="844dc-231">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="844dc-232">Com essa configuração, é possível especificar um arquivo contendo os argumentos opcionais usados sempre que você pressiona <kbd>F5</kbd>, não importa qual arquivo está ativo no editor.</span><span class="sxs-lookup"><span data-stu-id="844dc-232">With this configuration, you can specify a file containing optional arguments that are used whenever you press <kbd>F5</kbd> no matter which file is active in the editor.</span></span>

<span data-ttu-id="844dc-233">Depois que a configuração de depuração for estabelecida, você poderá selecionar qual configuração deseja usar durante uma sessão de depuração.</span><span class="sxs-lookup"><span data-stu-id="844dc-233">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="844dc-234">Selecione uma configuração na lista suspensa de configuração de depuração, na barra de ferramentas da exibição **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="844dc-234">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a><span data-ttu-id="844dc-235">Solucionar problemas na extensão do PowerShell para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="844dc-235">Troubleshooting the PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="844dc-236">Se você tiver problemas ao usar o Visual Studio Code para desenvolver scripts do PowerShell, confira o [guia de solução de problemas][troubleshooting] no GitHub.</span><span class="sxs-lookup"><span data-stu-id="844dc-236">If you experience any issues using Visual Studio Code for PowerShell script development, see the [troubleshooting guide][troubleshooting] on GitHub.</span></span>

## <a name="useful-resources"></a><span data-ttu-id="844dc-237">Recursos úteis</span><span class="sxs-lookup"><span data-stu-id="844dc-237">Useful resources</span></span>

<span data-ttu-id="844dc-238">Há alguns vídeos e postagens no blog que podem ser úteis para você começar a usar a extensão do PowerShell para o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="844dc-238">There are a few videos and blog posts that may be helpful to get you started using the PowerShell extension for Visual Studio Code:</span></span>

### <a name="videos"></a><span data-ttu-id="844dc-239">vídeos</span><span class="sxs-lookup"><span data-stu-id="844dc-239">Videos</span></span>

- [<span data-ttu-id="844dc-240">Usar o Visual Studio Code como seu editor padrão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="844dc-240">Using Visual Studio Code as Your Default PowerShell Editor</span></span>](https://youtu.be/bGn45vIeAMM)
- [<span data-ttu-id="844dc-241">Visual Studio Code: análise aprofundada sobre a depuração de scripts do PowerShell</span><span class="sxs-lookup"><span data-stu-id="844dc-241">Visual Studio Code: deep dive into debugging your PowerShell scripts</span></span>](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a><span data-ttu-id="844dc-242">Postagens no blog</span><span class="sxs-lookup"><span data-stu-id="844dc-242">Blog posts</span></span>

- <span data-ttu-id="844dc-243">[Extensão do PowerShell][pscdn]</span><span class="sxs-lookup"><span data-stu-id="844dc-243">[PowerShell Extension][pscdn]</span></span>
- <span data-ttu-id="844dc-244">[Gravar e depurar scripts do PowerShell no Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="844dc-244">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="844dc-245">[Diretrizes sobre depuração no Visual Studio Code][psdbgblog]</span><span class="sxs-lookup"><span data-stu-id="844dc-245">[Debugging Visual Studio Code Guidance][psdbgblog]</span></span>
- <span data-ttu-id="844dc-246">[Depuração do PowerShell no Visual Studio Code][psdbg-gh]</span><span class="sxs-lookup"><span data-stu-id="844dc-246">[Debugging PowerShell in Visual Studio Code][psdbg-gh]</span></span>
- <span data-ttu-id="844dc-247">[Introdução ao desenvolvimento do PowerShell no Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="844dc-247">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="844dc-248">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="844dc-248">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="844dc-249">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="844dc-249">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="844dc-250">[Depuração de script do PowerShell no Visual Studio Code– parte 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="844dc-250">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="844dc-251">[Depuração de script do PowerShell no Visual Studio Code– parte 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="844dc-251">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

## <a name="powershell-extension-project-source-code"></a><span data-ttu-id="844dc-252">Código-fonte do projeto de extensão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="844dc-252">PowerShell extension project source code</span></span>

<span data-ttu-id="844dc-253">O código-fonte da extensão do PowerShell pode ser encontrado no [GitHub][psext-src].</span><span class="sxs-lookup"><span data-stu-id="844dc-253">The PowerShell extension's source code can be found on [GitHub][psext-src].</span></span>

<span data-ttu-id="844dc-254">Se você tem interesse em contribuir, as solicitações de pull são uma ótima opção.</span><span class="sxs-lookup"><span data-stu-id="844dc-254">If you're interested in contributing, Pull Requests are greatly appreciated.</span></span> <span data-ttu-id="844dc-255">Siga a [documentação de desenvolvedor][dev-docs] no GitHub para começar.</span><span class="sxs-lookup"><span data-stu-id="844dc-255">Follow along with the [developer documentation][dev-docs] on GitHub to get started.</span></span>

<!-- related articles -->
[ise]:                    ../../windows-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:   ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:   ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]:          ../../install/Installing-Windows-PowerShell.md
[file-encoding]:          understanding-file-encoding.md
[vsc-ise]:                How-To-Replicate-the-ISE-Experience-In-VSCode.md

<!-- blogs -->
[debug]:                  https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[debugging-part1]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/
[editing-part1]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[getting-started]:        https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[psdbgblog]:              https://johnpapa.net/debugging-with-visual-studio-code/
[psdbg-gh]:               https://github.com/PowerShell/vscode-powershell/tree/master/examples
[pscdn]:                  https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/

<!-- issues -->
[Problemas do GitHub]:          https://github.com/PowerShell/vscode-powershell/issues
[GitHub issues]:          https://github.com/PowerShell/vscode-powershell/issues
[i1310]:                  https://github.com/PowerShell/vscode-powershell/issues/1310
[i606]:                   https://github.com/PowerShell/vscode-powershell/issues/606

<!-- product links -->
[Visual Studio]:          https://visualstudio.microsoft.com/
[vscode]:                 https://code.visualstudio.com/
[psext]:                  https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[vsc-settings]:           https://code.visualstudio.com/docs/getstarted/settings
[vsc-setup]:              https://code.visualstudio.com/Docs/setup/setup-overview
[vsc-setup-win]:          https://code.visualstudio.com/docs/setup/windows
[vsc-setup-macos]:        https://code.visualstudio.com/docs/setup/mac
[vsc-setup-linux]:        https://code.visualstudio.com/docs/setup/linux
[psext-src]:              https://github.com/PowerShell/vscode-powershell
[troubleshooting]:        https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md
[dev-docs]:               https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md
