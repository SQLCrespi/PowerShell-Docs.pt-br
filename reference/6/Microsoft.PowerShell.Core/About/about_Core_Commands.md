---
description: Lista os cmdlets que foram projetados para uso com provedores do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: d02067bca8f66c61a66ff121521a49668f32d839
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195763"
---
# <a name="about-core-commands"></a><span data-ttu-id="b31ec-104">Sobre os comandos principais</span><span class="sxs-lookup"><span data-stu-id="b31ec-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="b31ec-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="b31ec-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="b31ec-106">Lista os cmdlets que foram projetados para uso com provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b31ec-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="b31ec-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="b31ec-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b31ec-108">O PowerShell inclui um conjunto de cmdlets projetados especificamente para gerenciar os itens nos armazenamentos de dados que são expostos por provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b31ec-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="b31ec-109">Você pode usar esses cmdlets da mesma maneira para gerenciar todos os diferentes tipos de dados que os provedores disponibilizam para você.</span><span class="sxs-lookup"><span data-stu-id="b31ec-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="b31ec-110">Para obter mais informações sobre provedores, digite "Get-Help about_providers".</span><span class="sxs-lookup"><span data-stu-id="b31ec-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="b31ec-111">Por exemplo, você pode usar o cmdlet Get-ChildItem para listar os arquivos em um diretório do sistema de arquivos, as chaves em uma chave do registro ou os itens que são expostos por um provedor que você escreve ou baixa.</span><span class="sxs-lookup"><span data-stu-id="b31ec-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="b31ec-112">Veja a seguir uma lista dos cmdlets do PowerShell que foram projetados para uso com provedores:</span><span class="sxs-lookup"><span data-stu-id="b31ec-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="b31ec-113">Cmdlets ChildItem</span><span class="sxs-lookup"><span data-stu-id="b31ec-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="b31ec-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b31ec-114">Get-ChildItem</span></span>

<span data-ttu-id="b31ec-115">Cmdlets de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b31ec-115">Content cmdlets</span></span>

- <span data-ttu-id="b31ec-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="b31ec-116">Add-Content</span></span>
- <span data-ttu-id="b31ec-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="b31ec-117">Clear-Content</span></span>
- <span data-ttu-id="b31ec-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b31ec-118">Get-Content</span></span>
- <span data-ttu-id="b31ec-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="b31ec-119">Set-Content</span></span>

<span data-ttu-id="b31ec-120">Cmdlets de item</span><span class="sxs-lookup"><span data-stu-id="b31ec-120">Item cmdlets</span></span>

- <span data-ttu-id="b31ec-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-121">Clear-Item</span></span>
- <span data-ttu-id="b31ec-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-122">Copy-Item</span></span>
- <span data-ttu-id="b31ec-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-123">Get-Item</span></span>
- <span data-ttu-id="b31ec-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-124">Invoke-Item</span></span>
- <span data-ttu-id="b31ec-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-125">Move-Item</span></span>
- <span data-ttu-id="b31ec-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-126">New-Item</span></span>
- <span data-ttu-id="b31ec-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-127">Remove-Item</span></span>
- <span data-ttu-id="b31ec-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-128">Rename-Item</span></span>
- <span data-ttu-id="b31ec-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="b31ec-129">Set-Item</span></span>

<span data-ttu-id="b31ec-130">Cmdlets ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="b31ec-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="b31ec-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="b31ec-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-133">Get-ItemProperty</span></span>
- <span data-ttu-id="b31ec-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-134">Move-ItemProperty</span></span>
- <span data-ttu-id="b31ec-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-135">New-ItemProperty</span></span>
- <span data-ttu-id="b31ec-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="b31ec-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="b31ec-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b31ec-138">Set-ItemProperty</span></span>

<span data-ttu-id="b31ec-139">Cmdlets de local</span><span class="sxs-lookup"><span data-stu-id="b31ec-139">Location cmdlets</span></span>

- <span data-ttu-id="b31ec-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b31ec-140">Get-Location</span></span>
- <span data-ttu-id="b31ec-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="b31ec-141">Pop-Location</span></span>
- <span data-ttu-id="b31ec-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="b31ec-142">Push-Location</span></span>
- <span data-ttu-id="b31ec-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b31ec-143">Set-Location</span></span>

<span data-ttu-id="b31ec-144">Cmdlets de caminho</span><span class="sxs-lookup"><span data-stu-id="b31ec-144">Path cmdlets</span></span>

- <span data-ttu-id="b31ec-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="b31ec-145">Join-Path</span></span>
- <span data-ttu-id="b31ec-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="b31ec-146">Convert-Path</span></span>
- <span data-ttu-id="b31ec-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="b31ec-147">Split-Path</span></span>
- <span data-ttu-id="b31ec-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="b31ec-148">Resolve-Path</span></span>
- <span data-ttu-id="b31ec-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="b31ec-149">Test-Path</span></span>

<span data-ttu-id="b31ec-150">Cmdlets PSDrive</span><span class="sxs-lookup"><span data-stu-id="b31ec-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="b31ec-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b31ec-151">Get-PSDrive</span></span>
- <span data-ttu-id="b31ec-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b31ec-152">New-PSDrive</span></span>
- <span data-ttu-id="b31ec-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b31ec-153">Remove-PSDrive</span></span>

<span data-ttu-id="b31ec-154">Cmdlets PSProvider</span><span class="sxs-lookup"><span data-stu-id="b31ec-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="b31ec-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="b31ec-155">Get-PSProvider</span></span>

<span data-ttu-id="b31ec-156">Para obter mais informações sobre um cmdlet, digite `get-help <cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="b31ec-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b31ec-157">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="b31ec-157">SEE ALSO</span></span>

[<span data-ttu-id="b31ec-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b31ec-158">about_Providers</span></span>](about_Providers.md)
