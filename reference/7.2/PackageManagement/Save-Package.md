---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/save-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Package
ms.openlocfilehash: 93ec8264bad588e38554daddcdf5dc9befce053e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603764"
---
# <span data-ttu-id="5d328-102">Save-Package</span><span class="sxs-lookup"><span data-stu-id="5d328-102">Save-Package</span></span>

## <span data-ttu-id="5d328-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5d328-103">SYNOPSIS</span></span>
<span data-ttu-id="5d328-104">Salva pacotes no computador local sem instalá-los.</span><span class="sxs-lookup"><span data-stu-id="5d328-104">Saves packages to the local computer without installing them.</span></span>

## <span data-ttu-id="5d328-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5d328-105">SYNTAX</span></span>

### <span data-ttu-id="5d328-106">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="5d328-106">PackageBySearch</span></span>

```
Save-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Path <String>] [-LiteralPath <String>]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="5d328-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="5d328-107">PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] -InputObject <SoftwareIdentity>
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5d328-108">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="5d328-108">NuGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="5d328-109">NuGet</span><span class="sxs-lookup"><span data-stu-id="5d328-109">NuGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="5d328-110">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="5d328-110">PowerShellGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

### <span data-ttu-id="5d328-111">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5d328-111">PowerShellGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

## <span data-ttu-id="5d328-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5d328-112">DESCRIPTION</span></span>

<span data-ttu-id="5d328-113">O `Save-Package` cmdlet salva pacotes no computador local, mas não instala os pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d328-113">The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages.</span></span>
<span data-ttu-id="5d328-114">Esse cmdlet salva a versão mais recente de um pacote, a menos que você especifique um **RequiredVerion**.</span><span class="sxs-lookup"><span data-stu-id="5d328-114">This cmdlet saves the newest version of a package unless you specify a **RequiredVerion**.</span></span> <span data-ttu-id="5d328-115">Os parâmetros **Path** e **LiteralPath** são mutuamente exclusivos e não podem ser adicionados ao mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5d328-115">The **Path** and **LiteralPath** parameters are mutually exclusive, and cannot be added to the same command.</span></span>

## <span data-ttu-id="5d328-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5d328-116">EXAMPLES</span></span>

### <span data-ttu-id="5d328-117">Exemplo 1: salvar um pacote no computador local</span><span class="sxs-lookup"><span data-stu-id="5d328-117">Example 1: Save a package to the local computer</span></span>

<span data-ttu-id="5d328-118">Este exemplo salva a versão mais recente do pacote em um diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="5d328-118">This example saves the newest version of the package to a directory on the local computer.</span></span> <span data-ttu-id="5d328-119">As dependências do pacote são baixadas com o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-119">The package's dependencies are download with the package.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.14.0     Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="5d328-120">`Save-Package` usa o parâmetro **Name** para especificar o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-120">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="5d328-121">O pacote é baixado do repositório especificado pelo parâmetro **ProviderName** .</span><span class="sxs-lookup"><span data-stu-id="5d328-121">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="5d328-122">O parâmetro **path** determina onde o pacote é salvo.</span><span class="sxs-lookup"><span data-stu-id="5d328-122">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="5d328-123">Exemplo 2: salvar uma versão de pacote específica</span><span class="sxs-lookup"><span data-stu-id="5d328-123">Example 2: Save a specific package version</span></span>

<span data-ttu-id="5d328-124">Este exemplo especifica a versão do pacote e salva-o em um diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="5d328-124">This example specifies the package version and saves it to a directory on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -RequiredVersion 2.9.0 -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.9.0      Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="5d328-125">`Save-Package` usa o parâmetro **Name** para especificar o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-125">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="5d328-126">**RequiredVersion** indica uma versão de pacote específica.</span><span class="sxs-lookup"><span data-stu-id="5d328-126">**RequiredVersion** indicates a specific package version.</span></span> <span data-ttu-id="5d328-127">O pacote é baixado do repositório especificado pelo parâmetro **ProviderName** .</span><span class="sxs-lookup"><span data-stu-id="5d328-127">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="5d328-128">O parâmetro **path** determina onde o pacote é salvo.</span><span class="sxs-lookup"><span data-stu-id="5d328-128">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="5d328-129">Exemplo 3: usar Find-Package para salvar um pacote</span><span class="sxs-lookup"><span data-stu-id="5d328-129">Example 3: Use Find-Package to save a package</span></span>

<span data-ttu-id="5d328-130">Esse comando usa `Find-Package` para localizar a versão mais recente do pacote e envia o objeto para `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="5d328-130">This command uses `Find-Package` to locate the newest version of the package and sends the object to `Save-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -ProviderName NuGet | Save-Package -Path C:\LocalPkg
```

<span data-ttu-id="5d328-131">`Find-Package` usa o parâmetro **Name** para especificar o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-131">`Find-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="5d328-132">O pacote é baixado do repositório especificado pelo parâmetro **ProviderName** .</span><span class="sxs-lookup"><span data-stu-id="5d328-132">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="5d328-133">O objeto é enviado ao pipeline para `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="5d328-133">The object is sent down the pipeline to `Save-Package`.</span></span> <span data-ttu-id="5d328-134">O parâmetro **path** determina onde o pacote é salvo.</span><span class="sxs-lookup"><span data-stu-id="5d328-134">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="5d328-135">Exemplo 4: salvar e instalar o pacote</span><span class="sxs-lookup"><span data-stu-id="5d328-135">Example 4: Save and install the package</span></span>

<span data-ttu-id="5d328-136">A versão mais recente do pacote e suas dependências são baixadas e instaladas no computador local.</span><span class="sxs-lookup"><span data-stu-id="5d328-136">The newest version of the package and its dependencies are downloaded and installed on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
PS> Install-Package C:\LocalPkg\NuGet.Core.2.14.0.nupkg
```

<span data-ttu-id="5d328-137">`Save-Package` Baixa o arquivo de pacote e suas dependências no computador local.</span><span class="sxs-lookup"><span data-stu-id="5d328-137">`Save-Package` downloads the package file and its dependencies to the local computer.</span></span>
<span data-ttu-id="5d328-138">`Install-Package` instala o pacote e as dependências do diretório especificado.</span><span class="sxs-lookup"><span data-stu-id="5d328-138">`Install-Package` installs the package and dependencies from the specified directory.</span></span>

## <span data-ttu-id="5d328-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5d328-139">PARAMETERS</span></span>

### <span data-ttu-id="5d328-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="5d328-140">-AcceptLicense</span></span>

<span data-ttu-id="5d328-141">Aceite automaticamente o contrato de licença durante a instalação se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="5d328-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-142">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="5d328-142">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="5d328-143">Permite que os pacotes marcados como pré-lançamento sejam salvos.</span><span class="sxs-lookup"><span data-stu-id="5d328-143">Allows packages marked as Prerelease to be saved.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet, PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-144">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="5d328-144">-AllVersions</span></span>

<span data-ttu-id="5d328-145">Indica que esse cmdlet salva todas as versões disponíveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-145">Indicates that this cmdlet saves all available versions of the package.</span></span>

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

### <span data-ttu-id="5d328-146">-Command</span><span class="sxs-lookup"><span data-stu-id="5d328-146">-Command</span></span>

<span data-ttu-id="5d328-147">Especifica um ou mais comandos incluídos no pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-147">Specifies one or more commands included in the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-148">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="5d328-148">-ConfigFile</span></span>

<span data-ttu-id="5d328-149">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="5d328-149">Specifies a configuration File.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-150">-Contém</span><span class="sxs-lookup"><span data-stu-id="5d328-150">-Contains</span></span>

<span data-ttu-id="5d328-151">`Save-Package` Obtém os objetos se qualquer item nos valores de Propriedade do objeto for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="5d328-151">`Save-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="5d328-152">-Credential</span></span>

<span data-ttu-id="5d328-153">Especifica uma conta de usuário que tem permissão para salvar um pacote de um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="5d328-153">Specifies a user account that has permission to save a package from a specified package provider or source.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-154">-DscResource</span><span class="sxs-lookup"><span data-stu-id="5d328-154">-DscResource</span></span>

<span data-ttu-id="5d328-155">Especifica um ou mais recursos de DSC (configuração de estado desejado) para o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-155">Specifies one or more Desired State Configuration (DSC) resources for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-156">-Filter</span><span class="sxs-lookup"><span data-stu-id="5d328-156">-Filter</span></span>

<span data-ttu-id="5d328-157">Especifica um filtro para o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-157">Specifies a filter for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-158">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="5d328-158">-FilterOnTag</span></span>

<span data-ttu-id="5d328-159">Especifica a marca que filtra os resultados.</span><span class="sxs-lookup"><span data-stu-id="5d328-159">Specifies the tag that filters the results.</span></span> <span data-ttu-id="5d328-160">Os resultados que não contêm a marca especificada são excluídos.</span><span class="sxs-lookup"><span data-stu-id="5d328-160">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-161">-Force</span><span class="sxs-lookup"><span data-stu-id="5d328-161">-Force</span></span>

<span data-ttu-id="5d328-162">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="5d328-162">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5d328-163">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="5d328-163">-ForceBootstrap</span></span>

<span data-ttu-id="5d328-164">Indica que `Save-Package` o **PackageManagement** é forçado a instalar automaticamente o provedor de pacote para o pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="5d328-164">Indicates that `Save-Package` forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="5d328-165">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="5d328-165">-Headers</span></span>

<span data-ttu-id="5d328-166">Especifica os cabeçalhos do pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-166">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-167">-Inclui</span><span class="sxs-lookup"><span data-stu-id="5d328-167">-Includes</span></span>

<span data-ttu-id="5d328-168">Indica os recursos que o pacote inclui.</span><span class="sxs-lookup"><span data-stu-id="5d328-168">Indicates the resources that the package includes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: DscResource, Cmdlet, Function, Workflow, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-169">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5d328-169">-InputObject</span></span>

<span data-ttu-id="5d328-170">Um objeto de ID de software que representa o pacote que você deseja salvar.</span><span class="sxs-lookup"><span data-stu-id="5d328-170">A software ID object that represents the package that you want to save.</span></span> <span data-ttu-id="5d328-171">As IDs de software fazem parte dos resultados do `Find-Package` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d328-171">Software IDs are part of the results of the `Find-Package` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5d328-172">-LiteralPath</span></span>

<span data-ttu-id="5d328-173">Especifica o caminho literal para o qual você deseja salvar o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-173">Specifies the literal path to which you want to save the package.</span></span> <span data-ttu-id="5d328-174">Você não pode adicionar esse parâmetro e o parâmetro **path** ao mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5d328-174">You cannot add both this parameter and the **Path** parameter to the same command.</span></span>

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

### <span data-ttu-id="5d328-175">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="5d328-175">-MaximumVersion</span></span>

<span data-ttu-id="5d328-176">Especifica a versão máxima do pacote que você deseja salvar.</span><span class="sxs-lookup"><span data-stu-id="5d328-176">Specifies the maximum version of the package that you want to save.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-177">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="5d328-177">-MinimumVersion</span></span>

<span data-ttu-id="5d328-178">Especifica a versão mínima do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="5d328-178">Specifies the minimum version of the package that you want to find.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-179">-Name</span><span class="sxs-lookup"><span data-stu-id="5d328-179">-Name</span></span>

<span data-ttu-id="5d328-180">Especifica um ou mais nomes de pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-180">Specifies one or more package names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-181">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="5d328-181">-PackageManagementProvider</span></span>

<span data-ttu-id="5d328-182">Especifica um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d328-182">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-183">-Path</span><span class="sxs-lookup"><span data-stu-id="5d328-183">-Path</span></span>

<span data-ttu-id="5d328-184">Especifica o local no computador local para armazenar o pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-184">Specifies the location on the local computer to store the package.</span></span>

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

### <span data-ttu-id="5d328-185">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="5d328-185">-ProviderName</span></span>

<span data-ttu-id="5d328-186">Especifica um ou mais nomes de provedor.</span><span class="sxs-lookup"><span data-stu-id="5d328-186">Specifies one or more provider names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-187">-Proxy</span><span class="sxs-lookup"><span data-stu-id="5d328-187">-Proxy</span></span>

<span data-ttu-id="5d328-188">Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="5d328-188">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-189">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="5d328-189">-ProxyCredential</span></span>

<span data-ttu-id="5d328-190">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="5d328-190">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-191">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="5d328-191">-PublishLocation</span></span>

<span data-ttu-id="5d328-192">Especifica o local de publicação.</span><span class="sxs-lookup"><span data-stu-id="5d328-192">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-193">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="5d328-193">-RequiredVersion</span></span>

<span data-ttu-id="5d328-194">Especifica a versão exata do pacote a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="5d328-194">Specifies the exact version of the package to save.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-195">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="5d328-195">-RoleCapability</span></span>

<span data-ttu-id="5d328-196">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="5d328-196">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-197">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="5d328-197">-ScriptPublishLocation</span></span>

<span data-ttu-id="5d328-198">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="5d328-198">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-199">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="5d328-199">-ScriptSourceLocation</span></span>

<span data-ttu-id="5d328-200">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="5d328-200">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-201">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="5d328-201">-SkipValidate</span></span>

<span data-ttu-id="5d328-202">Opção que ignora a validação das credenciais de um pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-202">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-203">-Source</span><span class="sxs-lookup"><span data-stu-id="5d328-203">-Source</span></span>

<span data-ttu-id="5d328-204">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-204">Specifies one or more package sources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-205">-Tag</span><span class="sxs-lookup"><span data-stu-id="5d328-205">-Tag</span></span>

<span data-ttu-id="5d328-206">Especifica uma marca a ser pesquisada nos metadados do pacote.</span><span class="sxs-lookup"><span data-stu-id="5d328-206">Specifies a tag to search for within the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-207">-Type</span><span class="sxs-lookup"><span data-stu-id="5d328-207">-Type</span></span>

<span data-ttu-id="5d328-208">Especifica se os pacotes devem ser pesquisados com um módulo, um script ou um.</span><span class="sxs-lookup"><span data-stu-id="5d328-208">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-209">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5d328-209">-Confirm</span></span>

<span data-ttu-id="5d328-210">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d328-210">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5d328-211">-WhatIf</span></span>

<span data-ttu-id="5d328-212">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5d328-212">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5d328-213">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5d328-213">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d328-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5d328-214">CommonParameters</span></span>

<span data-ttu-id="5d328-215">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5d328-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5d328-216">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5d328-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5d328-217">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5d328-217">INPUTS</span></span>

### <span data-ttu-id="5d328-218">`Save-Package` aceita objetos do pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d328-218">`Save-Package` accepts objects from the pipeline.</span></span>

## <span data-ttu-id="5d328-219">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5d328-219">OUTPUTS</span></span>

### <span data-ttu-id="5d328-220">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="5d328-220">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5d328-221">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5d328-221">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d328-222">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5d328-222">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5d328-223">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d328-223">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5d328-224">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="5d328-224">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5d328-225">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d328-225">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5d328-226">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5d328-226">RELATED LINKS</span></span>

[<span data-ttu-id="5d328-227">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="5d328-227">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="5d328-228">Get-Package</span><span class="sxs-lookup"><span data-stu-id="5d328-228">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="5d328-229">Install-Package</span><span class="sxs-lookup"><span data-stu-id="5d328-229">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="5d328-230">Save-Package</span><span class="sxs-lookup"><span data-stu-id="5d328-230">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="5d328-231">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="5d328-231">Uninstall-Package</span></span>](Uninstall-Package.md)
