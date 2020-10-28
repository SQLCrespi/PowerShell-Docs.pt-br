---
ms.date: 10/19/2020
keywords: powershell,cmdlet,debug
title: Como usar o Visual Studio Code para depurar cmdlets compilados
description: Como definir uma tarefa de build e iniciar a configuração para um projeto PSModule no .NET Core
ms.openlocfilehash: b51a69110c64b386f5c3ccf2527d1e184ef89257
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501636"
---
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a><span data-ttu-id="f1d15-104">Como usar o Visual Studio Code para depurar cmdlets compilados</span><span class="sxs-lookup"><span data-stu-id="f1d15-104">Using Visual Studio Code to debug compiled cmdlets</span></span>

<span data-ttu-id="f1d15-105">Este guia mostra como depurar interativamente o código-fonte em C# para um módulo do PowerShell compilado usando o VS Code (Visual Studio Code) e a extensão C#.</span><span class="sxs-lookup"><span data-stu-id="f1d15-105">This guide shows you how to interactively debug C# source code for a compiled PowerShell module using Visual Studio Code (VS Code) and the C# extension.</span></span>

<span data-ttu-id="f1d15-106">É presumida alguma familiaridade com o depurador do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f1d15-106">Some familiarity with the Visual Studio Code debugger is assumed.</span></span>

- <span data-ttu-id="f1d15-107">Para obter uma introdução geral ao depurador do VS Code, confira [Como depurar no Visual Studio Code][].</span><span class="sxs-lookup"><span data-stu-id="f1d15-107">For a general introduction to the VS Code debugger, see [Debugging in Visual Studio Code][].</span></span>

- <span data-ttu-id="f1d15-108">Para obter exemplos de depuração de arquivos de script e módulos do PowerShell, confira [Como usar o Visual Studio Code para edição e depuração remotas][].</span><span class="sxs-lookup"><span data-stu-id="f1d15-108">For examples of debugging PowerShell script files and modules, see [Using Visual Studio Code for remote editing and debugging][].</span></span>

<span data-ttu-id="f1d15-109">Este guia pressupõe que você leu e seguiu as instruções no guia [Como escrever módulos portáteis][].</span><span class="sxs-lookup"><span data-stu-id="f1d15-109">This guide assumes you have read and followed the instructions in the [Writing Portable Modules][] guide.</span></span>

## <a name="creating-a-build-task"></a><span data-ttu-id="f1d15-110">Como criar uma tarefa de build</span><span class="sxs-lookup"><span data-stu-id="f1d15-110">Creating a build task</span></span>

<span data-ttu-id="f1d15-111">Crie seu projeto automaticamente antes de iniciar uma sessão de depuração.</span><span class="sxs-lookup"><span data-stu-id="f1d15-111">Build your project automatically before launching a debugging session.</span></span> <span data-ttu-id="f1d15-112">O rebuild garante que você depure a versão mais recente do código.</span><span class="sxs-lookup"><span data-stu-id="f1d15-112">Rebuilding ensures that you debug the latest version of your code.</span></span>

<span data-ttu-id="f1d15-113">Configurar uma tarefa de build:</span><span class="sxs-lookup"><span data-stu-id="f1d15-113">Configure a build task:</span></span>

1. <span data-ttu-id="f1d15-114">Na **Paleta de Comandos** , execute o comando **Configurar Tarefa de Build Padrão** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-114">In the **Command Palette** , run the **Configure Default Build Task** command.</span></span>

   ![Executar Configurar Tarefa de Build Padrão](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. <span data-ttu-id="f1d15-116">Na caixa de diálogo **Selecionar uma tarefa para configurar** , escolha **Criar arquivo tasks.json usando o modelo** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-116">In the **Select a task to configure** dialog, choose **Create tasks.json file from template** .</span></span>

1. <span data-ttu-id="f1d15-117">Na caixa de diálogo **Selecionar um Modelo de Tarefa** , escolha **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-117">In the **Select a Task Template** dialog, choose **.NET Core** .</span></span>

<span data-ttu-id="f1d15-118">Um novo arquivo `tasks.json` será criado, caso ainda não exista um.</span><span class="sxs-lookup"><span data-stu-id="f1d15-118">A new `tasks.json` file is created if one doesn't exist yet.</span></span>

<span data-ttu-id="f1d15-119">Para testar sua tarefa de build:</span><span class="sxs-lookup"><span data-stu-id="f1d15-119">To test your build task:</span></span>

1. <span data-ttu-id="f1d15-120">Na **Paleta de Comandos** , execute o comando **Executar Tarefa de Build** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-120">In the **Command Palette** , run the **Run Build Task** command.</span></span>

1. <span data-ttu-id="f1d15-121">No diálogo **Selecionar a tarefa de build a executar** , escolha **build** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-121">In the **Select the build task to run** dialog, choose **build** .</span></span>

### <a name="information-about-dll-files-being-locked"></a><span data-ttu-id="f1d15-122">Informações sobre arquivos DLL sendo bloqueados</span><span class="sxs-lookup"><span data-stu-id="f1d15-122">Information about DLL files being locked</span></span>

<span data-ttu-id="f1d15-123">Por padrão, um build bem-sucedido não mostra a saída no painel do terminal.</span><span class="sxs-lookup"><span data-stu-id="f1d15-123">By default, a successful build doesn't show output in the terminal pane.</span></span> <span data-ttu-id="f1d15-124">Se for exibida a saída com o texto **O arquivo de projeto não existe** , edite o arquivo `tasks.json`.</span><span class="sxs-lookup"><span data-stu-id="f1d15-124">If you see output that contains the text **Project file doesn't exist** , you should edit the `tasks.json` file.</span></span> <span data-ttu-id="f1d15-125">Inclua o caminho explícito para o projeto C# expresso como `"${workspaceFolder}/myModule"`.</span><span class="sxs-lookup"><span data-stu-id="f1d15-125">Include the explicit path to the C# project expressed as `"${workspaceFolder}/myModule"`.</span></span> <span data-ttu-id="f1d15-126">Neste exemplo, `myModule` é o nome da pasta do projeto.</span><span class="sxs-lookup"><span data-stu-id="f1d15-126">In this example, `myModule` is the name of the project folder.</span></span> <span data-ttu-id="f1d15-127">Essa entrada deve ir depois da entrada `build` na lista `args` da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f1d15-127">This entry must go after the `build` entry in the `args` list as follows:</span></span>

```json
    {
        "label": "build",
        "command": "dotnet",
        "type": "shell",
        "args": [
            "build",
            "${workspaceFolder}/myModule",
            // Ask dotnet build to generate full paths for file names.
            "/property:GenerateFullPaths=true",
            // Do not generate summary otherwise it leads to duplicate errors in Problems panel
            "/consoleloggerparameters:NoSummary",
        ],
        "group": "build",
        "presentation": {
            "reveal": "silent"
        },
        "problemMatcher": "$msCompile"
    }
```

<span data-ttu-id="f1d15-128">Durante a depuração, a DLL do módulo é importada para a sessão do PowerShell no terminal do VS Code.</span><span class="sxs-lookup"><span data-stu-id="f1d15-128">When debugging, your module DLL is imported into the PowerShell session in the VS Code terminal.</span></span> <span data-ttu-id="f1d15-129">A DLL fica bloqueada.</span><span class="sxs-lookup"><span data-stu-id="f1d15-129">The DLL becomes locked.</span></span> <span data-ttu-id="f1d15-130">A seguinte mensagem é exibida quando você executa a tarefa de build sem fechar a sessão de terminal:</span><span class="sxs-lookup"><span data-stu-id="f1d15-130">The following message is displayed when you run the build task without closing the terminal session:</span></span>

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

<span data-ttu-id="f1d15-131">As sessões de terminal devem ser fechadas antes de recompilar.</span><span class="sxs-lookup"><span data-stu-id="f1d15-131">Terminal sessions must be closed before you rebuild.</span></span>

## <a name="setting-up-the-debugger"></a><span data-ttu-id="f1d15-132">Como configurar o depurador</span><span class="sxs-lookup"><span data-stu-id="f1d15-132">Setting up the debugger</span></span>

<span data-ttu-id="f1d15-133">Para depurar o cmdlet do PowerShell, você precisa definir uma configuração de inicialização personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1d15-133">To debug the PowerShell cmdlet, you need to set up a custom launch configuration.</span></span> <span data-ttu-id="f1d15-134">Essa configuração é usada para:</span><span class="sxs-lookup"><span data-stu-id="f1d15-134">This configuration is used to:</span></span>

- <span data-ttu-id="f1d15-135">Criar seu código-fonte</span><span class="sxs-lookup"><span data-stu-id="f1d15-135">Build your source code</span></span>
- <span data-ttu-id="f1d15-136">Iniciar o PowerShell com seu módulo carregado</span><span class="sxs-lookup"><span data-stu-id="f1d15-136">Start PowerShell with your module loaded</span></span>
- <span data-ttu-id="f1d15-137">Deixar o PowerShell aberto no painel de terminal</span><span class="sxs-lookup"><span data-stu-id="f1d15-137">Leave PowerShell open in the terminal pane</span></span>

<span data-ttu-id="f1d15-138">Quando você invoca o cmdlet na sessão de terminal, o depurador é interrompido em qualquer ponto de interrupção definido no código-fonte.</span><span class="sxs-lookup"><span data-stu-id="f1d15-138">When you invoke your cmdlet in the terminal session, the debugger stops at any breakpoints set in your source code.</span></span>

### <a name="configuring-launchjson-for-powershell-core"></a><span data-ttu-id="f1d15-139">Como configurar o launch.json para o PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="f1d15-139">Configuring launch.json for PowerShell Core</span></span>

1. <span data-ttu-id="f1d15-140">Instalar a extensão [C# para Visual Studio Code][]</span><span class="sxs-lookup"><span data-stu-id="f1d15-140">Install the [C# for Visual Studio Code][] extension</span></span>

1. <span data-ttu-id="f1d15-141">No painel Depuração, adicione uma configuração de depuração</span><span class="sxs-lookup"><span data-stu-id="f1d15-141">In the Debug pane, add a debug configuration</span></span>

1. <span data-ttu-id="f1d15-142">Na caixa de diálogo `Select environment`, escolha `.NET Core`</span><span class="sxs-lookup"><span data-stu-id="f1d15-142">In the `Select environment` dialog, choose `.NET Core`</span></span>

1. <span data-ttu-id="f1d15-143">O arquivo `launch.json` é aberto no editor.</span><span class="sxs-lookup"><span data-stu-id="f1d15-143">The `launch.json` file is opened in the editor.</span></span> <span data-ttu-id="f1d15-144">Com o cursor dentro da matriz `configurations`, você verá o seletor `configuration`.</span><span class="sxs-lookup"><span data-stu-id="f1d15-144">With your cursor inside the `configurations` array, you see the `configuration` picker.</span></span> <span data-ttu-id="f1d15-145">Se você não vir essa lista, selecione **Adicionar Configuração** .</span><span class="sxs-lookup"><span data-stu-id="f1d15-145">If you don't see this list, select **Add Configuration** .</span></span>

1. <span data-ttu-id="f1d15-146">Para criar uma configuração de depuração padrão, selecione **Iniciar Aplicativo de Console do .NET Core** :</span><span class="sxs-lookup"><span data-stu-id="f1d15-146">To create a default debug configuration, select **Launch .NET Core Console App** :</span></span>

   ![Iniciar Aplicativo de Console do .NET Core](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. <span data-ttu-id="f1d15-148">Edite os campos `name`, `program`, `args` e `console` da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f1d15-148">Edit the `name`, `program`, `args`, and `console` fields as follows:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: pwsh",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "pwsh",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

<span data-ttu-id="f1d15-149">O campo `program` é usado para iniciar `pwsh` para que o cmdlet que está sendo depurado possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="f1d15-149">The `program` field is used to launch `pwsh` so that the cmdlet being debugged can be run.</span></span> <span data-ttu-id="f1d15-150">O argumento `-NoExit` impede que a sessão do PowerShell saia assim que o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="f1d15-150">The `-NoExit` argument prevents the PowerShell session from exiting as soon as the module is imported.</span></span>
<span data-ttu-id="f1d15-151">O caminho no argumento `Import-Module` é o caminho de saída de build padrão quando você seguiu o guia [Como Escrever Módulos Portáteis][].</span><span class="sxs-lookup"><span data-stu-id="f1d15-151">The path in the `Import-Module` argument is the default build output path when you've followed the [Writing Portable Modules][] guide.</span></span> <span data-ttu-id="f1d15-152">Se você tiver criado um manifesto de módulo (arquivo `.psd1`), use o caminho para ele em vez disso.</span><span class="sxs-lookup"><span data-stu-id="f1d15-152">If you've created a module manifest (`.psd1` file), you should use the path to that instead.</span></span> <span data-ttu-id="f1d15-153">O separador de caminho `/` funciona no Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="f1d15-153">The `/` path separator works on Windows, Linux, and macOS.</span></span> <span data-ttu-id="f1d15-154">Você deve usar o terminal integrado para executar os comandos do PowerShell que deseja depurar.</span><span class="sxs-lookup"><span data-stu-id="f1d15-154">You must use the integrated terminal to run the PowerShell commands you want to debug.</span></span>

> [!NOTE]
> <span data-ttu-id="f1d15-155">Se o depurador não parar em nenhum ponto de interrupção, procure no console de depuração do Visual Studio Code uma linha que diz:</span><span class="sxs-lookup"><span data-stu-id="f1d15-155">If the debugger doesn't stop at any breakpoints, look in the Visual Studio Code Debug Console for a line that says:</span></span>
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> <span data-ttu-id="f1d15-156">Se você vir isso, adicione `"justMyCode": false` à configuração de inicialização (no mesmo nível que `"console": "integratedTerminal"`).</span><span class="sxs-lookup"><span data-stu-id="f1d15-156">If you see this, add `"justMyCode": false` to your launch config (at the same level as `"console": "integratedTerminal"`.</span></span>

### <a name="configuring-launchjson-for-windows-powershell"></a><span data-ttu-id="f1d15-157">Como configurar o launch.json para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1d15-157">Configuring launch.json for Windows PowerShell</span></span>

<span data-ttu-id="f1d15-158">Essa configuração de inicialização funciona para testar seus cmdlets no Windows PowerShell (`powershell.exe`).</span><span class="sxs-lookup"><span data-stu-id="f1d15-158">This launch configuration works for testing your cmdlets in Windows PowerShell (`powershell.exe`).</span></span>
<span data-ttu-id="f1d15-159">Crie uma segunda configuração de inicialização com as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="f1d15-159">Create a second launch configuration with the following changes:</span></span>

1. <span data-ttu-id="f1d15-160">`name` deve ser `PowerShell cmdlets: powershell`</span><span class="sxs-lookup"><span data-stu-id="f1d15-160">`name` should be `PowerShell cmdlets: powershell`</span></span>

1. <span data-ttu-id="f1d15-161">`type` deve ser `clr`</span><span class="sxs-lookup"><span data-stu-id="f1d15-161">`type` should be `clr`</span></span>

1. <span data-ttu-id="f1d15-162">`program` deve ser `powershell`</span><span class="sxs-lookup"><span data-stu-id="f1d15-162">`program` should be `powershell`</span></span>

   <span data-ttu-id="f1d15-163">Ele deverá ser parecido com:</span><span class="sxs-lookup"><span data-stu-id="f1d15-163">It should look like this:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: powershell",
        "type": "clr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "powershell",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

## <a name="launching-a-debugging-session"></a><span data-ttu-id="f1d15-164">Como iniciar uma sessão de depuração</span><span class="sxs-lookup"><span data-stu-id="f1d15-164">Launching a debugging session</span></span>

<span data-ttu-id="f1d15-165">Agora tudo está pronto para começar a depuração.</span><span class="sxs-lookup"><span data-stu-id="f1d15-165">Now everything is ready to begin debugging.</span></span>

- <span data-ttu-id="f1d15-166">Coloque um ponto de interrupção no código-fonte do cmdlet que você deseja depurar:</span><span class="sxs-lookup"><span data-stu-id="f1d15-166">Place a breakpoint in the source code for the cmdlet you want to debug:</span></span>

  ![Um ponto de interrupção aparece como um ponto vermelho na medianiz](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- <span data-ttu-id="f1d15-168">Verifique se a configuração relevante de **cmdlets do PowerShell** está selecionada no menu suspenso de configuração na exibição **Depuração** :</span><span class="sxs-lookup"><span data-stu-id="f1d15-168">Ensure that the relevant **PowerShell cmdlets** configuration is selected in the configuration drop-down menu in the **Debug** view:</span></span>

  ![Selecionar a configuração de inicialização](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- <span data-ttu-id="f1d15-170">Pressione <kbd>F5</kbd> ou clique no botão **Iniciar Depuração**</span><span class="sxs-lookup"><span data-stu-id="f1d15-170">Press <kbd>F5</kbd> or click on the **Start Debugging** button</span></span>

- <span data-ttu-id="f1d15-171">Alterne para o painel do terminal e invoque o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f1d15-171">Switch to the terminal pane and invoke your cmdlet:</span></span>

  ![Invocar o cmdlet](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- <span data-ttu-id="f1d15-173">A execução é interrompida no ponto de interrupção:</span><span class="sxs-lookup"><span data-stu-id="f1d15-173">Execution stops at the breakpoint:</span></span>

  ![As execuções são interrompidas no ponto de interrupção](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

<span data-ttu-id="f1d15-175">Você pode percorrer o código-fonte, inspecionar variáveis e inspecionar a pilha de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f1d15-175">You can step through the source code, inspect variables, and inspect the call stack.</span></span>

<span data-ttu-id="f1d15-176">Para encerrar a depuração, clique em **Parar** na barra de ferramentas de depuração ou pressione <kbd>Shift</kbd>-<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f1d15-176">To end debugging, click **Stop** in the debug toolbar or press <kbd>Shift</kbd>-<kbd>F5</kbd>.</span></span> <span data-ttu-id="f1d15-177">O shell usado para depuração é encerrado e libera o bloqueio no arquivo DLL compilado.</span><span class="sxs-lookup"><span data-stu-id="f1d15-177">The shell used for debugging exits and releases the lock on the compiled DLL file.</span></span>

<!-- reference links -->
[Depurar no Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[Debugging in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[Usando o Visual Studio Code para edição e depuração remotas]: using-vscode-for-remote-editing-and-debugging.md
[Using Visual Studio Code for remote editing and debugging]: using-vscode-for-remote-editing-and-debugging.md
[Como Escrever Módulos Portáteis]: ../writing-portable-modules.md
[Writing Portable Modules]: ../writing-portable-modules.md
[C# para Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
[C# for Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
