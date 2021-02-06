---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 8b91c5b950e0e16c4ce0821ee2f96b830dab1fc2
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99596578"
---
# <span data-ttu-id="dbf7a-102">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dbf7a-102">Get-PackageSource</span></span>

## <span data-ttu-id="dbf7a-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="dbf7a-103">SYNOPSIS</span></span>
<span data-ttu-id="dbf7a-104">Obtém uma lista de origens de pacote registradas para um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-104">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="dbf7a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dbf7a-105">SYNTAX</span></span>

### <span data-ttu-id="dbf7a-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="dbf7a-106">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="dbf7a-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="dbf7a-107">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="dbf7a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dbf7a-108">DESCRIPTION</span></span>

<span data-ttu-id="dbf7a-109">O `Get-PackageSource` cmdlet obtém uma lista de origens de pacote registradas com **PackageManagement** no computador local.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-109">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="dbf7a-110">Se você especificar um provedor de pacote, o `Get-PackageSource` obterá somente as fontes associadas ao provedor especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-110">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="dbf7a-111">Caso contrário, o comando retorna todas as origens de pacote registradas com **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-111">Otherwise, the command returns all package sources that are registered with **PackageManagement**.</span></span>

## <span data-ttu-id="dbf7a-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="dbf7a-112">EXAMPLES</span></span>

### <span data-ttu-id="dbf7a-113">Exemplo 1: obter todas as origens do pacote</span><span class="sxs-lookup"><span data-stu-id="dbf7a-113">Example 1: Get all package sources</span></span>

<span data-ttu-id="dbf7a-114">O `Get-PackageSource` cmdlet obtém todas as origens de pacote registradas com **PackageManagement** no computador local.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-114">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

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

### <span data-ttu-id="dbf7a-115">Exemplo 2: obter todas as origens de pacote para um provedor específico</span><span class="sxs-lookup"><span data-stu-id="dbf7a-115">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="dbf7a-116">Esse comando obtém as origens do pacote registradas para um provedor específico.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-116">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="dbf7a-117">`Get-PackageSource` usa o parâmetro **ProviderName** para obter as origens do pacote que são registradas para o provedor do **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="dbf7a-117">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="dbf7a-118">Exemplo 3: obter fontes de um provedor de pacotes</span><span class="sxs-lookup"><span data-stu-id="dbf7a-118">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="dbf7a-119">Esse comando usa um provedor de pacote para obter as origens do pacote.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-119">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="dbf7a-120">`Get-PackageProvider` usa o parâmetro **Name** para especificar o nome do provedor, **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-120">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet**.</span></span> <span data-ttu-id="dbf7a-121">O objeto é enviado ao pipeline para `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="dbf7a-121">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="dbf7a-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dbf7a-122">PARAMETERS</span></span>

### <span data-ttu-id="dbf7a-123">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="dbf7a-123">-ConfigFile</span></span>

<span data-ttu-id="dbf7a-124">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-124">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="dbf7a-125">-Force</span><span class="sxs-lookup"><span data-stu-id="dbf7a-125">-Force</span></span>

<span data-ttu-id="dbf7a-126">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="dbf7a-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="dbf7a-127">-ForceBootstrap</span></span>

<span data-ttu-id="dbf7a-128">Indica que esse cmdlet força o **PackageManagement** a instalar automaticamente um provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-128">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="dbf7a-129">-Local</span><span class="sxs-lookup"><span data-stu-id="dbf7a-129">-Location</span></span>

<span data-ttu-id="dbf7a-130">Especifica o local de um repositório ou origem de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-130">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="dbf7a-131">-Name</span><span class="sxs-lookup"><span data-stu-id="dbf7a-131">-Name</span></span>

<span data-ttu-id="dbf7a-132">Especifica o nome de uma origem de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-132">Specifies the name of a package management source.</span></span>

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

### <span data-ttu-id="dbf7a-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="dbf7a-133">-PackageManagementProvider</span></span>

<span data-ttu-id="dbf7a-134">Especifica um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-134">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="dbf7a-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="dbf7a-135">-ProviderName</span></span>

<span data-ttu-id="dbf7a-136">Especifica um ou mais nomes de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-136">Specifies one or more package provider names.</span></span> <span data-ttu-id="dbf7a-137">Separe vários nomes de provedor de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-137">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="dbf7a-138">Use `Get-PackageProvider` para obter uma lista de provedores de pacotes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-138">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="dbf7a-139">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="dbf7a-139">-PublishLocation</span></span>

<span data-ttu-id="dbf7a-140">Especifica o local de publicação para a origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-140">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="dbf7a-141">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="dbf7a-141">-ScriptPublishLocation</span></span>

<span data-ttu-id="dbf7a-142">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-142">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="dbf7a-143">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="dbf7a-143">-ScriptSourceLocation</span></span>

<span data-ttu-id="dbf7a-144">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-144">Specifies the script source location.</span></span>

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

### <span data-ttu-id="dbf7a-145">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="dbf7a-145">-SkipValidate</span></span>

<span data-ttu-id="dbf7a-146">Opção que ignora a validação das credenciais de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-146">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="dbf7a-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dbf7a-147">CommonParameters</span></span>

<span data-ttu-id="dbf7a-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dbf7a-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dbf7a-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dbf7a-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="dbf7a-150">INPUTS</span></span>

## <span data-ttu-id="dbf7a-151">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="dbf7a-151">OUTPUTS</span></span>

### <span data-ttu-id="dbf7a-152">Packager []</span><span class="sxs-lookup"><span data-stu-id="dbf7a-152">PackageSource[]</span></span>

<span data-ttu-id="dbf7a-153">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-153">Specifies one or more package sources.</span></span>

## <span data-ttu-id="dbf7a-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="dbf7a-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbf7a-155">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="dbf7a-156">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="dbf7a-157">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="dbf7a-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="dbf7a-158">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbf7a-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="dbf7a-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="dbf7a-159">RELATED LINKS</span></span>

[<span data-ttu-id="dbf7a-160">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="dbf7a-160">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="dbf7a-161">Find-Package</span><span class="sxs-lookup"><span data-stu-id="dbf7a-161">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="dbf7a-162">Get-Package</span><span class="sxs-lookup"><span data-stu-id="dbf7a-162">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="dbf7a-163">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="dbf7a-163">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="dbf7a-164">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dbf7a-164">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="dbf7a-165">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dbf7a-165">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="dbf7a-166">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dbf7a-166">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
