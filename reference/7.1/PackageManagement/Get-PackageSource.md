---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 81b6f94be6293733ec75d48b1f9dd7ac4f4f8d96
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193532"
---
# <span data-ttu-id="e6831-103">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e6831-103">Get-PackageSource</span></span>

## <span data-ttu-id="e6831-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e6831-104">SYNOPSIS</span></span>
<span data-ttu-id="e6831-105">Obtém uma lista de origens de pacote registradas para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="e6831-105">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="e6831-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6831-106">SYNTAX</span></span>

### <span data-ttu-id="e6831-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="e6831-107">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="e6831-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e6831-108">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="e6831-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6831-109">DESCRIPTION</span></span>

<span data-ttu-id="e6831-110">O `Get-PackageSource` cmdlet obtém uma lista de origens de pacote registradas com **PackageManagement** no computador local.</span><span class="sxs-lookup"><span data-stu-id="e6831-110">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="e6831-111">Se você especificar um provedor de pacote, o `Get-PackageSource` obterá somente as fontes associadas ao provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="e6831-111">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="e6831-112">Caso contrário, o comando retorna todas as origens de pacote registradas com **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="e6831-112">Otherwise, the command returns all package sources that are registered with **PackageManagement** .</span></span>

## <span data-ttu-id="e6831-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e6831-113">EXAMPLES</span></span>

### <span data-ttu-id="e6831-114">Exemplo 1: obter todas as origens do pacote</span><span class="sxs-lookup"><span data-stu-id="e6831-114">Example 1: Get all package sources</span></span>

<span data-ttu-id="e6831-115">O `Get-PackageSource` cmdlet obtém todas as origens de pacote registradas com **PackageManagement** no computador local.</span><span class="sxs-lookup"><span data-stu-id="e6831-115">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

```powershell
Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
PSGallery            PowerShellGet    False      https://www.powershellgallery.com/api/v2
```

### <span data-ttu-id="e6831-116">Exemplo 2: obter todas as origens de pacote para um provedor específico</span><span class="sxs-lookup"><span data-stu-id="e6831-116">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="e6831-117">Esse comando obtém as origens do pacote registradas para um provedor específico.</span><span class="sxs-lookup"><span data-stu-id="e6831-117">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="e6831-118">`Get-PackageSource` usa o parâmetro **ProviderName** para obter as origens do pacote que são registradas para o provedor do **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="e6831-118">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="e6831-119">Exemplo 3: obter fontes de um provedor de pacotes</span><span class="sxs-lookup"><span data-stu-id="e6831-119">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="e6831-120">Esse comando usa um provedor de pacote para obter as origens do pacote.</span><span class="sxs-lookup"><span data-stu-id="e6831-120">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="e6831-121">`Get-PackageProvider` usa o parâmetro **Name** para especificar o nome do provedor, **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="e6831-121">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet** .</span></span> <span data-ttu-id="e6831-122">O objeto é enviado ao pipeline para `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="e6831-122">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="e6831-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6831-123">PARAMETERS</span></span>

### <span data-ttu-id="e6831-124">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="e6831-124">-ConfigFile</span></span>

<span data-ttu-id="e6831-125">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="e6831-125">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="e6831-126">-Force</span><span class="sxs-lookup"><span data-stu-id="e6831-126">-Force</span></span>

<span data-ttu-id="e6831-127">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6831-127">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e6831-128">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e6831-128">-ForceBootstrap</span></span>

<span data-ttu-id="e6831-129">Indica que esse cmdlet força o **PackageManagement** a instalar automaticamente um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="e6831-129">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="e6831-130">-Local</span><span class="sxs-lookup"><span data-stu-id="e6831-130">-Location</span></span>

<span data-ttu-id="e6831-131">Especifica o local de um repositório ou origem de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="e6831-131">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="e6831-132">-Name</span><span class="sxs-lookup"><span data-stu-id="e6831-132">-Name</span></span>

<span data-ttu-id="e6831-133">Especifica o nome de uma origem de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="e6831-133">Specifies the name of a package management source.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e6831-134">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="e6831-134">-PackageManagementProvider</span></span>

<span data-ttu-id="e6831-135">Especifica um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="e6831-135">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="e6831-136">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="e6831-136">-ProviderName</span></span>

<span data-ttu-id="e6831-137">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="e6831-137">Specifies one or more package provider names.</span></span> <span data-ttu-id="e6831-138">Separe vários nomes de provedor de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="e6831-138">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="e6831-139">Use `Get-PackageProvider` para obter uma lista de provedores de pacotes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e6831-139">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="e6831-140">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="e6831-140">-PublishLocation</span></span>

<span data-ttu-id="e6831-141">Especifica o local de publicação para a origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="e6831-141">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="e6831-142">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="e6831-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="e6831-143">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="e6831-143">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="e6831-144">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="e6831-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="e6831-145">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="e6831-145">Specifies the script source location.</span></span>

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

### <span data-ttu-id="e6831-146">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="e6831-146">-SkipValidate</span></span>

<span data-ttu-id="e6831-147">Opção que ignora a validação das credenciais de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="e6831-147">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="e6831-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e6831-148">CommonParameters</span></span>

<span data-ttu-id="e6831-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6831-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6831-150">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6831-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6831-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e6831-151">INPUTS</span></span>

## <span data-ttu-id="e6831-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e6831-152">OUTPUTS</span></span>

### <span data-ttu-id="e6831-153">Packager []</span><span class="sxs-lookup"><span data-stu-id="e6831-153">PackageSource[]</span></span>

<span data-ttu-id="e6831-154">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="e6831-154">Specifies one or more package sources.</span></span>

## <span data-ttu-id="e6831-155">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e6831-155">NOTES</span></span>

## <span data-ttu-id="e6831-156">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e6831-156">RELATED LINKS</span></span>

[<span data-ttu-id="e6831-157">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e6831-157">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e6831-158">Find-Package</span><span class="sxs-lookup"><span data-stu-id="e6831-158">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="e6831-159">Get-Package</span><span class="sxs-lookup"><span data-stu-id="e6831-159">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="e6831-160">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e6831-160">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="e6831-161">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e6831-161">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="e6831-162">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e6831-162">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="e6831-163">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e6831-163">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

