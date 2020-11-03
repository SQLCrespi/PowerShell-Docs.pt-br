---
description: Lista os cmdlets que foram projetados para uso com provedores do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 3391dce21cec5080020640be75e4c4df9da0c812
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196230"
---
# <a name="about-core-commands"></a><span data-ttu-id="b1a70-104">Sobre os comandos principais</span><span class="sxs-lookup"><span data-stu-id="b1a70-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="b1a70-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="b1a70-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b1a70-106">Lista os cmdlets que foram projetados para uso com provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1a70-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="b1a70-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="b1a70-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b1a70-108">O PowerShell inclui um conjunto de cmdlets projetados especificamente para gerenciar os itens nos armazenamentos de dados que são expostos por provedores do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1a70-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by Windows PowerShell providers.</span></span>
<span data-ttu-id="b1a70-109">Você pode usar esses cmdlets da mesma maneira para gerenciar todos os diferentes tipos de dados que os provedores disponibilizam para você.</span><span class="sxs-lookup"><span data-stu-id="b1a70-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="b1a70-110">Para obter mais informações sobre provedores, digite "Get-Help about_providers".</span><span class="sxs-lookup"><span data-stu-id="b1a70-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="b1a70-111">Por exemplo, você pode usar o cmdlet Get-ChildItem para listar os arquivos em um diretório do sistema de arquivos, as chaves em uma chave do registro ou os itens que são expostos por um provedor que você escreve ou baixa.</span><span class="sxs-lookup"><span data-stu-id="b1a70-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="b1a70-112">Veja a seguir uma lista dos cmdlets do PowerShell que foram projetados para uso com provedores:</span><span class="sxs-lookup"><span data-stu-id="b1a70-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="b1a70-113">Cmdlets ChildItem</span><span class="sxs-lookup"><span data-stu-id="b1a70-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="b1a70-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b1a70-114">Get-ChildItem</span></span>

<span data-ttu-id="b1a70-115">Cmdlets de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b1a70-115">Content cmdlets</span></span>

- <span data-ttu-id="b1a70-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="b1a70-116">Add-Content</span></span>
- <span data-ttu-id="b1a70-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="b1a70-117">Clear-Content</span></span>
- <span data-ttu-id="b1a70-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b1a70-118">Get-Content</span></span>
- <span data-ttu-id="b1a70-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="b1a70-119">Set-Content</span></span>

<span data-ttu-id="b1a70-120">Cmdlets de item</span><span class="sxs-lookup"><span data-stu-id="b1a70-120">Item cmdlets</span></span>

- <span data-ttu-id="b1a70-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-121">Clear-Item</span></span>
- <span data-ttu-id="b1a70-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-122">Copy-Item</span></span>
- <span data-ttu-id="b1a70-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-123">Get-Item</span></span>
- <span data-ttu-id="b1a70-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-124">Invoke-Item</span></span>
- <span data-ttu-id="b1a70-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-125">Move-Item</span></span>
- <span data-ttu-id="b1a70-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-126">New-Item</span></span>
- <span data-ttu-id="b1a70-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-127">Remove-Item</span></span>
- <span data-ttu-id="b1a70-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-128">Rename-Item</span></span>
- <span data-ttu-id="b1a70-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="b1a70-129">Set-Item</span></span>

<span data-ttu-id="b1a70-130">Cmdlets ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="b1a70-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="b1a70-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="b1a70-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-133">Get-ItemProperty</span></span>
- <span data-ttu-id="b1a70-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-134">Move-ItemProperty</span></span>
- <span data-ttu-id="b1a70-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-135">New-ItemProperty</span></span>
- <span data-ttu-id="b1a70-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="b1a70-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="b1a70-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1a70-138">Set-ItemProperty</span></span>

<span data-ttu-id="b1a70-139">Cmdlets de local</span><span class="sxs-lookup"><span data-stu-id="b1a70-139">Location cmdlets</span></span>

- <span data-ttu-id="b1a70-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b1a70-140">Get-Location</span></span>
- <span data-ttu-id="b1a70-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="b1a70-141">Pop-Location</span></span>
- <span data-ttu-id="b1a70-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="b1a70-142">Push-Location</span></span>
- <span data-ttu-id="b1a70-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b1a70-143">Set-Location</span></span>

<span data-ttu-id="b1a70-144">Cmdlets de caminho</span><span class="sxs-lookup"><span data-stu-id="b1a70-144">Path cmdlets</span></span>

- <span data-ttu-id="b1a70-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="b1a70-145">Join-Path</span></span>
- <span data-ttu-id="b1a70-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="b1a70-146">Convert-Path</span></span>
- <span data-ttu-id="b1a70-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="b1a70-147">Split-Path</span></span>
- <span data-ttu-id="b1a70-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="b1a70-148">Resolve-Path</span></span>
- <span data-ttu-id="b1a70-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="b1a70-149">Test-Path</span></span>

<span data-ttu-id="b1a70-150">Cmdlets PSDrive</span><span class="sxs-lookup"><span data-stu-id="b1a70-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="b1a70-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b1a70-151">Get-PSDrive</span></span>
- <span data-ttu-id="b1a70-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b1a70-152">New-PSDrive</span></span>
- <span data-ttu-id="b1a70-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b1a70-153">Remove-PSDrive</span></span>

<span data-ttu-id="b1a70-154">Cmdlets PSProvider</span><span class="sxs-lookup"><span data-stu-id="b1a70-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="b1a70-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="b1a70-155">Get-PSProvider</span></span>

<span data-ttu-id="b1a70-156">Para obter mais informações sobre um cmdlet, digite `get-help <cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="b1a70-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1a70-157">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="b1a70-157">SEE ALSO</span></span>

[<span data-ttu-id="b1a70-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b1a70-158">about_Providers</span></span>](about_Providers.md)
