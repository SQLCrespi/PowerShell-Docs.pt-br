---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: c45ff8443818580dcc57cd1a945822007ae259a8
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595794"
---
# <span data-ttu-id="2c68f-102">Find-Package</span><span class="sxs-lookup"><span data-stu-id="2c68f-102">Find-Package</span></span>

## <span data-ttu-id="2c68f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2c68f-103">SYNOPSIS</span></span>
<span data-ttu-id="2c68f-104">Localiza pacotes de software em fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2c68f-104">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="2c68f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2c68f-105">SYNTAX</span></span>

### <span data-ttu-id="2c68f-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="2c68f-106">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="2c68f-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="2c68f-107">PowerShellGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-AllowPrereleaseVersions] [-PackageManagementProvider <String>]
 [-PublishLocation <String>] [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
 [-Type <String>] [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>]
 [-DscResource <String[]>] [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense]
 [<CommonParameters>]
```

## <span data-ttu-id="2c68f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2c68f-108">DESCRIPTION</span></span>

<span data-ttu-id="2c68f-109">`Find-Package` localiza pacotes de software que estão disponíveis em fontes de pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-109">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="2c68f-110">`Get-PackageProvider` e `Get-PackageSource` Exibir detalhes sobre seus provedores.</span><span class="sxs-lookup"><span data-stu-id="2c68f-110">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="2c68f-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2c68f-111">EXAMPLES</span></span>

### <span data-ttu-id="2c68f-112">Exemplo 1: localizar todos os pacotes disponíveis de um provedor de pacotes</span><span class="sxs-lookup"><span data-stu-id="2c68f-112">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="2c68f-113">Esse comando localiza todos os pacotes de módulo do PowerShell disponíveis em uma galeria registrada.</span><span class="sxs-lookup"><span data-stu-id="2c68f-113">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="2c68f-114">Use `Get-PackageProvider` para obter o nome do provedor.</span><span class="sxs-lookup"><span data-stu-id="2c68f-114">Use `Get-PackageProvider` to get the provider name.</span></span>

```
Find-Package -ProviderName NuGet
```

```Output
Name               Version   Source     Summary
----               -------   ------     -------
NUnit              3.11.0    MyNuGet    NUnit is a unit-testing framework for all .NET langua...
Newtonsoft.Json    12.0.1    MyNuGet    Json.NET is a popular high-performance JSON framework...
EntityFramework    6.2.0     MyNuGet    Entity Framework is Microsoft's recommended data acce...
MySql.Data         8.0.15    MyNuGet    MySql.Data.MySqlClient .Net Core Class Library
bootstrap          4.3.1     MyNuGet    Bootstrap framework in CSS. Includes fonts and JavaSc...
NuGet.Core         2.14.0    MyNuGet    NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="2c68f-115">`Find-Package` usa o parâmetro **Provider** para especificar o **NuGet** do provedor.</span><span class="sxs-lookup"><span data-stu-id="2c68f-115">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet**.</span></span>

### <span data-ttu-id="2c68f-116">Exemplo 2: localizar um pacote de uma origem de pacote</span><span class="sxs-lookup"><span data-stu-id="2c68f-116">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="2c68f-117">Esse comando localiza a versão mais recente de um pacote de uma origem de pacote especificada.</span><span class="sxs-lookup"><span data-stu-id="2c68f-117">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="2c68f-118">Se uma origem de pacote não for fornecida, `Find-Package` o pesquisará cada provedor de pacote instalado e suas origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-118">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="2c68f-119">Use `Get-PackageSource` para obter o nome de origem.</span><span class="sxs-lookup"><span data-stu-id="2c68f-119">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="2c68f-120">`Find-Package` usa o parâmetro **Name** para especificar o nome do pacote **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-120">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="2c68f-121">O parâmetro de **origem** especifica a pesquisa do pacote em **MyNuGet**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-121">The **Source** parameter specifies to search for the package in **MyNuGet**.</span></span>

### <span data-ttu-id="2c68f-122">Exemplo 3: localizar todas as versões de um pacote</span><span class="sxs-lookup"><span data-stu-id="2c68f-122">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="2c68f-123">Esse comando localiza todas as versões de pacote disponíveis de um provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="2c68f-123">This command finds all available package versions from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.14.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.14.0-rtm-832   MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.13.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
...
NuGet.Core    1.1.229.159      MyNuGet      NuGet.Core is the core framework assembly for NuGet...
Nuget.Core    1.0.1120.104     MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="2c68f-124">`Find-Package` usa o parâmetro **Name** para especificar o pacote **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-124">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core**.</span></span> <span data-ttu-id="2c68f-125">O parâmetro **ProviderName** especifica a pesquisa do pacote em **MyNuGet**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-125">The **ProviderName** parameter specifies to search for the package in **MyNuGet**.</span></span> <span data-ttu-id="2c68f-126">O **Subversion** especifica que todas as versões disponíveis são retornadas.</span><span class="sxs-lookup"><span data-stu-id="2c68f-126">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="2c68f-127">Exemplo 4: localizar um pacote com um nome e uma versão específicos</span><span class="sxs-lookup"><span data-stu-id="2c68f-127">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="2c68f-128">Esse comando localiza uma versão de pacote específica de um provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="2c68f-128">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="2c68f-129">`Find-Package` usa o parâmetro **Name** para especificar o nome do pacote **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-129">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="2c68f-130">O parâmetro **ProviderName** especifica a pesquisa do pacote no **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-130">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="2c68f-131">**RequiredVersion** especifica que somente a versão **2.9.0** é retornada.</span><span class="sxs-lookup"><span data-stu-id="2c68f-131">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="2c68f-132">Exemplo 5: localizar pacotes em um intervalo de versões</span><span class="sxs-lookup"><span data-stu-id="2c68f-132">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="2c68f-133">Esse comando localiza um intervalo de versões para um pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="2c68f-133">This command finds a range of versions for a specified package.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -MinimumVersion 2.7.0 -MaximumVersion 2.9.0 -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.6            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.7.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="2c68f-134">`Find-Package` usa o parâmetro **Name** para especificar o nome do pacote **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-134">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="2c68f-135">O parâmetro **ProviderName** especifica a pesquisa do pacote no **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-135">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="2c68f-136">**MinimumVersion** especifica a versão mais baixa **2.7.0**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-136">**MinimumVersion** specifies the lowest version **2.7.0**.</span></span> <span data-ttu-id="2c68f-137">**MaximumVersion** especifica a versão mais recente **2.9.0**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-137">**MaximumVersion** specifies the highest version **2.9.0**.</span></span>
<span data-ttu-id="2c68f-138">As próprias **versões** determinam que o intervalo é retornado conforme especificado pelo mínimo e máximo.</span><span class="sxs-lookup"><span data-stu-id="2c68f-138">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="2c68f-139">Exemplo 6: localizar um pacote de um sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="2c68f-139">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="2c68f-140">Esse comando localiza pacotes com a extensão de arquivo `.nupkg` armazenada no computador local.</span><span class="sxs-lookup"><span data-stu-id="2c68f-140">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="2c68f-141">Os arquivos são pacotes baixados de uma galeria, como o **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-141">The files are packages downloaded from a gallery such as the **NuGet**.</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="2c68f-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2c68f-142">PARAMETERS</span></span>

### <span data-ttu-id="2c68f-143">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="2c68f-143">-AcceptLicense</span></span>

<span data-ttu-id="2c68f-144">O aceitará automaticamente um contrato de licença se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="2c68f-144">Automatically accepts a license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="2c68f-145">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="2c68f-145">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="2c68f-146">Inclui pacotes marcados como um pré-lançamento nos resultados.</span><span class="sxs-lookup"><span data-stu-id="2c68f-146">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="2c68f-147">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="2c68f-147">-AllVersions</span></span>

<span data-ttu-id="2c68f-148">Indica que o `Find-Package` retorna todas as versões disponíveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-148">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="2c68f-149">Por padrão, `Find-Package` o retorna apenas a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="2c68f-149">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="2c68f-150">-Command</span><span class="sxs-lookup"><span data-stu-id="2c68f-150">-Command</span></span>

<span data-ttu-id="2c68f-151">Especifica uma matriz de comandos pesquisados por `Find-Package` .</span><span class="sxs-lookup"><span data-stu-id="2c68f-151">Specifies an array of commands searched by `Find-Package`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-152">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="2c68f-152">-ConfigFile</span></span>

<span data-ttu-id="2c68f-153">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="2c68f-153">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="2c68f-154">-Contém</span><span class="sxs-lookup"><span data-stu-id="2c68f-154">-Contains</span></span>

<span data-ttu-id="2c68f-155">`Find-Package` Obtém os objetos se qualquer item nos valores de Propriedade do objeto for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="2c68f-155">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="2c68f-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="2c68f-156">-Credential</span></span>

<span data-ttu-id="2c68f-157">Especifica uma conta de usuário que tem permissão para pesquisar pacotes.</span><span class="sxs-lookup"><span data-stu-id="2c68f-157">Specifies a user account that has permission to search for packages.</span></span>

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

### <span data-ttu-id="2c68f-158">-DscResource</span><span class="sxs-lookup"><span data-stu-id="2c68f-158">-DscResource</span></span>

<span data-ttu-id="2c68f-159">Especifica uma matriz de recursos de DSC (configuração de estado desejado) que o cmdlet pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2c68f-159">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-160">-Filter</span><span class="sxs-lookup"><span data-stu-id="2c68f-160">-Filter</span></span>

<span data-ttu-id="2c68f-161">Especifica os termos a serem pesquisados nas propriedades **Name** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="2c68f-161">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="2c68f-162">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="2c68f-162">-FilterOnTag</span></span>

<span data-ttu-id="2c68f-163">Especifica a marca que filtra os resultados.</span><span class="sxs-lookup"><span data-stu-id="2c68f-163">Specifies the tag that filters the results.</span></span> <span data-ttu-id="2c68f-164">Os resultados que não contêm a marca especificada são excluídos.</span><span class="sxs-lookup"><span data-stu-id="2c68f-164">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-165">-Force</span><span class="sxs-lookup"><span data-stu-id="2c68f-165">-Force</span></span>

<span data-ttu-id="2c68f-166">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="2c68f-166">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2c68f-167">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="2c68f-167">-ForceBootstrap</span></span>

<span data-ttu-id="2c68f-168">Indica que `Find-Package` o **PackageManagement** é forçado a instalar automaticamente o provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2c68f-168">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="2c68f-169">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="2c68f-169">-Headers</span></span>

<span data-ttu-id="2c68f-170">Especifica os cabeçalhos do pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-170">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-171">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="2c68f-171">-IncludeDependencies</span></span>

<span data-ttu-id="2c68f-172">Indica que esse cmdlet inclui dependências de pacote nos resultados.</span><span class="sxs-lookup"><span data-stu-id="2c68f-172">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="2c68f-173">-Inclui</span><span class="sxs-lookup"><span data-stu-id="2c68f-173">-Includes</span></span>

<span data-ttu-id="2c68f-174">Especifica se o `Find-Package` deve localizar todos os pacotes em uma categoria.</span><span class="sxs-lookup"><span data-stu-id="2c68f-174">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="2c68f-175">Os valores aceitos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="2c68f-175">The accepted values are as follows:</span></span>

- <span data-ttu-id="2c68f-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2c68f-176">Cmdlet</span></span>
- <span data-ttu-id="2c68f-177">DscResource</span><span class="sxs-lookup"><span data-stu-id="2c68f-177">DscResource</span></span>
- <span data-ttu-id="2c68f-178">Função</span><span class="sxs-lookup"><span data-stu-id="2c68f-178">Function</span></span>
- <span data-ttu-id="2c68f-179">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="2c68f-179">RoleCapability</span></span>
- <span data-ttu-id="2c68f-180">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2c68f-180">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-181">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2c68f-181">-MaximumVersion</span></span>

<span data-ttu-id="2c68f-182">Especifica a versão máxima do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="2c68f-182">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="2c68f-183">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="2c68f-183">-MinimumVersion</span></span>

<span data-ttu-id="2c68f-184">Especifica a versão mínima do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="2c68f-184">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="2c68f-185">Se uma versão superior estiver disponível, essa versão será retornada.</span><span class="sxs-lookup"><span data-stu-id="2c68f-185">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="2c68f-186">-Name</span><span class="sxs-lookup"><span data-stu-id="2c68f-186">-Name</span></span>

<span data-ttu-id="2c68f-187">Especifica um ou mais nomes de pacote ou nomes de pacote com caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="2c68f-187">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="2c68f-188">Separe vários nomes de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2c68f-188">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="2c68f-189">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="2c68f-189">-PackageManagementProvider</span></span>

<span data-ttu-id="2c68f-190">Especifica o nome de um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2c68f-190">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="2c68f-191">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="2c68f-191">-ProviderName</span></span>

<span data-ttu-id="2c68f-192">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-192">Specifies one or more package provider names.</span></span> <span data-ttu-id="2c68f-193">Separe vários nomes de provedor de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2c68f-193">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="2c68f-194">Use `Get-PackageProvider` para obter uma lista de provedores de pacotes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2c68f-194">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="2c68f-195">-Proxy</span><span class="sxs-lookup"><span data-stu-id="2c68f-195">-Proxy</span></span>

<span data-ttu-id="2c68f-196">Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="2c68f-196">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="2c68f-197">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="2c68f-197">-ProxyCredential</span></span>

<span data-ttu-id="2c68f-198">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="2c68f-198">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="2c68f-199">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="2c68f-199">-PublishLocation</span></span>

<span data-ttu-id="2c68f-200">Especifica um local para publicar o pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-200">Specifies a location for publishing the package.</span></span>

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

### <span data-ttu-id="2c68f-201">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2c68f-201">-RequiredVersion</span></span>

<span data-ttu-id="2c68f-202">Especifica uma versão exata do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="2c68f-202">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="2c68f-203">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="2c68f-203">-RoleCapability</span></span>

<span data-ttu-id="2c68f-204">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="2c68f-204">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-205">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="2c68f-205">-ScriptPublishLocation</span></span>

<span data-ttu-id="2c68f-206">Especifica um local de publicação de script para o pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-206">Specifies a script publishing location for the package.</span></span>

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

### <span data-ttu-id="2c68f-207">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="2c68f-207">-ScriptSourceLocation</span></span>

<span data-ttu-id="2c68f-208">Especifica um local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="2c68f-208">Specifies a script source location.</span></span>

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

### <span data-ttu-id="2c68f-209">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="2c68f-209">-SkipValidate</span></span>

<span data-ttu-id="2c68f-210">Opção que ignora a validação de credenciais do pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-210">Switch that skips package credential validation.</span></span>

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

### <span data-ttu-id="2c68f-211">-Source</span><span class="sxs-lookup"><span data-stu-id="2c68f-211">-Source</span></span>

<span data-ttu-id="2c68f-212">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-212">Specifies one or more package sources.</span></span> <span data-ttu-id="2c68f-213">Use `Get-PackageSource` para obter uma lista de fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2c68f-213">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="2c68f-214">Um diretório do sistema de arquivos pode ser usado como uma fonte para baixar pacotes.</span><span class="sxs-lookup"><span data-stu-id="2c68f-214">A file system directory can be used as a source for download packages.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-215">-Tag</span><span class="sxs-lookup"><span data-stu-id="2c68f-215">-Tag</span></span>

<span data-ttu-id="2c68f-216">Especifica uma ou mais cadeias de caracteres a serem pesquisadas nos metadados do pacote.</span><span class="sxs-lookup"><span data-stu-id="2c68f-216">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2c68f-217">-Type</span><span class="sxs-lookup"><span data-stu-id="2c68f-217">-Type</span></span>

<span data-ttu-id="2c68f-218">Especifica se os pacotes devem ser pesquisados com um módulo, um script ou um.</span><span class="sxs-lookup"><span data-stu-id="2c68f-218">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="2c68f-219">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2c68f-219">CommonParameters</span></span>

<span data-ttu-id="2c68f-220">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2c68f-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2c68f-221">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2c68f-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2c68f-222">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2c68f-222">INPUTS</span></span>

### <span data-ttu-id="2c68f-223">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2c68f-223">None</span></span>

<span data-ttu-id="2c68f-224">`Find-Package` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="2c68f-224">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="2c68f-225">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2c68f-225">OUTPUTS</span></span>

### <span data-ttu-id="2c68f-226">SoftwareIdentify[]</span><span class="sxs-lookup"><span data-stu-id="2c68f-226">SoftwareIdentify[]</span></span>

<span data-ttu-id="2c68f-227">`Find-Package` gera um objeto **SoftwareIdentity** .</span><span class="sxs-lookup"><span data-stu-id="2c68f-227">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="2c68f-228">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2c68f-228">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c68f-229">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="2c68f-229">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="2c68f-230">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c68f-230">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="2c68f-231">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="2c68f-231">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="2c68f-232">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c68f-232">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="2c68f-233">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2c68f-233">RELATED LINKS</span></span>

[<span data-ttu-id="2c68f-234">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="2c68f-234">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="2c68f-235">Get-Package</span><span class="sxs-lookup"><span data-stu-id="2c68f-235">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="2c68f-236">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="2c68f-236">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="2c68f-237">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2c68f-237">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="2c68f-238">Install-Package</span><span class="sxs-lookup"><span data-stu-id="2c68f-238">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="2c68f-239">Save-Package</span><span class="sxs-lookup"><span data-stu-id="2c68f-239">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="2c68f-240">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="2c68f-240">Uninstall-Package</span></span>](Uninstall-Package.md)
