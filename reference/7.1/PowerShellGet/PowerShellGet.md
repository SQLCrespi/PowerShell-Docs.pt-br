---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell, cmdlet
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 577dc9a56da98d975b777e6cd48ecdcaafd3128d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892362"
---
# <span data-ttu-id="3c1e3-103">Módulo PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="3c1e3-103">PowerShellGet Module</span></span>

## <span data-ttu-id="3c1e3-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c1e3-104">Description</span></span>

<span data-ttu-id="3c1e3-105">O PowerShellGet é um módulo com comandos para descobrir, instalar, atualizar e publicar artefatos do PowerShell, como módulos, recursos de DSC, recursos de função e scripts.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-105">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c1e3-106">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="3c1e3-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="3c1e3-107">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="3c1e3-108">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="3c1e3-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="3c1e3-109">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="3c1e3-110">Cmdlets do PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="3c1e3-110">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="3c1e3-111">Find-Command</span><span class="sxs-lookup"><span data-stu-id="3c1e3-111">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="3c1e3-112">Localiza comandos do PowerShell em módulos.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-112">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="3c1e3-113">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="3c1e3-113">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="3c1e3-114">Localiza recursos de DSC (configuração de estado desejado).</span><span class="sxs-lookup"><span data-stu-id="3c1e3-114">Finds Desired State Configuration (DSC) resources.</span></span>

### [<span data-ttu-id="3c1e3-115">Find-Module</span><span class="sxs-lookup"><span data-stu-id="3c1e3-115">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="3c1e3-116">Localiza módulos em um repositório que corresponde aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-116">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="3c1e3-117">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="3c1e3-117">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="3c1e3-118">Localiza capacidades de função em módulos.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-118">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="3c1e3-119">Find-Script</span><span class="sxs-lookup"><span data-stu-id="3c1e3-119">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="3c1e3-120">Localiza um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-120">Finds a script.</span></span>

### [<span data-ttu-id="3c1e3-121">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="3c1e3-121">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="3c1e3-122">Obtém uma lista de módulos no computador que foram instalados pelo PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-122">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="3c1e3-123">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="3c1e3-123">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="3c1e3-124">Obtém um script instalado.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-124">Gets an installed script.</span></span>

### [<span data-ttu-id="3c1e3-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="3c1e3-125">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="3c1e3-126">Obtém repositórios do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-126">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="3c1e3-127">Install-Module</span><span class="sxs-lookup"><span data-stu-id="3c1e3-127">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="3c1e3-128">Baixa um ou mais módulos de um repositório e os instala no computador local.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-128">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="3c1e3-129">Install-Script</span><span class="sxs-lookup"><span data-stu-id="3c1e3-129">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="3c1e3-130">Instala um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-130">Installs a script.</span></span>

### [<span data-ttu-id="3c1e3-131">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="3c1e3-131">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="3c1e3-132">Cria um arquivo de script com metadados.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-132">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="3c1e3-133">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="3c1e3-133">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="3c1e3-134">Publica um módulo especificado do computador local em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-134">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="3c1e3-135">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="3c1e3-135">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="3c1e3-136">Publica um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-136">Publishes a script.</span></span>

### [<span data-ttu-id="3c1e3-137">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="3c1e3-137">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="3c1e3-138">Registra um repositório do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-138">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="3c1e3-139">Save-Module</span><span class="sxs-lookup"><span data-stu-id="3c1e3-139">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="3c1e3-140">Salva um módulo e suas dependências no computador local, mas não instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-140">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="3c1e3-141">Save-Script</span><span class="sxs-lookup"><span data-stu-id="3c1e3-141">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="3c1e3-142">Salva um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-142">Saves a script.</span></span>

### [<span data-ttu-id="3c1e3-143">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="3c1e3-143">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="3c1e3-144">Define valores para um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-144">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="3c1e3-145">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="3c1e3-145">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="3c1e3-146">Valida um bloco de comentário para um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-146">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="3c1e3-147">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="3c1e3-147">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="3c1e3-148">Desinstala um módulo.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-148">Uninstalls a module.</span></span>

### [<span data-ttu-id="3c1e3-149">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="3c1e3-149">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="3c1e3-150">Desinstala um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-150">Uninstalls a script.</span></span>

### [<span data-ttu-id="3c1e3-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="3c1e3-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="3c1e3-152">Cancela o registro de um repositório.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-152">Unregisters a repository.</span></span>

### [<span data-ttu-id="3c1e3-153">Update-Module</span><span class="sxs-lookup"><span data-stu-id="3c1e3-153">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="3c1e3-154">Baixa e instala a versão mais recente dos módulos especificados de uma galeria online para o computador local.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-154">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="3c1e3-155">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="3c1e3-155">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="3c1e3-156">Atualiza um arquivo de manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-156">Updates a module manifest file.</span></span>

### [<span data-ttu-id="3c1e3-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="3c1e3-157">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="3c1e3-158">Atualiza um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-158">Updates a script.</span></span>

### [<span data-ttu-id="3c1e3-159">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="3c1e3-159">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="3c1e3-160">Atualiza informações de um script.</span><span class="sxs-lookup"><span data-stu-id="3c1e3-160">Updates information for a script.</span></span>
