---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Melhorias na depuração de script do PowerShell
ms.openlocfilehash: f1771a451ba671da2371fcfc95374e6131573ddc
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147806"
---
# <a name="improvements-in-powershell-script-debugging"></a><span data-ttu-id="95eb3-103">Melhorias na depuração de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="95eb3-103">Improvements in PowerShell Script Debugging</span></span>

<span data-ttu-id="95eb3-104">O PowerShell 5.0 inclui várias melhorias para aprimorar a experiência de depuração.</span><span class="sxs-lookup"><span data-stu-id="95eb3-104">PowerShell 5.0 includes several improvements that enhance the debugging experience.</span></span>

## <a name="break-all"></a><span data-ttu-id="95eb3-105">Interromper Tudo</span><span class="sxs-lookup"><span data-stu-id="95eb3-105">Break All</span></span>

<span data-ttu-id="95eb3-106">O console do PowerShell e o ISE do PowerShell agora permitem interromper o depurador para executar scripts.</span><span class="sxs-lookup"><span data-stu-id="95eb3-106">The PowerShell console and PowerShell ISE now allow you to break into the debugger for running scripts.</span></span> <span data-ttu-id="95eb3-107">Isso funciona em sessões locais e remotas.</span><span class="sxs-lookup"><span data-stu-id="95eb3-107">This works in both local and remote sessions.</span></span>

<span data-ttu-id="95eb3-108">No console, pressione <kbd>Ctrl</kbd>+<kbd>Break</kbd>.</span><span class="sxs-lookup"><span data-stu-id="95eb3-108">In the console, press <kbd>Ctrl</kbd>+<kbd>Break</kbd>.</span></span>

<span data-ttu-id="95eb3-109">No ISE, pressione <kbd>Ctrl</kbd>+<kbd>B</kbd> ou use o comando de menu **Depurar -> Interromper Tudo**.</span><span class="sxs-lookup"><span data-stu-id="95eb3-109">In ISE, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, or use the **Debug -> Break All** menu command.</span></span>

## <a name="remote-debugging-and-remote-file-editing-in-powershell-ise"></a><span data-ttu-id="95eb3-110">Depuração remota e edição de arquivos remota no ISE do PowerShell</span><span class="sxs-lookup"><span data-stu-id="95eb3-110">Remote debugging and remote file editing in PowerShell ISE</span></span>

<span data-ttu-id="95eb3-111">O ISE do PowerShell agora permite abrir e editar arquivos em uma sessão remota com a execução do comando PSEdit.</span><span class="sxs-lookup"><span data-stu-id="95eb3-111">PowerShell ISE now lets you open and edit files in a remote session by running the PSEdit command.</span></span>
<span data-ttu-id="95eb3-112">Por exemplo, é possível abrir um arquivo para edição desde a linha de comando em uma sessão remota da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="95eb3-112">For example, you can open a file for editing from the command line in a remote session as follows:</span></span>

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

<span data-ttu-id="95eb3-113">Além disso, agora é possível editar e salvar alterações em um arquivo remoto aberto automaticamente no ISE do PowerShell ao atingir um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="95eb3-113">In addition, you can now edit and save changes in a remote file that is automatically opened in PowerShell ISE when you hit a breakpoint.</span></span> <span data-ttu-id="95eb3-114">Agora, você pode depurar um arquivo de script que está em execução em um computador remoto, editar o arquivo para corrigir um erro e executar novamente o script modificado.</span><span class="sxs-lookup"><span data-stu-id="95eb3-114">Now, you can debug a script file that is running on a remote computer, edit the file to fix an error, and then rerun the modified script.</span></span>

## <a name="advanced-script-debugging"></a><span data-ttu-id="95eb3-115">Depuração de script avançada</span><span class="sxs-lookup"><span data-stu-id="95eb3-115">Advanced Script Debugging</span></span>

<span data-ttu-id="95eb3-116">Há recursos de depuração novos e avançados que possibilitam anexar a qualquer processo de computador local que tenha carregado o PowerShell e depurar runspaces arbitrários no processo.</span><span class="sxs-lookup"><span data-stu-id="95eb3-116">There are new, advanced debugging features that let you attach to any local computer process that has loaded PowerShell, and debug arbitrary runspaces in that process.</span></span>

### <a name="runspace-debugging"></a><span data-ttu-id="95eb3-117">Depuração de runspaces</span><span class="sxs-lookup"><span data-stu-id="95eb3-117">Runspace Debugging</span></span>

<span data-ttu-id="95eb3-118">Foram adicionados novos cmdlets que permitem listar os runspaces atuais em um processo e anexar o console do PowerShell ou o depurador do ISE do PowerShell a esse runspace para a depuração de scripts:</span><span class="sxs-lookup"><span data-stu-id="95eb3-118">New cmdlets have been added that let you list current runspaces in a process, and attach the PowerShell console or PowerShell ISE debugger to that runspace for script debugging:</span></span>

- <span data-ttu-id="95eb3-119">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="95eb3-119">Get-Runspace</span></span>
- <span data-ttu-id="95eb3-120">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="95eb3-120">Debug-Runspace</span></span>
- <span data-ttu-id="95eb3-121">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="95eb3-121">Enable-RunspaceDebug</span></span>
- <span data-ttu-id="95eb3-122">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="95eb3-122">Disable-RunspaceDebug</span></span>
- <span data-ttu-id="95eb3-123">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="95eb3-123">Get-RunspaceDebug</span></span>

### <a name="attach-to-process-hosting-powershell"></a><span data-ttu-id="95eb3-124">Anexar a um processo que hospeda o PowerShell</span><span class="sxs-lookup"><span data-stu-id="95eb3-124">Attach to Process hosting PowerShell</span></span>

<span data-ttu-id="95eb3-125">Agora é possível anexar a qualquer processo de computador que tenha o PowerShell carregado.</span><span class="sxs-lookup"><span data-stu-id="95eb3-125">You can now attach to any computer process that has PowerShell loaded.</span></span> <span data-ttu-id="95eb3-126">Você pode fazer isso entrando em uma sessão interativa com o processo de host.</span><span class="sxs-lookup"><span data-stu-id="95eb3-126">You do this by entering into an interactive session with the host process.</span></span> <span data-ttu-id="95eb3-127">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="95eb3-127">For more information, see:</span></span>

- [<span data-ttu-id="95eb3-128">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="95eb3-128">Enter-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Enter-PSHostProcess)
- [<span data-ttu-id="95eb3-129">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="95eb3-129">Exit-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Exit-PSHostProcess)
