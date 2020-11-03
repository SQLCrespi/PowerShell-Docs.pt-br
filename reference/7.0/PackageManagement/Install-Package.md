---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 506775bf4ef58244a04cb13c1cab926d112111bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194656"
---
# <span data-ttu-id="69d55-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="69d55-103">Install-Package</span></span>

## <span data-ttu-id="69d55-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="69d55-104">SYNOPSIS</span></span>
<span data-ttu-id="69d55-105">Instala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="69d55-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="69d55-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="69d55-106">SYNTAX</span></span>

### <span data-ttu-id="69d55-107">PackageBySearch (padrão)</span><span class="sxs-lookup"><span data-stu-id="69d55-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="69d55-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="69d55-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="69d55-109">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="69d55-109">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="69d55-110">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="69d55-110">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="69d55-111">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="69d55-111">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="69d55-112">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="69d55-112">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="69d55-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="69d55-113">DESCRIPTION</span></span>

<span data-ttu-id="69d55-114">O `Install-Package` cmdlet instala um ou mais pacotes de software no computador local.</span><span class="sxs-lookup"><span data-stu-id="69d55-114">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="69d55-115">Se você tiver várias fontes de software, use `Get-PackageProvider` e `Get-PackageSource` para exibir detalhes sobre seus provedores.</span><span class="sxs-lookup"><span data-stu-id="69d55-115">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="69d55-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="69d55-116">EXAMPLES</span></span>

### <span data-ttu-id="69d55-117">Exemplo 1: instalar um pacote por nome de pacote</span><span class="sxs-lookup"><span data-stu-id="69d55-117">Example 1: Install a package by package name</span></span>

<span data-ttu-id="69d55-118">O `Install-Package` cmdlet instala um pacote de software e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="69d55-118">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="69d55-119">`Install-Package` usa parâmetros para especificar o **nome** e a **origem** dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="69d55-119">`Install-Package` uses parameters to specify the packages **Name** and **Source** .</span></span> <span data-ttu-id="69d55-120">O parâmetro **Credential** usa uma conta de usuário de domínio com permissões para instalar pacotes.</span><span class="sxs-lookup"><span data-stu-id="69d55-120">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="69d55-121">O comando solicita a senha da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="69d55-121">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="69d55-122">Exemplo 2: usar Find-Package para instalar um pacote</span><span class="sxs-lookup"><span data-stu-id="69d55-122">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="69d55-123">Neste exemplo, o objeto retornado por `Find-Package` é enviado pelo pipeline e instalado pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="69d55-123">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="69d55-124">`Find-Package` usa o **nome** e os parâmetros de **origem** para localizar um pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-124">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="69d55-125">O objeto é enviado pelo pipeline e `Install-Package` instala o pacote no computador local.</span><span class="sxs-lookup"><span data-stu-id="69d55-125">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="69d55-126">Exemplo 3: instalar pacotes especificando um intervalo de versões</span><span class="sxs-lookup"><span data-stu-id="69d55-126">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="69d55-127">`Install-Package` usa os parâmetros **MinimumVersion** e **MaximumVersion** para especificar um intervalo de versões de software.</span><span class="sxs-lookup"><span data-stu-id="69d55-127">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="69d55-128">`Install-Package` usa o **nome** e os parâmetros de **origem** para localizar um pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-128">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="69d55-129">Os parâmetros **MinimumVersion** e **MaximumVersion** especificam um intervalo de versões de software.</span><span class="sxs-lookup"><span data-stu-id="69d55-129">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="69d55-130">A versão mais alta no intervalo é instalada.</span><span class="sxs-lookup"><span data-stu-id="69d55-130">The highest version in the range is installed.</span></span>

## <span data-ttu-id="69d55-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="69d55-131">PARAMETERS</span></span>

### <span data-ttu-id="69d55-132">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="69d55-132">-AcceptLicense</span></span>

 <span data-ttu-id="69d55-133">O **AcceptLicense** aceita automaticamente o contrato de licença durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="69d55-133">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-134">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="69d55-134">-AllowClobber</span></span>

<span data-ttu-id="69d55-135">Substitui mensagens de aviso sobre conflitos com comandos existentes.</span><span class="sxs-lookup"><span data-stu-id="69d55-135">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="69d55-136">Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados.</span><span class="sxs-lookup"><span data-stu-id="69d55-136">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-137">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="69d55-137">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="69d55-138">Permite a instalação de pacotes marcados como pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="69d55-138">Allows the installation of packages marked as prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-139">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="69d55-139">-AllVersions</span></span>

<span data-ttu-id="69d55-140">`Install-Package` instala todas as versões disponíveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-140">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="69d55-141">Por padrão, apenas a versão mais recente é instalada.</span><span class="sxs-lookup"><span data-stu-id="69d55-141">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="69d55-142">-Command</span><span class="sxs-lookup"><span data-stu-id="69d55-142">-Command</span></span>

<span data-ttu-id="69d55-143">Especifica um ou mais comandos que o `Install-Package` pesquisa.</span><span class="sxs-lookup"><span data-stu-id="69d55-143">Specifies one or more commands that `Install-Package` searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-144">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="69d55-144">-ConfigFile</span></span>

<span data-ttu-id="69d55-145">Especifica um caminho que contém um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="69d55-145">Specifies a path that contains a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-146">-Contém</span><span class="sxs-lookup"><span data-stu-id="69d55-146">-Contains</span></span>

<span data-ttu-id="69d55-147">`Install-Package` Obtém objetos se o parâmetro **Contains** especifica um valor que corresponde a qualquer um dos valores de Propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="69d55-147">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="69d55-148">-Credential</span></span>

<span data-ttu-id="69d55-149">Especifica uma conta de usuário que tem permissão para acessar o computador e executar comandos.</span><span class="sxs-lookup"><span data-stu-id="69d55-149">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="69d55-150">Digite um nome de usuário, como **User01** , **Domínio01 \ Usuário01** ou insira um objeto **PSCredential** , gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69d55-150">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="69d55-151">Se você digitar um nome de usuário, você será solicitado a fornecer uma senha.</span><span class="sxs-lookup"><span data-stu-id="69d55-151">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="69d55-152">Quando o parâmetro **Credential** não for especificado, `Install-Package` o usará o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="69d55-152">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="69d55-153">-Destino</span><span class="sxs-lookup"><span data-stu-id="69d55-153">-Destination</span></span>

<span data-ttu-id="69d55-154">Especifica um caminho para um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="69d55-154">Specifies a path to an input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-155">-DscResource</span><span class="sxs-lookup"><span data-stu-id="69d55-155">-DscResource</span></span>

<span data-ttu-id="69d55-156">Especifica um ou mais recursos de DSC (configuração de estado desejado) que são pesquisados pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="69d55-156">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="69d55-157">Use o `Find-DscResource` cmdlet para localizar recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="69d55-157">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-158">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="69d55-158">-ExcludeVersion</span></span>

<span data-ttu-id="69d55-159">Alterne para excluir o número de versão no caminho da pasta.</span><span class="sxs-lookup"><span data-stu-id="69d55-159">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-160">-Filter</span><span class="sxs-lookup"><span data-stu-id="69d55-160">-Filter</span></span>

<span data-ttu-id="69d55-161">Especifica os termos a serem pesquisados nas propriedades **Name** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="69d55-161">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-162">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="69d55-162">-FilterOnTag</span></span>

<span data-ttu-id="69d55-163">Especifica uma marca que filtra os resultados e exclui os resultados que não contêm a marca especificada.</span><span class="sxs-lookup"><span data-stu-id="69d55-163">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-164">-Force</span><span class="sxs-lookup"><span data-stu-id="69d55-164">-Force</span></span>

<span data-ttu-id="69d55-165">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="69d55-165">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="69d55-166">Substitui as restrições que impedem `Install-Package` o sucesso, com exceção da segurança.</span><span class="sxs-lookup"><span data-stu-id="69d55-166">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="69d55-167">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="69d55-167">-ForceBootstrap</span></span>

<span data-ttu-id="69d55-168">Força o **PackageManagement** a instalar automaticamente o provedor de pacote para o pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="69d55-168">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="69d55-169">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="69d55-169">-Headers</span></span>

<span data-ttu-id="69d55-170">Especifica os cabeçalhos do pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-170">Specifies the package headers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-171">-Inclui</span><span class="sxs-lookup"><span data-stu-id="69d55-171">-Includes</span></span>

<span data-ttu-id="69d55-172">Especifica se o `Install-Package` deve localizar todos os tipos de pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-172">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="69d55-173">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69d55-173">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="69d55-174">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="69d55-174">Cmdlet</span></span>
- <span data-ttu-id="69d55-175">DscResource</span><span class="sxs-lookup"><span data-stu-id="69d55-175">DscResource</span></span>
- <span data-ttu-id="69d55-176">Função</span><span class="sxs-lookup"><span data-stu-id="69d55-176">Function</span></span>
- <span data-ttu-id="69d55-177">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="69d55-177">RoleCapability</span></span>
- <span data-ttu-id="69d55-178">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="69d55-178">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="69d55-179">-InputObject</span></span>

<span data-ttu-id="69d55-180">Aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="69d55-180">Accepts pipeline input.</span></span> <span data-ttu-id="69d55-181">Especifica um pacote usando o tipo de **SoftwareIdentity** do pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-181">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="69d55-182">`Find-Package` gera um objeto **SoftwareIdentity** .</span><span class="sxs-lookup"><span data-stu-id="69d55-182">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-183">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="69d55-183">-InstallUpdate</span></span>

<span data-ttu-id="69d55-184">Indica que o `Install-Package` instala atualizações.</span><span class="sxs-lookup"><span data-stu-id="69d55-184">Indicates that `Install-Package` installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-185">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="69d55-185">-MaximumVersion</span></span>

<span data-ttu-id="69d55-186">Especifica a versão de pacote máxima permitida que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="69d55-186">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="69d55-187">Se você não especificar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-187">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="69d55-188">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="69d55-188">-MinimumVersion</span></span>

<span data-ttu-id="69d55-189">Especifica a versão mínima permitida do pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="69d55-189">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="69d55-190">Se você não adicionar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="69d55-190">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="69d55-191">-Name</span><span class="sxs-lookup"><span data-stu-id="69d55-191">-Name</span></span>

<span data-ttu-id="69d55-192">Especifica um ou mais nomes de pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-192">Specifies one or more package names.</span></span> <span data-ttu-id="69d55-193">Vários nomes de pacote devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="69d55-193">Multiple package names must be separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-194">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="69d55-194">-NoPathUpdate</span></span>

<span data-ttu-id="69d55-195">**NoPathUpdate** se aplica somente ao `Install-Script` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69d55-195">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="69d55-196">**NoPathUpdate** é um parâmetro dinâmico adicionado pelo provedor e não é suportado pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="69d55-196">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-197">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="69d55-197">-PackageManagementProvider</span></span>

<span data-ttu-id="69d55-198">Especifica o nome do provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="69d55-198">Specifies the name of the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-199">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="69d55-199">-ProviderName</span></span>

<span data-ttu-id="69d55-200">Especifica um ou mais nomes de provedor de pacote para os quais o escopo da pesquisa de pacote será definido.</span><span class="sxs-lookup"><span data-stu-id="69d55-200">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="69d55-201">Você pode obter os nomes de provedor de pacotes executando o cmdlet `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="69d55-201">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="69d55-202">-Proxy</span><span class="sxs-lookup"><span data-stu-id="69d55-202">-Proxy</span></span>

<span data-ttu-id="69d55-203">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="69d55-203">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="69d55-204">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="69d55-204">-ProxyCredential</span></span>

<span data-ttu-id="69d55-205">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="69d55-205">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="69d55-206">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="69d55-206">-PublishLocation</span></span>

<span data-ttu-id="69d55-207">Especifica o caminho para o local de publicação de um pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-207">Specifies the path to a package's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-208">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="69d55-208">-RequiredVersion</span></span>

<span data-ttu-id="69d55-209">Especifica a versão exata permitida do pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="69d55-209">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="69d55-210">Se você não adicionar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="69d55-210">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="69d55-211">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="69d55-211">-RoleCapability</span></span>

<span data-ttu-id="69d55-212">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="69d55-212">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-213">-Escopo</span><span class="sxs-lookup"><span data-stu-id="69d55-213">-Scope</span></span>

<span data-ttu-id="69d55-214">Especifica o escopo para o qual instalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-214">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="69d55-215">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69d55-215">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="69d55-216">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="69d55-216">CurrentUser</span></span>
- <span data-ttu-id="69d55-217">AllUsers</span><span class="sxs-lookup"><span data-stu-id="69d55-217">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-218">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="69d55-218">-ScriptPublishLocation</span></span>

<span data-ttu-id="69d55-219">Especifica o caminho para o local de publicação de um script.</span><span class="sxs-lookup"><span data-stu-id="69d55-219">Specifies the path to a script's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-220">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="69d55-220">-ScriptSourceLocation</span></span>

<span data-ttu-id="69d55-221">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="69d55-221">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-222">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="69d55-222">-SkipDependencies</span></span>

<span data-ttu-id="69d55-223">Ignora a instalação de dependências de software.</span><span class="sxs-lookup"><span data-stu-id="69d55-223">Skips the installation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-224">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="69d55-224">-SkipPublisherCheck</span></span>

<span data-ttu-id="69d55-225">Permite obter uma versão de pacote mais nova do que a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="69d55-225">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="69d55-226">Por exemplo, um pacote instalado que é assinado digitalmente por um fornecedor confiável, mas uma nova versão não é assinada digitalmente.</span><span class="sxs-lookup"><span data-stu-id="69d55-226">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-227">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="69d55-227">-SkipValidate</span></span>

<span data-ttu-id="69d55-228">Opção que ignora a validação das credenciais de um pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-228">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-229">-Source</span><span class="sxs-lookup"><span data-stu-id="69d55-229">-Source</span></span>

<span data-ttu-id="69d55-230">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-230">Specifies one or more package sources.</span></span> <span data-ttu-id="69d55-231">Vários nomes de origem de pacote devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="69d55-231">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="69d55-232">Você pode obter os nomes de origem do pacote executando o `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69d55-232">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="69d55-233">-Tag</span><span class="sxs-lookup"><span data-stu-id="69d55-233">-Tag</span></span>

<span data-ttu-id="69d55-234">Especifica uma ou mais cadeias de caracteres a serem pesquisadas nos metadados do pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-234">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-235">-Type</span><span class="sxs-lookup"><span data-stu-id="69d55-235">-Type</span></span>

<span data-ttu-id="69d55-236">Especifica se é para procurar pacotes com um módulo, um script ou ambos.</span><span class="sxs-lookup"><span data-stu-id="69d55-236">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="69d55-237">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="69d55-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="69d55-238">Módulo</span><span class="sxs-lookup"><span data-stu-id="69d55-238">Module</span></span>
- <span data-ttu-id="69d55-239">Script</span><span class="sxs-lookup"><span data-stu-id="69d55-239">Script</span></span>
- <span data-ttu-id="69d55-240">Tudo</span><span class="sxs-lookup"><span data-stu-id="69d55-240">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69d55-241">-Confirm</span><span class="sxs-lookup"><span data-stu-id="69d55-241">-Confirm</span></span>

<span data-ttu-id="69d55-242">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69d55-242">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="69d55-243">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="69d55-243">-WhatIf</span></span>

<span data-ttu-id="69d55-244">Mostra o que aconteceria se o `Install-Package` cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="69d55-244">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="69d55-245">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="69d55-245">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="69d55-246">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="69d55-246">CommonParameters</span></span>

<span data-ttu-id="69d55-247">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="69d55-247">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="69d55-248">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="69d55-248">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="69d55-249">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="69d55-249">INPUTS</span></span>

### <span data-ttu-id="69d55-250">`Install-Package` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="69d55-250">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="69d55-251">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="69d55-251">OUTPUTS</span></span>

### <span data-ttu-id="69d55-252">SoftwareIdentity[]</span><span class="sxs-lookup"><span data-stu-id="69d55-252">SoftwareIdentity[]</span></span>

## <span data-ttu-id="69d55-253">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="69d55-253">NOTES</span></span>

<span data-ttu-id="69d55-254">A inclusão de um provedor de pacote em um comando pode tornar os parâmetros dinâmicos disponíveis para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="69d55-254">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="69d55-255">Parâmetros dinâmicos são específicos para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="69d55-255">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="69d55-256">O `Get-Help` cmdlet lista os conjuntos de parâmetros de um cmdlet e inclui o conjunto de parâmetros do provedor.</span><span class="sxs-lookup"><span data-stu-id="69d55-256">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="69d55-257">Por exemplo, `Install-Package` tem o conjunto de parâmetros **PowerShellGet** que inclui `-NoPathUpdate` , `AllowClobber` e `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="69d55-257">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="69d55-258">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="69d55-258">RELATED LINKS</span></span>

[<span data-ttu-id="69d55-259">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="69d55-259">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="69d55-260">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="69d55-260">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="69d55-261">Get-Help</span><span class="sxs-lookup"><span data-stu-id="69d55-261">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="69d55-262">Get-Package</span><span class="sxs-lookup"><span data-stu-id="69d55-262">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="69d55-263">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="69d55-263">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="69d55-264">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="69d55-264">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="69d55-265">Find-Package</span><span class="sxs-lookup"><span data-stu-id="69d55-265">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="69d55-266">Save-Package</span><span class="sxs-lookup"><span data-stu-id="69d55-266">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="69d55-267">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="69d55-267">Uninstall-Package</span></span>](Uninstall-Package.md)
