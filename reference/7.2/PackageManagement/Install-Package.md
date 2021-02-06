---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 1518be0d34733e36217b46cbbf496e580ec7b649
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595985"
---
# <span data-ttu-id="80f85-102">Install-Package</span><span class="sxs-lookup"><span data-stu-id="80f85-102">Install-Package</span></span>

## <span data-ttu-id="80f85-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="80f85-103">SYNOPSIS</span></span>
<span data-ttu-id="80f85-104">Instala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="80f85-104">Installs one or more software packages.</span></span>

## <span data-ttu-id="80f85-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80f85-105">SYNTAX</span></span>

### <span data-ttu-id="80f85-106">PackageBySearch (padrão)</span><span class="sxs-lookup"><span data-stu-id="80f85-106">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="80f85-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="80f85-107">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="80f85-108">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="80f85-108">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="80f85-109">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="80f85-109">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="80f85-110">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="80f85-110">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="80f85-111">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="80f85-111">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="80f85-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="80f85-112">DESCRIPTION</span></span>

<span data-ttu-id="80f85-113">O `Install-Package` cmdlet instala um ou mais pacotes de software no computador local.</span><span class="sxs-lookup"><span data-stu-id="80f85-113">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="80f85-114">Se você tiver várias fontes de software, use `Get-PackageProvider` e `Get-PackageSource` para exibir detalhes sobre seus provedores.</span><span class="sxs-lookup"><span data-stu-id="80f85-114">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="80f85-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="80f85-115">EXAMPLES</span></span>

### <span data-ttu-id="80f85-116">Exemplo 1: instalar um pacote por nome de pacote</span><span class="sxs-lookup"><span data-stu-id="80f85-116">Example 1: Install a package by package name</span></span>

<span data-ttu-id="80f85-117">O `Install-Package` cmdlet instala um pacote de software e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="80f85-117">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="80f85-118">`Install-Package` usa parâmetros para especificar o **nome** e a **origem** dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="80f85-118">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="80f85-119">O parâmetro **Credential** usa uma conta de usuário de domínio com permissões para instalar pacotes.</span><span class="sxs-lookup"><span data-stu-id="80f85-119">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="80f85-120">O comando solicita a senha da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="80f85-120">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="80f85-121">Exemplo 2: usar Find-Package para instalar um pacote</span><span class="sxs-lookup"><span data-stu-id="80f85-121">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="80f85-122">Neste exemplo, o objeto retornado por `Find-Package` é enviado pelo pipeline e instalado pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="80f85-122">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="80f85-123">`Find-Package` usa o **nome** e os parâmetros de **origem** para localizar um pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-123">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="80f85-124">O objeto é enviado pelo pipeline e `Install-Package` instala o pacote no computador local.</span><span class="sxs-lookup"><span data-stu-id="80f85-124">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="80f85-125">Exemplo 3: instalar pacotes especificando um intervalo de versões</span><span class="sxs-lookup"><span data-stu-id="80f85-125">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="80f85-126">`Install-Package` usa os parâmetros **MinimumVersion** e **MaximumVersion** para especificar um intervalo de versões de software.</span><span class="sxs-lookup"><span data-stu-id="80f85-126">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="80f85-127">`Install-Package` usa o **nome** e os parâmetros de **origem** para localizar um pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-127">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="80f85-128">Os parâmetros **MinimumVersion** e **MaximumVersion** especificam um intervalo de versões de software.</span><span class="sxs-lookup"><span data-stu-id="80f85-128">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="80f85-129">A versão mais alta no intervalo é instalada.</span><span class="sxs-lookup"><span data-stu-id="80f85-129">The highest version in the range is installed.</span></span>

## <span data-ttu-id="80f85-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80f85-130">PARAMETERS</span></span>

### <span data-ttu-id="80f85-131">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="80f85-131">-AcceptLicense</span></span>

 <span data-ttu-id="80f85-132">O **AcceptLicense** aceita automaticamente o contrato de licença durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="80f85-132">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

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

### <span data-ttu-id="80f85-133">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="80f85-133">-AllowClobber</span></span>

<span data-ttu-id="80f85-134">Substitui mensagens de aviso sobre conflitos com comandos existentes.</span><span class="sxs-lookup"><span data-stu-id="80f85-134">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="80f85-135">Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados.</span><span class="sxs-lookup"><span data-stu-id="80f85-135">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="80f85-136">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="80f85-136">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="80f85-137">Permite a instalação de pacotes marcados como pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="80f85-137">Allows the installation of packages marked as prerelease.</span></span>

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

### <span data-ttu-id="80f85-138">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="80f85-138">-AllVersions</span></span>

<span data-ttu-id="80f85-139">`Install-Package` instala todas as versões disponíveis do pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-139">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="80f85-140">Por padrão, apenas a versão mais recente é instalada.</span><span class="sxs-lookup"><span data-stu-id="80f85-140">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="80f85-141">-Command</span><span class="sxs-lookup"><span data-stu-id="80f85-141">-Command</span></span>

<span data-ttu-id="80f85-142">Especifica um ou mais comandos que o `Install-Package` pesquisa.</span><span class="sxs-lookup"><span data-stu-id="80f85-142">Specifies one or more commands that `Install-Package` searches.</span></span>

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

### <span data-ttu-id="80f85-143">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="80f85-143">-ConfigFile</span></span>

<span data-ttu-id="80f85-144">Especifica um caminho que contém um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="80f85-144">Specifies a path that contains a configuration file.</span></span>

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

### <span data-ttu-id="80f85-145">-Contém</span><span class="sxs-lookup"><span data-stu-id="80f85-145">-Contains</span></span>

<span data-ttu-id="80f85-146">`Install-Package` Obtém objetos se o parâmetro **Contains** especifica um valor que corresponde a qualquer um dos valores de Propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="80f85-146">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

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

### <span data-ttu-id="80f85-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="80f85-147">-Credential</span></span>

<span data-ttu-id="80f85-148">Especifica uma conta de usuário que tem permissão para acessar o computador e executar comandos.</span><span class="sxs-lookup"><span data-stu-id="80f85-148">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="80f85-149">Digite um nome de usuário, como **User01**, **Domínio01 \ Usuário01** ou insira um objeto **PSCredential** , gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="80f85-149">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="80f85-150">Se você digitar um nome de usuário, você será solicitado a fornecer uma senha.</span><span class="sxs-lookup"><span data-stu-id="80f85-150">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="80f85-151">Quando o parâmetro **Credential** não for especificado, `Install-Package` o usará o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="80f85-151">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="80f85-152">-Destino</span><span class="sxs-lookup"><span data-stu-id="80f85-152">-Destination</span></span>

<span data-ttu-id="80f85-153">Especifica um caminho para um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="80f85-153">Specifies a path to an input object.</span></span>

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

### <span data-ttu-id="80f85-154">-DscResource</span><span class="sxs-lookup"><span data-stu-id="80f85-154">-DscResource</span></span>

<span data-ttu-id="80f85-155">Especifica um ou mais recursos de DSC (configuração de estado desejado) que são pesquisados pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="80f85-155">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="80f85-156">Use o `Find-DscResource` cmdlet para localizar recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="80f85-156">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

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

### <span data-ttu-id="80f85-157">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="80f85-157">-ExcludeVersion</span></span>

<span data-ttu-id="80f85-158">Alterne para excluir o número de versão no caminho da pasta.</span><span class="sxs-lookup"><span data-stu-id="80f85-158">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="80f85-159">-Filter</span><span class="sxs-lookup"><span data-stu-id="80f85-159">-Filter</span></span>

<span data-ttu-id="80f85-160">Especifica os termos a serem pesquisados nas propriedades **Name** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="80f85-160">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="80f85-161">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="80f85-161">-FilterOnTag</span></span>

<span data-ttu-id="80f85-162">Especifica uma marca que filtra os resultados e exclui os resultados que não contêm a marca especificada.</span><span class="sxs-lookup"><span data-stu-id="80f85-162">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

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

### <span data-ttu-id="80f85-163">-Force</span><span class="sxs-lookup"><span data-stu-id="80f85-163">-Force</span></span>

<span data-ttu-id="80f85-164">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="80f85-164">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="80f85-165">Substitui as restrições que impedem `Install-Package` o sucesso, com exceção da segurança.</span><span class="sxs-lookup"><span data-stu-id="80f85-165">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="80f85-166">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="80f85-166">-ForceBootstrap</span></span>

<span data-ttu-id="80f85-167">Força o **PackageManagement** a instalar automaticamente o provedor de pacote para o pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="80f85-167">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="80f85-168">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="80f85-168">-Headers</span></span>

<span data-ttu-id="80f85-169">Especifica os cabeçalhos do pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-169">Specifies the package headers.</span></span>

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

### <span data-ttu-id="80f85-170">-Inclui</span><span class="sxs-lookup"><span data-stu-id="80f85-170">-Includes</span></span>

<span data-ttu-id="80f85-171">Especifica se o `Install-Package` deve localizar todos os tipos de pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-171">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="80f85-172">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="80f85-172">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="80f85-173">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="80f85-173">Cmdlet</span></span>
- <span data-ttu-id="80f85-174">DscResource</span><span class="sxs-lookup"><span data-stu-id="80f85-174">DscResource</span></span>
- <span data-ttu-id="80f85-175">Função</span><span class="sxs-lookup"><span data-stu-id="80f85-175">Function</span></span>
- <span data-ttu-id="80f85-176">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="80f85-176">RoleCapability</span></span>
- <span data-ttu-id="80f85-177">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="80f85-177">Workflow</span></span>

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

### <span data-ttu-id="80f85-178">-InputObject</span><span class="sxs-lookup"><span data-stu-id="80f85-178">-InputObject</span></span>

<span data-ttu-id="80f85-179">Aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="80f85-179">Accepts pipeline input.</span></span> <span data-ttu-id="80f85-180">Especifica um pacote usando o tipo de **SoftwareIdentity** do pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-180">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="80f85-181">`Find-Package` gera um objeto **SoftwareIdentity** .</span><span class="sxs-lookup"><span data-stu-id="80f85-181">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="80f85-182">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="80f85-182">-InstallUpdate</span></span>

<span data-ttu-id="80f85-183">Indica que o `Install-Package` instala atualizações.</span><span class="sxs-lookup"><span data-stu-id="80f85-183">Indicates that `Install-Package` installs updates.</span></span>

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

### <span data-ttu-id="80f85-184">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="80f85-184">-MaximumVersion</span></span>

<span data-ttu-id="80f85-185">Especifica a versão de pacote máxima permitida que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="80f85-185">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="80f85-186">Se você não especificar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-186">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="80f85-187">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="80f85-187">-MinimumVersion</span></span>

<span data-ttu-id="80f85-188">Especifica a versão mínima permitida do pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="80f85-188">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="80f85-189">Se você não adicionar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="80f85-189">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="80f85-190">-Name</span><span class="sxs-lookup"><span data-stu-id="80f85-190">-Name</span></span>

<span data-ttu-id="80f85-191">Especifica um ou mais nomes de pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-191">Specifies one or more package names.</span></span> <span data-ttu-id="80f85-192">Vários nomes de pacote devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="80f85-192">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="80f85-193">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="80f85-193">-NoPathUpdate</span></span>

<span data-ttu-id="80f85-194">**NoPathUpdate** se aplica somente ao `Install-Script` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="80f85-194">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="80f85-195">**NoPathUpdate** é um parâmetro dinâmico adicionado pelo provedor e não é suportado pelo `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="80f85-195">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

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

### <span data-ttu-id="80f85-196">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="80f85-196">-PackageManagementProvider</span></span>

<span data-ttu-id="80f85-197">Especifica o nome do provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="80f85-197">Specifies the name of the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="80f85-198">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="80f85-198">-ProviderName</span></span>

<span data-ttu-id="80f85-199">Especifica um ou mais nomes de provedor de pacote para os quais o escopo da pesquisa de pacote será definido.</span><span class="sxs-lookup"><span data-stu-id="80f85-199">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="80f85-200">Você pode obter os nomes de provedor de pacotes executando o cmdlet `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="80f85-200">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="80f85-201">-Proxy</span><span class="sxs-lookup"><span data-stu-id="80f85-201">-Proxy</span></span>

<span data-ttu-id="80f85-202">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="80f85-202">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="80f85-203">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="80f85-203">-ProxyCredential</span></span>

<span data-ttu-id="80f85-204">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="80f85-204">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="80f85-205">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="80f85-205">-PublishLocation</span></span>

<span data-ttu-id="80f85-206">Especifica o caminho para o local de publicação de um pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-206">Specifies the path to a package's published location.</span></span>

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

### <span data-ttu-id="80f85-207">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="80f85-207">-RequiredVersion</span></span>

<span data-ttu-id="80f85-208">Especifica a versão exata permitida do pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="80f85-208">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="80f85-209">Se você não adicionar esse parâmetro, `Install-Package` o instalará a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="80f85-209">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="80f85-210">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="80f85-210">-RoleCapability</span></span>

<span data-ttu-id="80f85-211">Especifica uma matriz de recursos de função.</span><span class="sxs-lookup"><span data-stu-id="80f85-211">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="80f85-212">-Escopo</span><span class="sxs-lookup"><span data-stu-id="80f85-212">-Scope</span></span>

<span data-ttu-id="80f85-213">Especifica o escopo para o qual instalar o pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-213">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="80f85-214">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="80f85-214">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="80f85-215">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="80f85-215">CurrentUser</span></span>
- <span data-ttu-id="80f85-216">AllUsers</span><span class="sxs-lookup"><span data-stu-id="80f85-216">AllUsers</span></span>

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

### <span data-ttu-id="80f85-217">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="80f85-217">-ScriptPublishLocation</span></span>

<span data-ttu-id="80f85-218">Especifica o caminho para o local de publicação de um script.</span><span class="sxs-lookup"><span data-stu-id="80f85-218">Specifies the path to a script's published location.</span></span>

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

### <span data-ttu-id="80f85-219">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="80f85-219">-ScriptSourceLocation</span></span>

<span data-ttu-id="80f85-220">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="80f85-220">Specifies the script source location.</span></span>

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

### <span data-ttu-id="80f85-221">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="80f85-221">-SkipDependencies</span></span>

<span data-ttu-id="80f85-222">Ignora a instalação de dependências de software.</span><span class="sxs-lookup"><span data-stu-id="80f85-222">Skips the installation of software dependencies.</span></span>

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

### <span data-ttu-id="80f85-223">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="80f85-223">-SkipPublisherCheck</span></span>

<span data-ttu-id="80f85-224">Permite obter uma versão de pacote mais nova do que a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="80f85-224">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="80f85-225">Por exemplo, um pacote instalado que é assinado digitalmente por um fornecedor confiável, mas uma nova versão não é assinada digitalmente.</span><span class="sxs-lookup"><span data-stu-id="80f85-225">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="80f85-226">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="80f85-226">-SkipValidate</span></span>

<span data-ttu-id="80f85-227">Opção que ignora a validação das credenciais de um pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-227">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="80f85-228">-Source</span><span class="sxs-lookup"><span data-stu-id="80f85-228">-Source</span></span>

<span data-ttu-id="80f85-229">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-229">Specifies one or more package sources.</span></span> <span data-ttu-id="80f85-230">Vários nomes de origem de pacote devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="80f85-230">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="80f85-231">Você pode obter os nomes de origem do pacote executando o `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="80f85-231">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="80f85-232">-Tag</span><span class="sxs-lookup"><span data-stu-id="80f85-232">-Tag</span></span>

<span data-ttu-id="80f85-233">Especifica uma ou mais cadeias de caracteres a serem pesquisadas nos metadados do pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-233">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="80f85-234">-Type</span><span class="sxs-lookup"><span data-stu-id="80f85-234">-Type</span></span>

<span data-ttu-id="80f85-235">Especifica se é para procurar pacotes com um módulo, um script ou ambos.</span><span class="sxs-lookup"><span data-stu-id="80f85-235">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="80f85-236">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="80f85-236">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="80f85-237">Módulo</span><span class="sxs-lookup"><span data-stu-id="80f85-237">Module</span></span>
- <span data-ttu-id="80f85-238">Script</span><span class="sxs-lookup"><span data-stu-id="80f85-238">Script</span></span>
- <span data-ttu-id="80f85-239">Tudo</span><span class="sxs-lookup"><span data-stu-id="80f85-239">All</span></span>

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

### <span data-ttu-id="80f85-240">-Confirm</span><span class="sxs-lookup"><span data-stu-id="80f85-240">-Confirm</span></span>

<span data-ttu-id="80f85-241">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="80f85-241">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="80f85-242">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="80f85-242">-WhatIf</span></span>

<span data-ttu-id="80f85-243">Mostra o que aconteceria se o `Install-Package` cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="80f85-243">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="80f85-244">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="80f85-244">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="80f85-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="80f85-245">CommonParameters</span></span>

<span data-ttu-id="80f85-246">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="80f85-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80f85-247">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="80f85-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="80f85-248">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="80f85-248">INPUTS</span></span>

### <span data-ttu-id="80f85-249">`Install-Package` aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="80f85-249">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="80f85-250">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="80f85-250">OUTPUTS</span></span>

### <span data-ttu-id="80f85-251">SoftwareIdentity[]</span><span class="sxs-lookup"><span data-stu-id="80f85-251">SoftwareIdentity[]</span></span>

## <span data-ttu-id="80f85-252">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="80f85-252">NOTES</span></span>

<span data-ttu-id="80f85-253">A inclusão de um provedor de pacote em um comando pode tornar os parâmetros dinâmicos disponíveis para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="80f85-253">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="80f85-254">Parâmetros dinâmicos são específicos para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="80f85-254">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="80f85-255">O `Get-Help` cmdlet lista os conjuntos de parâmetros de um cmdlet e inclui o conjunto de parâmetros do provedor.</span><span class="sxs-lookup"><span data-stu-id="80f85-255">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="80f85-256">Por exemplo, `Install-Package` tem o conjunto de parâmetros **PowerShellGet** que inclui `-NoPathUpdate` , `AllowClobber` e `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="80f85-256">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80f85-257">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="80f85-257">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="80f85-258">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80f85-258">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="80f85-259">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="80f85-259">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="80f85-260">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80f85-260">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="80f85-261">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="80f85-261">RELATED LINKS</span></span>

[<span data-ttu-id="80f85-262">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="80f85-262">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="80f85-263">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="80f85-263">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="80f85-264">Get-Help</span><span class="sxs-lookup"><span data-stu-id="80f85-264">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="80f85-265">Get-Package</span><span class="sxs-lookup"><span data-stu-id="80f85-265">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="80f85-266">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="80f85-266">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="80f85-267">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="80f85-267">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="80f85-268">Find-Package</span><span class="sxs-lookup"><span data-stu-id="80f85-268">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="80f85-269">Save-Package</span><span class="sxs-lookup"><span data-stu-id="80f85-269">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="80f85-270">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="80f85-270">Uninstall-Package</span></span>](Uninstall-Package.md)
