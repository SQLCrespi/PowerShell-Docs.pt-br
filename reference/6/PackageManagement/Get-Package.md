---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: 0b821f96606215d5d961329ebc69a1e5d3260763
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194027"
---
# <span data-ttu-id="2432e-103">Get-Package</span><span class="sxs-lookup"><span data-stu-id="2432e-103">Get-Package</span></span>

## <span data-ttu-id="2432e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2432e-104">SYNOPSIS</span></span>
<span data-ttu-id="2432e-105">Retorna uma lista de todos os pacotes de software que foram instalados com o **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="2432e-105">Returns a list of all software packages that were installed with **PackageManagement** .</span></span>

## <span data-ttu-id="2432e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2432e-106">SYNTAX</span></span>

### <span data-ttu-id="2432e-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="2432e-107">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="2432e-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="2432e-108">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="2432e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2432e-109">DESCRIPTION</span></span>

<span data-ttu-id="2432e-110">O `Get-Package` cmdlet retorna uma lista de todos os pacotes de software no computador local que foram instalados com o **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="2432e-110">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement** .</span></span> <span data-ttu-id="2432e-111">Você pode executar `Get-Package` em computadores remotos executando-o como parte de `Invoke-Command` um `Enter-PSSession` comando ou script.</span><span class="sxs-lookup"><span data-stu-id="2432e-111">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="2432e-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2432e-112">EXAMPLES</span></span>

### <span data-ttu-id="2432e-113">Exemplo 1: obter todos os pacotes instalados</span><span class="sxs-lookup"><span data-stu-id="2432e-113">Example 1: Get all installed packages</span></span>

<span data-ttu-id="2432e-114">O `Get-Package` cmdlet obtém todos os pacotes que estão instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="2432e-114">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="2432e-115">Exemplo 2: obter pacotes que estão instalados em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="2432e-115">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="2432e-116">Esse comando obtém uma lista de pacotes que foram instalados pelo **PackageManagement** em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2432e-116">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="2432e-117">Esse comando solicita que você forneça a senha do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="2432e-117">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="2432e-118">`Invoke-Command` usa o parâmetro **ComputerName** para especificar um computador remoto, **Server01** .</span><span class="sxs-lookup"><span data-stu-id="2432e-118">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01** .</span></span> <span data-ttu-id="2432e-119">O parâmetro **Credential** especifica um domínio e um nome de usuário com permissões para executar comandos no computador.</span><span class="sxs-lookup"><span data-stu-id="2432e-119">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="2432e-120">O parâmetro **scriptblock** executa o `Get-Package` cmdlet no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2432e-120">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="2432e-121">Exemplo 3: obter pacotes para um provedor especificado</span><span class="sxs-lookup"><span data-stu-id="2432e-121">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="2432e-122">Esse comando obtém os pacotes de software instalados no computador local a partir de um provedor específico.</span><span class="sxs-lookup"><span data-stu-id="2432e-122">This command gets software packages installed on the local computer from a specific provider.</span></span>

```powershell
Get-Package -ProviderName PowerShellGet -AllVersions
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.2.2        https://www.powershellgallery.com/api/v2   PowerShellGet
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
posh-git              0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
PowerShellGet         2.0.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="2432e-123">`Get-Package` usa o parâmetro **ProviderName** para especificar um provedor específico, **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2432e-123">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet** .</span></span>
<span data-ttu-id="2432e-124">O parâmetro **todas as versões** exibe cada versão instalada.</span><span class="sxs-lookup"><span data-stu-id="2432e-124">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="2432e-125">Exemplo 4: obter uma versão exata de um pacote específico</span><span class="sxs-lookup"><span data-stu-id="2432e-125">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="2432e-126">Esse comando obtém uma versão específica de um pacote instalado.</span><span class="sxs-lookup"><span data-stu-id="2432e-126">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="2432e-127">Mais de uma versão de um pacote pode ser instalada.</span><span class="sxs-lookup"><span data-stu-id="2432e-127">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="2432e-128">`Get-Package` usa o parâmetro **Name** para especificar o nome do pacote, **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="2432e-128">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement** .</span></span> <span data-ttu-id="2432e-129">O parâmetro **ProviderName** especifica o provedor, **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2432e-129">The **ProviderName** parameter specifies the provider, **PowerShellGet** .</span></span> <span data-ttu-id="2432e-130">O parâmetro **-version obrigatório** especifica uma versão instalada.</span><span class="sxs-lookup"><span data-stu-id="2432e-130">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="2432e-131">Exemplo 5: desinstalar um pacote</span><span class="sxs-lookup"><span data-stu-id="2432e-131">Example 5: Uninstall a package</span></span>

<span data-ttu-id="2432e-132">Este exemplo obtém informações do pacote e, em seguida, desinstala o pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-132">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="2432e-133">`Get-Package` usa o parâmetro **Name** para especificar o nome do pacote, **Posh-git** .</span><span class="sxs-lookup"><span data-stu-id="2432e-133">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git** .</span></span> <span data-ttu-id="2432e-134">O parâmetro **RequiredVersion** é uma versão específica do pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-134">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="2432e-135">O objeto é enviado ao pipeline para o `Uninstall-Package` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2432e-135">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="2432e-136">`Uninstall-Package` Remove o pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-136">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="2432e-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2432e-137">PARAMETERS</span></span>

### <span data-ttu-id="2432e-138">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="2432e-138">-AllowClobber</span></span>

<span data-ttu-id="2432e-139">Substitui mensagens de aviso sobre conflitos com comandos existentes.</span><span class="sxs-lookup"><span data-stu-id="2432e-139">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="2432e-140">Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados por um módulo.</span><span class="sxs-lookup"><span data-stu-id="2432e-140">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-141">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="2432e-141">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="2432e-142">Inclui pacotes marcados como um pré-lançamento nos resultados.</span><span class="sxs-lookup"><span data-stu-id="2432e-142">Includes packages marked as a prerelease in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-143">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="2432e-143">-AllVersions</span></span>

<span data-ttu-id="2432e-144">Indica que o `Get-Package` retorna todas as versões disponíveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-144">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="2432e-145">Por padrão, `Get-Package` o retorna apenas a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="2432e-145">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="2432e-146">-Destino</span><span class="sxs-lookup"><span data-stu-id="2432e-146">-Destination</span></span>

<span data-ttu-id="2432e-147">Especifica o caminho para um diretório que contém arquivos de pacote extraídos.</span><span class="sxs-lookup"><span data-stu-id="2432e-147">Specifies the path to a directory that contains extracted package files.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-148">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="2432e-148">-ExcludeVersion</span></span>

<span data-ttu-id="2432e-149">Alterne para excluir o número de versão no caminho da pasta.</span><span class="sxs-lookup"><span data-stu-id="2432e-149">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-150">-Force</span><span class="sxs-lookup"><span data-stu-id="2432e-150">-Force</span></span>

<span data-ttu-id="2432e-151">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="2432e-151">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2432e-152">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="2432e-152">-ForceBootstrap</span></span>

<span data-ttu-id="2432e-153">Indica que `Get-Package` o **PackageManagement** é forçado a instalar automaticamente o provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2432e-153">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="2432e-154">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="2432e-154">-InstallUpdate</span></span>

<span data-ttu-id="2432e-155">Indica que esse cmdlet instala atualizações.</span><span class="sxs-lookup"><span data-stu-id="2432e-155">Indicates that this cmdlet installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-156">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2432e-156">-MaximumVersion</span></span>

<span data-ttu-id="2432e-157">Especifica a versão máxima do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="2432e-157">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="2432e-158">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="2432e-158">-MinimumVersion</span></span>

<span data-ttu-id="2432e-159">Especifica a versão mínima do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="2432e-159">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="2432e-160">Se uma versão superior estiver disponível, essa versão será retornada.</span><span class="sxs-lookup"><span data-stu-id="2432e-160">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="2432e-161">-Name</span><span class="sxs-lookup"><span data-stu-id="2432e-161">-Name</span></span>

<span data-ttu-id="2432e-162">Especifica um ou mais nomes de pacote ou nomes de pacote com caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="2432e-162">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="2432e-163">Separe vários nomes de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2432e-163">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2432e-164">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="2432e-164">-NoPathUpdate</span></span>

<span data-ttu-id="2432e-165">**NoPathUpdate** se aplica somente ao `Install-Script` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2432e-165">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="2432e-166">**NoPathUpdate** é um parâmetro dinâmico adicionado pelo provedor e não é suportado pelo `Get-Package` .</span><span class="sxs-lookup"><span data-stu-id="2432e-166">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-167">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="2432e-167">-PackageManagementProvider</span></span>

<span data-ttu-id="2432e-168">Especifica o nome de um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2432e-168">Specifies the name of a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-169">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="2432e-169">-ProviderName</span></span>

<span data-ttu-id="2432e-170">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-170">Specifies one or more package provider names.</span></span> <span data-ttu-id="2432e-171">Separe vários nomes de provedor de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2432e-171">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="2432e-172">Use `Get-PackageProvider` para obter uma lista de provedores de pacotes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2432e-172">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-173">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2432e-173">-RequiredVersion</span></span>

<span data-ttu-id="2432e-174">Especifica a versão exata do pacote a ser localizado.</span><span class="sxs-lookup"><span data-stu-id="2432e-174">Specifies the exact version of the package to find.</span></span>

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

### <span data-ttu-id="2432e-175">-Escopo</span><span class="sxs-lookup"><span data-stu-id="2432e-175">-Scope</span></span>

<span data-ttu-id="2432e-176">Especifica o escopo de pesquisa para o pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-176">Specifies the search scope for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-177">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="2432e-177">-SkipDependencies</span></span>

<span data-ttu-id="2432e-178">Opção que especifica para ignorar a localização de qualquer dependência de pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-178">Switch that specifies to skip finding any package dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-179">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="2432e-179">-SkipPublisherCheck</span></span>

<span data-ttu-id="2432e-180">Permite obter uma versão de pacote mais nova do que a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="2432e-180">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="2432e-181">Por exemplo, um pacote instalado que é assinado digitalmente por um fornecedor confiável, mas uma nova versão não é assinada digitalmente.</span><span class="sxs-lookup"><span data-stu-id="2432e-181">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-182">-Type</span><span class="sxs-lookup"><span data-stu-id="2432e-182">-Type</span></span>

<span data-ttu-id="2432e-183">Especifica se os pacotes devem ser pesquisados com um módulo, um script ou um.</span><span class="sxs-lookup"><span data-stu-id="2432e-183">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2432e-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2432e-184">CommonParameters</span></span>

<span data-ttu-id="2432e-185">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2432e-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2432e-186">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2432e-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2432e-187">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2432e-187">INPUTS</span></span>

## <span data-ttu-id="2432e-188">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2432e-188">OUTPUTS</span></span>

### <span data-ttu-id="2432e-189">SoftwareIdentity[]</span><span class="sxs-lookup"><span data-stu-id="2432e-189">SoftwareIdentity[]</span></span>

## <span data-ttu-id="2432e-190">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2432e-190">NOTES</span></span>

<span data-ttu-id="2432e-191">A inclusão de um provedor de pacote em um comando pode tornar os parâmetros dinâmicos disponíveis para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2432e-191">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="2432e-192">Parâmetros dinâmicos são específicos para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="2432e-192">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="2432e-193">O `Get-Help` cmdlet lista os conjuntos de parâmetros de um cmdlet e inclui o conjunto de parâmetros do provedor.</span><span class="sxs-lookup"><span data-stu-id="2432e-193">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="2432e-194">Por exemplo, `Get-Package` tem o conjunto de parâmetros **PowerShellGet** que inclui `-NoPathUpdate` , `AllowClobber` e `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="2432e-194">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="2432e-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2432e-195">RELATED LINKS</span></span>

[<span data-ttu-id="2432e-196">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="2432e-196">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="2432e-197">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="2432e-197">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="2432e-198">Find-Package</span><span class="sxs-lookup"><span data-stu-id="2432e-198">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="2432e-199">Get-Help</span><span class="sxs-lookup"><span data-stu-id="2432e-199">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="2432e-200">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="2432e-200">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="2432e-201">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2432e-201">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="2432e-202">Install-Package</span><span class="sxs-lookup"><span data-stu-id="2432e-202">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="2432e-203">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2432e-203">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="2432e-204">Save-Package</span><span class="sxs-lookup"><span data-stu-id="2432e-204">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="2432e-205">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="2432e-205">Uninstall-Package</span></span>](Uninstall-Package.md)
