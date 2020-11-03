---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: 99e065ccdc8b450fa770e4d5f35fb04c747da063
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193989"
---
# <span data-ttu-id="f48cd-103">Find-Package</span><span class="sxs-lookup"><span data-stu-id="f48cd-103">Find-Package</span></span>

## <span data-ttu-id="f48cd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f48cd-104">SYNOPSIS</span></span>
<span data-ttu-id="f48cd-105">Localiza pacotes de software em fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f48cd-105">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="f48cd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f48cd-106">SYNTAX</span></span>

### <span data-ttu-id="f48cd-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="f48cd-107">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="f48cd-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="f48cd-108">PowerShellGet</span></span>

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

## <span data-ttu-id="f48cd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f48cd-109">DESCRIPTION</span></span>

<span data-ttu-id="f48cd-110">`Find-Package` localiza pacotes de software que estão disponíveis em fontes de pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-110">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="f48cd-111">`Get-PackageProvider` e `Get-PackageSource` Exibir detalhes sobre seus provedores.</span><span class="sxs-lookup"><span data-stu-id="f48cd-111">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="f48cd-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f48cd-112">EXAMPLES</span></span>

### <span data-ttu-id="f48cd-113">Exemplo 1: localizar todos os pacotes disponíveis de um provedor de pacotes</span><span class="sxs-lookup"><span data-stu-id="f48cd-113">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="f48cd-114">Esse comando localiza todos os pacotes de módulo do PowerShell disponíveis em uma galeria registrada.</span><span class="sxs-lookup"><span data-stu-id="f48cd-114">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="f48cd-115">Use `Get-PackageProvider` para obter o nome do provedor.</span><span class="sxs-lookup"><span data-stu-id="f48cd-115">Use `Get-PackageProvider` to get the provider name.</span></span>

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

<span data-ttu-id="f48cd-116">`Find-Package` usa o parâmetro **Provider** para especificar o **NuGet** do provedor.</span><span class="sxs-lookup"><span data-stu-id="f48cd-116">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet** .</span></span>

### <span data-ttu-id="f48cd-117">Exemplo 2: localizar um pacote de uma origem de pacote</span><span class="sxs-lookup"><span data-stu-id="f48cd-117">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="f48cd-118">Esse comando localiza a versão mais recente de um pacote de uma origem de pacote especificada.</span><span class="sxs-lookup"><span data-stu-id="f48cd-118">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="f48cd-119">Se uma origem de pacote não for fornecida, `Find-Package` o pesquisará cada provedor de pacote instalado e suas origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-119">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="f48cd-120">Use `Get-PackageSource` para obter o nome de origem.</span><span class="sxs-lookup"><span data-stu-id="f48cd-120">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="f48cd-121">`Find-Package` usa o parâmetro **Name** para especificar o nome do pacote **NuGet. Core** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-121">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core** .</span></span> <span data-ttu-id="f48cd-122">O parâmetro de **origem** especifica a pesquisa do pacote em **MyNuGet** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-122">The **Source** parameter specifies to search for the package in **MyNuGet** .</span></span>

### <span data-ttu-id="f48cd-123">Exemplo 3: localizar todas as versões de um pacote</span><span class="sxs-lookup"><span data-stu-id="f48cd-123">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="f48cd-124">Esse comando localiza todas as versões de pacote disponíveis de um provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="f48cd-124">This command finds all available package versions from a specified provider.</span></span>

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

<span data-ttu-id="f48cd-125">`Find-Package` usa o parâmetro **Name** para especificar o pacote **NuGet. Core** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-125">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core** .</span></span> <span data-ttu-id="f48cd-126">O parâmetro **ProviderName** especifica a pesquisa do pacote em **MyNuGet** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-126">The **ProviderName** parameter specifies to search for the package in **MyNuGet** .</span></span> <span data-ttu-id="f48cd-127">O **Subversion** especifica que todas as versões disponíveis são retornadas.</span><span class="sxs-lookup"><span data-stu-id="f48cd-127">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="f48cd-128">Exemplo 4: localizar um pacote com um nome e uma versão específicos</span><span class="sxs-lookup"><span data-stu-id="f48cd-128">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="f48cd-129">Esse comando localiza uma versão de pacote específica de um provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="f48cd-129">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="f48cd-130">`Find-Package` usa o parâmetro **Name** para especificar o nome do pacote **NuGet. Core** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-130">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core** .</span></span> <span data-ttu-id="f48cd-131">O parâmetro **ProviderName** especifica a pesquisa do pacote no **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-131">The **ProviderName** parameter specifies to search for the package in **NuGet** .</span></span> <span data-ttu-id="f48cd-132">**RequiredVersion** especifica que somente a versão **2.9.0** é retornada.</span><span class="sxs-lookup"><span data-stu-id="f48cd-132">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="f48cd-133">Exemplo 5: localizar pacotes em um intervalo de versões</span><span class="sxs-lookup"><span data-stu-id="f48cd-133">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="f48cd-134">Esse comando localiza um intervalo de versões para um pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="f48cd-134">This command finds a range of versions for a specified package.</span></span>

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

<span data-ttu-id="f48cd-135">`Find-Package` usa o parâmetro **Name** para especificar o nome do pacote **NuGet. Core** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-135">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core** .</span></span> <span data-ttu-id="f48cd-136">O parâmetro **ProviderName** especifica a pesquisa do pacote no **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-136">The **ProviderName** parameter specifies to search for the package in **NuGet** .</span></span> <span data-ttu-id="f48cd-137">**MinimumVersion** especifica a versão mais baixa **2.7.0** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-137">**MinimumVersion** specifies the lowest version **2.7.0** .</span></span> <span data-ttu-id="f48cd-138">**MaximumVersion** especifica a versão mais recente **2.9.0** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-138">**MaximumVersion** specifies the highest version **2.9.0** .</span></span>
<span data-ttu-id="f48cd-139">As próprias **versões** determinam que o intervalo é retornado conforme especificado pelo mínimo e máximo.</span><span class="sxs-lookup"><span data-stu-id="f48cd-139">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="f48cd-140">Exemplo 6: localizar um pacote de um sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="f48cd-140">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="f48cd-141">Esse comando localiza pacotes com a extensão de arquivo `.nupkg` armazenada no computador local.</span><span class="sxs-lookup"><span data-stu-id="f48cd-141">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="f48cd-142">Os arquivos são pacotes baixados de uma galeria, como o **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-142">The files are packages downloaded from a gallery such as the **NuGet** .</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="f48cd-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f48cd-143">PARAMETERS</span></span>

### <span data-ttu-id="f48cd-144">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="f48cd-144">-AcceptLicense</span></span>

<span data-ttu-id="f48cd-145">O aceitará automaticamente um contrato de licença se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="f48cd-145">Automatically accepts a license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="f48cd-146">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="f48cd-146">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="f48cd-147">Inclui pacotes marcados como um pré-lançamento nos resultados.</span><span class="sxs-lookup"><span data-stu-id="f48cd-147">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="f48cd-148">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="f48cd-148">-AllVersions</span></span>

<span data-ttu-id="f48cd-149">Indica que o `Find-Package` retorna todas as versões disponíveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-149">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="f48cd-150">Por padrão, `Find-Package` o retorna apenas a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="f48cd-150">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="f48cd-151">-Command</span><span class="sxs-lookup"><span data-stu-id="f48cd-151">-Command</span></span>

<span data-ttu-id="f48cd-152">Especifica uma matriz de comandos pesquisados por `Find-Package` .</span><span class="sxs-lookup"><span data-stu-id="f48cd-152">Specifies an array of commands searched by `Find-Package`.</span></span>

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

### <span data-ttu-id="f48cd-153">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="f48cd-153">-ConfigFile</span></span>

<span data-ttu-id="f48cd-154">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="f48cd-154">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="f48cd-155">-Contém</span><span class="sxs-lookup"><span data-stu-id="f48cd-155">-Contains</span></span>

<span data-ttu-id="f48cd-156">`Find-Package` Obtém os objetos se qualquer item nos valores de Propriedade do objeto for uma correspondência exata para o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="f48cd-156">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="f48cd-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="f48cd-157">-Credential</span></span>

<span data-ttu-id="f48cd-158">Especifica uma conta de usuário que tem permissão para pesquisar pacotes.</span><span class="sxs-lookup"><span data-stu-id="f48cd-158">Specifies a user account that has permission to search for packages.</span></span>

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

### <span data-ttu-id="f48cd-159">-DscResource</span><span class="sxs-lookup"><span data-stu-id="f48cd-159">-DscResource</span></span>

<span data-ttu-id="f48cd-160">Especifica uma matriz de recursos de DSC (configuração de estado desejado) que o cmdlet pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f48cd-160">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

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

### <span data-ttu-id="f48cd-161">-Filter</span><span class="sxs-lookup"><span data-stu-id="f48cd-161">-Filter</span></span>

<span data-ttu-id="f48cd-162">Especifica os termos a serem pesquisados nas propriedades **Name** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-162">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="f48cd-163">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="f48cd-163">-FilterOnTag</span></span>

<span data-ttu-id="f48cd-164">Especifica a marca que filtra os resultados.</span><span class="sxs-lookup"><span data-stu-id="f48cd-164">Specifies the tag that filters the results.</span></span> <span data-ttu-id="f48cd-165">Os resultados que não contêm a marca especificada são excluídos.</span><span class="sxs-lookup"><span data-stu-id="f48cd-165">Results that don't contain the specified tag are excluded.</span></span>

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

### <span data-ttu-id="f48cd-166">-Force</span><span class="sxs-lookup"><span data-stu-id="f48cd-166">-Force</span></span>

<span data-ttu-id="f48cd-167">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="f48cd-167">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="f48cd-168">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="f48cd-168">-ForceBootstrap</span></span>

<span data-ttu-id="f48cd-169">Indica que `Find-Package` o **PackageManagement** é forçado a instalar automaticamente o provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="f48cd-169">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="f48cd-170">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="f48cd-170">-Headers</span></span>

<span data-ttu-id="f48cd-171">Especifica os cabeçalhos do pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-171">Specifies the headers for the package.</span></span>

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

### <span data-ttu-id="f48cd-172">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="f48cd-172">-IncludeDependencies</span></span>

<span data-ttu-id="f48cd-173">Indica que esse cmdlet inclui dependências de pacote nos resultados.</span><span class="sxs-lookup"><span data-stu-id="f48cd-173">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="f48cd-174">-Inclui</span><span class="sxs-lookup"><span data-stu-id="f48cd-174">-Includes</span></span>

<span data-ttu-id="f48cd-175">Especifica se o `Find-Package` deve localizar todos os pacotes em uma categoria.</span><span class="sxs-lookup"><span data-stu-id="f48cd-175">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="f48cd-176">Os valores aceitos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f48cd-176">The accepted values are as follows:</span></span>

- <span data-ttu-id="f48cd-177">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f48cd-177">Cmdlet</span></span>
- <span data-ttu-id="f48cd-178">DscResource</span><span class="sxs-lookup"><span data-stu-id="f48cd-178">DscResource</span></span>
- <span data-ttu-id="f48cd-179">Função</span><span class="sxs-lookup"><span data-stu-id="f48cd-179">Function</span></span>
- <span data-ttu-id="f48cd-180">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="f48cd-180">RoleCapability</span></span>
- <span data-ttu-id="f48cd-181">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f48cd-181">Workflow</span></span>

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

### <span data-ttu-id="f48cd-182">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="f48cd-182">-MaximumVersion</span></span>

<span data-ttu-id="f48cd-183">Especifica a versão máxima do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="f48cd-183">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="f48cd-184">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="f48cd-184">-MinimumVersion</span></span>

<span data-ttu-id="f48cd-185">Especifica a versão mínima do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="f48cd-185">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="f48cd-186">Se uma versão superior estiver disponível, essa versão será retornada.</span><span class="sxs-lookup"><span data-stu-id="f48cd-186">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="f48cd-187">-Name</span><span class="sxs-lookup"><span data-stu-id="f48cd-187">-Name</span></span>

<span data-ttu-id="f48cd-188">Especifica um ou mais nomes de pacote ou nomes de pacote com caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="f48cd-188">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="f48cd-189">Separe vários nomes de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="f48cd-189">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="f48cd-190">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="f48cd-190">-PackageManagementProvider</span></span>

<span data-ttu-id="f48cd-191">Especifica o nome de um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="f48cd-191">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="f48cd-192">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="f48cd-192">-ProviderName</span></span>

<span data-ttu-id="f48cd-193">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-193">Specifies one or more package provider names.</span></span> <span data-ttu-id="f48cd-194">Separe vários nomes de provedor de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="f48cd-194">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="f48cd-195">Use `Get-PackageProvider` para obter uma lista de provedores de pacotes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f48cd-195">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="f48cd-196">-Proxy</span><span class="sxs-lookup"><span data-stu-id="f48cd-196">-Proxy</span></span>

<span data-ttu-id="f48cd-197">Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="f48cd-197">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="f48cd-198">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="f48cd-198">-ProxyCredential</span></span>

<span data-ttu-id="f48cd-199">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-199">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="f48cd-200">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="f48cd-200">-PublishLocation</span></span>

<span data-ttu-id="f48cd-201">Especifica um local para publicar o pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-201">Specifies a location for publishing the package.</span></span>

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

### <span data-ttu-id="f48cd-202">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="f48cd-202">-RequiredVersion</span></span>

<span data-ttu-id="f48cd-203">Especifica uma versão exata do pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="f48cd-203">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="f48cd-204">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="f48cd-204">-RoleCapability</span></span>

<span data-ttu-id="f48cd-205">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="f48cd-205">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="f48cd-206">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="f48cd-206">-ScriptPublishLocation</span></span>

<span data-ttu-id="f48cd-207">Especifica um local de publicação de script para o pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-207">Specifies a script publishing location for the package.</span></span>

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

### <span data-ttu-id="f48cd-208">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="f48cd-208">-ScriptSourceLocation</span></span>

<span data-ttu-id="f48cd-209">Especifica um local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="f48cd-209">Specifies a script source location.</span></span>

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

### <span data-ttu-id="f48cd-210">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="f48cd-210">-SkipValidate</span></span>

<span data-ttu-id="f48cd-211">Opção que ignora a validação de credenciais do pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-211">Switch that skips package credential validation.</span></span>

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

### <span data-ttu-id="f48cd-212">-Source</span><span class="sxs-lookup"><span data-stu-id="f48cd-212">-Source</span></span>

<span data-ttu-id="f48cd-213">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-213">Specifies one or more package sources.</span></span> <span data-ttu-id="f48cd-214">Use `Get-PackageSource` para obter uma lista de fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f48cd-214">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="f48cd-215">Um diretório do sistema de arquivos pode ser usado como uma fonte para baixar pacotes.</span><span class="sxs-lookup"><span data-stu-id="f48cd-215">A file system directory can be used as a source for download packages.</span></span>

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

### <span data-ttu-id="f48cd-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="f48cd-216">-Tag</span></span>

<span data-ttu-id="f48cd-217">Especifica uma ou mais cadeias de caracteres a serem pesquisadas nos metadados do pacote.</span><span class="sxs-lookup"><span data-stu-id="f48cd-217">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="f48cd-218">-Type</span><span class="sxs-lookup"><span data-stu-id="f48cd-218">-Type</span></span>

<span data-ttu-id="f48cd-219">Especifica se os pacotes devem ser pesquisados com um módulo, um script ou um.</span><span class="sxs-lookup"><span data-stu-id="f48cd-219">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="f48cd-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f48cd-220">CommonParameters</span></span>

<span data-ttu-id="f48cd-221">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f48cd-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f48cd-222">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f48cd-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f48cd-223">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f48cd-223">INPUTS</span></span>

### <span data-ttu-id="f48cd-224">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f48cd-224">None</span></span>

<span data-ttu-id="f48cd-225">`Find-Package` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="f48cd-225">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="f48cd-226">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f48cd-226">OUTPUTS</span></span>

### <span data-ttu-id="f48cd-227">SoftwareIdentify[]</span><span class="sxs-lookup"><span data-stu-id="f48cd-227">SoftwareIdentify[]</span></span>

<span data-ttu-id="f48cd-228">`Find-Package` gera um objeto **SoftwareIdentity** .</span><span class="sxs-lookup"><span data-stu-id="f48cd-228">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="f48cd-229">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f48cd-229">NOTES</span></span>

## <span data-ttu-id="f48cd-230">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f48cd-230">RELATED LINKS</span></span>

[<span data-ttu-id="f48cd-231">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f48cd-231">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="f48cd-232">Get-Package</span><span class="sxs-lookup"><span data-stu-id="f48cd-232">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="f48cd-233">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="f48cd-233">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="f48cd-234">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f48cd-234">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="f48cd-235">Install-Package</span><span class="sxs-lookup"><span data-stu-id="f48cd-235">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="f48cd-236">Save-Package</span><span class="sxs-lookup"><span data-stu-id="f48cd-236">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="f48cd-237">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="f48cd-237">Uninstall-Package</span></span>](Uninstall-Package.md)

