---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: a84dee14872ad5a7d0f7bac8e0057dc527855074
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603748"
---
# <span data-ttu-id="c99a8-102">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="c99a8-102">Find-RoleCapability</span></span>

## <span data-ttu-id="c99a8-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c99a8-103">SYNOPSIS</span></span>
<span data-ttu-id="c99a8-104">Localiza capacidades de função em módulos.</span><span class="sxs-lookup"><span data-stu-id="c99a8-104">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="c99a8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c99a8-105">SYNTAX</span></span>

### <span data-ttu-id="c99a8-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="c99a8-106">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="c99a8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c99a8-107">DESCRIPTION</span></span>

<span data-ttu-id="c99a8-108">O `Find-RoleCapability` cmdlet procura repositórios registrados para encontrar recursos e módulos de função do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c99a8-108">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="c99a8-109">Para cada recurso de função encontrado pelo `Find-RoleCapability` , um objeto **PSGetRoleCapabilityInfo** é retornado.</span><span class="sxs-lookup"><span data-stu-id="c99a8-109">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="c99a8-110">Os objetos **PSGetRoleCapabilityInfo** podem ser enviados para o pipeline para `Install-Module` os `Save-Module` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="c99a8-110">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="c99a8-111">Os recursos de função do PowerShell definem quais comandos e aplicativos estão disponíveis para um usuário em um ponto de extremidade de administração JEA (apenas suficiente).</span><span class="sxs-lookup"><span data-stu-id="c99a8-111">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="c99a8-112">Os recursos de função são definidos por arquivos com uma `.psrc` extensão.</span><span class="sxs-lookup"><span data-stu-id="c99a8-112">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="c99a8-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c99a8-113">EXAMPLES</span></span>

### <span data-ttu-id="c99a8-114">Exemplo 1: localizar recursos de função</span><span class="sxs-lookup"><span data-stu-id="c99a8-114">Example 1: Find role capabilities</span></span>

<span data-ttu-id="c99a8-115">`Find-RoleCapability` localiza recursos de função em cada repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="c99a8-115">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="c99a8-116">Para pesquisar um repositório específico, use o parâmetro **Repository** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-116">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-RoleCapability
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
General-Lev2     1.0        JeaExamples    PSGallery
IIS-Lev1         1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="c99a8-117">Exemplo 2: localizar recursos de função por nome</span><span class="sxs-lookup"><span data-stu-id="c99a8-117">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="c99a8-118">`Find-RoleCapability` localiza recursos de função por nome.</span><span class="sxs-lookup"><span data-stu-id="c99a8-118">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="c99a8-119">Use vírgulas para separar uma matriz de nomes.</span><span class="sxs-lookup"><span data-stu-id="c99a8-119">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="c99a8-120">Exemplo 3: localizar e salvar um módulo de capacidade de função</span><span class="sxs-lookup"><span data-stu-id="c99a8-120">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="c99a8-121">O `Find-RoleCapability` cmdlet encontra um recurso de função e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="c99a8-121">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="c99a8-122">`Save-Module` salva o módulo da capacidade da função em um sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c99a8-122">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="c99a8-123">`Get-ChildItem` exibe o conteúdo do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="c99a8-123">`Get-ChildItem` displays the contents of the module's directory.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Save-Module -Path C:\Test\Modules

PS> Get-ChildItem -Path C:\Test\Modules\JeaExamples\1.0\

    Directory: C:\Test\Modules\JeaExamples\1.0

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----          6/4/2019    16:37                RoleCapabilities
-a----          2/5/2019    18:46           1702 CreateRegisterPSSC.ps1
-a----          2/5/2019    18:46           7656 JeaExamples.psd1
-a----         10/1/2018    08:16            595 JeaExamples.psm1
```

<span data-ttu-id="c99a8-124">`Find-RoleCapability` usa o parâmetro **Name** para especificar a capacidade de função **geral-Lev1** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-124">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="c99a8-125">O objeto é enviado pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="c99a8-125">The object is sent down the pipeline.</span></span> <span data-ttu-id="c99a8-126">`Save-Module` usa o parâmetro **path** para o local do sistema de arquivos para salvar o módulo.</span><span class="sxs-lookup"><span data-stu-id="c99a8-126">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="c99a8-127">Depois que o módulo é salvo, `Get-ChildItem` especifica o **caminho** do módulo e exibe o conteúdo do diretório do módulo **JeaExamples** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-127">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="c99a8-128">Exemplo 4: localizar e instalar um módulo de capacidade de função</span><span class="sxs-lookup"><span data-stu-id="c99a8-128">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="c99a8-129">`Find-RoleCapability` localiza o módulo e envia o objeto para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="c99a8-129">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="c99a8-130">`Install-Module` instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="c99a8-130">`Install-Module` installs the module.</span></span> <span data-ttu-id="c99a8-131">Após a instalação, use `Get-InstalledModule` para ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="c99a8-131">After the installation, use `Get-InstalledModule` to see the results.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Install-Module -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'JeaExamples'.
VERBOSE: InstallPackageLocal' - name='JeaExamples', version='1.0',
VERBOSE: Validating the 'JeaExamples' module contents
VERBOSE: Test-ModuleManifest successfully validated the module manifest file
VERBOSE: Module 'JeaExamples' was installed successfully to path

PS> Get-InstalledModule

Version    Name            Repository     Description
-------    ----            ----------     -----------
1.0        JeaExamples     PSGallery      Some example Jea roles for general server maintenance...
```

<span data-ttu-id="c99a8-132">`Find-RoleCapability` usa o parâmetro **Name** para especificar a capacidade de função **geral-Lev1** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-132">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="c99a8-133">O objeto é enviado pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="c99a8-133">The object is sent down the pipeline.</span></span> <span data-ttu-id="c99a8-134">`Install-Module` usa o parâmetro **Verbose** para exibir mensagens de status durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="c99a8-134">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="c99a8-135">Após a conclusão da instalação, a `Get-InstalledModule` saída confirma que o módulo **JeaExamples** foi instalado.</span><span class="sxs-lookup"><span data-stu-id="c99a8-135">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="c99a8-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c99a8-136">PARAMETERS</span></span>

### <span data-ttu-id="c99a8-137">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="c99a8-137">-AllowPrerelease</span></span>

<span data-ttu-id="c99a8-138">Inclui recursos marcados como um pré-lançamento nos resultados.</span><span class="sxs-lookup"><span data-stu-id="c99a8-138">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="c99a8-139">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="c99a8-139">-AllVersions</span></span>

<span data-ttu-id="c99a8-140">Indica que este cmdlet obtém todas as versões de um módulo.</span><span class="sxs-lookup"><span data-stu-id="c99a8-140">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="c99a8-141">O **parâmetro** AllModules exibe cada uma das versões disponíveis de um módulo.</span><span class="sxs-lookup"><span data-stu-id="c99a8-141">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="c99a8-142">-Filter</span><span class="sxs-lookup"><span data-stu-id="c99a8-142">-Filter</span></span>

<span data-ttu-id="c99a8-143">Localiza recursos com base na sintaxe de pesquisa do provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-143">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="c99a8-144">Por exemplo, especifique as palavras a serem pesquisadas nas propriedades **ModuleName** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-144">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="c99a8-145">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c99a8-145">-MaximumVersion</span></span>

<span data-ttu-id="c99a8-146">Especifica a versão máxima do módulo a ser incluída nos resultados.</span><span class="sxs-lookup"><span data-stu-id="c99a8-146">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="c99a8-147">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="c99a8-147">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c99a8-148">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c99a8-148">-MinimumVersion</span></span>

<span data-ttu-id="c99a8-149">Especifica a versão mínima do módulo a ser incluída nos resultados.</span><span class="sxs-lookup"><span data-stu-id="c99a8-149">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="c99a8-150">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="c99a8-150">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c99a8-151">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="c99a8-151">-ModuleName</span></span>

<span data-ttu-id="c99a8-152">Especifica o nome do módulo no qual Pesquisar recursos de função.</span><span class="sxs-lookup"><span data-stu-id="c99a8-152">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="c99a8-153">O padrão é todos os módulos.</span><span class="sxs-lookup"><span data-stu-id="c99a8-153">The default is all modules.</span></span>

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

### <span data-ttu-id="c99a8-154">-Name</span><span class="sxs-lookup"><span data-stu-id="c99a8-154">-Name</span></span>

<span data-ttu-id="c99a8-155">Especifica o nome de uma capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="c99a8-155">Specifies the name of a role capability.</span></span> <span data-ttu-id="c99a8-156">O padrão é todos os recursos de função.</span><span class="sxs-lookup"><span data-stu-id="c99a8-156">The default is all role capabilities.</span></span> <span data-ttu-id="c99a8-157">Use vírgulas para separar uma matriz de nomes de recursos.</span><span class="sxs-lookup"><span data-stu-id="c99a8-157">Use commas to separate an array of resource names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c99a8-158">-Proxy</span><span class="sxs-lookup"><span data-stu-id="c99a8-158">-Proxy</span></span>

<span data-ttu-id="c99a8-159">Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="c99a8-159">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c99a8-160">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="c99a8-160">-ProxyCredential</span></span>

<span data-ttu-id="c99a8-161">Especifica uma conta de usuário com permissão para usar o servidor proxy especificado no parâmetro **proxy** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-161">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c99a8-162">-Repositório</span><span class="sxs-lookup"><span data-stu-id="c99a8-162">-Repository</span></span>

<span data-ttu-id="c99a8-163">Especifica um repositório para procurar recursos de função.</span><span class="sxs-lookup"><span data-stu-id="c99a8-163">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="c99a8-164">Use vírgulas para separar uma matriz de nomes de repositório.</span><span class="sxs-lookup"><span data-stu-id="c99a8-164">Use commas to separate an array of repository names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c99a8-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c99a8-165">-RequiredVersion</span></span>

<span data-ttu-id="c99a8-166">Especifica o número de versão exato do módulo a ser incluído nos resultados.</span><span class="sxs-lookup"><span data-stu-id="c99a8-166">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="c99a8-167">Os parâmetros **RequiredVersion** e **MinimumVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="c99a8-167">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c99a8-168">-Tag</span><span class="sxs-lookup"><span data-stu-id="c99a8-168">-Tag</span></span>

<span data-ttu-id="c99a8-169">Especifica as marcas que categorizam os módulos em um repositório.</span><span class="sxs-lookup"><span data-stu-id="c99a8-169">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="c99a8-170">Use vírgulas para separar uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="c99a8-170">Use commas to separate an array of tags.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c99a8-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c99a8-171">CommonParameters</span></span>

<span data-ttu-id="c99a8-172">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c99a8-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c99a8-173">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c99a8-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c99a8-174">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c99a8-174">INPUTS</span></span>

### <span data-ttu-id="c99a8-175">System.Uri</span><span class="sxs-lookup"><span data-stu-id="c99a8-175">System.Uri</span></span>

### <span data-ttu-id="c99a8-176">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="c99a8-176">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="c99a8-177">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c99a8-177">OUTPUTS</span></span>

### <span data-ttu-id="c99a8-178">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="c99a8-178">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="c99a8-179">O `Find-RoleCapability` cmdlet retorna um objeto **PSGetRoleCapabilityInfo** .</span><span class="sxs-lookup"><span data-stu-id="c99a8-179">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="c99a8-180">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c99a8-180">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c99a8-181">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="c99a8-181">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c99a8-182">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c99a8-182">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c99a8-183">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="c99a8-183">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c99a8-184">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c99a8-184">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c99a8-185">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c99a8-185">RELATED LINKS</span></span>

[<span data-ttu-id="c99a8-186">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="c99a8-186">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="c99a8-187">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="c99a8-187">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="c99a8-188">Install-Module</span><span class="sxs-lookup"><span data-stu-id="c99a8-188">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="c99a8-189">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="c99a8-189">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="c99a8-190">Save-Module</span><span class="sxs-lookup"><span data-stu-id="c99a8-190">Save-Module</span></span>](Save-Module.md)
