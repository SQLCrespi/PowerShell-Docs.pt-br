---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 86e6f37f6f7f0527c5dcca309cf581cb6f1b4de5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99598205"
---
# <span data-ttu-id="d442c-102">Módulo PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d442c-102">PackageManagement Module</span></span>

## <span data-ttu-id="d442c-103">Descrição</span><span class="sxs-lookup"><span data-stu-id="d442c-103">Description</span></span>

<span data-ttu-id="d442c-104">Este tópico exibe tópicos de ajuda para os cmdlets Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="d442c-104">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d442c-105">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="d442c-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d442c-106">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d442c-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d442c-107">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="d442c-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d442c-108">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d442c-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d442c-109">Cmdlets do PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d442c-109">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="d442c-110">Find-Package</span><span class="sxs-lookup"><span data-stu-id="d442c-110">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="d442c-111">Localiza pacotes de software em fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d442c-111">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="d442c-112">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d442c-112">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="d442c-113">Retorna uma lista de provedores de pacote Gerenciamento de Pacotes disponíveis para instalação.</span><span class="sxs-lookup"><span data-stu-id="d442c-113">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="d442c-114">Get-Package</span><span class="sxs-lookup"><span data-stu-id="d442c-114">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="d442c-115">Retorna uma lista de todos os pacotes de software que foram instalados com o **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="d442c-115">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="d442c-116">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d442c-116">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="d442c-117">Retorna uma lista de provedores de pacote que estão conectados a Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="d442c-117">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="d442c-118">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d442c-118">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="d442c-119">Obtém uma lista de origens de pacote registradas para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="d442c-119">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="d442c-120">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d442c-120">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="d442c-121">Adiciona Gerenciamento de Pacotes provedores de pacote à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d442c-121">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="d442c-122">Install-Package</span><span class="sxs-lookup"><span data-stu-id="d442c-122">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="d442c-123">Instala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="d442c-123">Installs one or more software packages.</span></span>

### [<span data-ttu-id="d442c-124">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d442c-124">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="d442c-125">Instala um ou mais provedores de pacote de Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="d442c-125">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="d442c-126">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d442c-126">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="d442c-127">Adiciona uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="d442c-127">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="d442c-128">Save-Package</span><span class="sxs-lookup"><span data-stu-id="d442c-128">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="d442c-129">Salva pacotes no computador local sem instalá-los.</span><span class="sxs-lookup"><span data-stu-id="d442c-129">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="d442c-130">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d442c-130">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="d442c-131">Substitui uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="d442c-131">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="d442c-132">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="d442c-132">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="d442c-133">Desinstala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="d442c-133">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="d442c-134">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d442c-134">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="d442c-135">Remove uma origem de pacote registrada.</span><span class="sxs-lookup"><span data-stu-id="d442c-135">Removes a registered package source.</span></span>
