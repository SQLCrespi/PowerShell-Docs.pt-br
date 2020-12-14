---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 9fcf71462e1bf411f3c7c5d8322e6b6f3a667b9f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892807"
---
# <span data-ttu-id="8f58d-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="8f58d-103">Install-Package</span></span>

## <span data-ttu-id="8f58d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8f58d-104">SYNOPSIS</span></span>
<span data-ttu-id="8f58d-105">Instala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="8f58d-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="8f58d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f58d-106">SYNTAX</span></span>

### <span data-ttu-id="8f58d-107">PackageBySearch (padrão)</span><span class="sxs-lookup"><span data-stu-id="8f58d-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="8f58d-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="8f58d-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="8f58d-109">Programas: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="8f58d-109">Programs:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="8f58d-110">Programas: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="8f58d-110">Programs:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="8f58d-111">MSI: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="8f58d-111">msi:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="8f58d-112">MSI: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="8f58d-112">msi:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="8f58d-113">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="8f58d-113">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="8f58d-114">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="8f58d-114">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="8f58d-115">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="8f58d-115">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="8f58d-116">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="8f58d-116">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="8f58d-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f58d-117">DESCRIPTION</span></span>

<span data-ttu-id="8f58d-118">O `Install-Package` cmdlet instala um ou mais pacotes de software no computador local.</span><span class="sxs-lookup"><span data-stu-id="8f58d-118">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="8f58d-119">Se você tiver várias fontes de software, use `Get-PackageProvider` e `Get-PackageSource` para exibir detalhes sobre seus provedores.</span><span class="sxs-lookup"><span data-stu-id="8f58d-119">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="8f58d-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8f58d-120">EXAMPLES</span></span>

### <span data-ttu-id="8f58d-121">Exemplo 1: instalar um pacote por nome de pacote</span><span class="sxs-lookup"><span data-stu-id="8f58d-121">Example 1: Install a package by package name</span></span>

<span data-ttu-id="8f58d-122">O `Install-Package` cmdlet instala um pacote de software e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="8f58d-122">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="8f58d-123">`Install-Package` usa parâmetros para especificar o **nome** e a **origem** dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f58d-123">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="8f58d-124">O parâmetro **Credential** usa uma conta de usuário de domínio com permissões para instalar pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f58d-124">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="8f58d-125">O comando solicita a senha da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="8f58d-125">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="8f58d-126">Exemplo 2: usar Find-Package para instalar um pacote</span><span class="sxs-lookup"><span data-stu-id="8f58d-126">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="8f58d-127">Neste exemplo, o objeto retornado por `Find-Package` é enviado pelo pipeline e instalado pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="8f58d-127">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="8f58d-128">`Find-Package` usa o **nome** e os parâmetros de **origem** para localizar um pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-128">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="8f58d-129">O objeto é enviado pelo pipeline e `Install-Package` instala o pacote no computador local.</span><span class="sxs-lookup"><span data-stu-id="8f58d-129">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="8f58d-130">Exemplo 3: instalar pacotes especificando um intervalo de versões</span><span class="sxs-lookup"><span data-stu-id="8f58d-130">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="8f58d-131">`Install-Package` usa os parâmetros **MinimumVersion** e **MaximumVersion** para especificar um intervalo de versões de software.</span><span class="sxs-lookup"><span data-stu-id="8f58d-131">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="8f58d-132">`Install-Package` usa o **nome** e os parâmetros de **origem** para localizar um pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-132">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="8f58d-133">Os parâmetros **MinimumVersion** e **MaximumVersion** especificam um intervalo de versões de software.</span><span class="sxs-lookup"><span data-stu-id="8f58d-133">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="8f58d-134">A versão mais alta no intervalo é instalada.</span><span class="sxs-lookup"><span data-stu-id="8f58d-134">The highest version in the range is installed.</span></span>

## <span data-ttu-id="8f58d-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f58d-135">PARAMETERS</span></span>

### <span data-ttu-id="8f58d-136">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="8f58d-136">-AcceptLicense</span></span>

 <span data-ttu-id="8f58d-137">O **AcceptLicense** aceita automaticamente o contrato de licença durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="8f58d-137">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

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

### <span data-ttu-id="8f58d-138">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="8f58d-138">-AllowClobber</span></span>

<span data-ttu-id="8f58d-139">Substitui mensagens de aviso sobre conflitos com comandos existentes.</span><span class="sxs-lookup"><span data-stu-id="8f58d-139">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="8f58d-140">Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados.</span><span class="sxs-lookup"><span data-stu-id="8f58d-140">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="8f58d-141">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="8f58d-141">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="8f58d-142">Permite a instalação de pacotes marcados como pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="8f58d-142">Allows the installation of packages marked as prerelease.</span></span>

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

### <span data-ttu-id="8f58d-143">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="8f58d-143">-AllVersions</span></span>

<span data-ttu-id="8f58d-144">`Install-Package` instala todas as versões disponíveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-144">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="8f58d-145">Por padrão, apenas a versão mais recente é instalada.</span><span class="sxs-lookup"><span data-stu-id="8f58d-145">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="8f58d-146">-Command</span><span class="sxs-lookup"><span data-stu-id="8f58d-146">-Command</span></span>

<span data-ttu-id="8f58d-147">Especifica um ou mais comandos que o `Install-Package` pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8f58d-147">Specifies one or more commands that `Install-Package` searches.</span></span>

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

### <span data-ttu-id="8f58d-148">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="8f58d-148">-ConfigFile</span></span>

<span data-ttu-id="8f58d-149">Especifica um caminho que contém um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="8f58d-149">Specifies a path that contains a configuration file.</span></span>

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

### <span data-ttu-id="8f58d-150">-Contém</span><span class="sxs-lookup"><span data-stu-id="8f58d-150">-Contains</span></span>

<span data-ttu-id="8f58d-151">`Install-Package` Obtém objetos se o parâmetro **Contains** especifica um valor que corresponde a qualquer um dos valores de Propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="8f58d-151">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

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

### <span data-ttu-id="8f58d-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="8f58d-152">-Credential</span></span>

<span data-ttu-id="8f58d-153">Especifica uma conta de usuário que tem permissão para acessar o computador e executar comandos.</span><span class="sxs-lookup"><span data-stu-id="8f58d-153">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="8f58d-154">Digite um nome de usuário, como **User01**, **Domínio01 \ Usuário01** ou insira um objeto **PSCredential** , gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f58d-154">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="8f58d-155">Se você digitar um nome de usuário, você será solicitado a fornecer uma senha.</span><span class="sxs-lookup"><span data-stu-id="8f58d-155">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="8f58d-156">Quando o parâmetro **Credential** não for especificado, `Install-Package` o usará o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="8f58d-156">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="8f58d-157">-Destino</span><span class="sxs-lookup"><span data-stu-id="8f58d-157">-Destination</span></span>

<span data-ttu-id="8f58d-158">Especifica um caminho para um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="8f58d-158">Specifies a path to an input object.</span></span>

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

### <span data-ttu-id="8f58d-159">-DscResource</span><span class="sxs-lookup"><span data-stu-id="8f58d-159">-DscResource</span></span>

<span data-ttu-id="8f58d-160">Especifica um ou mais recursos de DSC (configuração de estado desejado) que são pesquisados pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="8f58d-160">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="8f58d-161">Use o `Find-DscResource` cmdlet para localizar recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="8f58d-161">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

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

### <span data-ttu-id="8f58d-162">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="8f58d-162">-ExcludeVersion</span></span>

<span data-ttu-id="8f58d-163">Alterne para excluir o número de versão no caminho da pasta.</span><span class="sxs-lookup"><span data-stu-id="8f58d-163">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="8f58d-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="8f58d-164">-Filter</span></span>

<span data-ttu-id="8f58d-165">Especifica os termos a serem pesquisados nas propriedades **Name** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="8f58d-165">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="8f58d-166">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="8f58d-166">-FilterOnTag</span></span>

<span data-ttu-id="8f58d-167">Especifica uma marca que filtra os resultados e exclui os resultados que não contêm a marca especificada.</span><span class="sxs-lookup"><span data-stu-id="8f58d-167">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

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

### <span data-ttu-id="8f58d-168">-Force</span><span class="sxs-lookup"><span data-stu-id="8f58d-168">-Force</span></span>

<span data-ttu-id="8f58d-169">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="8f58d-169">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="8f58d-170">Substitui as restrições que impedem `Install-Package` o sucesso, com exceção da segurança.</span><span class="sxs-lookup"><span data-stu-id="8f58d-170">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="8f58d-171">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="8f58d-171">-ForceBootstrap</span></span>

<span data-ttu-id="8f58d-172">Força o **PackageManagement** a instalar automaticamente o provedor de pacote para o pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="8f58d-172">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="8f58d-173">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="8f58d-173">-Headers</span></span>

<span data-ttu-id="8f58d-174">Especifica os cabeçalhos do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-174">Specifies the package headers.</span></span>

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

### <span data-ttu-id="8f58d-175">-Inclui</span><span class="sxs-lookup"><span data-stu-id="8f58d-175">-Includes</span></span>

<span data-ttu-id="8f58d-176">Especifica se o `Install-Package` deve localizar todos os tipos de pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-176">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="8f58d-177">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="8f58d-177">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8f58d-178">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f58d-178">Cmdlet</span></span>
- <span data-ttu-id="8f58d-179">DscResource</span><span class="sxs-lookup"><span data-stu-id="8f58d-179">DscResource</span></span>
- <span data-ttu-id="8f58d-180">Função</span><span class="sxs-lookup"><span data-stu-id="8f58d-180">Function</span></span>
- <span data-ttu-id="8f58d-181">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="8f58d-181">RoleCapability</span></span>
- <span data-ttu-id="8f58d-182">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8f58d-182">Workflow</span></span>

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

### <span data-ttu-id="8f58d-183">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8f58d-183">-InputObject</span></span>

<span data-ttu-id="8f58d-184">Aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="8f58d-184">Accepts pipeline input.</span></span> <span data-ttu-id="8f58d-185">Especifica um pacote usando o tipo de **SoftwareIdentity** do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-185">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="8f58d-186">`Find-Package` gera um objeto **SoftwareIdentity** .</span><span class="sxs-lookup"><span data-stu-id="8f58d-186">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="8f58d-187">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="8f58d-187">-InstallUpdate</span></span>

<span data-ttu-id="8f58d-188">Indica que o `Install-Package` instala atualizações.</span><span class="sxs-lookup"><span data-stu-id="8f58d-188">Indicates that `Install-Package` installs updates.</span></span>

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

### <span data-ttu-id="8f58d-189">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8f58d-189">-MaximumVersion</span></span>

<span data-ttu-id="8f58d-190">Especifica a versão de pacote máxima permitida que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="8f58d-190">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="8f58d-191">Se você não especificar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-191">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="8f58d-192">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8f58d-192">-MinimumVersion</span></span>

<span data-ttu-id="8f58d-193">Especifica a versão mínima permitida do pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="8f58d-193">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="8f58d-194">Se você não adicionar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="8f58d-194">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="8f58d-195">-Name</span><span class="sxs-lookup"><span data-stu-id="8f58d-195">-Name</span></span>

<span data-ttu-id="8f58d-196">Especifica um ou mais nomes de pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-196">Specifies one or more package names.</span></span> <span data-ttu-id="8f58d-197">Vários nomes de pacote devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="8f58d-197">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="8f58d-198">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="8f58d-198">-NoPathUpdate</span></span>

<span data-ttu-id="8f58d-199">**NoPathUpdate** se aplica somente ao `Install-Script` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f58d-199">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="8f58d-200">**NoPathUpdate** é um parâmetro dinâmico adicionado pelo provedor e não é suportado pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="8f58d-200">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

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

### <span data-ttu-id="8f58d-201">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="8f58d-201">-PackageManagementProvider</span></span>

<span data-ttu-id="8f58d-202">Especifica o nome do provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="8f58d-202">Specifies the name of the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="8f58d-203">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="8f58d-203">-ProviderName</span></span>

<span data-ttu-id="8f58d-204">Especifica um ou mais nomes de provedor de pacote para os quais o escopo da pesquisa de pacote será definido.</span><span class="sxs-lookup"><span data-stu-id="8f58d-204">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="8f58d-205">Você pode obter os nomes de provedor de pacotes executando o cmdlet `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="8f58d-205">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="8f58d-206">-Proxy</span><span class="sxs-lookup"><span data-stu-id="8f58d-206">-Proxy</span></span>

<span data-ttu-id="8f58d-207">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="8f58d-207">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="8f58d-208">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="8f58d-208">-ProxyCredential</span></span>

<span data-ttu-id="8f58d-209">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="8f58d-209">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="8f58d-210">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="8f58d-210">-PublishLocation</span></span>

<span data-ttu-id="8f58d-211">Especifica o caminho para o local de publicação de um pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-211">Specifies the path to a package's published location.</span></span>

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

### <span data-ttu-id="8f58d-212">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8f58d-212">-RequiredVersion</span></span>

<span data-ttu-id="8f58d-213">Especifica a versão exata permitida do pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="8f58d-213">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="8f58d-214">Se você não adicionar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="8f58d-214">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="8f58d-215">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="8f58d-215">-RoleCapability</span></span>

<span data-ttu-id="8f58d-216">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="8f58d-216">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="8f58d-217">-Escopo</span><span class="sxs-lookup"><span data-stu-id="8f58d-217">-Scope</span></span>

<span data-ttu-id="8f58d-218">Especifica o escopo para o qual instalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-218">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="8f58d-219">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="8f58d-219">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8f58d-220">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="8f58d-220">CurrentUser</span></span>
- <span data-ttu-id="8f58d-221">AllUsers</span><span class="sxs-lookup"><span data-stu-id="8f58d-221">AllUsers</span></span>

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

### <span data-ttu-id="8f58d-222">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="8f58d-222">-ScriptPublishLocation</span></span>

<span data-ttu-id="8f58d-223">Especifica o caminho para o local de publicação de um script.</span><span class="sxs-lookup"><span data-stu-id="8f58d-223">Specifies the path to a script's published location.</span></span>

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

### <span data-ttu-id="8f58d-224">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="8f58d-224">-ScriptSourceLocation</span></span>

<span data-ttu-id="8f58d-225">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="8f58d-225">Specifies the script source location.</span></span>

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

### <span data-ttu-id="8f58d-226">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="8f58d-226">-SkipDependencies</span></span>

<span data-ttu-id="8f58d-227">Ignora a instalação de dependências de software.</span><span class="sxs-lookup"><span data-stu-id="8f58d-227">Skips the installation of software dependencies.</span></span>

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

### <span data-ttu-id="8f58d-228">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="8f58d-228">-SkipPublisherCheck</span></span>

<span data-ttu-id="8f58d-229">Permite obter uma versão de pacote mais nova do que a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="8f58d-229">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="8f58d-230">Por exemplo, um pacote instalado que é assinado digitalmente por um fornecedor confiável, mas uma nova versão não é assinada digitalmente.</span><span class="sxs-lookup"><span data-stu-id="8f58d-230">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="8f58d-231">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="8f58d-231">-SkipValidate</span></span>

<span data-ttu-id="8f58d-232">Opção que ignora a validação das credenciais de um pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-232">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="8f58d-233">-Source</span><span class="sxs-lookup"><span data-stu-id="8f58d-233">-Source</span></span>

<span data-ttu-id="8f58d-234">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-234">Specifies one or more package sources.</span></span> <span data-ttu-id="8f58d-235">Vários nomes de origem de pacote devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="8f58d-235">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="8f58d-236">Você pode obter os nomes de origem do pacote executando o `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f58d-236">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="8f58d-237">-Tag</span><span class="sxs-lookup"><span data-stu-id="8f58d-237">-Tag</span></span>

<span data-ttu-id="8f58d-238">Especifica uma ou mais cadeias de caracteres a serem pesquisadas nos metadados do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-238">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="8f58d-239">-Type</span><span class="sxs-lookup"><span data-stu-id="8f58d-239">-Type</span></span>

<span data-ttu-id="8f58d-240">Especifica se é para procurar pacotes com um módulo, um script ou ambos.</span><span class="sxs-lookup"><span data-stu-id="8f58d-240">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="8f58d-241">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="8f58d-241">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8f58d-242">Módulo</span><span class="sxs-lookup"><span data-stu-id="8f58d-242">Module</span></span>
- <span data-ttu-id="8f58d-243">Script</span><span class="sxs-lookup"><span data-stu-id="8f58d-243">Script</span></span>
- <span data-ttu-id="8f58d-244">Tudo</span><span class="sxs-lookup"><span data-stu-id="8f58d-244">All</span></span>

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

### <span data-ttu-id="8f58d-245">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8f58d-245">-Confirm</span></span>

<span data-ttu-id="8f58d-246">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f58d-246">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8f58d-247">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8f58d-247">-WhatIf</span></span>

<span data-ttu-id="8f58d-248">Mostra o que aconteceria se o `Install-Package` cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="8f58d-248">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="8f58d-249">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="8f58d-249">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8f58d-250">-AdditionalArguments</span><span class="sxs-lookup"><span data-stu-id="8f58d-250">-AdditionalArguments</span></span>

<span data-ttu-id="8f58d-251">Especifica um ou mais argumentos adicionais para instalação.</span><span class="sxs-lookup"><span data-stu-id="8f58d-251">Specifies one or more additional arguments for installation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi:PackageBySearch, msi:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f58d-252">-IncludeSystemComponent</span><span class="sxs-lookup"><span data-stu-id="8f58d-252">-IncludeSystemComponent</span></span>

<span data-ttu-id="8f58d-253">Indica que esse cmdlet inclui componentes do sistema nos resultados.</span><span class="sxs-lookup"><span data-stu-id="8f58d-253">Indicates that this cmdlet includes system components in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f58d-254">-IncludeWindowsInstaller</span><span class="sxs-lookup"><span data-stu-id="8f58d-254">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="8f58d-255">Indica que esse cmdlet inclui o Windows Installer nos resultados.</span><span class="sxs-lookup"><span data-stu-id="8f58d-255">Indicates that this cmdlet includes the Windows installer in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8f58d-256">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8f58d-256">CommonParameters</span></span>

<span data-ttu-id="8f58d-257">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f58d-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f58d-258">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f58d-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f58d-259">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8f58d-259">INPUTS</span></span>

### <span data-ttu-id="8f58d-260">`Install-Package` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="8f58d-260">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="8f58d-261">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8f58d-261">OUTPUTS</span></span>

### <span data-ttu-id="8f58d-262">SoftwareIdentity[]</span><span class="sxs-lookup"><span data-stu-id="8f58d-262">SoftwareIdentity[]</span></span>

## <span data-ttu-id="8f58d-263">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8f58d-263">NOTES</span></span>

<span data-ttu-id="8f58d-264">A inclusão de um provedor de pacote em um comando pode tornar os parâmetros dinâmicos disponíveis para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8f58d-264">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="8f58d-265">Parâmetros dinâmicos são específicos para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="8f58d-265">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="8f58d-266">O `Get-Help` cmdlet lista os conjuntos de parâmetros de um cmdlet e inclui o conjunto de parâmetros do provedor.</span><span class="sxs-lookup"><span data-stu-id="8f58d-266">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="8f58d-267">Por exemplo, `Install-Package` tem o conjunto de parâmetros **PowerShellGet** que inclui `-NoPathUpdate` , `AllowClobber` e `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="8f58d-267">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f58d-268">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="8f58d-268">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="8f58d-269">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f58d-269">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="8f58d-270">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="8f58d-270">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="8f58d-271">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f58d-271">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="8f58d-272">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8f58d-272">RELATED LINKS</span></span>

[<span data-ttu-id="8f58d-273">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="8f58d-273">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="8f58d-274">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="8f58d-274">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="8f58d-275">Get-Help</span><span class="sxs-lookup"><span data-stu-id="8f58d-275">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="8f58d-276">Get-Package</span><span class="sxs-lookup"><span data-stu-id="8f58d-276">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="8f58d-277">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8f58d-277">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="8f58d-278">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8f58d-278">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="8f58d-279">Find-Package</span><span class="sxs-lookup"><span data-stu-id="8f58d-279">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="8f58d-280">Save-Package</span><span class="sxs-lookup"><span data-stu-id="8f58d-280">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="8f58d-281">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="8f58d-281">Uninstall-Package</span></span>](Uninstall-Package.md)
