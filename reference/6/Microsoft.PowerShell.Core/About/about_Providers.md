---
description: Descreve como os provedores do PowerShell fornecem acesso a dados e componentes que, de outra forma, não poderiam ser facilmente acessados na linha de comando. Os dados são apresentados em um formato consistente que se assemelha a uma unidade do sistema de arquivos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: cbafcab2b24e77a43d7b628ce9500f480ed9b5b8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195668"
---
# <a name="about-providers"></a><span data-ttu-id="d4aba-105">Sobre provedores</span><span class="sxs-lookup"><span data-stu-id="d4aba-105">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="d4aba-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="d4aba-106">Short description</span></span>
<span data-ttu-id="d4aba-107">Descreve como os provedores do PowerShell fornecem acesso a dados e componentes que, de outra forma, não poderiam ser facilmente acessados na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d4aba-107">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="d4aba-108">Os dados são apresentados em um formato consistente que se assemelha a uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d4aba-108">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="d4aba-109">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="d4aba-109">Long description</span></span>

<span data-ttu-id="d4aba-110">Os provedores do PowerShell são programas .NET que fornecem acesso a armazenamentos de dados especializados para facilitar a visualização e o gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d4aba-110">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="d4aba-111">Os dados são exibidos em uma unidade e você acessa os dados em um caminho como faria em uma unidade de disco rígido.</span><span class="sxs-lookup"><span data-stu-id="d4aba-111">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="d4aba-112">Você pode usar qualquer um dos cmdlets internos aos quais o provedor dá suporte para gerenciar os dados na unidade do provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-112">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="d4aba-113">Além disso, você pode usar cmdlets personalizados projetados especialmente para os dados.</span><span class="sxs-lookup"><span data-stu-id="d4aba-113">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="d4aba-114">Os provedores também podem adicionar parâmetros dinâmicos aos cmdlets internos.</span><span class="sxs-lookup"><span data-stu-id="d4aba-114">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="d4aba-115">Esses parâmetros só estão disponíveis quando você usa o cmdlet com os dados do provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-115">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="d4aba-116">Provedores internos</span><span class="sxs-lookup"><span data-stu-id="d4aba-116">Built-in providers</span></span>

<span data-ttu-id="d4aba-117">O PowerShell inclui um conjunto de provedores internos que você pode usar para acessar os diferentes tipos de armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="d4aba-117">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="d4aba-118">Provedor</span><span class="sxs-lookup"><span data-stu-id="d4aba-118">Provider</span></span>   |   <span data-ttu-id="d4aba-119">Unidade (s)</span><span class="sxs-lookup"><span data-stu-id="d4aba-119">Drive(s)</span></span>  |<span data-ttu-id="d4aba-120">OutputType</span><span class="sxs-lookup"><span data-stu-id="d4aba-120">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="d4aba-121">Alias</span><span class="sxs-lookup"><span data-stu-id="d4aba-121">Alias</span></span>       |<span data-ttu-id="d4aba-122">Alias:</span><span class="sxs-lookup"><span data-stu-id="d4aba-122">Alias:</span></span>       |<span data-ttu-id="d4aba-123">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="d4aba-123">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="d4aba-124">Certificado</span><span class="sxs-lookup"><span data-stu-id="d4aba-124">Certificate</span></span> |<span data-ttu-id="d4aba-125">Cert:</span><span class="sxs-lookup"><span data-stu-id="d4aba-125">Cert:</span></span>        |<span data-ttu-id="d4aba-126">Microsoft. PowerShell. Commands. X509StoreLocation</span><span class="sxs-lookup"><span data-stu-id="d4aba-126">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="d4aba-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="d4aba-127">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="d4aba-128">Ambiente</span><span class="sxs-lookup"><span data-stu-id="d4aba-128">Environment</span></span> |<span data-ttu-id="d4aba-129">Env:</span><span class="sxs-lookup"><span data-stu-id="d4aba-129">Env:</span></span>         |<span data-ttu-id="d4aba-130">System. Collections. DictionaryEntry</span><span class="sxs-lookup"><span data-stu-id="d4aba-130">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="d4aba-131">FileSystem</span><span class="sxs-lookup"><span data-stu-id="d4aba-131">FileSystem</span></span>  |<span data-ttu-id="d4aba-132">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="d4aba-132">C: (\*)</span></span>       |<span data-ttu-id="d4aba-133">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="d4aba-133">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="d4aba-134">System. IO. DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="d4aba-134">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="d4aba-135">Função</span><span class="sxs-lookup"><span data-stu-id="d4aba-135">Function</span></span>    |<span data-ttu-id="d4aba-136">Função:</span><span class="sxs-lookup"><span data-stu-id="d4aba-136">Function:</span></span>    |<span data-ttu-id="d4aba-137">System. Management. Automation. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="d4aba-137">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="d4aba-138">Registro</span><span class="sxs-lookup"><span data-stu-id="d4aba-138">Registry</span></span>    |<span data-ttu-id="d4aba-139">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="d4aba-139">HKLM: HKCU:</span></span>  |<span data-ttu-id="d4aba-140">Microsoft. Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="d4aba-140">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="d4aba-141">Variável</span><span class="sxs-lookup"><span data-stu-id="d4aba-141">Variable</span></span>    |<span data-ttu-id="d4aba-142">Variável:</span><span class="sxs-lookup"><span data-stu-id="d4aba-142">Variable:</span></span>    |<span data-ttu-id="d4aba-143">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="d4aba-143">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="d4aba-144">WSMan</span><span class="sxs-lookup"><span data-stu-id="d4aba-144">WSMan</span></span>       |<span data-ttu-id="d4aba-145">WSMan:</span><span class="sxs-lookup"><span data-stu-id="d4aba-145">WSMan:</span></span>       |<span data-ttu-id="d4aba-146">Microsoft. WSMan. Management. WSManConfigContainerElement</span><span class="sxs-lookup"><span data-stu-id="d4aba-146">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="d4aba-147">(\*) As unidades do sistema de arquivos variam em cada sistema.</span><span class="sxs-lookup"><span data-stu-id="d4aba-147">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="d4aba-148">Você também pode criar seus próprios provedores do PowerShell e pode instalar provedores que outras pessoas desenvolvem.</span><span class="sxs-lookup"><span data-stu-id="d4aba-148">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="d4aba-149">Para listar os provedores que estão disponíveis em sua sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-149">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="d4aba-150">Instalando e removendo provedores</span><span class="sxs-lookup"><span data-stu-id="d4aba-150">Installing and removing providers</span></span>

<span data-ttu-id="d4aba-151">Normalmente, os provedores são instalados por meio de módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4aba-151">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="d4aba-152">A importação do módulo carrega o provedor em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="d4aba-152">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="d4aba-153">Não é possível desinstalar os provedores internos.</span><span class="sxs-lookup"><span data-stu-id="d4aba-153">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="d4aba-154">Você pode desinstalar provedores carregados por outros módulos.</span><span class="sxs-lookup"><span data-stu-id="d4aba-154">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="d4aba-155">Você pode descarregar um provedor da sessão atual usando o `Remove-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d4aba-155">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="d4aba-156">Esse cmdlet não desinstala o provedor, mas torna o provedor indisponível na sessão.</span><span class="sxs-lookup"><span data-stu-id="d4aba-156">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="d4aba-157">Você também pode usar o `Remove-PSDrive` cmdlet para remover qualquer unidade da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d4aba-157">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="d4aba-158">Esses dados na unidade não são afetados, mas a unidade não está mais disponível nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="d4aba-158">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="d4aba-159">Exibindo provedores</span><span class="sxs-lookup"><span data-stu-id="d4aba-159">Viewing providers</span></span>

<span data-ttu-id="d4aba-160">Para exibir os provedores do PowerShell no seu computador, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-160">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="d4aba-161">A saída lista os provedores internos e os provedores que você adicionou à sessão.</span><span class="sxs-lookup"><span data-stu-id="d4aba-161">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="d4aba-162">Os cmdlets do provedor</span><span class="sxs-lookup"><span data-stu-id="d4aba-162">The provider cmdlets</span></span>

<span data-ttu-id="d4aba-163">Os cmdlets a seguir foram projetados para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-163">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d4aba-164">Você pode usar os mesmos cmdlets da mesma maneira para gerenciar os diferentes tipos de dados que os provedores expõem.</span><span class="sxs-lookup"><span data-stu-id="d4aba-164">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="d4aba-165">Depois de aprender a gerenciar os dados de um provedor, você pode usar os mesmos procedimentos com os dados de qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-165">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="d4aba-166">Por exemplo, o `New-Item` cmdlet cria um novo item.</span><span class="sxs-lookup"><span data-stu-id="d4aba-166">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="d4aba-167">Na `C:` unidade com suporte do provedor **FileSystem** , você pode usar o `New-Item` para criar um novo arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="d4aba-167">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="d4aba-168">Nas unidades que têm suporte do provedor de **registro** , você pode usar o `New-Item` para criar uma nova chave do registro.</span><span class="sxs-lookup"><span data-stu-id="d4aba-168">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="d4aba-169">Na `Alias:` unidade, você pode usar `New-Item` para criar um novo alias.</span><span class="sxs-lookup"><span data-stu-id="d4aba-169">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="d4aba-170">Para obter informações detalhadas sobre qualquer um dos seguintes cmdlets, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-170">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="d4aba-171">Cmdlets ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4aba-171">ChildItem cmdlets</span></span>

- [<span data-ttu-id="d4aba-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d4aba-172">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="d4aba-173">Cmdlets de conteúdo</span><span class="sxs-lookup"><span data-stu-id="d4aba-173">Content Cmdlets</span></span>

- [<span data-ttu-id="d4aba-174">Add-Content</span><span class="sxs-lookup"><span data-stu-id="d4aba-174">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="d4aba-175">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="d4aba-175">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="d4aba-176">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d4aba-176">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="d4aba-177">Set-Content</span><span class="sxs-lookup"><span data-stu-id="d4aba-177">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="d4aba-178">Cmdlets de item</span><span class="sxs-lookup"><span data-stu-id="d4aba-178">Item Cmdlets</span></span>

- [<span data-ttu-id="d4aba-179">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-179">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="d4aba-180">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-180">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="d4aba-181">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-181">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="d4aba-182">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-182">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="d4aba-183">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-183">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="d4aba-184">New-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-184">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="d4aba-185">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-185">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d4aba-186">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-186">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="d4aba-187">Set-Item</span><span class="sxs-lookup"><span data-stu-id="d4aba-187">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="d4aba-188">Cmdlets ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-188">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="d4aba-189">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-189">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="d4aba-190">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-190">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="d4aba-191">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-191">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="d4aba-192">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-192">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="d4aba-193">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-193">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="d4aba-194">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-194">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="d4aba-195">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-195">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="d4aba-196">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d4aba-196">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="d4aba-197">Cmdlets de local</span><span class="sxs-lookup"><span data-stu-id="d4aba-197">Location cmdlets</span></span>

- [<span data-ttu-id="d4aba-198">Get-Location</span><span class="sxs-lookup"><span data-stu-id="d4aba-198">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="d4aba-199">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="d4aba-199">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="d4aba-200">Push-Location</span><span class="sxs-lookup"><span data-stu-id="d4aba-200">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="d4aba-201">Set-Location</span><span class="sxs-lookup"><span data-stu-id="d4aba-201">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="d4aba-202">Cmdlets de caminho</span><span class="sxs-lookup"><span data-stu-id="d4aba-202">Path cmdlets</span></span>

- [<span data-ttu-id="d4aba-203">Join-Path</span><span class="sxs-lookup"><span data-stu-id="d4aba-203">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="d4aba-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="d4aba-204">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="d4aba-205">Split-Path</span><span class="sxs-lookup"><span data-stu-id="d4aba-205">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="d4aba-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="d4aba-206">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="d4aba-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="d4aba-207">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="d4aba-208">Cmdlets PSDrive</span><span class="sxs-lookup"><span data-stu-id="d4aba-208">PSDrive cmdlets</span></span>

- [<span data-ttu-id="d4aba-209">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="d4aba-209">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="d4aba-210">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="d4aba-210">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="d4aba-211">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="d4aba-211">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="d4aba-212">Cmdlets PSProvider</span><span class="sxs-lookup"><span data-stu-id="d4aba-212">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="d4aba-213">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="d4aba-213">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="d4aba-214">Exibindo dados do provedor</span><span class="sxs-lookup"><span data-stu-id="d4aba-214">Viewing provider data</span></span>

<span data-ttu-id="d4aba-215">O principal benefício de um provedor é que ele expõe seus dados de uma maneira familiar e consistente.</span><span class="sxs-lookup"><span data-stu-id="d4aba-215">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="d4aba-216">O modelo de apresentação de dados é uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d4aba-216">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="d4aba-217">O provedor permite exibir, navegar e alterar itens no armazenamento de dados, como se eles fossem dados em um sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d4aba-217">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="d4aba-218">O armazenamento de dados é acessado pelo nome da unidade que ele suporta.</span><span class="sxs-lookup"><span data-stu-id="d4aba-218">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="d4aba-219">A unidade é listada na exibição padrão do `Get-PSProvider` cmdlet, mas você pode obter informações sobre a unidade do provedor usando o `Get-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d4aba-219">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="d4aba-220">Por exemplo, para obter todas as propriedades da unidade Function:, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-220">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="d4aba-221">Você pode exibir e percorrer os dados em uma unidade de provedor da mesma forma como faria em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d4aba-221">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="d4aba-222">Para exibir o conteúdo de uma unidade de provedor, use os cmdlets Get-Item ou Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="d4aba-222">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="d4aba-223">Digite o nome da unidade seguido por dois-pontos (:).</span><span class="sxs-lookup"><span data-stu-id="d4aba-223">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="d4aba-224">Por exemplo, para exibir o conteúdo da unidade Alias:, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-224">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="d4aba-225">Você pode exibir e gerenciar os dados em qualquer unidade de outra unidade, incluindo o nome da unidade no caminho.</span><span class="sxs-lookup"><span data-stu-id="d4aba-225">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="d4aba-226">Por exemplo, para exibir a chave do registro HKLM\Software na unidade HKLM: de outra unidade, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-226">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="d4aba-227">Para abrir a unidade, use o cmdlet Set-Location.</span><span class="sxs-lookup"><span data-stu-id="d4aba-227">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="d4aba-228">Lembre-se dos dois-pontos ao especificar o caminho da unidade.</span><span class="sxs-lookup"><span data-stu-id="d4aba-228">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="d4aba-229">Por exemplo, para alterar o local para o diretório raiz da unidade CERT:, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-229">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="d4aba-230">Em seguida, para exibir o conteúdo da unidade CERT:, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-230">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="d4aba-231">Movimentação por meio de dados hierárquicos</span><span class="sxs-lookup"><span data-stu-id="d4aba-231">Moving through hierarchical data</span></span>

<span data-ttu-id="d4aba-232">Você pode percorrer uma unidade de provedor assim como faria com uma unidade de disco rígido.</span><span class="sxs-lookup"><span data-stu-id="d4aba-232">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="d4aba-233">Se os dados forem organizados em uma hierarquia de itens dentro de itens, use uma barra invertida ( `\` ) para indicar um item filho.</span><span class="sxs-lookup"><span data-stu-id="d4aba-233">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="d4aba-234">Use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="d4aba-234">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="d4aba-235">Por exemplo, para alterar seu local para a chave do registro HKLM\Software, digite um comando Set-Location, como:</span><span class="sxs-lookup"><span data-stu-id="d4aba-235">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="d4aba-236">Se qualquer elemento no nome totalmente qualificado incluir espaços, você deverá colocar o nome entre aspas duplas ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="d4aba-236">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="d4aba-237">O exemplo a seguir mostra um caminho totalmente qualificado que inclui espaços.</span><span class="sxs-lookup"><span data-stu-id="d4aba-237">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="d4aba-238">Você também pode usar referências relativas a locais.</span><span class="sxs-lookup"><span data-stu-id="d4aba-238">You can also use relative references to locations.</span></span> <span data-ttu-id="d4aba-239">Um ponto ( `.` ) representa o local atual.</span><span class="sxs-lookup"><span data-stu-id="d4aba-239">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="d4aba-240">Por exemplo, se você estiver na `HKLM:\Software\Microsoft` chave do registro e desejar listar as subchaves do registro na `HKLM:\Software\Microsoft\PowerShell` chave, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d4aba-240">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="d4aba-241">Além disso, os pontos duplos ( `..` ) referem-se ao diretório ou contêiner diretamente acima do seu local atual.</span><span class="sxs-lookup"><span data-stu-id="d4aba-241">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="d4aba-242">Você pode usar pontos duplos ( `..` ) para navegar por uma hierarquia de provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-242">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="d4aba-243">Página inicial do provedor</span><span class="sxs-lookup"><span data-stu-id="d4aba-243">Provider Home</span></span>

<span data-ttu-id="d4aba-244">Os provedores também têm um local de **residência** .</span><span class="sxs-lookup"><span data-stu-id="d4aba-244">Providers also have a **Home** location.</span></span>  <span data-ttu-id="d4aba-245">Esse local é compartilhado por todos os `PSDrives` apoiados pelo provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-245">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="d4aba-246">Ele pode ser recuperado exibindo a propriedade **Home** do provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-246">It can be retrieved by viewing the **Home** property of the provider.</span></span>

```powershell
Get-PSProvider | Format-Table Name, Home
```

```Output
Name        Home
----        ----
Registry
Alias
Environment
FileSystem  C:\Users\username
Function
Variable
Certificate
```

<span data-ttu-id="d4aba-247">O provedor **FileSystem** é o único provedor que tem um valor padrão para **Home** .</span><span class="sxs-lookup"><span data-stu-id="d4aba-247">The **FileSystem** provider is the only provider that has a default value for **Home** .</span></span> <span data-ttu-id="d4aba-248">É o mesmo valor que `$Home` .</span><span class="sxs-lookup"><span data-stu-id="d4aba-248">It's the same value as `$Home`.</span></span> <span data-ttu-id="d4aba-249">Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d4aba-249">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="d4aba-250">Você pode definir o diretório **base** para um provedor, para a sessão atual, usando sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="d4aba-250">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="d4aba-251">O `~` caractere pode ser usado para representar o diretório base do provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-251">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="d4aba-252">Se o provedor não tiver um local de **residência** definido, você verá um erro.</span><span class="sxs-lookup"><span data-stu-id="d4aba-252">If the provider doesn't have a **Home** location set, you see an error.</span></span>

```powershell
Cert:\> Set-Location ~
```

```Output
Set-Location : Home location for this provider isn't set. To set the home
location, call "(get-psprovider 'Certificate').Home = 'path'".
At line:1 char:1
+ Set-Location ~
+ ~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Set-Location],
                              PSInvalidOperationException
...
```

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="d4aba-253">Localizando parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="d4aba-253">Finding dynamic parameters</span></span>

<span data-ttu-id="d4aba-254">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados a um cmdlet por um provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-254">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="d4aba-255">Esses parâmetros estão disponíveis somente quando o cmdlet é usado com o provedor que os adicionou.</span><span class="sxs-lookup"><span data-stu-id="d4aba-255">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="d4aba-256">Por exemplo, a `Cert:` unidade adiciona o parâmetro **CodeSigningCert** aos `Get-Item` `Get-ChildItem` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="d4aba-256">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="d4aba-257">Você pode usar esse parâmetro somente quando usar `Get-Item` ou `Get-ChildItem` na `Cert:` unidade.</span><span class="sxs-lookup"><span data-stu-id="d4aba-257">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="d4aba-258">Para obter uma lista dos parâmetros dinâmicos aos quais um provedor dá suporte, consulte o arquivo de ajuda para o provedor.</span><span class="sxs-lookup"><span data-stu-id="d4aba-258">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="d4aba-259">Tipo:</span><span class="sxs-lookup"><span data-stu-id="d4aba-259">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="d4aba-260">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d4aba-260">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="d4aba-261">Aprendendo sobre provedores</span><span class="sxs-lookup"><span data-stu-id="d4aba-261">Learning about providers</span></span>

<span data-ttu-id="d4aba-262">Embora todos os dados do provedor apareçam nas unidades e você use os mesmos métodos para movê-los, a similaridade é interrompida.</span><span class="sxs-lookup"><span data-stu-id="d4aba-262">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="d4aba-263">Os armazenamentos de dados que o provedor expõe podem ser tão variados quanto Active Directory locais e caixas de correio do Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d4aba-263">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="d4aba-264">Para obter informações sobre provedores individuais do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-264">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="d4aba-265">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d4aba-265">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="d4aba-266">Para obter uma lista de tópicos de ajuda sobre os provedores, digite:</span><span class="sxs-lookup"><span data-stu-id="d4aba-266">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="d4aba-267">Confira também</span><span class="sxs-lookup"><span data-stu-id="d4aba-267">See also</span></span>

[<span data-ttu-id="d4aba-268">about_Locations</span><span class="sxs-lookup"><span data-stu-id="d4aba-268">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="d4aba-269">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="d4aba-269">about_Path_Syntax</span></span>](about_Path_Syntax.md)
