---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: e499d1d2a32ed3f3cb9d583a1b2d728d15e8df8d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891363"
---
# <span data-ttu-id="78669-103">Find-Module</span><span class="sxs-lookup"><span data-stu-id="78669-103">Find-Module</span></span>

## <span data-ttu-id="78669-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="78669-104">SYNOPSIS</span></span>
<span data-ttu-id="78669-105">Localiza módulos em um repositório que corresponde aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="78669-105">Finds modules in a repository that match specified criteria.</span></span>

## <span data-ttu-id="78669-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="78669-106">SYNTAX</span></span>

### <span data-ttu-id="78669-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="78669-107">All</span></span>

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="78669-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78669-108">DESCRIPTION</span></span>

<span data-ttu-id="78669-109">O `Find-Module` cmdlet localiza módulos em um repositório que corresponde aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="78669-109">The `Find-Module` cmdlet finds modules in a repository that match the specified criteria.</span></span>
<span data-ttu-id="78669-110">`Find-Module` Retorna um objeto **PSRepositoryItemInfo** para cada módulo que encontrar.</span><span class="sxs-lookup"><span data-stu-id="78669-110">`Find-Module` returns a **PSRepositoryItemInfo** object for each module it finds.</span></span> <span data-ttu-id="78669-111">Os objetos podem ser enviados ao pipeline para cmdlets como `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="78669-111">The objects can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

<span data-ttu-id="78669-112">Na primeira vez que o `Find-Module` tentar usar um repositório, você poderá ser solicitado a instalar atualizações.</span><span class="sxs-lookup"><span data-stu-id="78669-112">The first time `Find-Module` attempts to use a repository, you might be prompted to install updates.</span></span>
<span data-ttu-id="78669-113">Se a origem do repositório não estiver registrada com o `Register-PSRepository` cmdlet, um erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="78669-113">If the repository source is not registered with `Register-PSRepository` cmdlet, an error is returned.</span></span>

<span data-ttu-id="78669-114">`Find-Module` Retorna a versão mais recente de um módulo se nenhum parâmetro for usado para limitar a versão.</span><span class="sxs-lookup"><span data-stu-id="78669-114">`Find-Module` returns the newest version of a module if no parameters are used that limit the version.</span></span> <span data-ttu-id="78669-115">Para obter uma lista de um repositório de versões de um módulo, use o **parâmetro AllModules**.</span><span class="sxs-lookup"><span data-stu-id="78669-115">To get a repository's list of a module's versions, use the parameter **AllVersions**.</span></span>

<span data-ttu-id="78669-116">Se o parâmetro **MinimumVersion** for especificado, `Find-Module` retornará a versão do módulo que é igual ou maior que o mínimo.</span><span class="sxs-lookup"><span data-stu-id="78669-116">If the **MinimumVersion** parameter is specified, `Find-Module` returns the module's version that is equal to or greater than the minimum.</span></span> <span data-ttu-id="78669-117">Se houver uma versão mais recente disponível no repositório, a versão mais recente será retornada.</span><span class="sxs-lookup"><span data-stu-id="78669-117">If there is a newer version available in the repository, the newer version is returned.</span></span>

<span data-ttu-id="78669-118">Se o parâmetro **MaximumVersion** for especificado, `Find-Module` retornará a versão mais recente do módulo que não exceda a versão especificada.</span><span class="sxs-lookup"><span data-stu-id="78669-118">If the **MaximumVersion** parameter is specified, `Find-Module` returns the newest version of the module that does not exceed the version specified.</span></span>

<span data-ttu-id="78669-119">Se o parâmetro **RequiredVersion** for especificado, `Find-Module` retornará apenas a versão do módulo que é uma correspondência exata com a versão especificada.</span><span class="sxs-lookup"><span data-stu-id="78669-119">If the **RequiredVersion** parameter is specified, `Find-Module` only returns the module version that is an exact match to the specified version.</span></span> <span data-ttu-id="78669-120">`Find-Module` pesquisa todos os módulos disponíveis, pois podem ocorrer conflitos de nome entre origens.</span><span class="sxs-lookup"><span data-stu-id="78669-120">`Find-Module` searches through all available modules, because name conflicts between sources can occur.</span></span>

<span data-ttu-id="78669-121">Os exemplos a seguir usam o [Galeria do PowerShell](https://www.powershellgallery.com/) como o único repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="78669-121">The following examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="78669-122">`Get-PSRepository` exibe os repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="78669-122">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="78669-123">Se você tiver vários repositórios registrados, use o `-Repository` parâmetro para especificar o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-123">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="78669-124">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="78669-124">EXAMPLES</span></span>

### <span data-ttu-id="78669-125">Exemplo 1: localizar um módulo por nome</span><span class="sxs-lookup"><span data-stu-id="78669-125">Example 1: Find a module by name</span></span>

<span data-ttu-id="78669-126">Este exemplo localiza um módulo no repositório padrão.</span><span class="sxs-lookup"><span data-stu-id="78669-126">This example finds a module in the default repository.</span></span>

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

<span data-ttu-id="78669-127">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="78669-127">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>

### <span data-ttu-id="78669-128">Exemplo 2: localizar módulos com nomes semelhantes</span><span class="sxs-lookup"><span data-stu-id="78669-128">Example 2: Find modules with similar names</span></span>

<span data-ttu-id="78669-129">Este exemplo usa o curinga asterisco ( `*` ) para localizar módulos com nomes semelhantes.</span><span class="sxs-lookup"><span data-stu-id="78669-129">This example uses the asterisk (`*`) wildcard to find modules with similar names.</span></span>

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

<span data-ttu-id="78669-130">O `Find-Module` cmdlet usa o parâmetro **Name** com o curinga asterisco ( `*` ) para localizar todos os módulos que contêm o **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78669-130">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to find all modules that contain **PowerShell**.</span></span>

### <span data-ttu-id="78669-131">Exemplo 3: localizar um módulo por versão mínima</span><span class="sxs-lookup"><span data-stu-id="78669-131">Example 3: Find a module by minimum version</span></span>

<span data-ttu-id="78669-132">Este exemplo pesquisa a versão mínima de um módulo.</span><span class="sxs-lookup"><span data-stu-id="78669-132">This example searches for a module's minimum version.</span></span> <span data-ttu-id="78669-133">Se o repositório contiver uma versão mais recente do módulo, a versão mais recente será retornada.</span><span class="sxs-lookup"><span data-stu-id="78669-133">If the repository contains a newer version of the module, the newer version is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="78669-134">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="78669-134">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="78669-135">**MinimumVersion** especifica a versão **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="78669-135">The **MinimumVersion** specifies version **1.6.5**.</span></span> <span data-ttu-id="78669-136">`Find-Module` Retorna o PowerShellGet versão **2.1.0** porque ele excede a versão mínima e é a versão mais atual.</span><span class="sxs-lookup"><span data-stu-id="78669-136">`Find-Module` returns PowerShellGet version **2.1.0** because it exceeds the minimum version and is the most current version.</span></span>

### <span data-ttu-id="78669-137">Exemplo 4: localizar um módulo por versão específica</span><span class="sxs-lookup"><span data-stu-id="78669-137">Example 4: Find a module by specific version</span></span>

<span data-ttu-id="78669-138">Este exemplo retorna um objeto que representa a versão específica de um módulo.</span><span class="sxs-lookup"><span data-stu-id="78669-138">This example returns an object that represents a module's specific version.</span></span> <span data-ttu-id="78669-139">Se a versão especificada não for encontrada, um erro será retornado.</span><span class="sxs-lookup"><span data-stu-id="78669-139">If the specified version is not found, an error is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="78669-140">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="78669-140">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="78669-141">O parâmetro **RequiredVersion** especifica a versão **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="78669-141">The **RequiredVersion** parameter specifies version **1.6.5**.</span></span>

### <span data-ttu-id="78669-142">Exemplo 5: localizar um módulo em um repositório específico</span><span class="sxs-lookup"><span data-stu-id="78669-142">Example 5: Find a module in a specific repository</span></span>

<span data-ttu-id="78669-143">Este exemplo usa o parâmetro **Repository** para localizar um módulo em um repositório específico.</span><span class="sxs-lookup"><span data-stu-id="78669-143">This example uses the **Repository** parameter to find a module in a specific repository.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="78669-144">O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="78669-144">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="78669-145">O parâmetro **Repository** especifica a pesquisa no repositório **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="78669-145">The **Repository** parameter specifies to search the **PSGallery** repository.</span></span>

### <span data-ttu-id="78669-146">Exemplo 6: localizar um módulo em vários repositórios</span><span class="sxs-lookup"><span data-stu-id="78669-146">Example 6: Find a module in multiple repositories</span></span>

<span data-ttu-id="78669-147">Este exemplo usa o `Register-PSRepository` para especificar um repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-147">This example uses the `Register-PSRepository` to specify a repository.</span></span> <span data-ttu-id="78669-148">`Find-Module` usa o repositório para pesquisar um módulo.</span><span class="sxs-lookup"><span data-stu-id="78669-148">`Find-Module` uses the repository to search for a module.</span></span>

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

<span data-ttu-id="78669-149">O `Register-PSRepository` cmdlet registra um novo repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-149">The `Register-PSRepository` cmdlet registers a new repository.</span></span> <span data-ttu-id="78669-150">O parâmetro **Name** atribui o nome **MySource**.</span><span class="sxs-lookup"><span data-stu-id="78669-150">The **Name** parameter assigns the name **MySource**.</span></span> <span data-ttu-id="78669-151">O parâmetro **SourceLocation** especifica o endereço do repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-151">The **SourceLocation** parameter specifies the repository's address.</span></span>

<span data-ttu-id="78669-152">O `Find-Module` cmdlet usa o parâmetro **Name** com o curinga asterisco ( `*` ) para especificar o módulo **contoso** .</span><span class="sxs-lookup"><span data-stu-id="78669-152">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to specify the **Contoso** module.</span></span> <span data-ttu-id="78669-153">O parâmetro **Repository** especifica a pesquisa de dois repositórios, **PSGallery** e **MySource**.</span><span class="sxs-lookup"><span data-stu-id="78669-153">The **Repository** parameter specifies to search two repositories, **PSGallery** and **MySource**.</span></span>

### <span data-ttu-id="78669-154">Exemplo 7: localizar um módulo que contém um recurso de DSC</span><span class="sxs-lookup"><span data-stu-id="78669-154">Example 7: Find a module that contains a DSC resource</span></span>

<span data-ttu-id="78669-155">Esse comando retorna módulos que contêm recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="78669-155">This command returns modules that contain DSC resources.</span></span> <span data-ttu-id="78669-156">O parâmetro **includes** tem quatro funcionalidades predefinidas que são usadas para pesquisar o repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-156">The **Includes** parameter has four predefined functionalities that are used to search the repository.</span></span> <span data-ttu-id="78669-157">Use Tab-Complete para exibir as quatro funcionalidades com suporte no parâmetro **includes** .</span><span class="sxs-lookup"><span data-stu-id="78669-157">Use tab-complete to display the four functionalities supported by the **Includes** parameter.</span></span>

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

<span data-ttu-id="78669-158">O `Find-Module` cmdlet usa o parâmetro **Repository** para pesquisar o repositório, **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="78669-158">The `Find-Module` cmdlet uses the **Repository** parameter to search the repository, **PSGallery**.</span></span>
<span data-ttu-id="78669-159">O parâmetro **includes** especifica **DscResource**, que é uma funcionalidade que o parâmetro pode pesquisar no repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-159">The **Includes** parameter specifies **DscResource**, which is a functionality that the parameter can search for in the repository.</span></span>

### <span data-ttu-id="78669-160">Exemplo 8: localizar um módulo com um filtro</span><span class="sxs-lookup"><span data-stu-id="78669-160">Example 8: Find a module with a filter</span></span>

<span data-ttu-id="78669-161">Neste exemplo, para localizar módulos, um filtro é usado para pesquisar o repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-161">In this example, to find modules, a filter is used to search the repository.</span></span>

<span data-ttu-id="78669-162">Para um repositório baseado em NuGet, o parâmetro de **filtro** pesquisa o nome, a descrição e as marcas do argumento.</span><span class="sxs-lookup"><span data-stu-id="78669-162">For a NuGet-based repository, the **Filter** parameter searches through the name, description, and tags for the argument.</span></span>

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

<span data-ttu-id="78669-163">O `Find-Module` cmdlet usa o parâmetro **Filter** para pesquisar no repositório o **AppDomain**.</span><span class="sxs-lookup"><span data-stu-id="78669-163">The `Find-Module` cmdlet uses the **Filter** parameter to search the repository for **AppDomain**.</span></span>

## <span data-ttu-id="78669-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="78669-164">PARAMETERS</span></span>

### <span data-ttu-id="78669-165">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="78669-165">-AllowPrerelease</span></span>

<span data-ttu-id="78669-166">Inclui nos módulos de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="78669-166">Includes in the results modules marked as a pre-release.</span></span>

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

### <span data-ttu-id="78669-167">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="78669-167">-AllVersions</span></span>

<span data-ttu-id="78669-168">Especifica para incluir todas as versões de um módulo nos resultados.</span><span class="sxs-lookup"><span data-stu-id="78669-168">Specifies to include all versions of a module in the results.</span></span> <span data-ttu-id="78669-169">Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="78669-169">You cannot use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="78669-170">-Command</span><span class="sxs-lookup"><span data-stu-id="78669-170">-Command</span></span>

<span data-ttu-id="78669-171">Especifica uma matriz de comandos para localizar em módulos.</span><span class="sxs-lookup"><span data-stu-id="78669-171">Specifies an array of commands to find in modules.</span></span> <span data-ttu-id="78669-172">Um comando pode ser uma função ou um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="78669-172">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="78669-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="78669-173">-Credential</span></span>

<span data-ttu-id="78669-174">Especifica uma conta de usuário que tem direitos para instalar um módulo para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="78669-174">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="78669-175">-DscResource</span><span class="sxs-lookup"><span data-stu-id="78669-175">-DscResource</span></span>

<span data-ttu-id="78669-176">Especifica o nome, ou parte do nome, dos módulos que contêm recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="78669-176">Specifies the name, or part of the name, of modules that contain DSC resources.</span></span> <span data-ttu-id="78669-177">Por convenções do PowerShell, o executa uma pesquisa **ou** quando você fornece vários argumentos.</span><span class="sxs-lookup"><span data-stu-id="78669-177">Per PowerShell conventions, performs an **OR** search when you provide multiple arguments.</span></span>

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

### <span data-ttu-id="78669-178">-Filter</span><span class="sxs-lookup"><span data-stu-id="78669-178">-Filter</span></span>

<span data-ttu-id="78669-179">Especifica um filtro com base na sintaxe de pesquisa específica do provedor **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="78669-179">Specifies a filter based on the **PackageManagement** provider-specific search syntax.</span></span> <span data-ttu-id="78669-180">Para módulos NuGet, esse parâmetro é o equivalente de Pesquisar usando a barra de pesquisa no site [Galeria do PowerShell](https://www.powershellgallery.com/) .</span><span class="sxs-lookup"><span data-stu-id="78669-180">For NuGet modules, this parameter is the equivalent of searching by using the Search bar on the [PowerShell Gallery](https://www.powershellgallery.com/) website.</span></span>

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

### <span data-ttu-id="78669-181">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="78669-181">-IncludeDependencies</span></span>

<span data-ttu-id="78669-182">Indica que essa operação inclui todos os módulos que dependem do módulo especificado no parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="78669-182">Indicates that this operation includes all modules that are dependent upon the module specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="78669-183">-Inclui</span><span class="sxs-lookup"><span data-stu-id="78669-183">-Includes</span></span>

<span data-ttu-id="78669-184">Retorna somente os módulos que incluem tipos específicos de funcionalidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78669-184">Returns only those modules that include specific kinds of PowerShell functionality.</span></span> <span data-ttu-id="78669-185">Por exemplo, talvez você queira apenas localizar módulos que incluem **DSCResource**.</span><span class="sxs-lookup"><span data-stu-id="78669-185">For example, you might only want to find modules that include **DSCResource**.</span></span> <span data-ttu-id="78669-186">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="78669-186">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="78669-187">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="78669-187">Cmdlet</span></span>
- <span data-ttu-id="78669-188">DscResource</span><span class="sxs-lookup"><span data-stu-id="78669-188">DscResource</span></span>
- <span data-ttu-id="78669-189">Função</span><span class="sxs-lookup"><span data-stu-id="78669-189">Function</span></span>
- <span data-ttu-id="78669-190">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="78669-190">RoleCapability</span></span>

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

### <span data-ttu-id="78669-191">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="78669-191">-MaximumVersion</span></span>

<span data-ttu-id="78669-192">Especifica a versão máxima ou mais recente do módulo a ser incluída nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="78669-192">Specifies the maximum, or latest, version of the module to include in the search results.</span></span>
<span data-ttu-id="78669-193">**MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="78669-193">**MaximumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

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

### <span data-ttu-id="78669-194">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="78669-194">-MinimumVersion</span></span>

<span data-ttu-id="78669-195">Especifica a versão mínima do módulo a ser incluída nos resultados.</span><span class="sxs-lookup"><span data-stu-id="78669-195">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="78669-196">**MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="78669-196">**MinimumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

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

### <span data-ttu-id="78669-197">-Name</span><span class="sxs-lookup"><span data-stu-id="78669-197">-Name</span></span>

<span data-ttu-id="78669-198">Especifica os nomes dos módulos a serem pesquisados no repositório.</span><span class="sxs-lookup"><span data-stu-id="78669-198">Specifies the names of modules to search for in the repository.</span></span> <span data-ttu-id="78669-199">Uma lista separada por vírgulas de nomes de módulo é aceita.</span><span class="sxs-lookup"><span data-stu-id="78669-199">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="78669-200">Caracteres curinga são aceitos.</span><span class="sxs-lookup"><span data-stu-id="78669-200">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="78669-201">-Proxy</span><span class="sxs-lookup"><span data-stu-id="78669-201">-Proxy</span></span>

<span data-ttu-id="78669-202">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="78669-202">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="78669-203">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="78669-203">-ProxyCredential</span></span>

<span data-ttu-id="78669-204">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="78669-204">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="78669-205">-Repositório</span><span class="sxs-lookup"><span data-stu-id="78669-205">-Repository</span></span>

<span data-ttu-id="78669-206">Use o parâmetro **Repository** para especificar qual repositório procurar um módulo.</span><span class="sxs-lookup"><span data-stu-id="78669-206">Use the **Repository** parameter to specify which repository to search for a module.</span></span> <span data-ttu-id="78669-207">Usado quando vários repositórios são registrados.</span><span class="sxs-lookup"><span data-stu-id="78669-207">Used when multiple repositories are registered.</span></span> <span data-ttu-id="78669-208">Aceita uma lista separada por vírgulas de repositórios.</span><span class="sxs-lookup"><span data-stu-id="78669-208">Accepts a comma-separated list of repositories.</span></span> <span data-ttu-id="78669-209">Para registrar um repositório, use `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="78669-209">To register a repository, use `Register-PSRepository`.</span></span> <span data-ttu-id="78669-210">Para exibir repositórios registrados, use `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="78669-210">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="78669-211">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="78669-211">-RequiredVersion</span></span>

<span data-ttu-id="78669-212">Especifica o número de versão exato do módulo a ser incluído nos resultados.</span><span class="sxs-lookup"><span data-stu-id="78669-212">Specifies the exact version number of the module to include in the results.</span></span> <span data-ttu-id="78669-213">**RequiredVersion** não pode ser usado no mesmo comando que **MinimumVersion** ou **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="78669-213">**RequiredVersion** cannot be used in the same command as **MinimumVersion** or **MaximumVersion**.</span></span>

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

### <span data-ttu-id="78669-214">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="78669-214">-RoleCapability</span></span>

<span data-ttu-id="78669-215">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="78669-215">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="78669-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="78669-216">-Tag</span></span>

<span data-ttu-id="78669-217">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="78669-217">Specifies an array of tags.</span></span> <span data-ttu-id="78669-218">As marcas de exemplo incluem **DesiredStateConfiguration**, **DSC**, **DSCResourceKit** ou **PSModule**.</span><span class="sxs-lookup"><span data-stu-id="78669-218">Example tags include **DesiredStateConfiguration**, **DSC**, **DSCResourceKit**, or **PSModule**.</span></span>

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

### <span data-ttu-id="78669-219">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="78669-219">CommonParameters</span></span>

<span data-ttu-id="78669-220">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="78669-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="78669-221">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="78669-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="78669-222">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="78669-222">INPUTS</span></span>

### <span data-ttu-id="78669-223">System.String[]</span><span class="sxs-lookup"><span data-stu-id="78669-223">System.String[]</span></span>

### <span data-ttu-id="78669-224">System.String</span><span class="sxs-lookup"><span data-stu-id="78669-224">System.String</span></span>

### <span data-ttu-id="78669-225">System.Uri</span><span class="sxs-lookup"><span data-stu-id="78669-225">System.Uri</span></span>

### <span data-ttu-id="78669-226">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="78669-226">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="78669-227">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="78669-227">OUTPUTS</span></span>

### <span data-ttu-id="78669-228">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="78669-228">PSRepositoryItemInfo</span></span>

<span data-ttu-id="78669-229">`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para cmdlets como `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="78669-229">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

## <span data-ttu-id="78669-230">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="78669-230">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78669-231">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="78669-231">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="78669-232">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78669-232">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="78669-233">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="78669-233">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="78669-234">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78669-234">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="78669-235">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="78669-235">RELATED LINKS</span></span>

[<span data-ttu-id="78669-236">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="78669-236">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="78669-237">Install-Module</span><span class="sxs-lookup"><span data-stu-id="78669-237">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="78669-238">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="78669-238">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="78669-239">Save-Module</span><span class="sxs-lookup"><span data-stu-id="78669-239">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="78669-240">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="78669-240">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="78669-241">Update-Module</span><span class="sxs-lookup"><span data-stu-id="78669-241">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="78669-242">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="78669-242">Register-PSRepository</span></span>](Register-PSRepository.md)
