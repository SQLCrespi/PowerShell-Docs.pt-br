---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: e1cb814d349d6b77885ebaaf176a7c3153d93eb5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99598825"
---
# <span data-ttu-id="96d34-102">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="96d34-102">Find-DscResource</span></span>

## <span data-ttu-id="96d34-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="96d34-103">SYNOPSIS</span></span>
<span data-ttu-id="96d34-104">Localiza recursos de DSC (configuração de estado desejado).</span><span class="sxs-lookup"><span data-stu-id="96d34-104">Finds Desired State Configuration (DSC) resources.</span></span>

## <span data-ttu-id="96d34-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="96d34-105">SYNTAX</span></span>

### <span data-ttu-id="96d34-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="96d34-106">All</span></span>

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="96d34-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="96d34-107">DESCRIPTION</span></span>

<span data-ttu-id="96d34-108">O `Find-DscResource` cmdlet procura repositórios registrados para localizar recursos de DSC contidos em módulos.</span><span class="sxs-lookup"><span data-stu-id="96d34-108">The `Find-DscResource` cmdlet searches registered repositories to find DSC resources contained in modules.</span></span> <span data-ttu-id="96d34-109">Por padrão, o `Find-DscResource` pesquisa todos os repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="96d34-109">By default `Find-DscResource` searches all registered repositories.</span></span>

<span data-ttu-id="96d34-110">Para cada módulo encontrado por `Find-DscResource` , um objeto **PSGetDscResourceInfo** é retornado.</span><span class="sxs-lookup"><span data-stu-id="96d34-110">For each module found by `Find-DscResource`, a **PSGetDscResourceInfo** object is returned.</span></span>
<span data-ttu-id="96d34-111">Os objetos **PSGetDscResourceInfo** podem ser enviados ao pipeline para o `Install-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96d34-111">**PSGetDscResourceInfo** objects can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="96d34-112">`Install-Module` instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="96d34-112">`Install-Module` installs the module.</span></span>

## <span data-ttu-id="96d34-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="96d34-113">EXAMPLES</span></span>

### <span data-ttu-id="96d34-114">Exemplo 1: localizar todos os recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="96d34-114">Example 1: Find all DSC resources</span></span>

<span data-ttu-id="96d34-115">`Find-DscResource` Retorna recursos de DSC de repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="96d34-115">`Find-DscResource` returns DSC resources from registered repositories.</span></span> <span data-ttu-id="96d34-116">Para pesquisar um repositório específico, use o parâmetro **Repository** .</span><span class="sxs-lookup"><span data-stu-id="96d34-116">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-DscResource
```

```Output
Name                           Version    ModuleName                     Repository
----                           -------    ----------                     ----------
Carbon_Privilege               2.8.1      Carbon                         PSGallery
Carbon_ScheduledTask           2.8.1      Carbon                         PSGallery
Carbon_Service                 2.8.1      Carbon                         PSGallery
PackageManagement              1.4        PackageManagement              PSGallery
PackageManagementSource        1.4        PackageManagement              PSGallery
PSModule                       2.1.4      PowerShellGet                  PSGallery
PSRepository                   2.1.4      PowerShellGet                  PSGallery
xArchive                       8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xDSCWebService                 8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xEnvironment                   8.7.0.0    xPSDesiredStateConfiguration   PSGallery
```

### <span data-ttu-id="96d34-117">Exemplo 2: localizar um recurso de DSC por nome</span><span class="sxs-lookup"><span data-stu-id="96d34-117">Example 2: Find a DSC resource by name</span></span>

<span data-ttu-id="96d34-118">`Find-DscResource` localiza recursos de DSC por nome.</span><span class="sxs-lookup"><span data-stu-id="96d34-118">`Find-DscResource` locates DSC resources by name.</span></span> <span data-ttu-id="96d34-119">Use vírgulas para separar uma matriz de nomes de recursos.</span><span class="sxs-lookup"><span data-stu-id="96d34-119">Use commas to separate an array of resource names.</span></span>

```powershell
Find-DscResource -Name xWebsite, xWebApplication, xWebSiteDefaults
```

```Output
Name               Version    ModuleName            Repository
----               -------    ----------            ----------
xWebApplication    2.6.0.0    xWebAdministration    PSGallery
xWebsite           2.6.0.0    xWebAdministration    PSGallery
xWebSiteDefaults   2.6.0.0    xWebAdministration    PSGallery
```

<span data-ttu-id="96d34-120">`Find-DscResource` usa o parâmetro **Name** para localizar a matriz especificada de recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="96d34-120">`Find-DscResource` uses the **Name** parameter to find the specified array of DSC resources.</span></span>

### <span data-ttu-id="96d34-121">Exemplo 3: localizar um recurso de DSC e instalá-lo</span><span class="sxs-lookup"><span data-stu-id="96d34-121">Example 3: Find a DSC resource and install it</span></span>

<span data-ttu-id="96d34-122">`Find-DscResource` localiza um recurso de DSC e envia o objeto para baixo no pipeline a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="96d34-122">`Find-DscResource` locates a DSC resource and sends the object down the pipeline to be installed.</span></span>
<span data-ttu-id="96d34-123">Após a instalação, use `Get-InstalledModule` para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="96d34-123">After the installation, use `Get-InstalledModule` to view the results.</span></span>

<span data-ttu-id="96d34-124">Vários recursos do mesmo módulo podem ser enviados para o pipeline para o `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="96d34-124">Multiple resources from the same module can be sent down the pipeline to the `Install-Module`.</span></span>
<span data-ttu-id="96d34-125">`Install-Module` tenta instalar o módulo apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="96d34-125">`Install-Module` attempts to only install the module once.</span></span>

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

<span data-ttu-id="96d34-126">`Find-DscResource` usa o parâmetro **Name** para localizar o recurso chamado **xWebsite**.</span><span class="sxs-lookup"><span data-stu-id="96d34-126">`Find-DscResource` uses the **Name** parameter to find the resource named **xWebsite**.</span></span> <span data-ttu-id="96d34-127">O objeto é enviado ao pipeline para o `Install-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="96d34-127">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="96d34-128">`Install-Module` instala o módulo **xWebAdministration** para o recurso.</span><span class="sxs-lookup"><span data-stu-id="96d34-128">`Install-Module` installs the **xWebAdministration** module for the resource.</span></span>

### <span data-ttu-id="96d34-129">Exemplo 4: localizar todos os recursos de DSC em um módulo</span><span class="sxs-lookup"><span data-stu-id="96d34-129">Example 4: Find all DSC resources in a module</span></span>

<span data-ttu-id="96d34-130">`Find-DscResource` localiza todos os recursos de DSC contidos em um módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="96d34-130">`Find-DscResource` finds all the DSC resources contained in a specified module.</span></span> <span data-ttu-id="96d34-131">Por padrão, a versão atual é exibida.</span><span class="sxs-lookup"><span data-stu-id="96d34-131">By default, the current version is displayed.</span></span> <span data-ttu-id="96d34-132">Para exibir outras versões, use os parâmetros **RequiredVersions** ou **getversions** .</span><span class="sxs-lookup"><span data-stu-id="96d34-132">To display other versions, use the **AllVersions** or **RequiredVersions** parameters.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration
```

```Output
Name                                Version    ModuleName              Repository
----                                -------    ----------              ----------
WebApplicationHandler               2.6.0.0    xWebAdministration      PSGallery
xIisFeatureDelegation               2.6.0.0    xWebAdministration      PSGallery
xIisHandler                         2.6.0.0    xWebAdministration      PSGallery
xIisLogging                         2.6.0.0    xWebAdministration      PSGallery
```

<span data-ttu-id="96d34-133">`Find-DscResource` usa o parâmetro **ModuleName** para especificar o **xWebAdministration** e localizar os recursos de DSC contidos no módulo.</span><span class="sxs-lookup"><span data-stu-id="96d34-133">`Find-DscResource` uses the **ModuleName** parameter to specify the **xWebAdministration** and find the DSC resources contained in the module.</span></span> <span data-ttu-id="96d34-134">A versão atual de cada recurso é exibida.</span><span class="sxs-lookup"><span data-stu-id="96d34-134">The current version of each resource is displayed.</span></span>

### <span data-ttu-id="96d34-135">Exemplo 5: localizar um recurso de DSC por marca e versão necessária</span><span class="sxs-lookup"><span data-stu-id="96d34-135">Example 5: Find a DSC resource by tag and required version</span></span>

<span data-ttu-id="96d34-136">Os recursos de DSC podem ser localizados usando a **marca** de parâmetros e **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="96d34-136">DSC resources can be located using the parameters **Tag** and **RequiredVersion**.</span></span> <span data-ttu-id="96d34-137">**Marca** exibe a versão atual de cada recurso que contém a marca especificada no repositório.</span><span class="sxs-lookup"><span data-stu-id="96d34-137">**Tag** displays the current version of every resource that contains the specified tag in the repository.</span></span>
<span data-ttu-id="96d34-138">**RequiredVersion** precisa do parâmetro **ModuleName** e o parâmetro **Name** é opcional.</span><span class="sxs-lookup"><span data-stu-id="96d34-138">**RequiredVersion** needs the **ModuleName** parameter and the **Name** parameter is optional.</span></span> <span data-ttu-id="96d34-139">Os parâmetros **Name** e **ModuleName** limitam a saída.</span><span class="sxs-lookup"><span data-stu-id="96d34-139">The **Name** and **ModuleName** parameters limit the output.</span></span> <span data-ttu-id="96d34-140">Use o parâmetro **Perversions** para exibir as versões disponíveis de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="96d34-140">Use the **AllVersions** parameter to display a DSC resource's available versions.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration -Tag DSC -RequiredVersion 1.20
```

```output
Name                    Version    ModuleName             Repository
----                    -------    ----------             ----------
xIisFeatureDelegation   1.20.0.0   xWebAdministration     PSGallery
xIisHandler             1.20.0.0   xWebAdministration     PSGallery
xIisLogging             1.20.0.0   xWebAdministration     PSGallery
xIisMimeTypeMapping     1.20.0.0   xWebAdministration     PSGallery
```

### <span data-ttu-id="96d34-141">Exemplo 6: localizar um recurso usando um filtro</span><span class="sxs-lookup"><span data-stu-id="96d34-141">Example 6: Find a resource by using a filter</span></span>

<span data-ttu-id="96d34-142">`Find-DscResource` localiza todos os recursos e usa o parâmetro de **filtro** para especificar os resultados por **domínio**.</span><span class="sxs-lookup"><span data-stu-id="96d34-142">`Find-DscResource` finds all resources and uses the **Filter** parameter to specify the results by **Domain**.</span></span> <span data-ttu-id="96d34-143">O parâmetro **Filter** localiza o valor do filtro na descrição do objeto ou no nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="96d34-143">The **Filter** parameter finds the filter value in the object's description or module name.</span></span> <span data-ttu-id="96d34-144">Use o `Select-Object` cmdlet para exibir as propriedades de um objeto.</span><span class="sxs-lookup"><span data-stu-id="96d34-144">Use the `Select-Object` cmdlet to view an object's properties.</span></span>

```powershell
Find-DscResource -Filter Domain
```

```output
Name                    Version    ModuleName                 Repository
----                    -------    ----------                 ---------
xComputer               4.1.0.0    xComputerManagement        PSGallery
Computer                6.4.0.0    ComputerManagementDsc      PSGallery
xDSCDomainjoin          1.1        xDSCDomainjoin             PSGallery
xDisk                   1.0        xDisk                      PSGallery
xDSCFirewall            1.6.21     xDSCFirewall               PSGallery
dmAwsTagInstance        1.0.1      domainAwsDSCResources      PSGallery
```

## <span data-ttu-id="96d34-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="96d34-145">PARAMETERS</span></span>

### <span data-ttu-id="96d34-146">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="96d34-146">-AllowPrerelease</span></span>

<span data-ttu-id="96d34-147">Inclui recursos marcados como um pré-lançamento nos resultados.</span><span class="sxs-lookup"><span data-stu-id="96d34-147">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="96d34-148">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="96d34-148">-AllVersions</span></span>

<span data-ttu-id="96d34-149">O parâmetro **Perversions** exibe cada uma das versões disponíveis de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="96d34-149">The **AllVersions** parameter displays each of a DSC resource's available versions.</span></span> <span data-ttu-id="96d34-150">Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="96d34-150">You can't use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="96d34-151">-Filter</span><span class="sxs-lookup"><span data-stu-id="96d34-151">-Filter</span></span>

<span data-ttu-id="96d34-152">Localiza recursos com base na sintaxe de pesquisa do provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="96d34-152">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="96d34-153">Por exemplo, especifique as palavras a serem pesquisadas nas propriedades **ModuleName** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="96d34-153">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="96d34-154">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="96d34-154">-MaximumVersion</span></span>

<span data-ttu-id="96d34-155">Especifica a versão máxima do recurso a ser incluído nos resultados.</span><span class="sxs-lookup"><span data-stu-id="96d34-155">Specifies the maximum version of the resource to include in results.</span></span> <span data-ttu-id="96d34-156">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="96d34-156">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="96d34-157">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="96d34-157">-MinimumVersion</span></span>

<span data-ttu-id="96d34-158">Especifica a versão mínima do recurso para incluir nos resultados.</span><span class="sxs-lookup"><span data-stu-id="96d34-158">Specifies the minimum version of the resource to include in results.</span></span> <span data-ttu-id="96d34-159">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="96d34-159">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="96d34-160">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="96d34-160">-ModuleName</span></span>

<span data-ttu-id="96d34-161">Especifica um módulo que contém o recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="96d34-161">Specifies a module that contains the DSC resource.</span></span>

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

### <span data-ttu-id="96d34-162">-Name</span><span class="sxs-lookup"><span data-stu-id="96d34-162">-Name</span></span>

<span data-ttu-id="96d34-163">Especifica o nome de um recurso.</span><span class="sxs-lookup"><span data-stu-id="96d34-163">Specifies the name of a resource.</span></span> <span data-ttu-id="96d34-164">O padrão é todos os recursos.</span><span class="sxs-lookup"><span data-stu-id="96d34-164">The default is all resources.</span></span> <span data-ttu-id="96d34-165">Use vírgulas para separar uma matriz de nomes de recursos.</span><span class="sxs-lookup"><span data-stu-id="96d34-165">Use commas to separate an array of resource names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96d34-166">-Proxy</span><span class="sxs-lookup"><span data-stu-id="96d34-166">-Proxy</span></span>

<span data-ttu-id="96d34-167">Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="96d34-167">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="96d34-168">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="96d34-168">-ProxyCredential</span></span>

<span data-ttu-id="96d34-169">Especifica uma conta de usuário com permissão para usar o servidor proxy especificado no parâmetro **proxy** .</span><span class="sxs-lookup"><span data-stu-id="96d34-169">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="96d34-170">-Repositório</span><span class="sxs-lookup"><span data-stu-id="96d34-170">-Repository</span></span>

<span data-ttu-id="96d34-171">Especifica um repositório para pesquisar recursos.</span><span class="sxs-lookup"><span data-stu-id="96d34-171">Specifies a repository to search for resources.</span></span> <span data-ttu-id="96d34-172">Use vírgulas para separar uma matriz de nomes de repositório.</span><span class="sxs-lookup"><span data-stu-id="96d34-172">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="96d34-173">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="96d34-173">-RequiredVersion</span></span>

<span data-ttu-id="96d34-174">Especifica o número de versão exato do módulo a ser incluído nos resultados.</span><span class="sxs-lookup"><span data-stu-id="96d34-174">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="96d34-175">Os parâmetros **RequiredVersion** e **MinimumVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="96d34-175">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="96d34-176">-Tag</span><span class="sxs-lookup"><span data-stu-id="96d34-176">-Tag</span></span>

<span data-ttu-id="96d34-177">Especifica as marcas que categorizam os módulos em um repositório.</span><span class="sxs-lookup"><span data-stu-id="96d34-177">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="96d34-178">Use vírgulas para separar uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="96d34-178">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="96d34-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="96d34-179">CommonParameters</span></span>

<span data-ttu-id="96d34-180">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="96d34-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="96d34-181">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="96d34-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="96d34-182">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="96d34-182">INPUTS</span></span>

## <span data-ttu-id="96d34-183">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="96d34-183">OUTPUTS</span></span>

### <span data-ttu-id="96d34-184">PSGetDscResourceInfo</span><span class="sxs-lookup"><span data-stu-id="96d34-184">PSGetDscResourceInfo</span></span>

<span data-ttu-id="96d34-185">`Find-DscResource` Retorna um objeto **PSGetDscResourceInfo** .</span><span class="sxs-lookup"><span data-stu-id="96d34-185">`Find-DscResource` returns a **PSGetDscResourceInfo** object.</span></span>

## <span data-ttu-id="96d34-186">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="96d34-186">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96d34-187">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="96d34-187">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="96d34-188">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96d34-188">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="96d34-189">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="96d34-189">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="96d34-190">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96d34-190">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="96d34-191">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="96d34-191">RELATED LINKS</span></span>

[<span data-ttu-id="96d34-192">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="96d34-192">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="96d34-193">Install-Module</span><span class="sxs-lookup"><span data-stu-id="96d34-193">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="96d34-194">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="96d34-194">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="96d34-195">Select-Object</span><span class="sxs-lookup"><span data-stu-id="96d34-195">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="96d34-196">Desinstalar-módulo</span><span class="sxs-lookup"><span data-stu-id="96d34-196">Uninstall-Module</span></span>](Uninstall-Module.md)
