---
title: Usando o Visual Studio Code para edição e depuração remotas
description: Usando o Visual Studio Code para edição e depuração remotas
ms.date: 06/13/2019
ms.openlocfilehash: 5ce7f575d90ff47fd6b8a0a2b567e972ec3a9fef
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809272"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="56775-103">Usando o Visual Studio Code para edição e depuração remotas</span><span class="sxs-lookup"><span data-stu-id="56775-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="56775-104">Para aqueles que se familiarizaram com o ISE, talvez se lembrem que podiam executar `psedit file.ps1` no console integrado para abrir arquivos locais ou remotos diretamente no ISE.</span><span class="sxs-lookup"><span data-stu-id="56775-104">For those of you that are familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="56775-105">Esse recurso também está disponível na extensão do PowerShell para VSCode.</span><span class="sxs-lookup"><span data-stu-id="56775-105">This feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="56775-106">Este guia mostra como fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="56775-106">This guide shows you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56775-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="56775-107">Prerequisites</span></span>

<span data-ttu-id="56775-108">Este guia pressupõe que você tenha:</span><span class="sxs-lookup"><span data-stu-id="56775-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="56775-109">Um recurso remoto (p.ex.: uma VM, um contêiner) ao qual você tenha acesso</span><span class="sxs-lookup"><span data-stu-id="56775-109">A remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="56775-110">O PowerShell em execução nesse recurso e no computador host</span><span class="sxs-lookup"><span data-stu-id="56775-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="56775-111">VSCode e a extensão do PowerShell para VSCode</span><span class="sxs-lookup"><span data-stu-id="56775-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="56775-112">Esse recurso funciona no Windows PowerShell e no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="56775-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="56775-113">Esse recurso também funciona ao se conectar a um computador remoto via WinRM, PowerShell Direct ou SSH.</span><span class="sxs-lookup"><span data-stu-id="56775-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="56775-114">Se você quer usar o SSH, mas está usando o Windows, consulte a [versão Win32 do SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span><span class="sxs-lookup"><span data-stu-id="56775-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56775-115">Os comandos `Open-EditorFile` e `psedit` funcionam somente no **Console integrado do PowerShell** criado pela extensão do PowerShell para VSCode.</span><span class="sxs-lookup"><span data-stu-id="56775-115">The `Open-EditorFile` and `psedit` commands only work in the **PowerShell Integrated Console** created by the PowerShell extension for VSCode.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="56775-116">Exemplos de uso</span><span class="sxs-lookup"><span data-stu-id="56775-116">Usage examples</span></span>

<span data-ttu-id="56775-117">Esses exemplos mostram a edição e a depuração remotas de uma VM Ubuntu em execução no Azure por um MacBook Pro.</span><span class="sxs-lookup"><span data-stu-id="56775-117">These examples show remote editing and debugging from a MacBook Pro to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="56775-118">O processo é idêntico no Windows.</span><span class="sxs-lookup"><span data-stu-id="56775-118">The process is identical on Windows.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="56775-119">Edição de arquivo local com o Open-EditorFile</span><span class="sxs-lookup"><span data-stu-id="56775-119">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="56775-120">Com a extensão do PowerShell para VSCode iniciada e o Console Integrado do PowerShell aberto, podemos digitar `Open-EditorFile foo.ps1` ou `psedit foo.ps1` para abrir o arquivo foo.ps1 local diretamente no editor.</span><span class="sxs-lookup"><span data-stu-id="56775-120">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![O arquivo foo.ps1 no Open-EditorFile funciona localmente](media/Using-VSCode-for-Remote-Editing-and-Debugging/1-open-local-file.png)

>[!NOTE]
> <span data-ttu-id="56775-122">O arquivo `foo.ps1` já deve existir.</span><span class="sxs-lookup"><span data-stu-id="56775-122">The file `foo.ps1` must already exist.</span></span>

<span data-ttu-id="56775-123">A partir daí, podemos:</span><span class="sxs-lookup"><span data-stu-id="56775-123">From there, we can:</span></span>

- <span data-ttu-id="56775-124">Adicionar pontos de interrupção à medianiz</span><span class="sxs-lookup"><span data-stu-id="56775-124">Add breakpoints to the gutter</span></span>

  ![adicionando pontos de interrupção à medianiz](media/Using-VSCode-for-Remote-Editing-and-Debugging/2-adding-breakpoint-gutter.png)

- <span data-ttu-id="56775-126">Pressione F5 para depurar o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56775-126">Hit F5 to debug the PowerShell script.</span></span>

  ![depurando o script local do PowerShell](media/Using-VSCode-for-Remote-Editing-and-Debugging/3-local-debug.png)

<span data-ttu-id="56775-128">Durante a depuração, você pode interagir com o console de depuração, ver as variáveis no escopo à esquerda e todas as outras ferramentas de depuração padrão.</span><span class="sxs-lookup"><span data-stu-id="56775-128">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="56775-129">Edição de arquivo remoto com o Open-EditorFile</span><span class="sxs-lookup"><span data-stu-id="56775-129">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="56775-130">Agora, vamos abordar a edição e a depuração de arquivo remoto.</span><span class="sxs-lookup"><span data-stu-id="56775-130">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="56775-131">As etapas são praticamente as mesmas, com exceção de um pequeno detalhe: precisamos informar nossa sessão do PowerShell ao servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="56775-131">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="56775-132">Há um cmdlet para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="56775-132">There's a cmdlet for to do so.</span></span> <span data-ttu-id="56775-133">Ele se chama `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="56775-133">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="56775-134">A explicação básica do cmdlet é esta:</span><span class="sxs-lookup"><span data-stu-id="56775-134">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="56775-135">`Enter-PSSession -ComputerName foo` inicia uma sessão via WinRM</span><span class="sxs-lookup"><span data-stu-id="56775-135">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="56775-136">`Enter-PSSession -ContainerId foo` e `Enter-PSSession -VmId foo` iniciam uma sessão via PowerShell Direct</span><span class="sxs-lookup"><span data-stu-id="56775-136">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="56775-137">`Enter-PSSession -HostName foo` inicia uma sessão via SSH</span><span class="sxs-lookup"><span data-stu-id="56775-137">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="56775-138">Para saber mais, veja a documentação para o [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span><span class="sxs-lookup"><span data-stu-id="56775-138">For more information, see the documentation for [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span></span>

<span data-ttu-id="56775-139">Como estamos passando de um macOS para uma VM Ubuntu no Azure, vamos usar SSH para a comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="56775-139">Since we are going from macOS to an Ubuntu VM in Azure, we are using SSH for remoting.</span></span>

<span data-ttu-id="56775-140">Primeiro, no Console Integrado, execute `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="56775-140">First, in the Integrated Console, run `Enter-PSSession`.</span></span> <span data-ttu-id="56775-141">Você estará conectado à sessão remota quando o `[<hostname>]` aparecer à esquerda de seu prompt.</span><span class="sxs-lookup"><span data-stu-id="56775-141">You're connected to the remote session when `[<hostname>]` shows up to the left of your prompt.</span></span>

![A chamada a Enter-PSSession](media/Using-VSCode-for-Remote-Editing-and-Debugging/4-enter-pssession.png)

<span data-ttu-id="56775-143">Agora podemos executar as mesmas etapas como se estivéssemos editando um script local.</span><span class="sxs-lookup"><span data-stu-id="56775-143">Now, we can do the same steps as if we are editing a local script.</span></span>

1. <span data-ttu-id="56775-144">Execute `Open-EditorFile test.ps1` ou `psedit test.ps1` para abrir o arquivo `test.ps1` remoto</span><span class="sxs-lookup"><span data-stu-id="56775-144">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file</span></span>

  ![Abrir o arquivo test.ps1 no EditorFile](media/Using-VSCode-for-Remote-Editing-and-Debugging/5-open-remote-file.png)

1. <span data-ttu-id="56775-146">Edite os pontos de interrupção do arquivo/conjunto</span><span class="sxs-lookup"><span data-stu-id="56775-146">Edit the file/set breakpoints</span></span>

   ![editar e definir pontos de interrupção](media/Using-VSCode-for-Remote-Editing-and-Debugging/6-set-breakpoints.png)

1. <span data-ttu-id="56775-148">Comece a depurar (F5) o arquivo remoto</span><span class="sxs-lookup"><span data-stu-id="56775-148">Start debugging (F5) the remote file</span></span>

   ![depurando o arquivo remoto](media/Using-VSCode-for-Remote-Editing-and-Debugging/7-start-debugging.png)

<span data-ttu-id="56775-150">Em caso de problemas, você pode abrir ocorrências [no repositório GitHub](https://github.com/powershell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="56775-150">If you have any problems, you can open issues in the [GitHub repo](https://github.com/powershell/vscode-powershell).</span></span>
