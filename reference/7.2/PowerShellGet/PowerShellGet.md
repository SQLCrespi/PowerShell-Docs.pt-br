---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 0d4e5e26184558055a17f99bd5321aaf3f3789f7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99596597"
---
# <span data-ttu-id="568a5-102">Módulo PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="568a5-102">PowerShellGet Module</span></span>

## <span data-ttu-id="568a5-103">Descrição</span><span class="sxs-lookup"><span data-stu-id="568a5-103">Description</span></span>

<span data-ttu-id="568a5-104">O PowerShellGet é um módulo com comandos para descobrir, instalar, atualizar e publicar artefatos do PowerShell, como módulos, recursos de DSC, recursos de função e scripts.</span><span class="sxs-lookup"><span data-stu-id="568a5-104">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="568a5-105">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="568a5-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="568a5-106">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="568a5-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="568a5-107">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="568a5-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="568a5-108">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="568a5-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="568a5-109">Cmdlets do PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="568a5-109">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="568a5-110">Find-Command</span><span class="sxs-lookup"><span data-stu-id="568a5-110">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="568a5-111">Localiza comandos do PowerShell em módulos.</span><span class="sxs-lookup"><span data-stu-id="568a5-111">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="568a5-112">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="568a5-112">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="568a5-113">Localiza recursos de DSC (configuração de estado desejado).</span><span class="sxs-lookup"><span data-stu-id="568a5-113">Finds Desired State Configuration (DSC) resources.</span></span>

### [<span data-ttu-id="568a5-114">Find-Module</span><span class="sxs-lookup"><span data-stu-id="568a5-114">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="568a5-115">Localiza módulos em um repositório que corresponde aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="568a5-115">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="568a5-116">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="568a5-116">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="568a5-117">Localiza capacidades de função em módulos.</span><span class="sxs-lookup"><span data-stu-id="568a5-117">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="568a5-118">Find-Script</span><span class="sxs-lookup"><span data-stu-id="568a5-118">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="568a5-119">Localiza um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-119">Finds a script.</span></span>

### [<span data-ttu-id="568a5-120">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="568a5-120">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="568a5-121">Obtém uma lista de módulos no computador que foram instalados pelo PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="568a5-121">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="568a5-122">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="568a5-122">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="568a5-123">Obtém um script instalado.</span><span class="sxs-lookup"><span data-stu-id="568a5-123">Gets an installed script.</span></span>

### [<span data-ttu-id="568a5-124">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="568a5-124">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="568a5-125">Obtém repositórios do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="568a5-125">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="568a5-126">Install-Module</span><span class="sxs-lookup"><span data-stu-id="568a5-126">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="568a5-127">Baixa um ou mais módulos de um repositório e os instala no computador local.</span><span class="sxs-lookup"><span data-stu-id="568a5-127">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="568a5-128">Install-Script</span><span class="sxs-lookup"><span data-stu-id="568a5-128">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="568a5-129">Instala um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-129">Installs a script.</span></span>

### [<span data-ttu-id="568a5-130">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="568a5-130">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="568a5-131">Cria um arquivo de script com metadados.</span><span class="sxs-lookup"><span data-stu-id="568a5-131">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="568a5-132">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="568a5-132">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="568a5-133">Publica um módulo especificado do computador local em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="568a5-133">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="568a5-134">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="568a5-134">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="568a5-135">Publica um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-135">Publishes a script.</span></span>

### [<span data-ttu-id="568a5-136">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="568a5-136">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="568a5-137">Registra um repositório do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="568a5-137">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="568a5-138">Save-Module</span><span class="sxs-lookup"><span data-stu-id="568a5-138">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="568a5-139">Salva um módulo e suas dependências no computador local, mas não instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="568a5-139">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="568a5-140">Save-Script</span><span class="sxs-lookup"><span data-stu-id="568a5-140">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="568a5-141">Salva um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-141">Saves a script.</span></span>

### [<span data-ttu-id="568a5-142">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="568a5-142">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="568a5-143">Define valores para um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="568a5-143">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="568a5-144">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="568a5-144">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="568a5-145">Valida um bloco de comentário para um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-145">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="568a5-146">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="568a5-146">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="568a5-147">Desinstala um módulo.</span><span class="sxs-lookup"><span data-stu-id="568a5-147">Uninstalls a module.</span></span>

### [<span data-ttu-id="568a5-148">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="568a5-148">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="568a5-149">Desinstala um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-149">Uninstalls a script.</span></span>

### [<span data-ttu-id="568a5-150">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="568a5-150">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="568a5-151">Cancela o registro de um repositório.</span><span class="sxs-lookup"><span data-stu-id="568a5-151">Unregisters a repository.</span></span>

### [<span data-ttu-id="568a5-152">Update-Module</span><span class="sxs-lookup"><span data-stu-id="568a5-152">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="568a5-153">Baixa e instala a versão mais recente dos módulos especificados de uma galeria online para o computador local.</span><span class="sxs-lookup"><span data-stu-id="568a5-153">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="568a5-154">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="568a5-154">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="568a5-155">Atualiza um arquivo de manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="568a5-155">Updates a module manifest file.</span></span>

### [<span data-ttu-id="568a5-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="568a5-156">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="568a5-157">Atualiza um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-157">Updates a script.</span></span>

### [<span data-ttu-id="568a5-158">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="568a5-158">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="568a5-159">Atualiza informações de um script.</span><span class="sxs-lookup"><span data-stu-id="568a5-159">Updates information for a script.</span></span>
