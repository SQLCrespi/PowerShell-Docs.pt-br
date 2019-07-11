---
title: Uso do Visual Studio Code para desenvolvimento do PowerShell
description: Uso do Visual Studio Code para desenvolvimento do PowerShell
ms.date: 08/06/2018
ms.openlocfilehash: 5badffd49252e0d72ae2c20d3147ad4b1e92d5ed
ms.sourcegitcommit: cf1a281cce9f7239c440c90f8b2798d32a13778d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882567"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="c5baf-103">Uso do Visual Studio Code para desenvolvimento do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5baf-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="c5baf-104">Além do [PowerShell ISE][ise], o PowerShell também tem suporte no Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c5baf-104">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code.</span></span>
<span data-ttu-id="c5baf-105">Além disso, o ISE não é compatível com o PowerShell Core, embora haja suporte do Visual Studio Code para o PowerShell Core em todas as plataformas (Windows, macOS e Linux)</span><span class="sxs-lookup"><span data-stu-id="c5baf-105">Furthermore, the ISE is not supported with PowerShell Core, while Visual Studio Code is supported for PowerShell Core on all platforms (Windows, macOS, and Linux)</span></span>

<span data-ttu-id="c5baf-106">Você pode usar o Visual Studio Code no Windows com o PowerShell versão 5 usando o Windows 10 ou instalando o [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) para sistemas operacionais do Windows de nível baixo (por exemplo, Windows 8.1 etc.).</span><span class="sxs-lookup"><span data-stu-id="c5baf-106">You can use Visual Studio Code on Windows with PowerShell version 5 by using Windows 10 or by installing [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) for down-level Windows OSs (e.g. Windows 8.1, etc.).</span></span>

<span data-ttu-id="c5baf-107">Antes de iniciá-lo, verifique se o PowerShell existe no sistema.</span><span class="sxs-lookup"><span data-stu-id="c5baf-107">Before starting it, please make sure PowerShell exists on your system.</span></span>
<span data-ttu-id="c5baf-108">Para cargas de trabalho modernas no Windows, macOS e Linux, consulte:</span><span class="sxs-lookup"><span data-stu-id="c5baf-108">For modern workloads on Windows, macOS, and Linux, see:</span></span>

- <span data-ttu-id="c5baf-109">[Instalar o PowerShell Core no Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="c5baf-109">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="c5baf-110">[Instalar o PowerShell Core no macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="c5baf-110">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="c5baf-111">[Instalação do PowerShell Core no Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="c5baf-111">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="c5baf-112">Para cargas de trabalho tradicionais do Windows PowerShell, veja [instalação do Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="c5baf-112">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="c5baf-113">Edição com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c5baf-113">Editing with Visual Studio Code</span></span>

### <a name="1-installing-visual-studio-codehttpscodevisualstudiocomdocssetupsetup-overview"></a>[<span data-ttu-id="c5baf-114">1. Instalação do Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c5baf-114">1. Installing Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/setup/setup-overview)

- <span data-ttu-id="c5baf-115">**Linux**: siga as instruções de instalação na página [Execução do código VS no Linux](https://code.visualstudio.com/docs/setup/linux)</span><span class="sxs-lookup"><span data-stu-id="c5baf-115">**Linux**: follow the installation instructions on the [Running VS Code on Linux](https://code.visualstudio.com/docs/setup/linux) page</span></span>

- <span data-ttu-id="c5baf-116">**macOS**: siga as instruções de instalação na página [Execução do código VS no macOS](https://code.visualstudio.com/docs/setup/mac)</span><span class="sxs-lookup"><span data-stu-id="c5baf-116">**macOS**: follow the installation instructions on the [Running VS Code on macOS](https://code.visualstudio.com/docs/setup/mac) page</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c5baf-117">No macOS, você deve instalar o OpenSSL para que a extensão do PowerShell funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="c5baf-117">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span>
  > <span data-ttu-id="c5baf-118">A maneira mais fácil de fazer isso é instalar o [Homebrew](https://brew.sh/) e, em seguida, executar `brew install openssl`.</span><span class="sxs-lookup"><span data-stu-id="c5baf-118">The easiest way to accomplish this is to install [Homebrew](https://brew.sh/) and then run `brew install openssl`.</span></span>
  > <span data-ttu-id="c5baf-119">Agora, o VS Code pode carregar a extensão do PowerShell com êxito.</span><span class="sxs-lookup"><span data-stu-id="c5baf-119">VS Code can now load the PowerShell extension successfully.</span></span>

- <span data-ttu-id="c5baf-120">**Windows**: siga as instruções de instalação na página [Execução do código VS no Windows](https://code.visualstudio.com/docs/setup/windows)</span><span class="sxs-lookup"><span data-stu-id="c5baf-120">**Windows**: follow the installation instructions on the [Running VS Code on Windows](https://code.visualstudio.com/docs/setup/windows) page</span></span>

### <a name="2-installing-powershell-extension"></a><span data-ttu-id="c5baf-121">2. Instalação da extensão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5baf-121">2. Installing PowerShell Extension</span></span>

- <span data-ttu-id="c5baf-122">Inicie o aplicativo Visual Studio Code pelo:</span><span class="sxs-lookup"><span data-stu-id="c5baf-122">Launch the Visual Studio Code app by:</span></span>
  - <span data-ttu-id="c5baf-123">**Windows**: digitando `code` na sua sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5baf-123">**Windows**: typing `code` in your PowerShell session</span></span>
  - <span data-ttu-id="c5baf-124">**Linux**: digitando `code` em seu terminal</span><span class="sxs-lookup"><span data-stu-id="c5baf-124">**Linux**: typing `code` in your terminal</span></span>
  - <span data-ttu-id="c5baf-125">**macOS**: digitando `code` em seu terminal</span><span class="sxs-lookup"><span data-stu-id="c5baf-125">**macOS**: typing `code` in your terminal</span></span>

- <span data-ttu-id="c5baf-126">Inicie **Abertura rápida** pressionando **Ctrl+P** (**Cmd+P** no Mac).</span><span class="sxs-lookup"><span data-stu-id="c5baf-126">Launch **Quick Open** by pressing **Ctrl+P** (**Cmd+P** on Mac).</span></span>
- <span data-ttu-id="c5baf-127">Na Abertura rápida, digite `ext install powershell` e clique em **Enter**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-127">In Quick Open, type `ext install powershell` and hit **Enter**.</span></span>
- <span data-ttu-id="c5baf-128">A exibição **Extensões** será aberta na barra lateral.</span><span class="sxs-lookup"><span data-stu-id="c5baf-128">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="c5baf-129">Selecione a extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5baf-129">Select the PowerShell extension from Microsoft.</span></span>
  <span data-ttu-id="c5baf-130">Você deve ver algo como:</span><span class="sxs-lookup"><span data-stu-id="c5baf-130">You should see something like below:</span></span>

  ![VSCode](../../images/vscode.png)

- <span data-ttu-id="c5baf-132">Clique no botão **Instalar** na extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5baf-132">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
- <span data-ttu-id="c5baf-133">Após a instalação, você verá que o botão **Instalar** mudará para **Recarregar**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-133">After the install, you see the **Install** button turns to **Reload**.</span></span>
  <span data-ttu-id="c5baf-134">Clique em **Recarregar**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-134">Click on **Reload**.</span></span>
- <span data-ttu-id="c5baf-135">Depois de recarregar o Visual Studio Code, você está pronto para edição.</span><span class="sxs-lookup"><span data-stu-id="c5baf-135">After Visual Studio Code has reload, you are ready for editing.</span></span>

<span data-ttu-id="c5baf-136">Por exemplo, para criar um novo arquivo, clique em **Arquivo -> Novo**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-136">For example, to create a new file, click **File->New**.</span></span>
<span data-ttu-id="c5baf-137">Para salvá-lo, clique em **Arquivo -> Salvar** e, em seguida, forneça um nome de arquivo. Digamos `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c5baf-137">To save it, click **File->Save** and then provide a file name, let's say `HelloWorld.ps1`.</span></span>
<span data-ttu-id="c5baf-138">Para fechar o arquivo, clique no "x" ao lado do nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5baf-138">To close the file, click on "x" next to the file name.</span></span>
<span data-ttu-id="c5baf-139">Para sair do Visual Studio Code, **Arquivo -> Sair**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-139">To exit Visual Studio Code, **File->Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="c5baf-140">Instalando a extensão do PowerShell em sistemas restritos</span><span class="sxs-lookup"><span data-stu-id="c5baf-140">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="c5baf-141">Alguns sistemas são configurados de forma a exigir que todas as assinaturas de código sejam verificadas e, portanto, exigem que os Serviços do Editor do PowerShell sejam aprovados manualmente para serem executados no sistema.</span><span class="sxs-lookup"><span data-stu-id="c5baf-141">Some systems are set up in a way that requires all code signatures to be checked and thus requires PowerShell Editor Services to be manually approved to run on the system.</span></span>
<span data-ttu-id="c5baf-142">Uma atualização da Política de Grupo que altera a política de execução é uma causa provável caso tenha instalado a extensão do PowerShell, mas veja um erro como:</span><span class="sxs-lookup"><span data-stu-id="c5baf-142">A Group Policy update that changes execution policy is a likely cause if you have installed the PowerShell extension but are reaching an error like:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="c5baf-143">Para aprovar manualmente os Serviços do Editor do PowerShell e, portanto, a extensão do PowerShell para VSCode, abra um prompt do PowerShell e execute:</span><span class="sxs-lookup"><span data-stu-id="c5baf-143">To manually approve PowerShell Editor Services and thus the PowerShell extension for VSCode open a PowerShell prompt and run:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="c5baf-144">O sistema mostrará a mensagem "Você deseja executar o software desse editor não confiável?"</span><span class="sxs-lookup"><span data-stu-id="c5baf-144">You are prompted with "Do you want to run software from this untrusted publisher?"</span></span>
<span data-ttu-id="c5baf-145">Digite `R` para executar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5baf-145">Type `R` to run the file.</span></span> <span data-ttu-id="c5baf-146">Em seguida, abra o Visual Studio Code e verifique se a extensão do PowerShell está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="c5baf-146">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="c5baf-147">Se você ainda tiver problemas para começar, fale conosco no [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span><span class="sxs-lookup"><span data-stu-id="c5baf-147">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

#### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="c5baf-148">Escolha de uma versão do PowerShell para ser usada com a extensão</span><span class="sxs-lookup"><span data-stu-id="c5baf-148">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="c5baf-149">Com o PowerShell Core instalado com o Windows PowerShell, agora é possível usar uma versão específica do PowerShell com a extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5baf-149">With PowerShell Core installing side-by-side with Windows PowerShell, is it now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="c5baf-150">Siga estas etapas para escolher a versão:</span><span class="sxs-lookup"><span data-stu-id="c5baf-150">Use the following these steps to choose the version:</span></span>

1. <span data-ttu-id="c5baf-151">Abra a paleta de comando (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no Windows e Linux, ou <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> no macOS).</span><span class="sxs-lookup"><span data-stu-id="c5baf-151">Open the command pallet (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on Windows & Linux, <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS).</span></span>
1. <span data-ttu-id="c5baf-152">Pesquise "Sessão".</span><span class="sxs-lookup"><span data-stu-id="c5baf-152">Search for "Session".</span></span>
1. <span data-ttu-id="c5baf-153">Clique em "PowerShell: mostrar menu de sessão".</span><span class="sxs-lookup"><span data-stu-id="c5baf-153">Click on "PowerShell: Show Session Menu".</span></span>
1. <span data-ttu-id="c5baf-154">Na lista, escolha a versão do PowerShell que deseja usar; por exemplo, "PowerShell Core".</span><span class="sxs-lookup"><span data-stu-id="c5baf-154">Choose the version of PowerShell you want to use from the list - for example, "PowerShell Core".</span></span>

>[!IMPORTANT]
> <span data-ttu-id="c5baf-155">Esse recurso analisa alguns caminhos conhecidos em diferentes sistemas operacionais para descobrir locais de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5baf-155">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="c5baf-156">Se você instalou o PowerShell em um local não típico, talvez ele não apareça inicialmente no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="c5baf-156">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="c5baf-157">Você pode estender o menu de sessão [adicionando seus próprios caminhos personalizados](#adding-your-own-powershell-paths-to-the-session-menu) conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="c5baf-157">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="c5baf-158">Há outra maneira de acessar o menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="c5baf-158">There is another way to get to the session menu.</span></span> <span data-ttu-id="c5baf-159">Quando um arquivo do PowerShell é aberto no editor, um número de versão em verde aparece no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="c5baf-159">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="c5baf-160">Clicar nesse número de versão levará ao menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="c5baf-160">Clicking this version number will bring you to the session menu.</span></span>

##### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="c5baf-161">Adição dos seus caminhos do PowerShell ao menu de sessão</span><span class="sxs-lookup"><span data-stu-id="c5baf-161">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="c5baf-162">É possível adicionar outros caminhos executáveis do PowerShell ao menu de sessão por meio de uma configuração do VS Code.</span><span class="sxs-lookup"><span data-stu-id="c5baf-162">You can add other PowerShell executable paths to the session menu through a VS Code setting.</span></span>

<span data-ttu-id="c5baf-163">Adicione um item à lista `powershell.powerShellAdditionalExePaths` ou crie a lista se ela não estiver em `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="c5baf-163">Add an item to the list  `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="c5baf-164">Cada item precisa ter:</span><span class="sxs-lookup"><span data-stu-id="c5baf-164">Each item must have:</span></span>

* <span data-ttu-id="c5baf-165">`exePath`: o caminho para o executável `pwsh` ou `powershell`.</span><span class="sxs-lookup"><span data-stu-id="c5baf-165">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
* <span data-ttu-id="c5baf-166">`versionName`: o texto que aparece no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="c5baf-166">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="c5baf-167">É possível definir a versão padrão do PowerShell a ser usada. Para isso, utilize a configuração `powershell.powerShellDefaultVersion` definindo-a como o texto exibido no menu de sessão (também conhecido como `versionName` na última configuração):</span><span class="sxs-lookup"><span data-stu-id="c5baf-167">You can set the default PowerShell version to use using the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (aka the `versionName` in the last setting):</span></span>

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

<span data-ttu-id="c5baf-168">Depois de definir essa configuração, reinicie o Visual Studio Code ou use a ação "Desenvolvedor: recarregar janela" da paleta de comando para atualizar a janela atual do vscode.</span><span class="sxs-lookup"><span data-stu-id="c5baf-168">Once you've set this setting, restart Visual Studio Code or use the the "Developer: Reload Window" command pallet action to reload the current vscode window.</span></span>

<span data-ttu-id="c5baf-169">Se você abrir o menu de sessão, agora verá versões adicionais do PowerShell!</span><span class="sxs-lookup"><span data-stu-id="c5baf-169">If you open the session menu, you will now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="c5baf-170">Compilar o PowerShell na origem é uma ótima maneira de testar sua compilação local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5baf-170">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

#### <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="c5baf-171">Definições de configuração para o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c5baf-171">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="c5baf-172">Usando as etapas no parágrafo anterior, você pode adicionar configurações no `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="c5baf-172">By using the steps in the previous paragraph you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="c5baf-173">Recomendamos as seguintes definições de configuração para o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c5baf-173">We recommend the following configuration settings for Visual Studio Code:</span></span>

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="c5baf-174">Caso não queira que essas configurações afetem todos os tipos de arquivos, o VSCode também permite configurações por idioma.</span><span class="sxs-lookup"><span data-stu-id="c5baf-174">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="c5baf-175">Crie uma configuração específica para um idioma colocando as configurações em um campo `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="c5baf-175">Create a language specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="c5baf-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c5baf-176">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="c5baf-177">Para saber mais sobre a codificação do arquivo no VS Code, confira [Entendendo a codificação do arquivo](understanding-file-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="c5baf-177">For more information about file encoding in VS Code, see [Understanding file encoding](understanding-file-encoding.md).</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="c5baf-178">Depuração com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c5baf-178">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="c5baf-179">Depuração sem espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="c5baf-179">No-workspace debugging</span></span>

<span data-ttu-id="c5baf-180">A partir da versão do Visual Studio Code 1.9, você pode depurar scripts do PowerShell sem a necessidade de abrir a pasta que contém o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5baf-180">As of Visual Studio Code version 1.9 you can debug PowerShell scripts without having to open the folder containing the PowerShell script.</span></span> <span data-ttu-id="c5baf-181">Abra o arquivo de script do PowerShell usando **Arquivo -> Abrir Arquivo...** , defina um ponto de interrupção em uma linha (pressione F9) e, em seguida, pressione F5 para iniciar a depuração.</span><span class="sxs-lookup"><span data-stu-id="c5baf-181">Open the PowerShell script file with **File->Open File...**, set a breakpoint on a line (press F9) and then press F5 to start debugging.</span></span> <span data-ttu-id="c5baf-182">Será exibido o painel de ações de depuração, que permite que você interrompa o depurador, execute em etapas, retome e pare a depuração.</span><span class="sxs-lookup"><span data-stu-id="c5baf-182">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="c5baf-183">Depuração do workspace</span><span class="sxs-lookup"><span data-stu-id="c5baf-183">Workspace debugging</span></span>

<span data-ttu-id="c5baf-184">A depuração do workspace refere-se a depuração no contexto de uma pasta que você abriu no Visual Studio Code usando **Abrir Pasta...**  do menu **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-184">Workspace debugging refers to debugging in the context of a folder that you have opened in Visual Studio Code using **Open Folder...** from the **File** menu.</span></span>
<span data-ttu-id="c5baf-185">A pasta que você abrir normalmente é a pasta do projeto do PowerShell e/ou a raiz do repositório Git.</span><span class="sxs-lookup"><span data-stu-id="c5baf-185">The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="c5baf-186">Mesmo nesse modo, você pode iniciar a depuração de script do PowerShell selecionado no momento pressionando F5.</span><span class="sxs-lookup"><span data-stu-id="c5baf-186">Even in this mode, you can start debugging the currently selected PowerShell script by simply pressing F5.</span></span>
<span data-ttu-id="c5baf-187">No entanto, a depuração do workspace permite definir várias configurações de depuração diferentes de depurar apenas o arquivo aberto no momento.</span><span class="sxs-lookup"><span data-stu-id="c5baf-187">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>
<span data-ttu-id="c5baf-188">Por exemplo, você pode adicionar configurações para:</span><span class="sxs-lookup"><span data-stu-id="c5baf-188">For instance, you can add a configurations to:</span></span>

- <span data-ttu-id="c5baf-189">Iniciar testes Pester no depurador</span><span class="sxs-lookup"><span data-stu-id="c5baf-189">Launch Pester tests in the debugger</span></span>
- <span data-ttu-id="c5baf-190">Abrir um arquivo específico com argumentos no depurador</span><span class="sxs-lookup"><span data-stu-id="c5baf-190">Launch a specific file with arguments in the debugger</span></span>
- <span data-ttu-id="c5baf-191">Inicie uma sessão interativa no depurador</span><span class="sxs-lookup"><span data-stu-id="c5baf-191">Launch an interactive session in the debugger</span></span>
- <span data-ttu-id="c5baf-192">Anexar o depurador a um processo de host do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5baf-192">Attach the debugger to a PowerShell host process</span></span>

<span data-ttu-id="c5baf-193">Siga estas etapas para criar o arquivo de configuração de depuração:</span><span class="sxs-lookup"><span data-stu-id="c5baf-193">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="c5baf-194">Abra a exibição **Depurar** pressionando **Ctrl+Shift+D** (**Cmd+Shift+D** no Mac).</span><span class="sxs-lookup"><span data-stu-id="c5baf-194">Open the **Debug** view by pressing **Ctrl+Shift+D** (**Cmd+Shift+D** on Mac).</span></span>
  2. <span data-ttu-id="c5baf-195">Pressione o ícone de engrenagem **Configurar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="c5baf-195">Press the **Configure** gear icon in the toolbar.</span></span>
  3. <span data-ttu-id="c5baf-196">O Visual Studio Code solicitará que você **Selecione o Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-196">Visual Studio Code prompts you to **Select Environment**.</span></span> <span data-ttu-id="c5baf-197">Escolha **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-197">Choose **PowerShell**.</span></span>

  <span data-ttu-id="c5baf-198">Quando você fizer isso, o Visual Studio Code criará um diretório e um arquivo ".vscode\launch.json" na raiz da sua pasta de workspace.</span><span class="sxs-lookup"><span data-stu-id="c5baf-198">When you do this, Visual Studio Code creates a directory and a file ".vscode\launch.json" in the root of your workspace folder.</span></span>
  <span data-ttu-id="c5baf-199">A configuração de depuração é armazena nesse local.</span><span class="sxs-lookup"><span data-stu-id="c5baf-199">This is where your debug configuration is stored.</span></span> <span data-ttu-id="c5baf-200">Quando os arquivos estão em um repositório Git, normalmente deseja-se confirmar o arquivo launch.json.</span><span class="sxs-lookup"><span data-stu-id="c5baf-200">If your files are in a Git repository, you typically want to commit the launch.json file.</span></span>
  <span data-ttu-id="c5baf-201">O conteúdo do arquivo launch.json é:</span><span class="sxs-lookup"><span data-stu-id="c5baf-201">The contents of the launch.json file are:</span></span>

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

  <span data-ttu-id="c5baf-202">Isso representa os cenários comuns de depuração.</span><span class="sxs-lookup"><span data-stu-id="c5baf-202">This represents the common debug scenarios.</span></span>
  <span data-ttu-id="c5baf-203">No entanto, ao abrir este arquivo no editor, você vê um botão **Adicionar Configuração...** .</span><span class="sxs-lookup"><span data-stu-id="c5baf-203">However, when you open this file in the editor, you see an **Add Configuration...** button.</span></span>
  <span data-ttu-id="c5baf-204">Você pode pressionar esse botão para adicionar mais configurações de depuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5baf-204">You can press this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="c5baf-205">Uma configuração útil a adicionar é **PowerShell: Iniciar Script**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-205">One handy configuration to add is **PowerShell: Launch Script**.</span></span>
  <span data-ttu-id="c5baf-206">Com essa configuração, você pode especificar um arquivo específico com argumentos opcionais que devem ser iniciado sempre que você pressionar F5, não importa qual arquivo está ativo no momento no editor.</span><span class="sxs-lookup"><span data-stu-id="c5baf-206">With this configuration, you can specify a specific file with optional arguments that should be launched whenever you press F5 no matter which file is currently active in the editor.</span></span>

  <span data-ttu-id="c5baf-207">Quando a configuração de depuração é estabelecida, selecione qual configuração você deseja usar durante uma sessão de depuração, selecionando uma no menu suspenso de configuração de depuração na barra de ferramentas da exibição **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="c5baf-207">Once the debug configuration is established, you can select which configuration you want to use during a debug session by selecting one from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

<span data-ttu-id="c5baf-208">Há alguns blogs que podem ser úteis para você começar a usar a extensão do PowerShell para o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="c5baf-208">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code:</span></span>

- <span data-ttu-id="c5baf-209">[Extensão do PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="c5baf-209">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="c5baf-210">[Gravar e depurar scripts do PowerShell no Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="c5baf-210">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="c5baf-211">[Orientação sobre depuração no Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="c5baf-211">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="c5baf-212">[Depuração do PowerShell no Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="c5baf-212">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="c5baf-213">[Introdução ao desenvolvimento do PowerShell no Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="c5baf-213">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="c5baf-214">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="c5baf-214">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="c5baf-215">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="c5baf-215">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="c5baf-216">[Depuração de script do PowerShell no Visual Studio Code– parte 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="c5baf-216">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="c5baf-217">[Depuração de script do PowerShell no Visual Studio Code– parte 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="c5baf-217">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../setup/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../setup/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../setup/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../setup/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://blogs.msdn.microsoft.com/powershell/2015/11/16/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://blogs.technet.microsoft.com/heyscriptingguy/2016/12/05/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/11/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/12/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/06/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/13/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-visual-studio-code"></a><span data-ttu-id="c5baf-218">Extensão do PowerShell para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c5baf-218">PowerShell Extension for Visual Studio Code</span></span>

<span data-ttu-id="c5baf-219">O código-fonte da extensão do PowerShell pode ser encontrado no [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5baf-219">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>
