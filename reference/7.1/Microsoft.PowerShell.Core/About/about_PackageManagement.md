---
description: PackageManagement é um agregador para gerenciadores de pacotes de software.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 5af3095675015eb043ca3299f5e44b0bc7ac4aa1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196331"
---
# <a name="about-packagemanagement"></a><span data-ttu-id="8445e-104">Sobre PackageManagement</span><span class="sxs-lookup"><span data-stu-id="8445e-104">About PackageManagement</span></span>

## <a name="short-description"></a><span data-ttu-id="8445e-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="8445e-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8445e-106">PackageManagement é um agregador para gerenciadores de pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="8445e-106">PackageManagement is an aggregator for software package managers.</span></span>

## <a name="long-description"></a><span data-ttu-id="8445e-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="8445e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8445e-108">A funcionalidade de PackageManagement foi introduzida no Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="8445e-108">PackageManagement functionality was introduced in Windows PowerShell 5.0.</span></span>

<span data-ttu-id="8445e-109">O PackageManagement é uma interface unificada para sistemas de gerenciamento de pacotes de software; Você pode executar cmdlets do PackageManagement para executar tarefas de descoberta de software, instalação e inventário (SDII).</span><span class="sxs-lookup"><span data-stu-id="8445e-109">PackageManagement is a unified interface for software package management systems; you can run PackageManagement cmdlets to perform software discovery, installation, and inventory (SDII) tasks.</span></span> <span data-ttu-id="8445e-110">Independentemente da tecnologia de instalação subjacente, você pode executar os cmdlets comuns no módulo PackageManagement para pesquisar, instalar ou desinstalar pacotes; Adicionar, remover e consultar repositórios de pacotes; e executar consultas em um computador para determinar quais pacotes de software estão instalados.</span><span class="sxs-lookup"><span data-stu-id="8445e-110">Regardless of the underlying installation technology, you can run the common cmdlets in the PackageManagement module to search for, install, or uninstall packages; add, remove, and query package repositories; and run queries on a computer to determine which software packages are installed.</span></span>

<span data-ttu-id="8445e-111">O PackageManagement dá suporte a um modelo de plug-in flexível que habilita o suporte para outros sistemas de gerenciamento de pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="8445e-111">PackageManagement supports a flexible plug-in model that enables support for other software package management systems.</span></span>

<span data-ttu-id="8445e-112">O módulo PackageManagement está incluído no Windows PowerShell 5,0 e versões posteriores do PowerShell e funciona em três níveis de estrutura de gerenciamento de pacotes: provedores de pacote, origens de pacote e os próprios pacotes.</span><span class="sxs-lookup"><span data-stu-id="8445e-112">The PackageManagement module is included with Windows PowerShell 5.0 and later releases of PowerShell, and works on three levels of package management structure: package providers, package sources, and the packages themselves.</span></span> <span data-ttu-id="8445e-113">Vamos definir alguns termos:</span><span class="sxs-lookup"><span data-stu-id="8445e-113">Let us define some terms:</span></span>

- <span data-ttu-id="8445e-114">Gerenciador de pacotes: sistema de gerenciamento de pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="8445e-114">Package manager: Software package management system.</span></span> <span data-ttu-id="8445e-115">Em termos de PackageManagement, este é um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="8445e-115">In PackageManagement terms, this is a package provider.</span></span>
- <span data-ttu-id="8445e-116">Provedor de pacote: termo PackageManagement para um Gerenciador de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8445e-116">Package provider: PackageManagement term for a package manager.</span></span> <span data-ttu-id="8445e-117">Os exemplos podem incluir Windows Installer, Chocolatey e outros.</span><span class="sxs-lookup"><span data-stu-id="8445e-117">Examples can include Windows Installer, Chocolatey, and others.</span></span>
- <span data-ttu-id="8445e-118">Origem do pacote: uma URL, uma pasta local ou uma pasta de rede compartilhada que você configura provedores de pacote para usar como um repositório.</span><span class="sxs-lookup"><span data-stu-id="8445e-118">Package source: A URL, local folder, or network shared folder that you configure package providers to use as a repository.</span></span>
- <span data-ttu-id="8445e-119">Pacote: uma parte do software que um provedor de pacote gerencia e que é armazenado em uma origem de pacote específica.</span><span class="sxs-lookup"><span data-stu-id="8445e-119">Package: A piece of software that a package provider manages, and that is stored in a specific package source.</span></span>

<span data-ttu-id="8445e-120">O módulo PackageManagement inclui os cmdlets a seguir.</span><span class="sxs-lookup"><span data-stu-id="8445e-120">The PackageManagement module includes the following cmdlets.</span></span> <span data-ttu-id="8445e-121">Para obter mais informações, consulte a ajuda do [PackageManagement](/powershell/module/packagemanagement) .</span><span class="sxs-lookup"><span data-stu-id="8445e-121">For more information, see the [PackageManagement](/powershell/module/packagemanagement) help.</span></span>

- <span data-ttu-id="8445e-122">`Get-PackageProvider`: Retorna uma lista de provedores de pacote que estão conectados ao PackageManagement.</span><span class="sxs-lookup"><span data-stu-id="8445e-122">`Get-PackageProvider`: Returns a list of package providers that are  connected to PackageManagement.</span></span>
- <span data-ttu-id="8445e-123">`Get-PackageSource`: Obtém uma lista de origens de pacote que são registradas para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="8445e-123">`Get-PackageSource`: Gets a list of package sources that are registered for a package provider.</span></span>
- <span data-ttu-id="8445e-124">`Register-PackageSource`: Adiciona uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="8445e-124">`Register-PackageSource`: Adds a package source for a specified package provider.</span></span>
- <span data-ttu-id="8445e-125">`Set-PackageSource`: Define as propriedades em uma origem de pacote existente.</span><span class="sxs-lookup"><span data-stu-id="8445e-125">`Set-PackageSource`: Sets properties on an existing package source.</span></span>
- <span data-ttu-id="8445e-126">`Unregister-PackageSource`: Remove uma origem de pacote registrada.</span><span class="sxs-lookup"><span data-stu-id="8445e-126">`Unregister-PackageSource`: Removes a registered package source.</span></span>
- <span data-ttu-id="8445e-127">`Get-Package`: Retorna uma lista de pacotes de software instalados.</span><span class="sxs-lookup"><span data-stu-id="8445e-127">`Get-Package`: Returns a list of installed software packages.</span></span>
- <span data-ttu-id="8445e-128">`Find-Package`: Localiza pacotes de software em fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8445e-128">`Find-Package`: Finds software packages in available package sources.</span></span>
- <span data-ttu-id="8445e-129">`Install-Package`: Instala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="8445e-129">`Install-Package`: Installs one or more software packages.</span></span>
- <span data-ttu-id="8445e-130">`Save-Package`: Salva pacotes no computador local sem instalá-los.</span><span class="sxs-lookup"><span data-stu-id="8445e-130">`Save-Package`: Saves packages to the local computer without installing them.</span></span>
- <span data-ttu-id="8445e-131">`Uninstall-Package`: Desinstala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="8445e-131">`Uninstall-Package`: Uninstalls one or more software packages.</span></span>

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a><span data-ttu-id="8445e-132">Inicialização do provedor de pacote e parâmetros de cmdlet dinâmico</span><span class="sxs-lookup"><span data-stu-id="8445e-132">Package Provider Bootstrapping and Dynamic Cmdlet Parameters</span></span>

<span data-ttu-id="8445e-133">Por padrão, o PackageManagement é fornecido com um provedor de inicialização principal.</span><span class="sxs-lookup"><span data-stu-id="8445e-133">By default, PackageManagement ships with a core bootstrap provider.</span></span> <span data-ttu-id="8445e-134">Você pode instalar provedores de pacote adicionais conforme precisar deles inicializando os provedores; ou seja, responder a um prompt para instalar o provedor automaticamente, de um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="8445e-134">You can install additional package providers as you need them by bootstrapping the providers; that is, responding to a prompt to install the provider automatically, from a web service.</span></span> <span data-ttu-id="8445e-135">Você pode especificar um provedor de pacote com qualquer cmdlet de PackageManagement; Se o provedor especificado não estiver disponível, o PackageManagement solicitará que você inicialize (ou instale automaticamente) o provedor.</span><span class="sxs-lookup"><span data-stu-id="8445e-135">You can specify a package provider with any PackageManagement cmdlet; if the specified provider is not available, PackageManagement prompts you to bootstrap (or automatically install) the provider.</span></span> <span data-ttu-id="8445e-136">Nos exemplos a seguir, se o provedor de Chocolatey ainda não estiver instalado, a inicialização de PackageManagement instalará o provedor.</span><span class="sxs-lookup"><span data-stu-id="8445e-136">In the following examples, if the Chocolatey provider is not already installed, PackageManagement bootstrapping installs the provider.</span></span>

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

<span data-ttu-id="8445e-137">Se o provedor de Chocolatey ainda não estiver instalado, quando você executar o comando anterior, será solicitado a instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="8445e-137">If the Chocolatey provider is not already installed, when you run the preceding command, you are prompted to install it.</span></span>

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

<span data-ttu-id="8445e-138">Se o provedor de Chocolatey ainda não estiver instalado, quando você executar o comando anterior, o provedor será instalado; Mas como o parâmetro ForceBootstrap foi adicionado ao comando, você não será solicitado a instalá-lo; o provedor e o pacote são instalados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8445e-138">If the Chocolatey provider is not already installed, when you run the preceding command, the provider is installed; but because the ForceBootstrap parameter has been added to the command, you are not prompted to install it; both the provider and the package are installed automatically.</span></span>

<span data-ttu-id="8445e-139">Ao tentar instalar um pacote, se você ainda não tiver o provedor de suporte instalado e não adicionar o parâmetro ForceBootstrap ao comando, o PackageManagement solicitará que você instale o provedor.</span><span class="sxs-lookup"><span data-stu-id="8445e-139">When you try to install a package, if you do not already have the supporting provider installed, and you do not add the ForceBootstrap parameter to your command, PackageManagement prompts you to install the provider.</span></span>

<span data-ttu-id="8445e-140">A especificação de um provedor de pacote no comando PackageManagement pode disponibilizar parâmetros dinâmicos específicos para esse provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="8445e-140">Specifying a package provider in your PackageManagement command can make dynamic parameters available that are specific to that package provider.</span></span> <span data-ttu-id="8445e-141">Quando você executa Get-Help para um cmdlet de PackageManagement específico, uma lista de conjuntos de parâmetros é retornada, agrupando parâmetros dinâmicos para provedores de pacotes disponíveis em conjuntos de parâmetros separados.</span><span class="sxs-lookup"><span data-stu-id="8445e-141">When you run Get-Help for a specific PackageManagement cmdlet, a list of parameter sets are returned, grouping dynamic parameters for available package providers in separate parameter sets.</span></span>

<span data-ttu-id="8445e-142">Mais informações sobre o projeto PackageManagement</span><span class="sxs-lookup"><span data-stu-id="8445e-142">More Information About the PackageManagement Project</span></span>

<span data-ttu-id="8445e-143">Para obter mais informações sobre o projeto de desenvolvimento aberto do PackageManagement, incluindo como criar um provedor de pacote de PackageManagement, consulte o projeto PackageManagement no GitHub em https://oneget.org .</span><span class="sxs-lookup"><span data-stu-id="8445e-143">For more information about the PackageManagement open development project, including how to create a PackageManagement package provider, see the PackageManagement project on GitHub at https://oneget.org.</span></span>

## <a name="see-also"></a><span data-ttu-id="8445e-144">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="8445e-144">SEE ALSO</span></span>

[<span data-ttu-id="8445e-145">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8445e-145">Get-PackageProvider</span></span>](xref:PackageManagement.Get-PackageProvider)

[<span data-ttu-id="8445e-146">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8445e-146">Get-PackageSource</span></span>](xref:PackageManagement.Get-PackageSource)

[<span data-ttu-id="8445e-147">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8445e-147">Register-PackageSource</span></span>](xref:PackageManagement.Register-PackageSource)

[<span data-ttu-id="8445e-148">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8445e-148">Set-PackageSource</span></span>](xref:PackageManagement.Set-PackageSource)

[<span data-ttu-id="8445e-149">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8445e-149">Unregister-PackageSource</span></span>](xref:PackageManagement.Unregister-PackageSource)

[<span data-ttu-id="8445e-150">Get-Package</span><span class="sxs-lookup"><span data-stu-id="8445e-150">Get-Package</span></span>](xref:PackageManagement.Get-Package)

[<span data-ttu-id="8445e-151">Find-Package</span><span class="sxs-lookup"><span data-stu-id="8445e-151">Find-Package</span></span>](xref:PackageManagement.Find-Package)

[<span data-ttu-id="8445e-152">Install-Package</span><span class="sxs-lookup"><span data-stu-id="8445e-152">Install-Package</span></span>](xref:PackageManagement.Install-Package)

[<span data-ttu-id="8445e-153">Save-Package</span><span class="sxs-lookup"><span data-stu-id="8445e-153">Save-Package</span></span>](xref:PackageManagement.Save-Package)

[<span data-ttu-id="8445e-154">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="8445e-154">Uninstall-Package</span></span>](xref:PackageManagement.Uninstall-Package)

