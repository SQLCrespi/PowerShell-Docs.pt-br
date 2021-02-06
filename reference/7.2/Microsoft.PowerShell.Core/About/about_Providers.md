---
description: Descreve como os provedores do PowerShell fornecem acesso a dados e componentes que, de outra forma, não poderiam ser facilmente acessados na linha de comando. Os dados são apresentados em um formato consistente que se assemelha a uma unidade do sistema de arquivos.
Locale: en-US
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Providers
ms.openlocfilehash: 6073ef13a6d0a02cded69073d7ffaef903a807ea
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597189"
---
# <a name="about-providers"></a><span data-ttu-id="380a6-104">Sobre provedores</span><span class="sxs-lookup"><span data-stu-id="380a6-104">About Providers</span></span>

## <a name="short-description"></a><span data-ttu-id="380a6-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="380a6-105">Short description</span></span>
<span data-ttu-id="380a6-106">Descreve como os provedores do PowerShell fornecem acesso a dados e componentes que, de outra forma, não poderiam ser facilmente acessados na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="380a6-106">Describes how PowerShell providers provide access to data and components that wouldn't otherwise be easily accessible at the command line.</span></span>
<span data-ttu-id="380a6-107">Os dados são apresentados em um formato consistente que se assemelha a uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="380a6-107">The data is presented in a consistent format that resembles a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="380a6-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="380a6-108">Long description</span></span>

<span data-ttu-id="380a6-109">Os provedores do PowerShell são programas .NET que fornecem acesso a armazenamentos de dados especializados para facilitar a visualização e o gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="380a6-109">PowerShell providers are .NET programs that provide access to specialized data stores for easier viewing and management.</span></span> <span data-ttu-id="380a6-110">Os dados são exibidos em uma unidade e você acessa os dados em um caminho como faria em uma unidade de disco rígido.</span><span class="sxs-lookup"><span data-stu-id="380a6-110">The data appears in a drive, and you access the data in a path like you would on a hard disk drive.</span></span> <span data-ttu-id="380a6-111">Você pode usar qualquer um dos cmdlets internos aos quais o provedor dá suporte para gerenciar os dados na unidade do provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-111">You can use any of the built-in cmdlets that the provider supports to manage the data in the provider drive.</span></span> <span data-ttu-id="380a6-112">Além disso, você pode usar cmdlets personalizados projetados especialmente para os dados.</span><span class="sxs-lookup"><span data-stu-id="380a6-112">And, you can use custom cmdlets that are designed especially for the data.</span></span>

<span data-ttu-id="380a6-113">Os provedores também podem adicionar parâmetros dinâmicos aos cmdlets internos.</span><span class="sxs-lookup"><span data-stu-id="380a6-113">The providers can also add dynamic parameters to the built-in cmdlets.</span></span> <span data-ttu-id="380a6-114">Esses parâmetros só estão disponíveis quando você usa o cmdlet com os dados do provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-114">These parameters are only available when you use the cmdlet with the provider data.</span></span>

## <a name="built-in-providers"></a><span data-ttu-id="380a6-115">Provedores internos</span><span class="sxs-lookup"><span data-stu-id="380a6-115">Built-in providers</span></span>

<span data-ttu-id="380a6-116">O PowerShell inclui um conjunto de provedores internos que você pode usar para acessar os diferentes tipos de armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="380a6-116">PowerShell includes a set of built-in providers that you can use to access the different types of data stores.</span></span>

| <span data-ttu-id="380a6-117">Provedor</span><span class="sxs-lookup"><span data-stu-id="380a6-117">Provider</span></span>   |   <span data-ttu-id="380a6-118">Unidade (s)</span><span class="sxs-lookup"><span data-stu-id="380a6-118">Drive(s)</span></span>  |<span data-ttu-id="380a6-119">OutputType</span><span class="sxs-lookup"><span data-stu-id="380a6-119">OutputType</span></span>                                                    |
|----------- |------------ |--------------------------------------------------------------|
|<span data-ttu-id="380a6-120">Alias</span><span class="sxs-lookup"><span data-stu-id="380a6-120">Alias</span></span>       |<span data-ttu-id="380a6-121">Alias:</span><span class="sxs-lookup"><span data-stu-id="380a6-121">Alias:</span></span>       |<span data-ttu-id="380a6-122">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="380a6-122">System.Management.Automation.AliasInfo</span></span>                        |
|<span data-ttu-id="380a6-123">Certificado</span><span class="sxs-lookup"><span data-stu-id="380a6-123">Certificate</span></span> |<span data-ttu-id="380a6-124">Cert:</span><span class="sxs-lookup"><span data-stu-id="380a6-124">Cert:</span></span>        |<span data-ttu-id="380a6-125">Microsoft. PowerShell. Commands. X509StoreLocation</span><span class="sxs-lookup"><span data-stu-id="380a6-125">Microsoft.PowerShell.Commands.X509StoreLocation</span></span>               |
|            |             |<span data-ttu-id="380a6-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="380a6-126">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>|
|<span data-ttu-id="380a6-127">Ambiente</span><span class="sxs-lookup"><span data-stu-id="380a6-127">Environment</span></span> |<span data-ttu-id="380a6-128">Env:</span><span class="sxs-lookup"><span data-stu-id="380a6-128">Env:</span></span>         |<span data-ttu-id="380a6-129">System. Collections. DictionaryEntry</span><span class="sxs-lookup"><span data-stu-id="380a6-129">System.Collections.DictionaryEntry</span></span>                            |
|<span data-ttu-id="380a6-130">FileSystem</span><span class="sxs-lookup"><span data-stu-id="380a6-130">FileSystem</span></span>  |<span data-ttu-id="380a6-131">C: (\*)</span><span class="sxs-lookup"><span data-stu-id="380a6-131">C: (\*)</span></span>       |<span data-ttu-id="380a6-132">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="380a6-132">System.IO.FileInfo</span></span>                                            |
|            |             |<span data-ttu-id="380a6-133">System. IO. DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="380a6-133">System.IO.DirectoryInfo</span></span>                                       |
|<span data-ttu-id="380a6-134">Função</span><span class="sxs-lookup"><span data-stu-id="380a6-134">Function</span></span>    |<span data-ttu-id="380a6-135">Função:</span><span class="sxs-lookup"><span data-stu-id="380a6-135">Function:</span></span>    |<span data-ttu-id="380a6-136">System. Management. Automation. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="380a6-136">System.Management.Automation.FunctionInfo</span></span>                     |
|<span data-ttu-id="380a6-137">Registro</span><span class="sxs-lookup"><span data-stu-id="380a6-137">Registry</span></span>    |<span data-ttu-id="380a6-138">HKLM: HKCU:</span><span class="sxs-lookup"><span data-stu-id="380a6-138">HKLM: HKCU:</span></span>  |<span data-ttu-id="380a6-139">Microsoft. Win32. RegistryKey</span><span class="sxs-lookup"><span data-stu-id="380a6-139">Microsoft.Win32.RegistryKey</span></span>                                   |
|<span data-ttu-id="380a6-140">Variável</span><span class="sxs-lookup"><span data-stu-id="380a6-140">Variable</span></span>    |<span data-ttu-id="380a6-141">Variável:</span><span class="sxs-lookup"><span data-stu-id="380a6-141">Variable:</span></span>    |<span data-ttu-id="380a6-142">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="380a6-142">System.Management.Automation.PSVariable</span></span>                       |
|<span data-ttu-id="380a6-143">WSMan</span><span class="sxs-lookup"><span data-stu-id="380a6-143">WSMan</span></span>       |<span data-ttu-id="380a6-144">WSMan:</span><span class="sxs-lookup"><span data-stu-id="380a6-144">WSMan:</span></span>       |<span data-ttu-id="380a6-145">Microsoft. WSMan. Management. WSManConfigContainerElement</span><span class="sxs-lookup"><span data-stu-id="380a6-145">Microsoft.WSMan.Management.WSManConfigContainerElement</span></span>        |

<span data-ttu-id="380a6-146">(\*) As unidades do sistema de arquivos variam em cada sistema.</span><span class="sxs-lookup"><span data-stu-id="380a6-146">(\*) The FileSystem drives vary on each system.</span></span>

<span data-ttu-id="380a6-147">Você também pode criar seus próprios provedores do PowerShell e pode instalar provedores que outras pessoas desenvolvem.</span><span class="sxs-lookup"><span data-stu-id="380a6-147">You can also create your own PowerShell providers, and you can install providers that others develop.</span></span> <span data-ttu-id="380a6-148">Para listar os provedores que estão disponíveis em sua sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-148">To list the providers that are available in your session, type:</span></span>

```powershell
Get-PSProvider
```

## <a name="installing-and-removing-providers"></a><span data-ttu-id="380a6-149">Instalando e removendo provedores</span><span class="sxs-lookup"><span data-stu-id="380a6-149">Installing and removing providers</span></span>

<span data-ttu-id="380a6-150">Normalmente, os provedores são instalados por meio de módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="380a6-150">Providers are typically installed via PowerShell modules.</span></span> <span data-ttu-id="380a6-151">A importação do módulo carrega o provedor em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="380a6-151">Importing the module loads the provider into your session.</span></span> <span data-ttu-id="380a6-152">Não é possível desinstalar os provedores internos.</span><span class="sxs-lookup"><span data-stu-id="380a6-152">You can't uninstall the built-in providers.</span></span> <span data-ttu-id="380a6-153">Você pode desinstalar provedores carregados por outros módulos.</span><span class="sxs-lookup"><span data-stu-id="380a6-153">You can uninstall providers loaded by other modules.</span></span>

<span data-ttu-id="380a6-154">Você pode descarregar um provedor da sessão atual usando o `Remove-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="380a6-154">You can unload a provider from the current session using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="380a6-155">Esse cmdlet não desinstala o provedor, mas torna o provedor indisponível na sessão.</span><span class="sxs-lookup"><span data-stu-id="380a6-155">This cmdlet doesn't uninstall the provider, but it makes the provider unavailable in the session.</span></span>

<span data-ttu-id="380a6-156">Você também pode usar o `Remove-PSDrive` cmdlet para remover qualquer unidade da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="380a6-156">You can also use the `Remove-PSDrive` cmdlet to remove any drive from the current session.</span></span> <span data-ttu-id="380a6-157">Esses dados na unidade não são afetados, mas a unidade não está mais disponível nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="380a6-157">This data on the drive isn't affected, but the drive is no longer available in that session.</span></span>

## <a name="viewing-providers"></a><span data-ttu-id="380a6-158">Exibindo provedores</span><span class="sxs-lookup"><span data-stu-id="380a6-158">Viewing providers</span></span>

<span data-ttu-id="380a6-159">Para exibir os provedores do PowerShell no seu computador, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-159">To view the PowerShell providers on your computer, type:</span></span>

```powershell
Get-PSProvider
```

<span data-ttu-id="380a6-160">A saída lista os provedores internos e os provedores que você adicionou à sessão.</span><span class="sxs-lookup"><span data-stu-id="380a6-160">The output lists the built-in providers and the providers that you added to the session.</span></span>

## <a name="the-provider-cmdlets"></a><span data-ttu-id="380a6-161">Os cmdlets do provedor</span><span class="sxs-lookup"><span data-stu-id="380a6-161">The provider cmdlets</span></span>

<span data-ttu-id="380a6-162">Os cmdlets a seguir foram projetados para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-162">The following cmdlets are designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="380a6-163">Você pode usar os mesmos cmdlets da mesma maneira para gerenciar os diferentes tipos de dados que os provedores expõem.</span><span class="sxs-lookup"><span data-stu-id="380a6-163">You can use the same cmdlets in the same way to manage the different types of data that providers expose.</span></span> <span data-ttu-id="380a6-164">Depois de aprender a gerenciar os dados de um provedor, você pode usar os mesmos procedimentos com os dados de qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-164">After you learn to manage the data of one provider, you can use the same procedures with the data from any provider.</span></span>

<span data-ttu-id="380a6-165">Por exemplo, o `New-Item` cmdlet cria um novo item.</span><span class="sxs-lookup"><span data-stu-id="380a6-165">For example, the `New-Item` cmdlet creates a new item.</span></span> <span data-ttu-id="380a6-166">Na `C:` unidade com suporte do provedor **FileSystem** , você pode usar o `New-Item` para criar um novo arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="380a6-166">In the `C:` drive that is supported by the **FileSystem** provider, you can use `New-Item` to create a new file or folder.</span></span> <span data-ttu-id="380a6-167">Nas unidades que têm suporte do provedor de **registro** , você pode usar o `New-Item` para criar uma nova chave do registro.</span><span class="sxs-lookup"><span data-stu-id="380a6-167">In the drives that are supported by the **Registry** provider, you can use `New-Item` to create a new registry key.</span></span> <span data-ttu-id="380a6-168">Na `Alias:` unidade, você pode usar `New-Item` para criar um novo alias.</span><span class="sxs-lookup"><span data-stu-id="380a6-168">In the `Alias:` drive, you can use `New-Item` to create a new alias.</span></span>

<span data-ttu-id="380a6-169">Para obter informações detalhadas sobre qualquer um dos seguintes cmdlets, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-169">For detailed information about any of the following cmdlets, type:</span></span>

```
Get-Help <cmdlet-name> -Detailed
```

### <a name="childitem-cmdlets"></a><span data-ttu-id="380a6-170">Cmdlets ChildItem</span><span class="sxs-lookup"><span data-stu-id="380a6-170">ChildItem cmdlets</span></span>

- [<span data-ttu-id="380a6-171">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="380a6-171">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="content-cmdlets"></a><span data-ttu-id="380a6-172">Cmdlets de conteúdo</span><span class="sxs-lookup"><span data-stu-id="380a6-172">Content Cmdlets</span></span>

- [<span data-ttu-id="380a6-173">Add-Content</span><span class="sxs-lookup"><span data-stu-id="380a6-173">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="380a6-174">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="380a6-174">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="380a6-175">Get-Content</span><span class="sxs-lookup"><span data-stu-id="380a6-175">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="380a6-176">Set-Content</span><span class="sxs-lookup"><span data-stu-id="380a6-176">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="item-cmdlets"></a><span data-ttu-id="380a6-177">Cmdlets de item</span><span class="sxs-lookup"><span data-stu-id="380a6-177">Item Cmdlets</span></span>

- [<span data-ttu-id="380a6-178">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-178">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="380a6-179">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-179">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="380a6-180">Get-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-180">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="380a6-181">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-181">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="380a6-182">Move-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-182">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="380a6-183">New-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-183">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="380a6-184">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-184">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="380a6-185">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-185">Rename-Item</span></span>](xref:Microsoft.PowerShell.Management.Rename-Item)
- [<span data-ttu-id="380a6-186">Set-Item</span><span class="sxs-lookup"><span data-stu-id="380a6-186">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

### <a name="itemproperty-cmdlets"></a><span data-ttu-id="380a6-187">Cmdlets ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-187">ItemProperty cmdlets</span></span>

- [<span data-ttu-id="380a6-188">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-188">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="380a6-189">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-189">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)
- [<span data-ttu-id="380a6-190">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-190">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="380a6-191">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-191">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)
- [<span data-ttu-id="380a6-192">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-192">New-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.New-ItemProperty)
- [<span data-ttu-id="380a6-193">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-193">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="380a6-194">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-194">Rename-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Rename-ItemProperty)
- [<span data-ttu-id="380a6-195">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="380a6-195">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

### <a name="location-cmdlets"></a><span data-ttu-id="380a6-196">Cmdlets de local</span><span class="sxs-lookup"><span data-stu-id="380a6-196">Location cmdlets</span></span>

- [<span data-ttu-id="380a6-197">Get-Location</span><span class="sxs-lookup"><span data-stu-id="380a6-197">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="380a6-198">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="380a6-198">Pop-Location</span></span>](xref:Microsoft.PowerShell.Management.Pop-Location)
- [<span data-ttu-id="380a6-199">Push-Location</span><span class="sxs-lookup"><span data-stu-id="380a6-199">Push-Location</span></span>](xref:Microsoft.PowerShell.Management.Push-Location)
- [<span data-ttu-id="380a6-200">Set-Location</span><span class="sxs-lookup"><span data-stu-id="380a6-200">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

### <a name="path-cmdlets"></a><span data-ttu-id="380a6-201">Cmdlets de caminho</span><span class="sxs-lookup"><span data-stu-id="380a6-201">Path cmdlets</span></span>

- [<span data-ttu-id="380a6-202">Join-Path</span><span class="sxs-lookup"><span data-stu-id="380a6-202">Join-Path</span></span>](xref:Microsoft.PowerShell.Management.Join-Path)
- [<span data-ttu-id="380a6-203">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="380a6-203">Convert-Path</span></span>](xref:Microsoft.PowerShell.Management.Convert-Path)
- [<span data-ttu-id="380a6-204">Split-Path</span><span class="sxs-lookup"><span data-stu-id="380a6-204">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)
- [<span data-ttu-id="380a6-205">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="380a6-205">Resolve-Path</span></span>](xref:Microsoft.PowerShell.Management.Resolve-Path)
- [<span data-ttu-id="380a6-206">Test-Path</span><span class="sxs-lookup"><span data-stu-id="380a6-206">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="psdrive-cmdlets"></a><span data-ttu-id="380a6-207">Cmdlets PSDrive</span><span class="sxs-lookup"><span data-stu-id="380a6-207">PSDrive cmdlets</span></span>

- [<span data-ttu-id="380a6-208">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="380a6-208">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="380a6-209">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="380a6-209">New-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.New-PSDrive)
- [<span data-ttu-id="380a6-210">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="380a6-210">Remove-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Remove-PSDrive)

### <a name="psprovider-cmdlets"></a><span data-ttu-id="380a6-211">Cmdlets PSProvider</span><span class="sxs-lookup"><span data-stu-id="380a6-211">PSProvider Cmdlets</span></span>

- [<span data-ttu-id="380a6-212">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="380a6-212">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

## <a name="viewing-provider-data"></a><span data-ttu-id="380a6-213">Exibindo dados do provedor</span><span class="sxs-lookup"><span data-stu-id="380a6-213">Viewing provider data</span></span>

<span data-ttu-id="380a6-214">O principal benefício de um provedor é que ele expõe seus dados de uma maneira familiar e consistente.</span><span class="sxs-lookup"><span data-stu-id="380a6-214">The primary benefit of a provider is that it exposes its data in a familiar and consistent way.</span></span> <span data-ttu-id="380a6-215">O modelo de apresentação de dados é uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="380a6-215">The model for data presentation is a file system drive.</span></span>

<span data-ttu-id="380a6-216">O provedor permite exibir, navegar e alterar itens no armazenamento de dados, como se eles fossem dados em um sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="380a6-216">The provider allows you to view, navigate, and change items in the data store as though they were data in a file system.</span></span> <span data-ttu-id="380a6-217">O armazenamento de dados é acessado pelo nome da unidade que ele suporta.</span><span class="sxs-lookup"><span data-stu-id="380a6-217">The data store is accessed by the name of the drive that it supports.</span></span>

<span data-ttu-id="380a6-218">A unidade é listada na exibição padrão do `Get-PSProvider` cmdlet, mas você pode obter informações sobre a unidade do provedor usando o `Get-PSDrive` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="380a6-218">The drive is listed in the default display of the `Get-PSProvider` cmdlet, but you can get information about the provider drive using the `Get-PSDrive` cmdlet.</span></span> <span data-ttu-id="380a6-219">Por exemplo, para obter todas as propriedades da unidade Function:, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-219">For example, to get all the properties of the Function: drive, type:</span></span>

```powershell
Get-PSDrive Function | Format-List *
```

<span data-ttu-id="380a6-220">Você pode exibir e percorrer os dados em uma unidade de provedor da mesma forma como faria em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="380a6-220">You can view and move through the data in a provider drive just as you would on a file system drive.</span></span>

<span data-ttu-id="380a6-221">Para exibir o conteúdo de uma unidade de provedor, use os cmdlets Get-Item ou Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="380a6-221">To view the contents of a provider drive, use the Get-Item or Get-ChildItem cmdlets.</span></span> <span data-ttu-id="380a6-222">Digite o nome da unidade seguido por dois-pontos (:).</span><span class="sxs-lookup"><span data-stu-id="380a6-222">Type the drive name followed by a colon (:).</span></span> <span data-ttu-id="380a6-223">Por exemplo, para exibir o conteúdo da unidade Alias:, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-223">For example, to view the contents of the Alias: drive, type:</span></span>

```powershell
Get-Item alias:
```

<span data-ttu-id="380a6-224">Você pode exibir e gerenciar os dados em qualquer unidade de outra unidade, incluindo o nome da unidade no caminho.</span><span class="sxs-lookup"><span data-stu-id="380a6-224">You can view and manage the data in any drive from another drive by including the drive name in the path.</span></span> <span data-ttu-id="380a6-225">Por exemplo, para exibir a chave do registro HKLM\Software na unidade HKLM: de outra unidade, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-225">For example, to view the HKLM\Software registry key in the HKLM: drive from another drive, type:</span></span>

```powershell
Get-ChildItem HKLM:\SOFTWARE\
```

<span data-ttu-id="380a6-226">Para abrir a unidade, use o cmdlet Set-Location.</span><span class="sxs-lookup"><span data-stu-id="380a6-226">To open the drive, use the Set-Location cmdlet.</span></span> <span data-ttu-id="380a6-227">Lembre-se dos dois-pontos ao especificar o caminho da unidade.</span><span class="sxs-lookup"><span data-stu-id="380a6-227">Remember the colon when you specify the drive path.</span></span> <span data-ttu-id="380a6-228">Por exemplo, para alterar o local para o diretório raiz da unidade CERT:, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-228">For example, to change your location to the root directory of the Cert: drive, type:</span></span>

```powershell
Set-Location cert:
```

<span data-ttu-id="380a6-229">Em seguida, para exibir o conteúdo da unidade CERT:, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-229">Then, to view the contents of the Cert: drive, type:</span></span>

```powershell
Get-ChildItem
```

## <a name="moving-through-hierarchical-data"></a><span data-ttu-id="380a6-230">Movimentação por meio de dados hierárquicos</span><span class="sxs-lookup"><span data-stu-id="380a6-230">Moving through hierarchical data</span></span>

<span data-ttu-id="380a6-231">Você pode percorrer uma unidade de provedor assim como faria com uma unidade de disco rígido.</span><span class="sxs-lookup"><span data-stu-id="380a6-231">You can move through a provider drive just as you would a hard disk drive.</span></span>
<span data-ttu-id="380a6-232">Se os dados forem organizados em uma hierarquia de itens dentro de itens, use uma barra invertida ( `\` ) para indicar um item filho.</span><span class="sxs-lookup"><span data-stu-id="380a6-232">If the data is arranged in a hierarchy of items within items, use a backslash (`\`) to indicate a child item.</span></span> <span data-ttu-id="380a6-233">Use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="380a6-233">Use the following format:</span></span>

```
drive:\location\child-location\...
```

<span data-ttu-id="380a6-234">Por exemplo, para alterar seu local para a chave do registro HKLM\Software, digite um comando Set-Location, como:</span><span class="sxs-lookup"><span data-stu-id="380a6-234">For example, to change your location to the HKLM\Software registry key, type a Set-Location command, such as:</span></span>

```powershell
Set-Location HKLM:\SOFTWARE\
```

<span data-ttu-id="380a6-235">Se qualquer elemento no nome totalmente qualificado incluir espaços, você deverá colocar o nome entre aspas duplas ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="380a6-235">If any element in the fully qualified name includes spaces, you must enclose the name in double-quotation marks (`"`).</span></span> <span data-ttu-id="380a6-236">O exemplo a seguir mostra um caminho totalmente qualificado que inclui espaços.</span><span class="sxs-lookup"><span data-stu-id="380a6-236">The following example shows a fully qualified path that includes spaces.</span></span>

```
"C:\Program Files\Internet Explorer\iexplore.exe"
```

<span data-ttu-id="380a6-237">Você também pode usar referências relativas a locais.</span><span class="sxs-lookup"><span data-stu-id="380a6-237">You can also use relative references to locations.</span></span> <span data-ttu-id="380a6-238">Um ponto ( `.` ) representa o local atual.</span><span class="sxs-lookup"><span data-stu-id="380a6-238">A dot (`.`) represents the current location.</span></span> <span data-ttu-id="380a6-239">Por exemplo, se você estiver na `HKLM:\Software\Microsoft` chave do registro e desejar listar as subchaves do registro na `HKLM:\Software\Microsoft\PowerShell` chave, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="380a6-239">For example, if you are in the `HKLM:\Software\Microsoft` registry key, and you want to list the registry subkeys in the `HKLM:\Software\Microsoft\PowerShell` key, type the following command:</span></span>

```powershell
Get-ChildItem .\PowerShell
```

<span data-ttu-id="380a6-240">Além disso, os pontos duplos ( `..` ) referem-se ao diretório ou contêiner diretamente acima do seu local atual.</span><span class="sxs-lookup"><span data-stu-id="380a6-240">Also, double-dots (`..`) refers to the directory or container directly above your current location.</span></span> <span data-ttu-id="380a6-241">Você pode usar pontos duplos ( `..` ) para navegar por uma hierarquia de provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-241">You can use double-dots (`..`) to navigate through a provider hierarchy.</span></span>

```
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\> cd ..\..\LanmanWorkstation\Parameters
PS HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters>
```

## <a name="provider-home"></a><span data-ttu-id="380a6-242">Página inicial do provedor</span><span class="sxs-lookup"><span data-stu-id="380a6-242">Provider Home</span></span>

<span data-ttu-id="380a6-243">Os provedores também têm um local de **residência** .</span><span class="sxs-lookup"><span data-stu-id="380a6-243">Providers also have a **Home** location.</span></span>  <span data-ttu-id="380a6-244">Esse local é compartilhado por todos os `PSDrives` apoiados pelo provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-244">This location is shared by all `PSDrives` backed by the provider.</span></span> <span data-ttu-id="380a6-245">Ele pode ser recuperado exibindo a propriedade **Home** do provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-245">It can be retrieved by viewing the **Home** property of the provider.</span></span>

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

<span data-ttu-id="380a6-246">O provedor **FileSystem** é o único provedor que tem um valor padrão para **Home**.</span><span class="sxs-lookup"><span data-stu-id="380a6-246">The **FileSystem** provider is the only provider that has a default value for **Home**.</span></span> <span data-ttu-id="380a6-247">É o mesmo valor que `$Home` .</span><span class="sxs-lookup"><span data-stu-id="380a6-247">It's the same value as `$Home`.</span></span> <span data-ttu-id="380a6-248">Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="380a6-248">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="380a6-249">Você pode definir o diretório **base** para um provedor, para a sessão atual, usando sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="380a6-249">You can set the **Home** directory for a provider, for the current session, using its property.</span></span>

```powershell
(Get-PSProvider FileSystem).Home = "C:\"
```

<span data-ttu-id="380a6-250">O `~` caractere pode ser usado para representar o diretório base do provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-250">The `~` character can be used to represent the provider's home directory.</span></span>
<span data-ttu-id="380a6-251">Se o provedor não tiver um local de **residência** definido, você verá um erro.</span><span class="sxs-lookup"><span data-stu-id="380a6-251">If the provider doesn't have a **Home** location set, you see an error.</span></span>

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

## <a name="finding-dynamic-parameters"></a><span data-ttu-id="380a6-252">Localizando parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="380a6-252">Finding dynamic parameters</span></span>

<span data-ttu-id="380a6-253">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados a um cmdlet por um provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-253">Dynamic parameters are cmdlet parameters that are added to a cmdlet by a provider.</span></span> <span data-ttu-id="380a6-254">Esses parâmetros estão disponíveis somente quando o cmdlet é usado com o provedor que os adicionou.</span><span class="sxs-lookup"><span data-stu-id="380a6-254">These parameters are available only when the cmdlet is used with the provider that added them.</span></span>

<span data-ttu-id="380a6-255">Por exemplo, a `Cert:` unidade adiciona o parâmetro **CodeSigningCert** aos `Get-Item` `Get-ChildItem` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="380a6-255">For example, the `Cert:` drive adds the **CodeSigningCert** parameter to the `Get-Item` and `Get-ChildItem` cmdlets.</span></span> <span data-ttu-id="380a6-256">Você pode usar esse parâmetro somente quando usar `Get-Item` ou `Get-ChildItem` na `Cert:` unidade.</span><span class="sxs-lookup"><span data-stu-id="380a6-256">You can use this parameter only when you use `Get-Item` or `Get-ChildItem` in the `Cert:` drive.</span></span>

<span data-ttu-id="380a6-257">Para obter uma lista dos parâmetros dinâmicos aos quais um provedor dá suporte, consulte o arquivo de ajuda para o provedor.</span><span class="sxs-lookup"><span data-stu-id="380a6-257">For a list of the dynamic parameters that a provider supports, see the Help file for the provider.</span></span> <span data-ttu-id="380a6-258">Tipo:</span><span class="sxs-lookup"><span data-stu-id="380a6-258">Type:</span></span>

```
Get-Help <provider-name>
```

<span data-ttu-id="380a6-259">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="380a6-259">For example:</span></span>

```powershell
Get-Help certificate
```

## <a name="learning-about-providers"></a><span data-ttu-id="380a6-260">Aprendendo sobre provedores</span><span class="sxs-lookup"><span data-stu-id="380a6-260">Learning about providers</span></span>

<span data-ttu-id="380a6-261">Embora todos os dados do provedor apareçam nas unidades e você use os mesmos métodos para movê-los, a similaridade é interrompida.</span><span class="sxs-lookup"><span data-stu-id="380a6-261">Although all provider data appears in drives and you use the same methods to move through them, the similarity stops there.</span></span> <span data-ttu-id="380a6-262">Os armazenamentos de dados que o provedor expõe podem ser tão variados quanto Active Directory locais e caixas de correio do Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="380a6-262">The data stores that the provider exposes can be as varied as Active Directory locations and Microsoft Exchange Server mailboxes.</span></span>

<span data-ttu-id="380a6-263">Para obter informações sobre provedores individuais do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-263">For information about individual PowerShell providers, type:</span></span>

```
Get-Help <ProviderName>
```

<span data-ttu-id="380a6-264">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="380a6-264">For example:</span></span>

```powershell
Get-Help registry
```

<span data-ttu-id="380a6-265">Para obter uma lista de tópicos de ajuda sobre os provedores, digite:</span><span class="sxs-lookup"><span data-stu-id="380a6-265">For a list of Help topics about the providers, type:</span></span>

```powershell
Get-Help * -Category Provider
```

## <a name="see-also"></a><span data-ttu-id="380a6-266">Consulte também</span><span class="sxs-lookup"><span data-stu-id="380a6-266">See also</span></span>

[<span data-ttu-id="380a6-267">about_Locations</span><span class="sxs-lookup"><span data-stu-id="380a6-267">about_Locations</span></span>](about_Locations.md)

[<span data-ttu-id="380a6-268">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="380a6-268">about_Path_Syntax</span></span>](about_Path_Syntax.md)

