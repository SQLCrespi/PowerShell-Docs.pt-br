---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: e1e4814d0128cc1f170bee26425c540c007dbdd4
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890484"
---
# <span data-ttu-id="91f52-103">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="91f52-103">Get-PackageSource</span></span>

## <span data-ttu-id="91f52-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="91f52-104">SYNOPSIS</span></span>
<span data-ttu-id="91f52-105">Obtém uma lista de origens de pacote registradas para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="91f52-105">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="91f52-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91f52-106">SYNTAX</span></span>

### <span data-ttu-id="91f52-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="91f52-107">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="91f52-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="91f52-108">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="91f52-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91f52-109">DESCRIPTION</span></span>

<span data-ttu-id="91f52-110">O `Get-PackageSource` cmdlet obtém uma lista de origens de pacote registradas com **PackageManagement** no computador local.</span><span class="sxs-lookup"><span data-stu-id="91f52-110">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="91f52-111">Se você especificar um provedor de pacote, o `Get-PackageSource` obterá somente as fontes associadas ao provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="91f52-111">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="91f52-112">Caso contrário, o comando retorna todas as origens de pacote registradas com **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="91f52-112">Otherwise, the command returns all package sources that are registered with **PackageManagement**.</span></span>

## <span data-ttu-id="91f52-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="91f52-113">EXAMPLES</span></span>

### <span data-ttu-id="91f52-114">Exemplo 1: obter todas as origens do pacote</span><span class="sxs-lookup"><span data-stu-id="91f52-114">Example 1: Get all package sources</span></span>

<span data-ttu-id="91f52-115">O `Get-PackageSource` cmdlet obtém todas as origens de pacote registradas com **PackageManagement** no computador local.</span><span class="sxs-lookup"><span data-stu-id="91f52-115">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

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

### <span data-ttu-id="91f52-116">Exemplo 2: obter todas as origens de pacote para um provedor específico</span><span class="sxs-lookup"><span data-stu-id="91f52-116">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="91f52-117">Esse comando obtém as origens do pacote registradas para um provedor específico.</span><span class="sxs-lookup"><span data-stu-id="91f52-117">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="91f52-118">`Get-PackageSource` usa o parâmetro **ProviderName** para obter as origens do pacote que são registradas para o provedor do **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="91f52-118">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="91f52-119">Exemplo 3: obter fontes de um provedor de pacotes</span><span class="sxs-lookup"><span data-stu-id="91f52-119">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="91f52-120">Esse comando usa um provedor de pacote para obter as origens do pacote.</span><span class="sxs-lookup"><span data-stu-id="91f52-120">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="91f52-121">`Get-PackageProvider` usa o parâmetro **Name** para especificar o nome do provedor, **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="91f52-121">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet**.</span></span> <span data-ttu-id="91f52-122">O objeto é enviado ao pipeline para `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="91f52-122">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="91f52-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91f52-123">PARAMETERS</span></span>

### <span data-ttu-id="91f52-124">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="91f52-124">-ConfigFile</span></span>

<span data-ttu-id="91f52-125">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="91f52-125">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="91f52-126">-Force</span><span class="sxs-lookup"><span data-stu-id="91f52-126">-Force</span></span>

<span data-ttu-id="91f52-127">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="91f52-127">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="91f52-128">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="91f52-128">-ForceBootstrap</span></span>

<span data-ttu-id="91f52-129">Indica que esse cmdlet força o **PackageManagement** a instalar automaticamente um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="91f52-129">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="91f52-130">-Local</span><span class="sxs-lookup"><span data-stu-id="91f52-130">-Location</span></span>

<span data-ttu-id="91f52-131">Especifica o local de um repositório ou origem de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="91f52-131">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="91f52-132">-Name</span><span class="sxs-lookup"><span data-stu-id="91f52-132">-Name</span></span>

<span data-ttu-id="91f52-133">Especifica o nome de uma origem de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="91f52-133">Specifies the name of a package management source.</span></span>

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

### <span data-ttu-id="91f52-134">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="91f52-134">-PackageManagementProvider</span></span>

<span data-ttu-id="91f52-135">Especifica um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="91f52-135">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="91f52-136">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="91f52-136">-ProviderName</span></span>

<span data-ttu-id="91f52-137">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="91f52-137">Specifies one or more package provider names.</span></span> <span data-ttu-id="91f52-138">Separe vários nomes de provedor de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="91f52-138">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="91f52-139">Use `Get-PackageProvider` para obter uma lista de provedores de pacotes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="91f52-139">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="91f52-140">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="91f52-140">-PublishLocation</span></span>

<span data-ttu-id="91f52-141">Especifica o local de publicação para a origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="91f52-141">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="91f52-142">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="91f52-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="91f52-143">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="91f52-143">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="91f52-144">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="91f52-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="91f52-145">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="91f52-145">Specifies the script source location.</span></span>

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

### <span data-ttu-id="91f52-146">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="91f52-146">-SkipValidate</span></span>

<span data-ttu-id="91f52-147">Opção que ignora a validação das credenciais de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="91f52-147">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="91f52-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="91f52-148">CommonParameters</span></span>

<span data-ttu-id="91f52-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="91f52-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91f52-150">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="91f52-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91f52-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="91f52-151">INPUTS</span></span>

## <span data-ttu-id="91f52-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="91f52-152">OUTPUTS</span></span>

### <span data-ttu-id="91f52-153">Packager []</span><span class="sxs-lookup"><span data-stu-id="91f52-153">PackageSource[]</span></span>

<span data-ttu-id="91f52-154">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="91f52-154">Specifies one or more package sources.</span></span>

## <span data-ttu-id="91f52-155">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="91f52-155">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91f52-156">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="91f52-156">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="91f52-157">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91f52-157">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="91f52-158">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="91f52-158">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="91f52-159">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91f52-159">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="91f52-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="91f52-160">RELATED LINKS</span></span>

[<span data-ttu-id="91f52-161">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="91f52-161">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="91f52-162">Find-Package</span><span class="sxs-lookup"><span data-stu-id="91f52-162">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="91f52-163">Get-Package</span><span class="sxs-lookup"><span data-stu-id="91f52-163">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="91f52-164">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="91f52-164">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="91f52-165">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="91f52-165">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="91f52-166">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="91f52-166">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="91f52-167">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="91f52-167">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
