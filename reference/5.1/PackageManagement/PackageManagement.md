---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=392040
Help Version: 5.2.0.0
keywords: powershell, cmdlet
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 208545677771270ad8f2e9d76ba01046b07e86e2
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892773"
---
# <span data-ttu-id="a4004-103">Módulo PackageManagement</span><span class="sxs-lookup"><span data-stu-id="a4004-103">PackageManagement Module</span></span>

## <span data-ttu-id="a4004-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4004-104">Description</span></span>

<span data-ttu-id="a4004-105">Este tópico exibe tópicos de ajuda para os cmdlets Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="a4004-105">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4004-106">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="a4004-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="a4004-107">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4004-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="a4004-108">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="a4004-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="a4004-109">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4004-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="a4004-110">Cmdlets do PackageManagement</span><span class="sxs-lookup"><span data-stu-id="a4004-110">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="a4004-111">Find-Package</span><span class="sxs-lookup"><span data-stu-id="a4004-111">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="a4004-112">Localiza pacotes de software em fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a4004-112">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="a4004-113">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a4004-113">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="a4004-114">Retorna uma lista de provedores de pacote Gerenciamento de Pacotes disponíveis para instalação.</span><span class="sxs-lookup"><span data-stu-id="a4004-114">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="a4004-115">Get-Package</span><span class="sxs-lookup"><span data-stu-id="a4004-115">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="a4004-116">Retorna uma lista de todos os pacotes de software que foram instalados com o **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="a4004-116">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="a4004-117">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a4004-117">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="a4004-118">Retorna uma lista de provedores de pacote que estão conectados a Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="a4004-118">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="a4004-119">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a4004-119">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="a4004-120">Obtém uma lista de origens de pacote registradas para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="a4004-120">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="a4004-121">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a4004-121">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="a4004-122">Adiciona Gerenciamento de Pacotes provedores de pacote à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a4004-122">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="a4004-123">Install-Package</span><span class="sxs-lookup"><span data-stu-id="a4004-123">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="a4004-124">Instala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="a4004-124">Installs one or more software packages.</span></span>

### [<span data-ttu-id="a4004-125">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a4004-125">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="a4004-126">Instala um ou mais provedores de pacote de Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="a4004-126">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="a4004-127">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a4004-127">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="a4004-128">Adiciona uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="a4004-128">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="a4004-129">Save-Package</span><span class="sxs-lookup"><span data-stu-id="a4004-129">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="a4004-130">Salva pacotes no computador local sem instalá-los.</span><span class="sxs-lookup"><span data-stu-id="a4004-130">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="a4004-131">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a4004-131">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="a4004-132">Substitui uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="a4004-132">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="a4004-133">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="a4004-133">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="a4004-134">Desinstala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="a4004-134">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="a4004-135">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a4004-135">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="a4004-136">Remove uma origem de pacote registrada.</span><span class="sxs-lookup"><span data-stu-id="a4004-136">Removes a registered package source.</span></span>
