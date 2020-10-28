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
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a>Como usar o Visual Studio Code para depurar cmdlets compilados

Este guia mostra como depurar interativamente o código-fonte em C# para um módulo do PowerShell compilado usando o VS Code (Visual Studio Code) e a extensão C#.

É presumida alguma familiaridade com o depurador do Visual Studio Code.

- Para obter uma introdução geral ao depurador do VS Code, confira [Como depurar no Visual Studio Code][].

- Para obter exemplos de depuração de arquivos de script e módulos do PowerShell, confira [Como usar o Visual Studio Code para edição e depuração remotas][].

Este guia pressupõe que você leu e seguiu as instruções no guia [Como escrever módulos portáteis][].

## <a name="creating-a-build-task"></a>Como criar uma tarefa de build

Crie seu projeto automaticamente antes de iniciar uma sessão de depuração. O rebuild garante que você depure a versão mais recente do código.

Configurar uma tarefa de build:

1. Na **Paleta de Comandos** , execute o comando **Configurar Tarefa de Build Padrão** .

   ![Executar Configurar Tarefa de Build Padrão](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. Na caixa de diálogo **Selecionar uma tarefa para configurar** , escolha **Criar arquivo tasks.json usando o modelo** .

1. Na caixa de diálogo **Selecionar um Modelo de Tarefa** , escolha **.NET Core** .

Um novo arquivo `tasks.json` será criado, caso ainda não exista um.

Para testar sua tarefa de build:

1. Na **Paleta de Comandos** , execute o comando **Executar Tarefa de Build** .

1. No diálogo **Selecionar a tarefa de build a executar** , escolha **build** .

### <a name="information-about-dll-files-being-locked"></a>Informações sobre arquivos DLL sendo bloqueados

Por padrão, um build bem-sucedido não mostra a saída no painel do terminal. Se for exibida a saída com o texto **O arquivo de projeto não existe** , edite o arquivo `tasks.json`. Inclua o caminho explícito para o projeto C# expresso como `"${workspaceFolder}/myModule"`. Neste exemplo, `myModule` é o nome da pasta do projeto. Essa entrada deve ir depois da entrada `build` na lista `args` da seguinte maneira:

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

Durante a depuração, a DLL do módulo é importada para a sessão do PowerShell no terminal do VS Code. A DLL fica bloqueada. A seguinte mensagem é exibida quando você executa a tarefa de build sem fechar a sessão de terminal:

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

As sessões de terminal devem ser fechadas antes de recompilar.

## <a name="setting-up-the-debugger"></a>Como configurar o depurador

Para depurar o cmdlet do PowerShell, você precisa definir uma configuração de inicialização personalizada. Essa configuração é usada para:

- Criar seu código-fonte
- Iniciar o PowerShell com seu módulo carregado
- Deixar o PowerShell aberto no painel de terminal

Quando você invoca o cmdlet na sessão de terminal, o depurador é interrompido em qualquer ponto de interrupção definido no código-fonte.

### <a name="configuring-launchjson-for-powershell-core"></a>Como configurar o launch.json para o PowerShell Core

1. Instalar a extensão [C# para Visual Studio Code][]

1. No painel Depuração, adicione uma configuração de depuração

1. Na caixa de diálogo `Select environment`, escolha `.NET Core`

1. O arquivo `launch.json` é aberto no editor. Com o cursor dentro da matriz `configurations`, você verá o seletor `configuration`. Se você não vir essa lista, selecione **Adicionar Configuração** .

1. Para criar uma configuração de depuração padrão, selecione **Iniciar Aplicativo de Console do .NET Core** :

   ![Iniciar Aplicativo de Console do .NET Core](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. Edite os campos `name`, `program`, `args` e `console` da seguinte maneira:

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

O campo `program` é usado para iniciar `pwsh` para que o cmdlet que está sendo depurado possa ser executado. O argumento `-NoExit` impede que a sessão do PowerShell saia assim que o módulo é importado.
O caminho no argumento `Import-Module` é o caminho de saída de build padrão quando você seguiu o guia [Como Escrever Módulos Portáteis][]. Se você tiver criado um manifesto de módulo (arquivo `.psd1`), use o caminho para ele em vez disso. O separador de caminho `/` funciona no Windows, Linux e macOS. Você deve usar o terminal integrado para executar os comandos do PowerShell que deseja depurar.

> [!NOTE]
> Se o depurador não parar em nenhum ponto de interrupção, procure no console de depuração do Visual Studio Code uma linha que diz:
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> Se você vir isso, adicione `"justMyCode": false` à configuração de inicialização (no mesmo nível que `"console": "integratedTerminal"`).

### <a name="configuring-launchjson-for-windows-powershell"></a>Como configurar o launch.json para o Windows PowerShell

Essa configuração de inicialização funciona para testar seus cmdlets no Windows PowerShell (`powershell.exe`).
Crie uma segunda configuração de inicialização com as seguintes alterações:

1. `name` deve ser `PowerShell cmdlets: powershell`

1. `type` deve ser `clr`

1. `program` deve ser `powershell`

   Ele deverá ser parecido com:

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

## <a name="launching-a-debugging-session"></a>Como iniciar uma sessão de depuração

Agora tudo está pronto para começar a depuração.

- Coloque um ponto de interrupção no código-fonte do cmdlet que você deseja depurar:

  ![Um ponto de interrupção aparece como um ponto vermelho na medianiz](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- Verifique se a configuração relevante de **cmdlets do PowerShell** está selecionada no menu suspenso de configuração na exibição **Depuração** :

  ![Selecionar a configuração de inicialização](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- Pressione <kbd>F5</kbd> ou clique no botão **Iniciar Depuração**

- Alterne para o painel do terminal e invoque o cmdlet:

  ![Invocar o cmdlet](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- A execução é interrompida no ponto de interrupção:

  ![As execuções são interrompidas no ponto de interrupção](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

Você pode percorrer o código-fonte, inspecionar variáveis e inspecionar a pilha de chamadas.

Para encerrar a depuração, clique em **Parar** na barra de ferramentas de depuração ou pressione <kbd>Shift</kbd>-<kbd>F5</kbd>. O shell usado para depuração é encerrado e libera o bloqueio no arquivo DLL compilado.

<!-- reference links -->
[Depurar no Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[Usando o Visual Studio Code para edição e depuração remotas]: using-vscode-for-remote-editing-and-debugging.md
[Como Escrever Módulos Portáteis]: ../writing-portable-modules.md
[C# para Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
