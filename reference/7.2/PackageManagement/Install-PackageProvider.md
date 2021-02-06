---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: 683329aac35744697d80e22efff5ec53bae74830
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603567"
---
# <span data-ttu-id="d5491-102">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d5491-102">Install-PackageProvider</span></span>

## <span data-ttu-id="d5491-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d5491-103">SYNOPSIS</span></span>
<span data-ttu-id="d5491-104">Instala um ou mais provedores de pacote de Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="d5491-104">Installs one or more Package Management package providers.</span></span>

## <span data-ttu-id="d5491-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5491-105">SYNTAX</span></span>

### <span data-ttu-id="d5491-106">PackageBySearch (padrão)</span><span class="sxs-lookup"><span data-stu-id="d5491-106">PackageBySearch (Default)</span></span>

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="d5491-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="d5491-107">PackageByInputObject</span></span>

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="d5491-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5491-108">DESCRIPTION</span></span>

<span data-ttu-id="d5491-109">O `Install-PackageProvider` cmdlet instala provedores de gerenciamento de pacotes correspondentes que estão disponíveis em fontes de pacote registradas com **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="d5491-109">The `Install-PackageProvider` cmdlet installs matching Package Management providers that are available in package sources registered with **PowerShellGet**.</span></span> <span data-ttu-id="d5491-110">Por padrão, isso inclui módulos disponíveis no Windows Galeria do PowerShell com a marca **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="d5491-110">By default, this includes modules available in the Windows PowerShell Gallery with the **PackageManagement** tag.</span></span> <span data-ttu-id="d5491-111">O provedor de Gerenciamento de Pacotes **PowerShellGet** é usado para localizar provedores nesses repositórios.</span><span class="sxs-lookup"><span data-stu-id="d5491-111">The **PowerShellGet** Package Management provider is used for finding providers in these repositories.</span></span>

<span data-ttu-id="d5491-112">Esse cmdlet também instala os provedores de Gerenciamento de Pacotes correspondentes que estão disponíveis usando o aplicativo de inicialização Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="d5491-112">This cmdlet also installs matching Package Management providers that are available using the Package Management bootstrapping application.</span></span>

<span data-ttu-id="d5491-113">Esse cmdlet também instala os provedores de Gerenciamento de Pacotes correspondentes que estão disponíveis no repositório de blob do Azure Gerenciamento de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="d5491-113">This cmdlet also installs matching Package Management providers that are available in the Package Management Azure Blob store.</span></span> <span data-ttu-id="d5491-114">Use o provedor de bootstrapper para localizá-los e instalá-los.</span><span class="sxs-lookup"><span data-stu-id="d5491-114">Use the bootstrapper provider to find and install them.</span></span>

<span data-ttu-id="d5491-115">Para executar a primeira vez, o PackageManagement requer uma conexão com a Internet para baixar o provedor de pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5491-115">In order to execute the first time, PackageManagement requires an internet connection to download the NuGet package provider.</span></span> <span data-ttu-id="d5491-116">No entanto, se o computador não tiver uma conexão com a Internet e você precisar usar o provedor NuGet ou PowerShellGet, você poderá baixá-los em outro computador e copiá-los para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="d5491-116">However, if your computer does not have an internet connection and you need to use the NuGet or PowerShellGet provider, you can download them on another computer and copy them to your target computer.</span></span> <span data-ttu-id="d5491-117">Use as seguintes etapas para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="d5491-117">Use the following steps to do this:</span></span>

1. <span data-ttu-id="d5491-118">Execute `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` para instalar o provedor de um computador com uma conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="d5491-118">Run `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` to install the provider from a computer with an internet connection.</span></span>
1. <span data-ttu-id="d5491-119">Após a instalação, você pode encontrar o provedor instalado no `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` ou no `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>` .</span><span class="sxs-lookup"><span data-stu-id="d5491-119">After the install, you can find the provider installed in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>`.</span></span>
1. <span data-ttu-id="d5491-120">Coloque a `<ProviderName>` pasta, que, nesse caso, é a pasta NuGet, no local correspondente no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="d5491-120">Place the `<ProviderName>` folder, which in this case is the NuGet folder, in the corresponding location on your target computer.</span></span> <span data-ttu-id="d5491-121">Se o computador de destino for um nano Server, você precisará executar `Install-PackageProvider` do nano Server para baixar os binários do NuGet corretos.</span><span class="sxs-lookup"><span data-stu-id="d5491-121">If your target computer is a Nano server, you need to run `Install-PackageProvider` from Nano Server to download the correct NuGet binaries.</span></span>
1. <span data-ttu-id="d5491-122">Reinicie o PowerShell para carregar automaticamente o provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="d5491-122">Restart PowerShell to auto-load the package provider.</span></span> <span data-ttu-id="d5491-123">Como alternativa, execute `Get-PackageProvider -ListAvailable` para listar todos os provedores de pacote disponíveis no computador.</span><span class="sxs-lookup"><span data-stu-id="d5491-123">Alternatively, run `Get-PackageProvider -ListAvailable` to list all the package providers available on the computer.</span></span>
   <span data-ttu-id="d5491-124">Em seguida, use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` para importar o provedor para a sessão atual do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5491-124">Then use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` to import the provider to the current Windows PowerShell session.</span></span>

## <span data-ttu-id="d5491-125">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d5491-125">EXAMPLES</span></span>

### <span data-ttu-id="d5491-126">Exemplo 1: instalar um provedor de pacote do Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5491-126">Example 1: Install a package provider from the PowerShell Gallery</span></span>

<span data-ttu-id="d5491-127">Esse comando instala o provedor de pacote do do Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5491-127">This command installs the GistProvider package provider from the PowerShell Gallery.</span></span>

```powershell
Install-PackageProvider -Name "GistProvider" -Verbose
```

### <span data-ttu-id="d5491-128">Exemplo 2: instalar uma versão especificada de um provedor de pacote</span><span class="sxs-lookup"><span data-stu-id="d5491-128">Example 2: Install a specified version of a package provider</span></span>

<span data-ttu-id="d5491-129">Este exemplo instala uma versão especificada do provedor de pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5491-129">This example installs a specified version of the NuGet package provider.</span></span>

<span data-ttu-id="d5491-130">O primeiro comando localiza todas as versões do provedor de pacote chamado NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5491-130">The first command finds all versions of the package provider named NuGet.</span></span>
<span data-ttu-id="d5491-131">O segundo comando instala uma versão especificada do provedor de pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5491-131">The second command installs a specified version of the NuGet package provider.</span></span>

```powershell
Find-PackageProvider -Name "NuGet" -AllVersions
Install-PackageProvider -Name "NuGet" -RequiredVersion "2.8.5.216" -Force
```

### <span data-ttu-id="d5491-132">Exemplo 3: localizar um provedor e instalá-lo</span><span class="sxs-lookup"><span data-stu-id="d5491-132">Example 3: Find a provider and install it</span></span>

<span data-ttu-id="d5491-133">Este exemplo usa `Find-PackageProvider` e o pipeline para pesquisar o provedor de registro e instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="d5491-133">This example uses `Find-PackageProvider` and the pipeline to search for the Gist provider and install it.</span></span>

```powershell
Find-PackageProvider -Name "GistProvider" | Install-PackageProvider -Verbose
```

### <span data-ttu-id="d5491-134">Exemplo 4: instalar um provedor na pasta de módulo do usuário atual</span><span class="sxs-lookup"><span data-stu-id="d5491-134">Example 4: Install a provider to the current user's module folder</span></span>

<span data-ttu-id="d5491-135">Esse comando instala um provedor de pacote para `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` que somente o usuário atual possa usá-lo.</span><span class="sxs-lookup"><span data-stu-id="d5491-135">This command installs a package provider to `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` so that only the current user can use it.</span></span>

```powershell
Install-PackageProvider -Name GistProvider -Verbose -Scope CurrentUser
```

## <span data-ttu-id="d5491-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5491-136">PARAMETERS</span></span>

### <span data-ttu-id="d5491-137">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="d5491-137">-AllVersions</span></span>

<span data-ttu-id="d5491-138">Indica que esse cmdlet instala todas as versões disponíveis do provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="d5491-138">Indicates that this cmdlet installs all available versions of the package provider.</span></span> <span data-ttu-id="d5491-139">Por padrão, `Install-PackageProvider` o retorna apenas a versão mais alta disponível.</span><span class="sxs-lookup"><span data-stu-id="d5491-139">By default, `Install-PackageProvider` only returns the highest available version.</span></span>

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

### <span data-ttu-id="d5491-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="d5491-140">-Credential</span></span>

<span data-ttu-id="d5491-141">Especifica uma conta de usuário que tem permissão para instalar provedores de pacote.</span><span class="sxs-lookup"><span data-stu-id="d5491-141">Specifies a user account that has permission to install package providers.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5491-142">-Force</span><span class="sxs-lookup"><span data-stu-id="d5491-142">-Force</span></span>

<span data-ttu-id="d5491-143">Indica que esse cmdlet força todas as ações com este cmdlet que podem ser forçadas.</span><span class="sxs-lookup"><span data-stu-id="d5491-143">Indicates that this cmdlet forces all actions with this cmdlet that can be forced.</span></span> <span data-ttu-id="d5491-144">Atualmente, isso significa que o parâmetro **Force** age da mesma forma que o parâmetro **ForceBootstrap** .</span><span class="sxs-lookup"><span data-stu-id="d5491-144">Currently, this means the **Force** parameter acts the same as the **ForceBootstrap** parameter.</span></span>

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

### <span data-ttu-id="d5491-145">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="d5491-145">-ForceBootstrap</span></span>

<span data-ttu-id="d5491-146">Indica que esse cmdlet instala automaticamente o provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="d5491-146">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="d5491-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d5491-147">-InputObject</span></span>

<span data-ttu-id="d5491-148">Especifica um objeto **SoftwareIdentity** .</span><span class="sxs-lookup"><span data-stu-id="d5491-148">Specifies a **SoftwareIdentity** object.</span></span> <span data-ttu-id="d5491-149">Use o `Find-PackageProvider` cmdlet para obter um objeto **SoftwareIdentity** para o pipe `Install-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="d5491-149">Use the `Find-PackageProvider` cmdlet to obtain a **SoftwareIdentity** object to pipe into `Install-PackageProvider`.</span></span>

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

### <span data-ttu-id="d5491-150">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d5491-150">-MaximumVersion</span></span>

<span data-ttu-id="d5491-151">Especifica a versão máxima permitida do provedor de pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="d5491-151">Specifies the maximum allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="d5491-152">Se você não adicionar esse parâmetro, `Install-PackageProvider` o instalará a versão mais recente disponível do provedor.</span><span class="sxs-lookup"><span data-stu-id="d5491-152">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the provider.</span></span>

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

### <span data-ttu-id="d5491-153">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d5491-153">-MinimumVersion</span></span>

<span data-ttu-id="d5491-154">Especifica a versão mínima permitida do provedor de pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="d5491-154">Specifies the minimum allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="d5491-155">Se você não adicionar esse parâmetro, `Install-PackageProvider` o instalará a versão mais recente disponível do pacote que também atende a qualquer requisito especificado pelo parâmetro *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="d5491-155">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the package that also satisfies any requirement specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="d5491-156">-Name</span><span class="sxs-lookup"><span data-stu-id="d5491-156">-Name</span></span>

<span data-ttu-id="d5491-157">Especifica um ou mais nomes de módulo de provedor de pacote.</span><span class="sxs-lookup"><span data-stu-id="d5491-157">Specifies one or more package provider module names.</span></span> <span data-ttu-id="d5491-158">Separe vários nomes de pacote com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="d5491-158">Separate multiple package names with commas.</span></span>
<span data-ttu-id="d5491-159">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d5491-159">Wildcard characters are not supported.</span></span>

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

### <span data-ttu-id="d5491-160">-Proxy</span><span class="sxs-lookup"><span data-stu-id="d5491-160">-Proxy</span></span>

<span data-ttu-id="d5491-161">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="d5491-161">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="d5491-162">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="d5491-162">-ProxyCredential</span></span>

<span data-ttu-id="d5491-163">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="d5491-163">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="d5491-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="d5491-164">-RequiredVersion</span></span>

<span data-ttu-id="d5491-165">Especifica a versão exata permitida do provedor de pacote que você deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="d5491-165">Specifies the exact allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="d5491-166">Se você não adicionar esse parâmetro, `Install-PackageProvider` o instalará a versão mais recente disponível do provedor que também atende a qualquer versão máxima especificada pelo parâmetro **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="d5491-166">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the provider that also satisfies any maximum version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="d5491-167">-Escopo</span><span class="sxs-lookup"><span data-stu-id="d5491-167">-Scope</span></span>

<span data-ttu-id="d5491-168">Especifica o escopo de instalação do provedor.</span><span class="sxs-lookup"><span data-stu-id="d5491-168">Specifies the installation scope of the provider.</span></span> <span data-ttu-id="d5491-169">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d5491-169">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d5491-170">**AllUsers** – instala provedores em um local que pode ser acessado por todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="d5491-170">**AllUsers** - installs providers in a location that is accessible to all users of the computer.</span></span>
  <span data-ttu-id="d5491-171">Por padrão, isso é **$env:P rogramfiles\packagemanagement\providerassemblies.**</span><span class="sxs-lookup"><span data-stu-id="d5491-171">By default, this is **$env:ProgramFiles\PackageManagement\ProviderAssemblies.**</span></span>

- <span data-ttu-id="d5491-172">**CurrentUser** – instala provedores em um local onde eles só podem ser acessados pelo usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d5491-172">**CurrentUser** - installs providers in a location where they are only accessible to the current user.</span></span> <span data-ttu-id="d5491-173">Por padrão, isso é **$env: LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span><span class="sxs-lookup"><span data-stu-id="d5491-173">By default, this is **$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5491-174">-Source</span><span class="sxs-lookup"><span data-stu-id="d5491-174">-Source</span></span>

<span data-ttu-id="d5491-175">Especifica uma ou mais origens de pacote.</span><span class="sxs-lookup"><span data-stu-id="d5491-175">Specifies one or more package sources.</span></span> <span data-ttu-id="d5491-176">Use o `Get-PackageSource` cmdlet para obter uma lista de fontes de pacote disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d5491-176">Use the `Get-PackageSource` cmdlet to get a list of available package sources.</span></span>

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

### <span data-ttu-id="d5491-177">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d5491-177">-Confirm</span></span>

<span data-ttu-id="d5491-178">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5491-178">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d5491-179">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d5491-179">-WhatIf</span></span>

<span data-ttu-id="d5491-180">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d5491-180">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d5491-181">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d5491-181">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d5491-182">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d5491-182">CommonParameters</span></span>

<span data-ttu-id="d5491-183">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5491-183">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5491-184">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d5491-184">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d5491-185">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d5491-185">INPUTS</span></span>

### <span data-ttu-id="d5491-186">Microsoft. PackageManagement. Packaging. SoftwareIdentity</span><span class="sxs-lookup"><span data-stu-id="d5491-186">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="d5491-187">É possível canalizar um objeto **SoftwareIdentity** para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5491-187">You can pipe a **SoftwareIdentity** object to this cmdlet.</span></span> <span data-ttu-id="d5491-188">Use `Find-PackageProvider` para obter um objeto **SoftwareIdentity** que pode ser canalizado no `Install-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="d5491-188">Use `Find-PackageProvider` to get a **SoftwareIdentity** object that can be piped into `Install-PackageProvider`.</span></span>

## <span data-ttu-id="d5491-189">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d5491-189">OUTPUTS</span></span>

## <span data-ttu-id="d5491-190">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d5491-190">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5491-191">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="d5491-191">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d5491-192">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5491-192">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d5491-193">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="d5491-193">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d5491-194">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5491-194">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d5491-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d5491-195">RELATED LINKS</span></span>

[<span data-ttu-id="d5491-196">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d5491-196">Find-PackageProvider</span></span>](Find-PackageProvider.md)

[<span data-ttu-id="d5491-197">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d5491-197">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="d5491-198">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="d5491-198">Import-PackageProvider</span></span>](Import-PackageProvider.md)
