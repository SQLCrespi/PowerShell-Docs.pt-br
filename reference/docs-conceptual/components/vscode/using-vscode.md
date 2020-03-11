---
title: Uso do Visual Studio Code para desenvolvimento do PowerShell
description: Uso do Visual Studio Code para desenvolvimento do PowerShell
ms.date: 11/07/2019
ms.openlocfilehash: 16ae228c0d169261b783366a730fd2d5d77d32d6
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279054"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="fc2ab-103">Uso do Visual Studio Code para desenvolvimento do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc2ab-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="fc2ab-104">Além do [ISE do PowerShell][ise], o PowerShell também tem um bom suporte no VSCode (Visual Studio Code).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-104">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code (VSCode).</span></span> <span data-ttu-id="fc2ab-105">O ISE não tem suporte com o PowerShell Core, mas o VSCode tem suporte para o PowerShell Core em todas as plataformas: Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-105">The ISE isn't supported with PowerShell Core, but VSCode is supported for PowerShell Core on all platforms: Windows, macOS, and Linux.</span></span>

<span data-ttu-id="fc2ab-106">É possível usar o VSCode no Windows com o PowerShell versão 5 usando o Windows 10 ou instalando o Windows Management Framework 5.1 para sistemas operacionais do Windows de nível baixo (por exemplo, Windows 8.1).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-106">You can use VSCode on Windows with PowerShell version 5 by using Windows 10 or by installing Windows Management Framework 5.1 for down-level Windows OSs such as Windows 8.1.</span></span> <span data-ttu-id="fc2ab-107">Para obter mais informações, confira [Instalar e configurar WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-107">For more information, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>

<span data-ttu-id="fc2ab-108">Antes de começar, verifique se o PowerShell existe no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-108">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="fc2ab-109">Para cargas de trabalho modernas no Windows, macOS e Linux, confira os seguintes links:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-109">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="fc2ab-110">[Instalar o PowerShell Core no Linux][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-110">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="fc2ab-111">[Instalar o PowerShell Core no macOS][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-111">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="fc2ab-112">[Instalar o PowerShell Core no Windows][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-112">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="fc2ab-113">Para cargas de trabalho tradicionais do Windows PowerShell, confira [Como instalar o Windows PowerShell][install-winps].</span><span class="sxs-lookup"><span data-stu-id="fc2ab-113">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-vscode"></a><span data-ttu-id="fc2ab-114">Editar com VSCode</span><span class="sxs-lookup"><span data-stu-id="fc2ab-114">Editing with VSCode</span></span>

1. <span data-ttu-id="fc2ab-115">Instale o VSCode.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-115">Install VSCode.</span></span> <span data-ttu-id="fc2ab-116">Para obter mais informações, confira a visão geral [Configurar o Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-116">For more information, see the overview [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span></span>

   <span data-ttu-id="fc2ab-117">Há instruções de instalação para cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-117">There are installation instructions for each platform:</span></span>

   - <span data-ttu-id="fc2ab-118">**Linux**: siga as instruções de instalação na página [Executar o VSCode no Linux](https://code.visualstudio.com/docs/setup/linux).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-118">**Linux**: follow the installation instructions on the [Running VSCode on Linux](https://code.visualstudio.com/docs/setup/linux) page.</span></span>
   - <span data-ttu-id="fc2ab-119">**macOS**: siga as instruções de instalação na página [Executar o VSCode no macOS](https://code.visualstudio.com/docs/setup/mac).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-119">**macOS**: follow the installation instructions on the [Running VSCode on macOS](https://code.visualstudio.com/docs/setup/mac) page.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="fc2ab-120">No macOS, você deve instalar o OpenSSL para que a extensão do PowerShell funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-120">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span> <span data-ttu-id="fc2ab-121">A maneira mais fácil de fazer isso é instalar o [Homebrew](https://brew.sh/) e, em seguida, executar `brew install openssl`.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-121">The easiest way to accomplish this is to install [Homebrew](https://brew.sh/) and then run `brew install openssl`.</span></span> <span data-ttu-id="fc2ab-122">Agora, o VS Code pode carregar a extensão do PowerShell com êxito.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-122">VSCode can now load the PowerShell extension successfully.</span></span>

   - <span data-ttu-id="fc2ab-123">**Windows**: siga as instruções de instalação na página [Executar o VSCode no Windows](https://code.visualstudio.com/docs/setup/windows).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-123">**Windows**: follow the installation instructions on the [Running VSCode on Windows](https://code.visualstudio.com/docs/setup/windows) page.</span></span>

1. <span data-ttu-id="fc2ab-124">Instale a extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-124">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="fc2ab-125">Inicie o aplicativo VSCode das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-125">Launch the VSCode app by:</span></span>
      - <span data-ttu-id="fc2ab-126">**Windows**: digitando `code` na sua sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc2ab-126">**Windows**: typing `code` in your PowerShell session</span></span>
      - <span data-ttu-id="fc2ab-127">**Linux**: digitando `code` em seu terminal</span><span class="sxs-lookup"><span data-stu-id="fc2ab-127">**Linux**: typing `code` in your terminal</span></span>
      - <span data-ttu-id="fc2ab-128">**macOS**: digitando `code` em seu terminal</span><span class="sxs-lookup"><span data-stu-id="fc2ab-128">**macOS**: typing `code` in your terminal</span></span>
   1. <span data-ttu-id="fc2ab-129">Inicie o **Abertura rápida** no Windows ou no Linux pressionando <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-129">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="fc2ab-130">No macOS, pressione <kbd>Cmd</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-130">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="fc2ab-131">Em Abertura rápida, digite `ext install powershell` e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-131">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="fc2ab-132">A exibição **Extensões** será aberta na barra lateral.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-132">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="fc2ab-133">Selecione a extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-133">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="fc2ab-134">Você deverá ver uma tela VSCode semelhante à imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-134">You should see a VSCode screen similar to the following image:</span></span>

      ![VSCode](media/using-vscode/vscode.png)

   1. <span data-ttu-id="fc2ab-136">Clique no botão **Instalar** na extensão do PowerShell da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-136">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="fc2ab-137">Após a instalação, você verá que o botão **Instalar** mudará para **Recarregar**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-137">After the install, you see the **Install** button turns to **Reload**.</span></span> <span data-ttu-id="fc2ab-138">Clique em **Recarregar**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-138">Click on **Reload**.</span></span>
   1. <span data-ttu-id="fc2ab-139">Depois que o VSCode for carregado, você estará pronto para edição.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-139">After VSCode has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="fc2ab-140">Por exemplo, para criar um novo arquivo, clique em **Arquivo > Novo**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-140">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="fc2ab-141">Para salvá-lo, clique em **Arquivo > Salvar** e forneça um nome de arquivo, como `HelloWorld.ps1`.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-141">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="fc2ab-142">Para fechar o arquivo, clique no `X` ao lado do nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-142">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="fc2ab-143">Para sair do VSCode, **Arquivo > Sair**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-143">To exit VSCode, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="fc2ab-144">Instalando a extensão do PowerShell em sistemas restritos</span><span class="sxs-lookup"><span data-stu-id="fc2ab-144">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="fc2ab-145">Alguns sistemas são configurados de forma a exigir que todas as assinaturas de código sejam verificadas e exigem que os Serviços do Editor do PowerShell sejam aprovados manualmente para serem executados no sistema.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-145">Some systems are set up in a way that requires all code signatures to be checked and requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="fc2ab-146">Uma atualização da Política de Grupo que altera a política de execução é uma causa provável caso tenha instalado a extensão do PowerShell, mas está recebendo um erro como:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-146">A Group Policy update that changes execution policy is a likely cause if you've installed the PowerShell extension but are receiving an error such as:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="fc2ab-147">Para aprovar manualmente os Serviços do Editor do PowerShell e a extensão do PowerShell para VSCode, abra um prompt do PowerShell e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-147">To manually approve PowerShell Editor Services and the PowerShell extension for VSCode, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="fc2ab-148">O sistema mostrará a mensagem **Você deseja executar o software desse editor não confiável?**</span><span class="sxs-lookup"><span data-stu-id="fc2ab-148">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span> <span data-ttu-id="fc2ab-149">Digite `A` para executar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-149">Type `A` to run the file.</span></span> <span data-ttu-id="fc2ab-150">Em seguida, abra o VSCode e verifique se a extensão do PowerShell está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-150">Then, open VSCode and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="fc2ab-151">Se você ainda tiver problemas para começar, fale conosco no [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-151">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="fc2ab-152">Escolha de uma versão do PowerShell para ser usada com a extensão</span><span class="sxs-lookup"><span data-stu-id="fc2ab-152">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="fc2ab-153">Com o PowerShell Core instalado com o Windows PowerShell, agora é possível usar uma versão específica do PowerShell com a extensão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-153">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="fc2ab-154">Siga as etapas a seguir para escolher a versão:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-154">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="fc2ab-155">Abra a **Paleta de comandos** no Windows ou Linux com <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-155">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="fc2ab-156">No macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-156">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="fc2ab-157">Pesquise por **Sessão**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-157">Search for **Session**.</span></span>
1. <span data-ttu-id="fc2ab-158">Clique em **PowerShell: mostrar menu de sessão**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-158">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="fc2ab-159">Na lista, escolha a versão do PowerShell que deseja usar, por exemplo: **PowerShell Core**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-159">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc2ab-160">Esse recurso analisa alguns caminhos conhecidos em diferentes sistemas operacionais para descobrir locais de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-160">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="fc2ab-161">Se você instalou o PowerShell em um local não típico, talvez ele não apareça inicialmente no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-161">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="fc2ab-162">Você pode estender o menu de sessão [adicionando seus próprios caminhos personalizados](#adding-your-own-powershell-paths-to-the-session-menu) conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-162">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="fc2ab-163">Há outra maneira de acessar o menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-163">There's another way to get to the session menu.</span></span> <span data-ttu-id="fc2ab-164">Quando um arquivo do PowerShell é aberto no editor, um número de versão em verde aparece no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-164">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="fc2ab-165">Clicar nesse número de versão levará ao menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-165">Clicking this version number will bring you to the session menu.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="fc2ab-166">Adição dos seus caminhos do PowerShell ao menu de sessão</span><span class="sxs-lookup"><span data-stu-id="fc2ab-166">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="fc2ab-167">É possível adicionar outros caminhos executáveis do PowerShell ao menu de sessão por meio de uma configuração do VSCode.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-167">You can add other PowerShell executable paths to the session menu through a VSCode setting.</span></span>

<span data-ttu-id="fc2ab-168">Adicione um item à lista `powershell.powerShellAdditionalExePaths` ou crie a lista se ela não estiver em `settings.json`:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-168">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="fc2ab-169">Cada item precisa ter:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-169">Each item must have:</span></span>

* <span data-ttu-id="fc2ab-170">`exePath`: o caminho para o executável `pwsh` ou `powershell`.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-170">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
* <span data-ttu-id="fc2ab-171">`versionName`: o texto que aparece no menu de sessão.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-171">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="fc2ab-172">É possível definir a versão padrão do PowerShell para usar a configuração `powershell.powerShellDefaultVersion` definindo-a como o texto exibido no menu de sessão (também conhecido como `versionName` na última configuração):</span><span class="sxs-lookup"><span data-stu-id="fc2ab-172">You can set the default PowerShell version to use the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (also known as the `versionName` in the last setting):</span></span>

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

<span data-ttu-id="fc2ab-173">Depois de definir essa configuração, reinicie o VSCode ou recarregue a janela atual do VSCode na **Paleta de comandos**, digite **Developer: Reload Window**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-173">After you've configured this setting, restart VSCode or to reload the current VSCode window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="fc2ab-174">Se você abrir o menu de sessão, agora verá versões adicionais do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-174">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="fc2ab-175">Compilar o PowerShell na origem é uma ótima maneira de testar sua compilação local do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-175">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="configuration-settings-for-vscode"></a><span data-ttu-id="fc2ab-176">Definições de configuração do VSCode</span><span class="sxs-lookup"><span data-stu-id="fc2ab-176">Configuration settings for VSCode</span></span>

<span data-ttu-id="fc2ab-177">Usando as etapas no parágrafo anterior, você pode adicionar configurações no `settings.json`.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-177">By using the steps in the previous paragraph, you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="fc2ab-178">Recomendamos as seguintes definições de configuração para o VSCode:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-178">We recommend the following configuration settings for VSCode:</span></span>

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

<span data-ttu-id="fc2ab-179">Caso não queira que essas configurações afetem todos os tipos de arquivos, o VSCode também permite configurações por idioma.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-179">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="fc2ab-180">Crie uma configuração específica a um idioma colocando as configurações em um campo `[<language-name>]`.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-180">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="fc2ab-181">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-181">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="fc2ab-182">Para saber mais sobre a codificação do arquivo no VS Code, confira [Entendendo a codificação do arquivo](understanding-file-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-182">For more information about file encoding in VSCode, see [Understanding file encoding](understanding-file-encoding.md).</span></span>

## <a name="debugging-with-vscode"></a><span data-ttu-id="fc2ab-183">Depurar com o VSCode</span><span class="sxs-lookup"><span data-stu-id="fc2ab-183">Debugging with VSCode</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="fc2ab-184">Depuração sem espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="fc2ab-184">No-workspace debugging</span></span>

<span data-ttu-id="fc2ab-185">A partir da versão 1.9 do VSCode, é possível depurar scripts do PowerShell sem abrir a pasta que contém o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-185">As of VSCode version 1.9 you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span> <span data-ttu-id="fc2ab-186">Abra o arquivo de script do PowerShell usando **Arquivo > Abrir Arquivo…** , defina um ponto de interrupção em uma linha, pressione <kbd>F9</kbd> e <kbd>F5</kbd> para iniciar a depuração.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-186">Open the PowerShell script file with **File > Open File...**, set a breakpoint on a line, press <kbd>F9</kbd>, and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="fc2ab-187">Será exibido o painel de ações de depuração, que permite que você interrompa o depurador, execute em etapas, retome e pare a depuração.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-187">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="fc2ab-188">Depuração do workspace</span><span class="sxs-lookup"><span data-stu-id="fc2ab-188">Workspace debugging</span></span>

<span data-ttu-id="fc2ab-189">A depuração do workspace refere-se a depuração no contexto de uma pasta que você abriu no Visual Studio Code a partir do menu **Arquivo** usando **Abrir Pasta...** . A pasta que você abrir normalmente é a pasta do projeto do PowerShell e/ou a raiz do repositório Git.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-189">Workspace debugging refers to debugging in the context of a folder that you've opened in Visual Studio Code from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="fc2ab-190">Mesmo nesse modo, é possível iniciar a depuração de script do PowerShell selecionado no momento pressionando <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-190">Even in this mode, you can start debugging the currently selected PowerShell script by pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="fc2ab-191">No entanto, a depuração do workspace permite definir várias configurações de depuração diferentes de depurar apenas o arquivo aberto no momento.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-191">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="fc2ab-192">Por exemplo, é possível adicionar configurações para:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-192">For instance, you can add a configuration to:</span></span>

- <span data-ttu-id="fc2ab-193">Iniciar testes Pester no depurador.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-193">Launch Pester tests in the debugger.</span></span>
- <span data-ttu-id="fc2ab-194">Abrir um arquivo específico com argumentos no depurador.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-194">Launch a specific file with arguments in the debugger.</span></span>
- <span data-ttu-id="fc2ab-195">Iniciar uma sessão interativa no depurador.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-195">Launch an interactive session in the debugger.</span></span>
- <span data-ttu-id="fc2ab-196">Anexar o depurador a um processo de host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-196">Attach the debugger to a PowerShell host process.</span></span>

<span data-ttu-id="fc2ab-197">Siga estas etapas para criar o arquivo de configuração de depuração:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-197">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="fc2ab-198">Abra a exibição **Depurar** no Windows ou Linux pressionando <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-198">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="fc2ab-199">No macOS, pressione <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-199">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
  1. <span data-ttu-id="fc2ab-200">Clique no ícone de engrenagem **Configurar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-200">Click the **Configure** gear icon in the toolbar.</span></span>
  1. <span data-ttu-id="fc2ab-201">O VSCode solicitará que você **Selecionar o Ambiente**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-201">VSCode prompts you to **Select Environment**.</span></span> <span data-ttu-id="fc2ab-202">Escolha **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-202">Choose **PowerShell**.</span></span>

<span data-ttu-id="fc2ab-203">O resultado é que o VSCode cria um diretório e um arquivo `.vscode\launch.json` na raiz da sua pasta de espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-203">The result is that VSCode creates a directory and a file `.vscode\launch.json` in the root of your workspace folder.</span></span> <span data-ttu-id="fc2ab-204">A configuração de depuração é armazenada nesse local.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-204">This location is where your debug configuration is stored.</span></span> <span data-ttu-id="fc2ab-205">Se os arquivos estiverem em um repositório Git, normalmente você desejará confirmar o arquivo `launch.json`.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-205">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="fc2ab-206">O conteúdo do arquivo `launch.json` e:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-206">The contents of the `launch.json` file are:</span></span>

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

<span data-ttu-id="fc2ab-207">Esse arquivo representa os cenários comuns de depuração.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-207">This file represents the common debug scenarios.</span></span> <span data-ttu-id="fc2ab-208">Ao abrir este arquivo no editor, você vê um botão **Adicionar configuração...** .</span><span class="sxs-lookup"><span data-stu-id="fc2ab-208">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="fc2ab-209">É possível clicar nesse botão para adicionar mais configurações de depuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-209">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="fc2ab-210">Uma configuração útil a adicionar é **PowerShell: Iniciar Script**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-210">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="fc2ab-211">Com essa configuração, é possível especificar um arquivo com argumentos opcionais que devem ser iniciados sempre que você pressionar <kbd>F5</kbd>, não importa qual arquivo está ativo no momento no editor.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-211">With this configuration, you can specify a file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

<span data-ttu-id="fc2ab-212">Depois que a configuração de depuração for estabelecida, você poderá selecionar qual configuração deseja usar durante uma sessão de depuração.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-212">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="fc2ab-213">Selecione uma configuração na lista suspensa de configuração de depuração, na barra de ferramentas da exibição **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="fc2ab-213">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

<span data-ttu-id="fc2ab-214">Há alguns blogs que podem ser úteis para você começar a usar a extensão do PowerShell para o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="fc2ab-214">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code:</span></span>

- <span data-ttu-id="fc2ab-215">[Extensão do PowerShell][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-215">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="fc2ab-216">[Gravar e depurar scripts do PowerShell no Visual Studio Code][debug]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-216">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="fc2ab-217">[Diretrizes sobre depuração no Visual Studio Code][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-217">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="fc2ab-218">[Depuração do PowerShell no Visual Studio Code][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-218">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="fc2ab-219">[Introdução ao desenvolvimento do PowerShell no Visual Studio Code][getting-started]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-219">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="fc2ab-220">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-220">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="fc2ab-221">[Recursos de edição do Visual Studio Code para desenvolvimento do PowerShell – parte 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-221">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="fc2ab-222">[Depuração de script do PowerShell no Visual Studio Code– parte 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-222">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="fc2ab-223">[Depuração de script do PowerShell no Visual Studio Code– parte 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="fc2ab-223">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

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

## <a name="powershell-extension-for-vscode"></a><span data-ttu-id="fc2ab-224">Extensão do PowerShell para VSCode</span><span class="sxs-lookup"><span data-stu-id="fc2ab-224">PowerShell Extension for VSCode</span></span>

<span data-ttu-id="fc2ab-225">O código-fonte da extensão do PowerShell pode ser encontrado no [GitHub](https://github.com/PowerShell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="fc2ab-225">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>
