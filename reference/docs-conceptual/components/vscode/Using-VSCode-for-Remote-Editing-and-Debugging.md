---
title: Usando o Visual Studio Code para edição e depuração remotas
description: Usando o Visual Studio Code para edição e depuração remotas
ms.date: 08/06/2018
ms.openlocfilehash: fbc1ee3556e822b4afb2b37111d0688dc89fdab3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086656"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="e5334-103">Usando o Visual Studio Code para edição e depuração remotas</span><span class="sxs-lookup"><span data-stu-id="e5334-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="e5334-104">Para aqueles que se familiarizaram com o ISE, talvez vocês se lembrem que podiam executar `psedit file.ps1` no console integrado para abrir arquivos locais ou remotos diretamente no ISE.</span><span class="sxs-lookup"><span data-stu-id="e5334-104">For those of you that were familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="e5334-105">Como podemos ver, esse recurso também está disponível na extensão do PowerShell para VSCode.</span><span class="sxs-lookup"><span data-stu-id="e5334-105">As it turns out, this feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="e5334-106">Este guia mostrará como fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="e5334-106">This guide will show you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e5334-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e5334-107">Prerequisites</span></span>

<span data-ttu-id="e5334-108">Este guia pressupõe que você tenha:</span><span class="sxs-lookup"><span data-stu-id="e5334-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="e5334-109">Um recurso remoto (p.ex.: uma VM, um contêiner) ao qual você tenha acesso</span><span class="sxs-lookup"><span data-stu-id="e5334-109">a remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="e5334-110">O PowerShell em execução nesse recurso e no computador host</span><span class="sxs-lookup"><span data-stu-id="e5334-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="e5334-111">VSCode e a extensão do PowerShell para VSCode</span><span class="sxs-lookup"><span data-stu-id="e5334-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="e5334-112">Esse recurso funciona no Windows PowerShell e no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="e5334-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="e5334-113">Esse recurso também funciona ao se conectar a um computador remoto via WinRM, PowerShell Direct ou SSH.</span><span class="sxs-lookup"><span data-stu-id="e5334-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="e5334-114">Se você quer usar o SSH, mas está usando o Windows, consulte a [versão Win32 do SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span><span class="sxs-lookup"><span data-stu-id="e5334-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

## <a name="lets-go"></a><span data-ttu-id="e5334-115">Vamos lá</span><span class="sxs-lookup"><span data-stu-id="e5334-115">Let's go</span></span>

<span data-ttu-id="e5334-116">Nesta seção, vou detalhar a edição e a depuração remotas de uma VM Ubuntu em execução no Azure pelo meu MacBook Pro.</span><span class="sxs-lookup"><span data-stu-id="e5334-116">In this section, I'll walk through remote editing and debugging from my MacBook Pro, to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="e5334-117">Posso não estar usando o Windows, mas **o processo é idêntico**.</span><span class="sxs-lookup"><span data-stu-id="e5334-117">I might not be using Windows, but **the process is identical**.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="e5334-118">Edição de arquivo local com o Open-EditorFile</span><span class="sxs-lookup"><span data-stu-id="e5334-118">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="e5334-119">Com a extensão do PowerShell para VSCode iniciada e o Console Integrado do PowerShell aberto, podemos digitar `Open-EditorFile foo.ps1` ou `psedit foo.ps1` para abrir o arquivo foo.ps1 local diretamente no editor.</span><span class="sxs-lookup"><span data-stu-id="e5334-119">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![O arquivo foo.ps1 no Open-EditorFile funciona localmente](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> <span data-ttu-id="e5334-121">foo.ps1 já deve existir.</span><span class="sxs-lookup"><span data-stu-id="e5334-121">foo.ps1 must already exist.</span></span>

<span data-ttu-id="e5334-122">A partir daí, podemos:</span><span class="sxs-lookup"><span data-stu-id="e5334-122">From there, we can:</span></span>

<span data-ttu-id="e5334-123">adicionar pontos de interrupção à medianiz ![adicionando ponto de interrupção à medianiz](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span><span class="sxs-lookup"><span data-stu-id="e5334-123">add breakpoints to the gutter ![adding breakpoint to gutter](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span></span>

<span data-ttu-id="e5334-124">e pressionar F5 para depurar o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5334-124">and hit F5 to debug the PowerShell script.</span></span>
<span data-ttu-id="e5334-125">![depurando o script local do PowerShell](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span><span class="sxs-lookup"><span data-stu-id="e5334-125">![debugging the PowerShell local script](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span></span>

<span data-ttu-id="e5334-126">Durante a depuração, você pode interagir com o console de depuração, ver as variáveis no escopo à esquerda e todas as outras ferramentas de depuração padrão.</span><span class="sxs-lookup"><span data-stu-id="e5334-126">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="e5334-127">Edição de arquivo remoto com o Open-EditorFile</span><span class="sxs-lookup"><span data-stu-id="e5334-127">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="e5334-128">Agora, vamos abordar a edição e a depuração de arquivo remoto.</span><span class="sxs-lookup"><span data-stu-id="e5334-128">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="e5334-129">As etapas são praticamente as mesmas, com exceção de um pequeno detalhe: precisamos informar nossa sessão do PowerShell ao servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="e5334-129">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="e5334-130">Há um cmdlet para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="e5334-130">There's a cmdlet for to do so.</span></span> <span data-ttu-id="e5334-131">Ele se chama `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="e5334-131">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="e5334-132">A explicação básica do cmdlet é esta:</span><span class="sxs-lookup"><span data-stu-id="e5334-132">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="e5334-133">`Enter-PSSession -ComputerName foo` inicia uma sessão via WinRM</span><span class="sxs-lookup"><span data-stu-id="e5334-133">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="e5334-134">`Enter-PSSession -ContainerId foo` e `Enter-PSSession -VmId foo` iniciam uma sessão via PowerShell Direct</span><span class="sxs-lookup"><span data-stu-id="e5334-134">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="e5334-135">`Enter-PSSession -HostName foo` inicia uma sessão via SSH</span><span class="sxs-lookup"><span data-stu-id="e5334-135">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="e5334-136">Para saber mais sobre `Enter-PSSession`, confira os documentos [aqui](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="e5334-136">For more info on `Enter-PSSession`, check out the docs [here](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span></span>

<span data-ttu-id="e5334-137">Usarei SSH para a comunicação remota, pois vou passar de um macOS para uma VM Ubuntu no Azure.</span><span class="sxs-lookup"><span data-stu-id="e5334-137">I'll be using SSH for remoting since I'm going from macOS to an Ubuntu VM in Azure.</span></span>

<span data-ttu-id="e5334-138">Em primeiro lugar, no Console Integrado, vamos executar nosso Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="e5334-138">First, in the Integrated Console, let's run our Enter-PSSession.</span></span> <span data-ttu-id="e5334-139">Você saberá que está na sessão porque `[something]` será mostrado à esquerda do seu prompt.</span><span class="sxs-lookup"><span data-stu-id="e5334-139">You'll know that you're in the session because `[something]` will show up to the left of your prompt.</span></span>

![A chamada a Enter-PSSession](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

<span data-ttu-id="e5334-141">Nela, podemos executar as mesmas etapas como se estivéssemos editando um script local.</span><span class="sxs-lookup"><span data-stu-id="e5334-141">From there, we can do the exact steps as if we were editing a local script.</span></span>

1. <span data-ttu-id="e5334-142">Execute `Open-EditorFile test.ps1` ou `psedit test.ps1` para abrir o arquivo remoto `test.ps1` ![O arquivo test.ps1 do Open-EditorFile](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span><span class="sxs-lookup"><span data-stu-id="e5334-142">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file ![Open-EditorFile the test.ps1 file](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span></span>
2. <span data-ttu-id="e5334-143">Edite os pontos de interrupção do arquivo/conjunto</span><span class="sxs-lookup"><span data-stu-id="e5334-143">Edit the file/set breakpoints</span></span> ![editar e definir pontos de interrupção](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. <span data-ttu-id="e5334-145">Comece a depurar (F5) o arquivo remoto</span><span class="sxs-lookup"><span data-stu-id="e5334-145">Start debugging (F5) the remote file</span></span>

![depurando o arquivo remoto](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

<span data-ttu-id="e5334-147">E isso é tudo!</span><span class="sxs-lookup"><span data-stu-id="e5334-147">That's all there's to it!</span></span> <span data-ttu-id="e5334-148">Esperamos que este guia tenha ajudado a esclarecer quaisquer dúvidas sobre a depuração e edição remotas do PowerShell no VSCode.</span><span class="sxs-lookup"><span data-stu-id="e5334-148">We hope that this guide helped clear up any questions about remote debugging and editing PowerShell in VSCode.</span></span>

<span data-ttu-id="e5334-149">Em caso de problemas, fique à vontade para abrir ocorrências [no repositório GitHub](http://github.com/powershell/vscode-powershell).</span><span class="sxs-lookup"><span data-stu-id="e5334-149">If you have any problems, feel free to open issues [on the GitHub repo](http://github.com/powershell/vscode-powershell).</span></span>
