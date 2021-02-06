---
description: Lista os cmdlets que foram projetados para uso com provedores do PowerShell.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 1f023c5a66265f561ef6644afdc45cd0149f35b7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603775"
---
# <a name="about-core-commands"></a><span data-ttu-id="564fb-103">Sobre os comandos principais</span><span class="sxs-lookup"><span data-stu-id="564fb-103">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="564fb-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="564fb-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="564fb-105">Lista os cmdlets que foram projetados para uso com provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="564fb-105">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="564fb-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="564fb-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="564fb-107">O PowerShell inclui um conjunto de cmdlets projetados especificamente para gerenciar os itens nos armazenamentos de dados que são expostos por provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="564fb-107">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="564fb-108">Você pode usar esses cmdlets da mesma maneira para gerenciar todos os diferentes tipos de dados que os provedores disponibilizam para você.</span><span class="sxs-lookup"><span data-stu-id="564fb-108">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="564fb-109">Para obter mais informações sobre provedores, digite "Get-Help about_providers".</span><span class="sxs-lookup"><span data-stu-id="564fb-109">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="564fb-110">Por exemplo, você pode usar o cmdlet Get-ChildItem para listar os arquivos em um diretório do sistema de arquivos, as chaves em uma chave do registro ou os itens que são expostos por um provedor que você escreve ou baixa.</span><span class="sxs-lookup"><span data-stu-id="564fb-110">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="564fb-111">Veja a seguir uma lista dos cmdlets do PowerShell que foram projetados para uso com provedores:</span><span class="sxs-lookup"><span data-stu-id="564fb-111">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="564fb-112">Cmdlets ChildItem</span><span class="sxs-lookup"><span data-stu-id="564fb-112">ChildItem cmdlets</span></span>

- <span data-ttu-id="564fb-113">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="564fb-113">Get-ChildItem</span></span>

<span data-ttu-id="564fb-114">Cmdlets de conteúdo</span><span class="sxs-lookup"><span data-stu-id="564fb-114">Content cmdlets</span></span>

- <span data-ttu-id="564fb-115">Add-Content</span><span class="sxs-lookup"><span data-stu-id="564fb-115">Add-Content</span></span>
- <span data-ttu-id="564fb-116">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="564fb-116">Clear-Content</span></span>
- <span data-ttu-id="564fb-117">Get-Content</span><span class="sxs-lookup"><span data-stu-id="564fb-117">Get-Content</span></span>
- <span data-ttu-id="564fb-118">Set-Content</span><span class="sxs-lookup"><span data-stu-id="564fb-118">Set-Content</span></span>

<span data-ttu-id="564fb-119">Cmdlets de item</span><span class="sxs-lookup"><span data-stu-id="564fb-119">Item cmdlets</span></span>

- <span data-ttu-id="564fb-120">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-120">Clear-Item</span></span>
- <span data-ttu-id="564fb-121">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-121">Copy-Item</span></span>
- <span data-ttu-id="564fb-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-122">Get-Item</span></span>
- <span data-ttu-id="564fb-123">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-123">Invoke-Item</span></span>
- <span data-ttu-id="564fb-124">Move-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-124">Move-Item</span></span>
- <span data-ttu-id="564fb-125">New-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-125">New-Item</span></span>
- <span data-ttu-id="564fb-126">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-126">Remove-Item</span></span>
- <span data-ttu-id="564fb-127">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-127">Rename-Item</span></span>
- <span data-ttu-id="564fb-128">Set-Item</span><span class="sxs-lookup"><span data-stu-id="564fb-128">Set-Item</span></span>

<span data-ttu-id="564fb-129">Cmdlets ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-129">ItemProperty cmdlets</span></span>

- <span data-ttu-id="564fb-130">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-130">Clear-ItemProperty</span></span>
- <span data-ttu-id="564fb-131">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-131">Copy-ItemProperty</span></span>
- <span data-ttu-id="564fb-132">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-132">Get-ItemProperty</span></span>
- <span data-ttu-id="564fb-133">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-133">Move-ItemProperty</span></span>
- <span data-ttu-id="564fb-134">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-134">New-ItemProperty</span></span>
- <span data-ttu-id="564fb-135">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-135">Remove-ItemProperty</span></span>
- <span data-ttu-id="564fb-136">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-136">Rename-ItemProperty</span></span>
- <span data-ttu-id="564fb-137">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="564fb-137">Set-ItemProperty</span></span>

<span data-ttu-id="564fb-138">Cmdlets de local</span><span class="sxs-lookup"><span data-stu-id="564fb-138">Location cmdlets</span></span>

- <span data-ttu-id="564fb-139">Get-Location</span><span class="sxs-lookup"><span data-stu-id="564fb-139">Get-Location</span></span>
- <span data-ttu-id="564fb-140">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="564fb-140">Pop-Location</span></span>
- <span data-ttu-id="564fb-141">Push-Location</span><span class="sxs-lookup"><span data-stu-id="564fb-141">Push-Location</span></span>
- <span data-ttu-id="564fb-142">Set-Location</span><span class="sxs-lookup"><span data-stu-id="564fb-142">Set-Location</span></span>

<span data-ttu-id="564fb-143">Cmdlets de caminho</span><span class="sxs-lookup"><span data-stu-id="564fb-143">Path cmdlets</span></span>

- <span data-ttu-id="564fb-144">Join-Path</span><span class="sxs-lookup"><span data-stu-id="564fb-144">Join-Path</span></span>
- <span data-ttu-id="564fb-145">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="564fb-145">Convert-Path</span></span>
- <span data-ttu-id="564fb-146">Split-Path</span><span class="sxs-lookup"><span data-stu-id="564fb-146">Split-Path</span></span>
- <span data-ttu-id="564fb-147">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="564fb-147">Resolve-Path</span></span>
- <span data-ttu-id="564fb-148">Test-Path</span><span class="sxs-lookup"><span data-stu-id="564fb-148">Test-Path</span></span>

<span data-ttu-id="564fb-149">Cmdlets PSDrive</span><span class="sxs-lookup"><span data-stu-id="564fb-149">PSDrive cmdlets</span></span>

- <span data-ttu-id="564fb-150">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="564fb-150">Get-PSDrive</span></span>
- <span data-ttu-id="564fb-151">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="564fb-151">New-PSDrive</span></span>
- <span data-ttu-id="564fb-152">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="564fb-152">Remove-PSDrive</span></span>

<span data-ttu-id="564fb-153">Cmdlets PSProvider</span><span class="sxs-lookup"><span data-stu-id="564fb-153">PSProvider cmdlets</span></span>

- <span data-ttu-id="564fb-154">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="564fb-154">Get-PSProvider</span></span>

<span data-ttu-id="564fb-155">Para obter mais informações sobre um cmdlet, digite `get-help <cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="564fb-155">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="564fb-156">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="564fb-156">SEE ALSO</span></span>

[<span data-ttu-id="564fb-157">about_Providers</span><span class="sxs-lookup"><span data-stu-id="564fb-157">about_Providers</span></span>](about_Providers.md)

