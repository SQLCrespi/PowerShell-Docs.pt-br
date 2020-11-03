---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: 664e6064580f9212c25632a1146d1ac67f2308bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193546"
---
# <span data-ttu-id="b6e4a-103">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b6e4a-103">Find-PackageProvider</span></span>

## <span data-ttu-id="b6e4a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b6e4a-104">SYNOPSIS</span></span>
<span data-ttu-id="b6e4a-105">Retorna uma lista de provedores de pacote Gerenciamento de Pacotes disponíveis para instalação.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-105">Returns a list of Package Management package providers available for installation.</span></span>

## <span data-ttu-id="b6e4a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6e4a-106">SYNTAX</span></span>

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="b6e4a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6e4a-107">DESCRIPTION</span></span>

<span data-ttu-id="b6e4a-108">O cmdlet **Find-packageprovider** localiza provedores de PackageManagement correspondentes que estão disponíveis em fontes de pacote registradas com PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-108">The **Find-PackageProvider** cmdlet finds matching PackageManagement providers that are available in package sources registered with PowerShellGet.</span></span>
<span data-ttu-id="b6e4a-109">Esses são os provedores de pacote disponíveis para instalação com o cmdlet Install-PackageProvider.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-109">These are package providers available for installation with the Install-PackageProvider cmdlet.</span></span>
<span data-ttu-id="b6e4a-110">Por padrão, isso inclui módulos disponíveis no Galeria do PowerShell com as marcas **PackageManagement** e **Provider** .</span><span class="sxs-lookup"><span data-stu-id="b6e4a-110">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** and **Provider** tags.</span></span>

<span data-ttu-id="b6e4a-111">**Find-packageprovider** também localiza provedores de gerenciamento de pacotes correspondentes que estão disponíveis no repositório de Blob do gerenciamento de pacotes Azure.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-111">**Find-PackageProvider** also finds matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="b6e4a-112">Use o provedor de bootstrapper para localizá-los e instalá-los.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-112">Use the bootstrapper provider to find and install them.</span></span>

## <span data-ttu-id="b6e4a-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b6e4a-113">EXAMPLES</span></span>

### <span data-ttu-id="b6e4a-114">Exemplo 1: localizar todos os provedores de pacote disponíveis</span><span class="sxs-lookup"><span data-stu-id="b6e4a-114">Example 1: Find all available package providers</span></span>

```
PS C:\> Find-PackageProvider
```

<span data-ttu-id="b6e4a-115">Esse comando obtém uma lista de todos os provedores de pacote que estão disponíveis nos repositórios com suporte pelo Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-115">This command gets a list of all package providers that are available on the repositories supported by Package Management.</span></span>
<span data-ttu-id="b6e4a-116">Por padrão, esses provedores de pacotes estão disponíveis no Galeria do PowerShell e usando o aplicativo de inicialização Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-116">By default, those package providers are available on the PowerShell Gallery and by using the Package Management bootstrapping application.</span></span>

### <span data-ttu-id="b6e4a-117">Exemplo 2: localizar todas as versões de um provedor</span><span class="sxs-lookup"><span data-stu-id="b6e4a-117">Example 2: Find all versions of a provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

<span data-ttu-id="b6e4a-118">Esse comando localiza todas as versões do provedor de pacote chamado NuGet.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-118">This command finds all versions of the package provider named Nuget.</span></span>

### <span data-ttu-id="b6e4a-119">Exemplo 3: localizar um provedor de uma fonte especificada</span><span class="sxs-lookup"><span data-stu-id="b6e4a-119">Example 3: Find a provider from a specified source</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

<span data-ttu-id="b6e4a-120">Esse comando localiza um provedor de pacote disponível usando uma origem de pacote especificada.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-120">This command finds a package provider available by using a specified package source.</span></span>

## <span data-ttu-id="b6e4a-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6e4a-121">PARAMETERS</span></span>

### <span data-ttu-id="b6e4a-122">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="b6e4a-122">-AllVersions</span></span>

<span data-ttu-id="b6e4a-123">Indica que esse cmdlet retorna todas as versões disponíveis do provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-123">Indicates that this cmdlet returns all available versions of the package provider.</span></span>
<span data-ttu-id="b6e4a-124">Por padrão, **Find-packageprovider** retorna apenas a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-124">By default, **Find-PackageProvider** only returns the newest available version.</span></span>

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

### <span data-ttu-id="b6e4a-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="b6e4a-125">-Credential</span></span>

<span data-ttu-id="b6e4a-126">Especifica uma conta de usuário que tem permissão para pesquisar provedores de pacote.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-126">Specifies a user account that has permission to search for package providers.</span></span>

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

### <span data-ttu-id="b6e4a-127">-Force</span><span class="sxs-lookup"><span data-stu-id="b6e4a-127">-Force</span></span>

<span data-ttu-id="b6e4a-128">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-128">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="b6e4a-129">Atualmente, isso é equivalente ao parâmetro *ForceBootstrap* .</span><span class="sxs-lookup"><span data-stu-id="b6e4a-129">Currently, this is equivalent to the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="b6e4a-130">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="b6e4a-130">-ForceBootstrap</span></span>

<span data-ttu-id="b6e4a-131">Indica que esse cmdlet força Gerenciamento de Pacotes a instalar automaticamente o provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-131">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="b6e4a-132">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="b6e4a-132">-IncludeDependencies</span></span>

<span data-ttu-id="b6e4a-133">Indica que esse cmdlet inclui dependências.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-133">Indicates that this cmdlet includes dependencies.</span></span>

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

### <span data-ttu-id="b6e4a-134">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="b6e4a-134">-MaximumVersion</span></span>

<span data-ttu-id="b6e4a-135">Especifica a versão máxima permitida do provedor de pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-135">Specifies the maximum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="b6e4a-136">Se você não adicionar esse parâmetro, **Find-packageprovider** encontrará a versão mais alta disponível do provedor.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-136">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider.</span></span>

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

### <span data-ttu-id="b6e4a-137">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="b6e4a-137">-MinimumVersion</span></span>

<span data-ttu-id="b6e4a-138">Especifica a versão mínima permitida do provedor de pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-138">Specifies the minimum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="b6e4a-139">Se você não adicionar esse parâmetro, **Find-packageprovider** encontrará a versão mais alta disponível do pacote que também atende a qualquer versão especificada máxima especificada pelo parâmetro *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="b6e4a-139">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the package that also satisfies any maximum specified version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="b6e4a-140">-Name</span><span class="sxs-lookup"><span data-stu-id="b6e4a-140">-Name</span></span>

<span data-ttu-id="b6e4a-141">Especifica um ou mais nomes de módulo de provedor de pacote ou nomes de provedor com caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-141">Specifies one or more package provider module names, or provider names with wildcard characters.</span></span>
<span data-ttu-id="b6e4a-142">Separe vários nomes de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-142">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b6e4a-143">-Proxy</span><span class="sxs-lookup"><span data-stu-id="b6e4a-143">-Proxy</span></span>

<span data-ttu-id="b6e4a-144">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-144">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="b6e4a-145">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="b6e4a-145">-ProxyCredential</span></span>

<span data-ttu-id="b6e4a-146">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="b6e4a-146">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="b6e4a-147">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="b6e4a-147">-RequiredVersion</span></span>

<span data-ttu-id="b6e4a-148">Especifica a versão exata permitida do provedor de pacote que você deseja localizar.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-148">Specifies the exact allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="b6e4a-149">Se você não adicionar esse parâmetro, **Find-packageprovider** encontrará a versão mais alta disponível do provedor que também atende a qualquer versão máxima especificada pelo parâmetro *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="b6e4a-149">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="b6e4a-150">-Source</span><span class="sxs-lookup"><span data-stu-id="b6e4a-150">-Source</span></span>

<span data-ttu-id="b6e4a-151">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-151">Specifies one or more package sources.</span></span>
<span data-ttu-id="b6e4a-152">Você pode obter uma lista de fontes de pacote disponíveis usando o cmdlet Get-PackageSource.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-152">You can get a list of available package sources by using the Get-PackageSource cmdlet.</span></span>

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

### <span data-ttu-id="b6e4a-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b6e4a-153">CommonParameters</span></span>

<span data-ttu-id="b6e4a-154">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b6e4a-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6e4a-155">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b6e4a-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b6e4a-156">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b6e4a-156">INPUTS</span></span>

## <span data-ttu-id="b6e4a-157">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b6e4a-157">OUTPUTS</span></span>

### <span data-ttu-id="b6e4a-158">Microsoft. PackageManagement. Packaging. SoftwareIdentity</span><span class="sxs-lookup"><span data-stu-id="b6e4a-158">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="b6e4a-159">Esse cmdlet retorna um objeto **SoftwareIdentity** .</span><span class="sxs-lookup"><span data-stu-id="b6e4a-159">This cmdlet returns a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="b6e4a-160">Um objeto **SoftwareIdentity** pode ser canalizado para **install-packageprovider** para instalar os resultados de **Find-packageprovider** .</span><span class="sxs-lookup"><span data-stu-id="b6e4a-160">A **SoftwareIdentity** object can be piped into **Install-PackageProvider** to install the results of **Find-PackageProvider** .</span></span>

## <span data-ttu-id="b6e4a-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b6e4a-161">NOTES</span></span>

## <span data-ttu-id="b6e4a-162">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b6e4a-162">RELATED LINKS</span></span>

[<span data-ttu-id="b6e4a-163">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b6e4a-163">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="b6e4a-164">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b6e4a-164">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="b6e4a-165">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b6e4a-165">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="b6e4a-166">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b6e4a-166">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="b6e4a-167">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b6e4a-167">Install-PackageProvider</span></span>](Install-PackageProvider.md)

