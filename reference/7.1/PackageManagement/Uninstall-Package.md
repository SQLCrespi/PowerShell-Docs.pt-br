---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 4da97d9643483db0eae4fc7d34e0e6997d16bd04
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194258"
---
# <span data-ttu-id="39eee-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="39eee-103">Uninstall-Package</span></span>

## <span data-ttu-id="39eee-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="39eee-104">SYNOPSIS</span></span>
<span data-ttu-id="39eee-105">Desinstala um ou mais pacotes de software.</span><span class="sxs-lookup"><span data-stu-id="39eee-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="39eee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39eee-106">SYNTAX</span></span>

### <span data-ttu-id="39eee-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="39eee-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39eee-108">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="39eee-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="39eee-109">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="39eee-109">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="39eee-110">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="39eee-110">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="39eee-111">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="39eee-111">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="39eee-112">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="39eee-112">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="39eee-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39eee-113">DESCRIPTION</span></span>

<span data-ttu-id="39eee-114">O `Uninstall-Package` cmdlet desinstala um ou mais pacotes de software do computador local.</span><span class="sxs-lookup"><span data-stu-id="39eee-114">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="39eee-115">Para localizar os pacotes instalados, use o `Get-Package` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39eee-115">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="39eee-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="39eee-116">EXAMPLES</span></span>

### <span data-ttu-id="39eee-117">Exemplo 1: desinstalar um pacote</span><span class="sxs-lookup"><span data-stu-id="39eee-117">Example 1: Uninstall a package</span></span>

<span data-ttu-id="39eee-118">O `Uninstall-Package` cmdlet desinstala pacotes.</span><span class="sxs-lookup"><span data-stu-id="39eee-118">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="39eee-119">O parâmetro **Name** especifica o pacote a ser desinstalado.</span><span class="sxs-lookup"><span data-stu-id="39eee-119">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="39eee-120">Se várias versões de um pacote forem instaladas, a versão mais recente será desinstalada.</span><span class="sxs-lookup"><span data-stu-id="39eee-120">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="39eee-121">Exemplo 2: usar o pipeline para desinstalar um pacote</span><span class="sxs-lookup"><span data-stu-id="39eee-121">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="39eee-122">`Get-Package` localiza um pacote específico e envia o objeto **SoftwareIdentity** para baixo do pipeline para o `Uninsall-Package` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39eee-122">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="39eee-123">O `Get-Package` cmdlet usa os parâmetros **Name** e **RequiredVersion** para especificar um pacote.</span><span class="sxs-lookup"><span data-stu-id="39eee-123">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="39eee-124">Um objeto **SoftwareIdentity** é enviado pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="39eee-124">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="39eee-125">O `Uninstall-Package` cmdlet recebe o objeto como **InputObject** e remove o pacote.</span><span class="sxs-lookup"><span data-stu-id="39eee-125">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="39eee-126">Como alternativa, o `Uninstall-Package` cmdlet pode especificar um valor para o parâmetro **InputObject** :</span><span class="sxs-lookup"><span data-stu-id="39eee-126">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="39eee-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39eee-127">PARAMETERS</span></span>

### <span data-ttu-id="39eee-128">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="39eee-128">-AllowClobber</span></span>

<span data-ttu-id="39eee-129">Substitui mensagens de aviso sobre conflitos com comandos existentes.</span><span class="sxs-lookup"><span data-stu-id="39eee-129">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="39eee-130">Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados.</span><span class="sxs-lookup"><span data-stu-id="39eee-130">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-131">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="39eee-131">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="39eee-132">Permite que os pacotes marcados como pré-lançamento sejam desinstalados.</span><span class="sxs-lookup"><span data-stu-id="39eee-132">Allows packages marked as prerelease to be uninstalled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-133">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="39eee-133">-AllVersions</span></span>

<span data-ttu-id="39eee-134">Indica que esse cmdlet desinstala todas as versões do pacote.</span><span class="sxs-lookup"><span data-stu-id="39eee-134">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="39eee-135">-Destino</span><span class="sxs-lookup"><span data-stu-id="39eee-135">-Destination</span></span>

<span data-ttu-id="39eee-136">Especifica uma cadeia de caracteres do caminho para o objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="39eee-136">Specifies a string of the path to the input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-137">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="39eee-137">-ExcludeVersion</span></span>

<span data-ttu-id="39eee-138">Alterne para excluir o número de versão no caminho da pasta.</span><span class="sxs-lookup"><span data-stu-id="39eee-138">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-139">-Force</span><span class="sxs-lookup"><span data-stu-id="39eee-139">-Force</span></span>

<span data-ttu-id="39eee-140">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="39eee-140">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="39eee-141">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="39eee-141">-ForceBootstrap</span></span>

<span data-ttu-id="39eee-142">Força o **PackageManagement** a instalar automaticamente o provedor de pacote para o pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="39eee-142">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="39eee-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="39eee-143">-InputObject</span></span>

<span data-ttu-id="39eee-144">Aceita a entrada de pipeline que especifica o objeto **SoftwareIdentity** do pacote do `Get-Package` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39eee-144">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="39eee-145">**InputObject** aceita o objeto **SoftwareIdentity** como um `Get-Package` valor ou uma variável que contém o objeto.</span><span class="sxs-lookup"><span data-stu-id="39eee-145">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="39eee-146">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="39eee-146">-InstallUpdate</span></span>

<span data-ttu-id="39eee-147">Indica que o `Uninstall-Package` desinstala as atualizações.</span><span class="sxs-lookup"><span data-stu-id="39eee-147">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="39eee-148">-MaximumVersion</span></span>

<span data-ttu-id="39eee-149">Especifica a versão de pacote máxima permitida que você deseja desinstalar.</span><span class="sxs-lookup"><span data-stu-id="39eee-149">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="39eee-150">Se você não especificar esse parâmetro, `Uninstall-Package` o desinstalará a versão mais recente do pacote.</span><span class="sxs-lookup"><span data-stu-id="39eee-150">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="39eee-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="39eee-151">-MinimumVersion</span></span>

<span data-ttu-id="39eee-152">Especifica a versão mínima permitida do pacote que você deseja desinstalar.</span><span class="sxs-lookup"><span data-stu-id="39eee-152">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="39eee-153">Se você não adicionar esse parâmetro, `Uninstall-Package` o desinstala a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="39eee-153">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="39eee-154">-Name</span><span class="sxs-lookup"><span data-stu-id="39eee-154">-Name</span></span>

<span data-ttu-id="39eee-155">Especifica um ou mais nomes de pacote.</span><span class="sxs-lookup"><span data-stu-id="39eee-155">Specifies one or more package names.</span></span> <span data-ttu-id="39eee-156">Vários nomes de pacote devem ser separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="39eee-156">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="39eee-157">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="39eee-157">-NoPathUpdate</span></span>

<span data-ttu-id="39eee-158">**NoPathUpdate** se aplica somente ao `Install-Script` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39eee-158">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="39eee-159">**NoPathUpdate** é um parâmetro dinâmico adicionado pelo provedor e não é suportado pelo `Uninstall-Package` .</span><span class="sxs-lookup"><span data-stu-id="39eee-159">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-160">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="39eee-160">-PackageManagementProvider</span></span>

<span data-ttu-id="39eee-161">Especifica o provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="39eee-161">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-162">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="39eee-162">-ProviderName</span></span>

<span data-ttu-id="39eee-163">Especifica um ou mais nomes de provedor de pacote para pesquisar pacotes.</span><span class="sxs-lookup"><span data-stu-id="39eee-163">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="39eee-164">Você pode obter os nomes de provedor de pacotes executando o cmdlet `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="39eee-164">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="39eee-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="39eee-165">-RequiredVersion</span></span>

<span data-ttu-id="39eee-166">Especifica a versão exata permitida do pacote que você deseja desinstalar.</span><span class="sxs-lookup"><span data-stu-id="39eee-166">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="39eee-167">Se você não adicionar esse parâmetro, `Uninstall-Package` o desinstala a versão mais recente do pacote que atende a qualquer versão especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="39eee-167">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="39eee-168">-Escopo</span><span class="sxs-lookup"><span data-stu-id="39eee-168">-Scope</span></span>

<span data-ttu-id="39eee-169">Especifica o escopo para o qual o pacote será desinstalado.</span><span class="sxs-lookup"><span data-stu-id="39eee-169">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="39eee-170">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="39eee-170">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="39eee-171">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="39eee-171">CurrentUser</span></span>
- <span data-ttu-id="39eee-172">AllUsers</span><span class="sxs-lookup"><span data-stu-id="39eee-172">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch, PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-173">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="39eee-173">-SkipDependencies</span></span>

<span data-ttu-id="39eee-174">Ignora a desinstalação de dependências de software.</span><span class="sxs-lookup"><span data-stu-id="39eee-174">Skips the uninstallation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-175">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="39eee-175">-SkipPublisherCheck</span></span>

<span data-ttu-id="39eee-176">Permite obter uma versão de pacote mais nova do que a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="39eee-176">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="39eee-177">Por exemplo, um pacote instalado que é assinado digitalmente por um fornecedor confiável, mas uma nova versão não é assinada digitalmente.</span><span class="sxs-lookup"><span data-stu-id="39eee-177">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-178">-Type</span><span class="sxs-lookup"><span data-stu-id="39eee-178">-Type</span></span>

<span data-ttu-id="39eee-179">Especifica se é para procurar pacotes com um módulo, um script ou ambos.</span><span class="sxs-lookup"><span data-stu-id="39eee-179">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="39eee-180">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="39eee-180">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="39eee-181">Módulo</span><span class="sxs-lookup"><span data-stu-id="39eee-181">Module</span></span>
- <span data-ttu-id="39eee-182">Script</span><span class="sxs-lookup"><span data-stu-id="39eee-182">Script</span></span>
- <span data-ttu-id="39eee-183">Tudo</span><span class="sxs-lookup"><span data-stu-id="39eee-183">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39eee-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="39eee-184">-Confirm</span></span>

<span data-ttu-id="39eee-185">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39eee-185">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="39eee-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="39eee-186">-WhatIf</span></span>

<span data-ttu-id="39eee-187">Mostra o que aconteceria se o `Uninstall-Package` cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="39eee-187">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="39eee-188">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="39eee-188">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="39eee-189">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="39eee-189">CommonParameters</span></span>

<span data-ttu-id="39eee-190">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39eee-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39eee-191">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="39eee-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39eee-192">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="39eee-192">INPUTS</span></span>

### <span data-ttu-id="39eee-193">`Uninstall-Package` aceita objetos **SoftwareIdentity** do pipeline como entrada.</span><span class="sxs-lookup"><span data-stu-id="39eee-193">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="39eee-194">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="39eee-194">OUTPUTS</span></span>

### <span data-ttu-id="39eee-195">`Uninstall-Package` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="39eee-195">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="39eee-196">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="39eee-196">NOTES</span></span>

<span data-ttu-id="39eee-197">A inclusão de um provedor de pacote em um comando pode tornar os parâmetros dinâmicos disponíveis para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="39eee-197">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="39eee-198">Parâmetros dinâmicos são específicos para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="39eee-198">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="39eee-199">O `Get-Help` cmdlet lista os conjuntos de parâmetros de um cmdlet e inclui o conjunto de parâmetros do provedor.</span><span class="sxs-lookup"><span data-stu-id="39eee-199">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="39eee-200">Por exemplo, `Uninstall-Package` tem o conjunto de parâmetros **PowerShellGet** que inclui `-NoPathUpdate` , `AllowClobber` e `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="39eee-200">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="39eee-201">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="39eee-201">RELATED LINKS</span></span>

[<span data-ttu-id="39eee-202">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="39eee-202">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="39eee-203">Find-Package</span><span class="sxs-lookup"><span data-stu-id="39eee-203">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="39eee-204">Get-Package</span><span class="sxs-lookup"><span data-stu-id="39eee-204">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="39eee-205">Install-Package</span><span class="sxs-lookup"><span data-stu-id="39eee-205">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="39eee-206">Save-Package</span><span class="sxs-lookup"><span data-stu-id="39eee-206">Save-Package</span></span>](Save-Package.md)

