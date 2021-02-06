---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: f9cba90ffa69d04df196f4062c8f190d545b9bc3
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599030"
---
# <span data-ttu-id="8447b-102">Find-Module</span><span class="sxs-lookup"><span data-stu-id="8447b-102">Find-Module</span></span>

## <span data-ttu-id="8447b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8447b-103">SYNOPSIS</span></span>
<span data-ttu-id="8447b-104">Localiza módulos em um repositório que corresponde aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="8447b-104">Finds modules in a repository that match specified criteria.</span></span>

## <span data-ttu-id="8447b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8447b-105">SYNTAX</span></span>

### <span data-ttu-id="8447b-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="8447b-106">All</span></span>

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="8447b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8447b-107">DESCRIPTION</span></span>

<span data-ttu-id="8447b-108">O `Find-Module` cmdlet localiza módulos em um repositório que corresponde aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="8447b-108">The `Find-Module` cmdlet finds modules in a repository that match the specified criteria.</span></span>
<span data-ttu-id="8447b-109">`Find-Module` Retorna um objeto **PSRepositoryItemInfo** para cada módulo que encontrar.</span><span class="sxs-lookup"><span data-stu-id="8447b-109">`Find-Module` returns a **PSRepositoryItemInfo** object for each module it finds.</span></span> <span data-ttu-id="8447b-110">Os objetos podem ser enviados ao pipeline para cmdlets como `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="8447b-110">The objects can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

<span data-ttu-id="8447b-111">Na primeira vez que o `Find-Module` tentar usar um repositório, você poderá ser solicitado a instalar atualizações.</span><span class="sxs-lookup"><span data-stu-id="8447b-111">The first time `Find-Module` attempts to use a repository, you might be prompted to install updates.</span></span>
<span data-ttu-id="8447b-112">Se a origem do repositório não estiver registrada com o `Register-PSRepository` cmdlet, um erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="8447b-112">If the repository source is not registered with `Register-PSRepository` cmdlet, an error is returned.</span></span>

<span data-ttu-id="8447b-113">`Find-Module` Retorna a versão mais recente de um módulo se nenhum parâmetro for usado para limitar a versão.</span><span class="sxs-lookup"><span data-stu-id="8447b-113">`Find-Module` returns the newest version of a module if no parameters are used that limit the version.</span></span> <span data-ttu-id="8447b-114">Para obter uma lista de um repositório de versões de um módulo, use o **parâmetro AllModules**.</span><span class="sxs-lookup"><span data-stu-id="8447b-114">To get a repository's list of a module's versions, use the parameter **AllVersions**.</span></span>

<span data-ttu-id="8447b-115">Se o parâmetro **MinimumVersion** for especificado, `Find-Module` retornará a versão do módulo que é igual ou maior que o mínimo.</span><span class="sxs-lookup"><span data-stu-id="8447b-115">If the **MinimumVersion** parameter is specified, `Find-Module` returns the module's version that is equal to or greater than the minimum.</span></span> <span data-ttu-id="8447b-116">Se houver uma versão mais recente disponível no repositório, a versão mais recente será retornada.</span><span class="sxs-lookup"><span data-stu-id="8447b-116">If there is a newer version available in the repository, the newer version is returned.</span></span>

<span data-ttu-id="8447b-117">Se o parâmetro **MaximumVersion** for especificado, `Find-Module` retornará a versão mais recente do módulo que não exceda a versão especificada.</span><span class="sxs-lookup"><span data-stu-id="8447b-117">If the **MaximumVersion** parameter is specified, `Find-Module` returns the newest version of the module that does not exceed the version specified.</span></span>

<span data-ttu-id="8447b-118">Se o parâmetro **RequiredVersion** for especificado, `Find-Module` retornará apenas a versão do módulo que é uma correspondência exata com a versão especificada.</span><span class="sxs-lookup"><span data-stu-id="8447b-118">If the **RequiredVersion** parameter is specified, `Find-Module` only returns the module version that is an exact match to the specified version.</span></span> <span data-ttu-id="8447b-119">`Find-Module` pesquisa todos os módulos disponíveis, pois podem ocorrer conflitos de nome entre origens.</span><span class="sxs-lookup"><span data-stu-id="8447b-119">`Find-Module` searches through all available modules, because name conflicts between sources can occur.</span></span>

<span data-ttu-id="8447b-120">Os exemplos a seguir usam o [Galeria do PowerShell](https://www.powershellgallery.com/) como o único repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="8447b-120">The following examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="8447b-121">`Get-PSRepository` exibe os repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="8447b-121">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="8447b-122">Se você tiver vários repositórios registrados, use o `-Repository` parâmetro para especificar o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-122">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="8447b-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8447b-123">EXAMPLES</span></span>

### <span data-ttu-id="8447b-124">Exemplo 1: localizar um módulo por nome</span><span class="sxs-lookup"><span data-stu-id="8447b-124">Example 1: Find a module by name</span></span>

<span data-ttu-id="8447b-125">Este exemplo localiza um módulo no repositório padrão.</span><span class="sxs-lookup"><span data-stu-id="8447b-125">This example finds a module in the default repository.</span></span>

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

<span data-ttu-id="8447b-126">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="8447b-126">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>

### <span data-ttu-id="8447b-127">Exemplo 2: localizar módulos com nomes semelhantes</span><span class="sxs-lookup"><span data-stu-id="8447b-127">Example 2: Find modules with similar names</span></span>

<span data-ttu-id="8447b-128">Este exemplo usa o curinga asterisco ( `*` ) para localizar módulos com nomes semelhantes.</span><span class="sxs-lookup"><span data-stu-id="8447b-128">This example uses the asterisk (`*`) wildcard to find modules with similar names.</span></span>

```powershell
Find-Module -Name PowerShell*
```

```Output
Version   Name                            Repository    Description
-------   ----                            ----------    -----------
0.4.0     powershell-yaml                 PSGallery     Powershell module for serializing and...
2.1.0     PowerShellGet                   PSGallery     PowerShell module with commands for...
1.9       Powershell.Helper.Extension     PSGallery     # Powershell.Helper.Extension...
3.1       PowerShellHumanizer             PSGallery     PowerShell Humanizer wraps Humanizer...
4.0       PowerShellISEModule             PSGallery     a module that adds capability to the ISE
```

<span data-ttu-id="8447b-129">O `Find-Module` cmdlet usa o parâmetro **Name** com o curinga asterisco ( `*` ) para localizar todos os módulos que contêm o **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8447b-129">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to find all modules that contain **PowerShell**.</span></span>

### <span data-ttu-id="8447b-130">Exemplo 3: localizar um módulo por versão mínima</span><span class="sxs-lookup"><span data-stu-id="8447b-130">Example 3: Find a module by minimum version</span></span>

<span data-ttu-id="8447b-131">Este exemplo pesquisa a versão mínima de um módulo.</span><span class="sxs-lookup"><span data-stu-id="8447b-131">This example searches for a module's minimum version.</span></span> <span data-ttu-id="8447b-132">Se o repositório contiver uma versão mais recente do módulo, a versão mais recente será retornada.</span><span class="sxs-lookup"><span data-stu-id="8447b-132">If the repository contains a newer version of the module, the newer version is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="8447b-133">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="8447b-133">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="8447b-134">**MinimumVersion** especifica a versão **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="8447b-134">The **MinimumVersion** specifies version **1.6.5**.</span></span> <span data-ttu-id="8447b-135">`Find-Module` Retorna o PowerShellGet versão **2.1.0** porque ele excede a versão mínima e é a versão mais atual.</span><span class="sxs-lookup"><span data-stu-id="8447b-135">`Find-Module` returns PowerShellGet version **2.1.0** because it exceeds the minimum version and is the most current version.</span></span>

### <span data-ttu-id="8447b-136">Exemplo 4: localizar um módulo por versão específica</span><span class="sxs-lookup"><span data-stu-id="8447b-136">Example 4: Find a module by specific version</span></span>

<span data-ttu-id="8447b-137">Este exemplo retorna um objeto que representa a versão específica de um módulo.</span><span class="sxs-lookup"><span data-stu-id="8447b-137">This example returns an object that represents a module's specific version.</span></span> <span data-ttu-id="8447b-138">Se a versão especificada não for encontrada, um erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="8447b-138">If the specified version is not found, an error is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="8447b-139">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="8447b-139">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="8447b-140">O parâmetro **RequiredVersion** especifica a versão **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="8447b-140">The **RequiredVersion** parameter specifies version **1.6.5**.</span></span>

### <span data-ttu-id="8447b-141">Exemplo 5: localizar um módulo em um repositório específico</span><span class="sxs-lookup"><span data-stu-id="8447b-141">Example 5: Find a module in a specific repository</span></span>

<span data-ttu-id="8447b-142">Este exemplo usa o parâmetro **Repository** para localizar um módulo em um repositório específico.</span><span class="sxs-lookup"><span data-stu-id="8447b-142">This example uses the **Repository** parameter to find a module in a specific repository.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="8447b-143">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="8447b-143">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="8447b-144">O parâmetro **Repository** especifica a pesquisa no repositório **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="8447b-144">The **Repository** parameter specifies to search the **PSGallery** repository.</span></span>

### <span data-ttu-id="8447b-145">Exemplo 6: localizar um módulo em vários repositórios</span><span class="sxs-lookup"><span data-stu-id="8447b-145">Example 6: Find a module in multiple repositories</span></span>

<span data-ttu-id="8447b-146">Este exemplo usa o `Register-PSRepository` para especificar um repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-146">This example uses the `Register-PSRepository` to specify a repository.</span></span> <span data-ttu-id="8447b-147">`Find-Module` usa o repositório para pesquisar um módulo.</span><span class="sxs-lookup"><span data-stu-id="8447b-147">`Find-Module` uses the repository to search for a module.</span></span>

```powershell
Register-PSRepository -Name MySource -SourceLocation https://www.myget.org/F/powershellgetdemo/
Find-Module -Name Contoso* -Repository PSGallery, MySource
```

```Output
Repository    Version   Name             Description
----------    -------   ----             -----------
PSGallery     2.0.0.0   ContosoServer    Cmdlets and DSC resources for managing Contoso Server...
MySource      1.2.0.0   ContosoClient    Cmdlets and DSC resources for managing Contoso Client...
```

<span data-ttu-id="8447b-148">O `Register-PSRepository` cmdlet registra um novo repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-148">The `Register-PSRepository` cmdlet registers a new repository.</span></span> <span data-ttu-id="8447b-149">O parâmetro **Name** atribui o nome **MySource**.</span><span class="sxs-lookup"><span data-stu-id="8447b-149">The **Name** parameter assigns the name **MySource**.</span></span> <span data-ttu-id="8447b-150">O parâmetro **SourceLocation** especifica o endereço do repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-150">The **SourceLocation** parameter specifies the repository's address.</span></span>

<span data-ttu-id="8447b-151">O `Find-Module` cmdlet usa o parâmetro **Name** com o curinga asterisco ( `*` ) para especificar o módulo **contoso** .</span><span class="sxs-lookup"><span data-stu-id="8447b-151">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to specify the **Contoso** module.</span></span> <span data-ttu-id="8447b-152">O parâmetro **Repository** especifica a pesquisa de dois repositórios, **PSGallery** e **MySource**.</span><span class="sxs-lookup"><span data-stu-id="8447b-152">The **Repository** parameter specifies to search two repositories, **PSGallery** and **MySource**.</span></span>

### <span data-ttu-id="8447b-153">Exemplo 7: localizar um módulo que contém um recurso de DSC</span><span class="sxs-lookup"><span data-stu-id="8447b-153">Example 7: Find a module that contains a DSC resource</span></span>

<span data-ttu-id="8447b-154">Esse comando retorna módulos que contêm recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="8447b-154">This command returns modules that contain DSC resources.</span></span> <span data-ttu-id="8447b-155">O parâmetro **includes** tem quatro funcionalidades predefinidas que são usadas para pesquisar o repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-155">The **Includes** parameter has four predefined functionalities that are used to search the repository.</span></span> <span data-ttu-id="8447b-156">Use Tab-Complete para exibir as quatro funcionalidades com suporte no parâmetro **includes** .</span><span class="sxs-lookup"><span data-stu-id="8447b-156">Use tab-complete to display the four functionalities supported by the **Includes** parameter.</span></span>

```powershell
Find-Module -Repository PSGallery -Includes DscResource
```

```Output
Version     Name                            Repository    Description
-------     ----                            ----------    -----------
2.7.0       Carbon                          PSGallery     Carbon is a PowerShell module...
8.5.0.0     xPSDesiredStateConfiguration    PSGallery     The xPSDesiredStateConfiguration module...
1.3.1       PackageManagement               PSGallery     PackageManagement (a.k.a. OneGet) is...
2.7.0.0     xWindowsUpdate                  PSGallery     Module with DSC Resources...
3.2.0.0     xCertificate                    PSGallery     This module includes DSC resources...
3.1.0.0     xPowerShellExecutionPolicy      PSGallery     This DSC resource can change the user...
```

<span data-ttu-id="8447b-157">O `Find-Module` cmdlet usa o parâmetro **Repository** para pesquisar o repositório, **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="8447b-157">The `Find-Module` cmdlet uses the **Repository** parameter to search the repository, **PSGallery**.</span></span>
<span data-ttu-id="8447b-158">O parâmetro **includes** especifica **DscResource**, que é uma funcionalidade que o parâmetro pode pesquisar no repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-158">The **Includes** parameter specifies **DscResource**, which is a functionality that the parameter can search for in the repository.</span></span>

### <span data-ttu-id="8447b-159">Exemplo 8: localizar um módulo com um filtro</span><span class="sxs-lookup"><span data-stu-id="8447b-159">Example 8: Find a module with a filter</span></span>

<span data-ttu-id="8447b-160">Neste exemplo, para localizar módulos, um filtro é usado para pesquisar o repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-160">In this example, to find modules, a filter is used to search the repository.</span></span>

<span data-ttu-id="8447b-161">Para um repositório baseado em NuGet, o parâmetro de **filtro** pesquisa o nome, a descrição e as marcas do argumento.</span><span class="sxs-lookup"><span data-stu-id="8447b-161">For a NuGet-based repository, the **Filter** parameter searches through the name, description, and tags for the argument.</span></span>

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

<span data-ttu-id="8447b-162">O `Find-Module` cmdlet usa o parâmetro **Filter** para pesquisar no repositório o **AppDomain**.</span><span class="sxs-lookup"><span data-stu-id="8447b-162">The `Find-Module` cmdlet uses the **Filter** parameter to search the repository for **AppDomain**.</span></span>

## <span data-ttu-id="8447b-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8447b-163">PARAMETERS</span></span>

### <span data-ttu-id="8447b-164">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="8447b-164">-AllowPrerelease</span></span>

<span data-ttu-id="8447b-165">Inclui nos módulos de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="8447b-165">Includes in the results modules marked as a pre-release.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-166">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="8447b-166">-AllVersions</span></span>

<span data-ttu-id="8447b-167">Especifica para incluir todas as versões de um módulo nos resultados.</span><span class="sxs-lookup"><span data-stu-id="8447b-167">Specifies to include all versions of a module in the results.</span></span> <span data-ttu-id="8447b-168">Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="8447b-168">You cannot use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-169">-Command</span><span class="sxs-lookup"><span data-stu-id="8447b-169">-Command</span></span>

<span data-ttu-id="8447b-170">Especifica uma matriz de comandos para localizar em módulos.</span><span class="sxs-lookup"><span data-stu-id="8447b-170">Specifies an array of commands to find in modules.</span></span> <span data-ttu-id="8447b-171">Um comando pode ser uma função ou um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8447b-171">A command can be a function or workflow.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="8447b-172">-Credential</span></span>

<span data-ttu-id="8447b-173">Especifica uma conta de usuário que tem direitos para instalar um módulo para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="8447b-173">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-174">-DscResource</span><span class="sxs-lookup"><span data-stu-id="8447b-174">-DscResource</span></span>

<span data-ttu-id="8447b-175">Especifica o nome, ou parte do nome, dos módulos que contêm recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="8447b-175">Specifies the name, or part of the name, of modules that contain DSC resources.</span></span> <span data-ttu-id="8447b-176">Por convenções do PowerShell, o executa uma pesquisa **ou** quando você fornece vários argumentos.</span><span class="sxs-lookup"><span data-stu-id="8447b-176">Per PowerShell conventions, performs an **OR** search when you provide multiple arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-177">-Filter</span><span class="sxs-lookup"><span data-stu-id="8447b-177">-Filter</span></span>

<span data-ttu-id="8447b-178">Especifica um filtro com base na sintaxe de pesquisa específica do provedor **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="8447b-178">Specifies a filter based on the **PackageManagement** provider-specific search syntax.</span></span> <span data-ttu-id="8447b-179">Para módulos NuGet, esse parâmetro é o equivalente de Pesquisar usando a barra de pesquisa no site [Galeria do PowerShell](https://www.powershellgallery.com/) .</span><span class="sxs-lookup"><span data-stu-id="8447b-179">For NuGet modules, this parameter is the equivalent of searching by using the Search bar on the [PowerShell Gallery](https://www.powershellgallery.com/) website.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-180">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="8447b-180">-IncludeDependencies</span></span>

<span data-ttu-id="8447b-181">Indica que essa operação inclui todos os módulos que dependem do módulo especificado no parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="8447b-181">Indicates that this operation includes all modules that are dependent upon the module specified in the **Name** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-182">-Inclui</span><span class="sxs-lookup"><span data-stu-id="8447b-182">-Includes</span></span>

<span data-ttu-id="8447b-183">Retorna somente os módulos que incluem tipos específicos de funcionalidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8447b-183">Returns only those modules that include specific kinds of PowerShell functionality.</span></span> <span data-ttu-id="8447b-184">Por exemplo, talvez você queira apenas localizar módulos que incluem **DSCResource**.</span><span class="sxs-lookup"><span data-stu-id="8447b-184">For example, you might only want to find modules that include **DSCResource**.</span></span> <span data-ttu-id="8447b-185">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="8447b-185">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8447b-186">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8447b-186">Cmdlet</span></span>
- <span data-ttu-id="8447b-187">DscResource</span><span class="sxs-lookup"><span data-stu-id="8447b-187">DscResource</span></span>
- <span data-ttu-id="8447b-188">Função</span><span class="sxs-lookup"><span data-stu-id="8447b-188">Function</span></span>
- <span data-ttu-id="8447b-189">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="8447b-189">RoleCapability</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: DscResource, Cmdlet, Function, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-190">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8447b-190">-MaximumVersion</span></span>

<span data-ttu-id="8447b-191">Especifica a versão máxima ou mais recente do módulo a ser incluída nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8447b-191">Specifies the maximum, or latest, version of the module to include in the search results.</span></span>
<span data-ttu-id="8447b-192">**MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="8447b-192">**MaximumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-193">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8447b-193">-MinimumVersion</span></span>

<span data-ttu-id="8447b-194">Especifica a versão mínima do módulo a ser incluída nos resultados.</span><span class="sxs-lookup"><span data-stu-id="8447b-194">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="8447b-195">**MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="8447b-195">**MinimumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-196">-Name</span><span class="sxs-lookup"><span data-stu-id="8447b-196">-Name</span></span>

<span data-ttu-id="8447b-197">Especifica os nomes dos módulos a serem pesquisados no repositório.</span><span class="sxs-lookup"><span data-stu-id="8447b-197">Specifies the names of modules to search for in the repository.</span></span> <span data-ttu-id="8447b-198">Uma lista separada por vírgulas de nomes de módulo é aceita.</span><span class="sxs-lookup"><span data-stu-id="8447b-198">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="8447b-199">Caracteres curinga são aceitos.</span><span class="sxs-lookup"><span data-stu-id="8447b-199">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-200">-Proxy</span><span class="sxs-lookup"><span data-stu-id="8447b-200">-Proxy</span></span>

<span data-ttu-id="8447b-201">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="8447b-201">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-202">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="8447b-202">-ProxyCredential</span></span>

<span data-ttu-id="8447b-203">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="8447b-203">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-204">-Repositório</span><span class="sxs-lookup"><span data-stu-id="8447b-204">-Repository</span></span>

<span data-ttu-id="8447b-205">Use o parâmetro **Repository** para especificar qual repositório procurar um módulo.</span><span class="sxs-lookup"><span data-stu-id="8447b-205">Use the **Repository** parameter to specify which repository to search for a module.</span></span> <span data-ttu-id="8447b-206">Usado quando vários repositórios são registrados.</span><span class="sxs-lookup"><span data-stu-id="8447b-206">Used when multiple repositories are registered.</span></span> <span data-ttu-id="8447b-207">Aceita uma lista separada por vírgulas de repositórios.</span><span class="sxs-lookup"><span data-stu-id="8447b-207">Accepts a comma-separated list of repositories.</span></span> <span data-ttu-id="8447b-208">Para registrar um repositório, use `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="8447b-208">To register a repository, use `Register-PSRepository`.</span></span> <span data-ttu-id="8447b-209">Para exibir repositórios registrados, use `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="8447b-209">To display registered repositories, use `Get-PSRepository`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-210">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8447b-210">-RequiredVersion</span></span>

<span data-ttu-id="8447b-211">Especifica o número de versão exato do módulo a ser incluído nos resultados.</span><span class="sxs-lookup"><span data-stu-id="8447b-211">Specifies the exact version number of the module to include in the results.</span></span> <span data-ttu-id="8447b-212">**RequiredVersion** não pode ser usado no mesmo comando que **MinimumVersion** ou **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="8447b-212">**RequiredVersion** cannot be used in the same command as **MinimumVersion** or **MaximumVersion**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-213">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="8447b-213">-RoleCapability</span></span>

<span data-ttu-id="8447b-214">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="8447b-214">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-215">-Tag</span><span class="sxs-lookup"><span data-stu-id="8447b-215">-Tag</span></span>

<span data-ttu-id="8447b-216">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="8447b-216">Specifies an array of tags.</span></span> <span data-ttu-id="8447b-217">As marcas de exemplo incluem **DesiredStateConfiguration**, **DSC**, **DSCResourceKit** ou **PSModule**.</span><span class="sxs-lookup"><span data-stu-id="8447b-217">Example tags include **DesiredStateConfiguration**, **DSC**, **DSCResourceKit**, or **PSModule**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8447b-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8447b-218">CommonParameters</span></span>

<span data-ttu-id="8447b-219">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8447b-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8447b-220">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8447b-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8447b-221">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8447b-221">INPUTS</span></span>

### <span data-ttu-id="8447b-222">System.String[]</span><span class="sxs-lookup"><span data-stu-id="8447b-222">System.String[]</span></span>

### <span data-ttu-id="8447b-223">System.String</span><span class="sxs-lookup"><span data-stu-id="8447b-223">System.String</span></span>

### <span data-ttu-id="8447b-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="8447b-224">System.Uri</span></span>

### <span data-ttu-id="8447b-225">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="8447b-225">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="8447b-226">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8447b-226">OUTPUTS</span></span>

### <span data-ttu-id="8447b-227">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="8447b-227">PSRepositoryItemInfo</span></span>

<span data-ttu-id="8447b-228">`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para cmdlets como `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="8447b-228">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

## <span data-ttu-id="8447b-229">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8447b-229">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8447b-230">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="8447b-230">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="8447b-231">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8447b-231">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="8447b-232">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="8447b-232">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="8447b-233">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8447b-233">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="8447b-234">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8447b-234">RELATED LINKS</span></span>

[<span data-ttu-id="8447b-235">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8447b-235">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="8447b-236">Install-Module</span><span class="sxs-lookup"><span data-stu-id="8447b-236">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="8447b-237">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="8447b-237">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="8447b-238">Save-Module</span><span class="sxs-lookup"><span data-stu-id="8447b-238">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="8447b-239">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="8447b-239">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="8447b-240">Update-Module</span><span class="sxs-lookup"><span data-stu-id="8447b-240">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="8447b-241">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8447b-241">Register-PSRepository</span></span>](Register-PSRepository.md)
