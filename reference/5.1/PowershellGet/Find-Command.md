---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: eb305801bb6f8c84ffdf0ff34936ec3156ba5b0e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891247"
---
# <span data-ttu-id="9075c-103">Find-Command</span><span class="sxs-lookup"><span data-stu-id="9075c-103">Find-Command</span></span>

## <span data-ttu-id="9075c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9075c-104">SYNOPSIS</span></span>
<span data-ttu-id="9075c-105">Localiza comandos do PowerShell em módulos.</span><span class="sxs-lookup"><span data-stu-id="9075c-105">Finds PowerShell commands in modules.</span></span>

## <span data-ttu-id="9075c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9075c-106">SYNTAX</span></span>

### <span data-ttu-id="9075c-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="9075c-107">All</span></span>

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="9075c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9075c-108">DESCRIPTION</span></span>

<span data-ttu-id="9075c-109">O `Find-Command` cmdlet localiza comandos do PowerShell, como cmdlets, aliases, funções e fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9075c-109">The `Find-Command` cmdlet finds PowerShell commands such as cmdlets, aliases, functions, and workflows.</span></span> <span data-ttu-id="9075c-110">`Find-Command` pesquisa módulos em repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="9075c-110">`Find-Command` searches modules in registered repositories.</span></span>

<span data-ttu-id="9075c-111">Para cada comando encontrado por `Find-Command` , um objeto **PSGetCommandInfo** é retornado.</span><span class="sxs-lookup"><span data-stu-id="9075c-111">For each command found by `Find-Command`, a **PSGetCommandInfo** object is returned.</span></span> <span data-ttu-id="9075c-112">O objeto **PSGetCommandInfo** pode ser enviado ao pipeline para o `Install-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9075c-112">The **PSGetCommandInfo** object can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="9075c-113">`Install-Module` instala o módulo que contém o comando.</span><span class="sxs-lookup"><span data-stu-id="9075c-113">`Install-Module` installs the module that contains the command.</span></span>

## <span data-ttu-id="9075c-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9075c-114">EXAMPLES</span></span>

### <span data-ttu-id="9075c-115">Exemplo 1: localizar todos os comandos em um repositório especificado</span><span class="sxs-lookup"><span data-stu-id="9075c-115">Example 1: Find all commands in a specified repository</span></span>

<span data-ttu-id="9075c-116">O `Find-Command` cmdlet pesquisa um repositório registrado em busca de módulos.</span><span class="sxs-lookup"><span data-stu-id="9075c-116">The `Find-Command` cmdlet searches a registered repository for modules.</span></span>

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

<span data-ttu-id="9075c-117">`Find-Command` usa o parâmetro **Repository** para especificar o nome de um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="9075c-117">`Find-Command` uses the **Repository** parameter to specify a registered repository's name.</span></span> <span data-ttu-id="9075c-118">Os objetos são enviados pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="9075c-118">The objects are sent down the pipeline.</span></span> <span data-ttu-id="9075c-119">`Select-Object` recebe os objetos e usa o **primeiro** parâmetro para exibir os 10 primeiros resultados.</span><span class="sxs-lookup"><span data-stu-id="9075c-119">`Select-Object` receives the objects and uses the **First** parameter to display the first 10 results.</span></span>

### <span data-ttu-id="9075c-120">Exemplo 2: localizar um comando por nome</span><span class="sxs-lookup"><span data-stu-id="9075c-120">Example 2: Find a command by name</span></span>

<span data-ttu-id="9075c-121">`Find-Command` pode usar o nome de um comando para localizar o módulo em um repositório.</span><span class="sxs-lookup"><span data-stu-id="9075c-121">`Find-Command` can use the name of a command to locate the module in a repository.</span></span> <span data-ttu-id="9075c-122">É possível que exista um nome de comando em vários **modulenames**.</span><span class="sxs-lookup"><span data-stu-id="9075c-122">It's possible that a command name exists in multiple **ModuleNames**.</span></span>

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

<span data-ttu-id="9075c-123">`Find-Command` usa o parâmetro **Repository** para pesquisar o **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="9075c-123">`Find-Command` uses the **Repository** parameter to search the **PSGallery**.</span></span> <span data-ttu-id="9075c-124">O parâmetro **Name** especifica o comando **Get-TargetResource**.</span><span class="sxs-lookup"><span data-stu-id="9075c-124">The **Name** parameter specifies the command **Get-TargetResource**.</span></span>

### <span data-ttu-id="9075c-125">Exemplo 3: localizar comandos por nome e instalar o módulo</span><span class="sxs-lookup"><span data-stu-id="9075c-125">Example 3: Find commands by name and install the module</span></span>

<span data-ttu-id="9075c-126">`Find-Command` pode localizar o comando e o módulo e, em seguida, enviar o objeto para `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="9075c-126">`Find-Command` can locate the command and module, then send the object to `Install-Module`.</span></span> <span data-ttu-id="9075c-127">Se um comando for incluído em vários módulos, use o `Find-Command` parâmetro **Module-Name** do cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9075c-127">If a command is included in multiple modules, use the `Find-Command` cmdlets **Module-Name** parameter.</span></span>
<span data-ttu-id="9075c-128">Caso contrário, os módulos podem ser instalados e você não deseja instalar.</span><span class="sxs-lookup"><span data-stu-id="9075c-128">Otherwise, modules might be installed that you didn't want to install.</span></span>

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

<span data-ttu-id="9075c-129">`Find-Command` usa o parâmetro **Name** para especificar o comando **Get-TargetResource**.</span><span class="sxs-lookup"><span data-stu-id="9075c-129">`Find-Command` uses the **Name** parameter to specify the command **Get-TargetResource**.</span></span> <span data-ttu-id="9075c-130">O parâmetro **Repository** pesquisa o **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="9075c-130">The **Repository** parameter searches the **PSGallery**.</span></span> <span data-ttu-id="9075c-131">O parâmetro **ModuleName** especifica o módulo que você deseja instalar, **SystemLocaleDsc**.</span><span class="sxs-lookup"><span data-stu-id="9075c-131">The **ModuleName** parameter specifies the module you want to install, **SystemLocaleDsc**.</span></span> <span data-ttu-id="9075c-132">O objeto é enviado ao pipeline para o `Install-Module` e o módulo é instalado.</span><span class="sxs-lookup"><span data-stu-id="9075c-132">The object is sent down the pipeline to `Install-Module` and the module is installed.</span></span> <span data-ttu-id="9075c-133">Após a conclusão da instalação, você pode usar `Get-InstalledModule` o para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="9075c-133">After the installation finishes, you can use `Get-InstalledModule` to display the results.</span></span>

### <span data-ttu-id="9075c-134">Exemplo 4: localizar um comando e salvar seu módulo</span><span class="sxs-lookup"><span data-stu-id="9075c-134">Example 4: Find a command and save its module</span></span>

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

<span data-ttu-id="9075c-135">`Find-Command` usa os parâmetros **Name** e **Repository** para pesquisar o comando **Invoke-ScriptAnalyzer** no repositório **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="9075c-135">`Find-Command` uses the **Name** and **Repository** parameters to search for the command **Invoke-ScriptAnalyzer** in the **PSGallery** repository.</span></span> <span data-ttu-id="9075c-136">O objeto é enviado ao pipeline para `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="9075c-136">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="9075c-137">O parâmetro **path** determina o local para salvar o módulo.</span><span class="sxs-lookup"><span data-stu-id="9075c-137">The **Path** parameter determines the location to save the module.</span></span> <span data-ttu-id="9075c-138">**Verbose** é um parâmetro opcional, mas exibe a saída de status no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9075c-138">**Verbose** is an optional parameter, but displays status output in the PowerShell console.</span></span> <span data-ttu-id="9075c-139">A saída detalhada é benéfica para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="9075c-139">The verbose output is beneficial for troubleshooting.</span></span>

## <span data-ttu-id="9075c-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9075c-140">PARAMETERS</span></span>

### <span data-ttu-id="9075c-141">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="9075c-141">-AllowPrerelease</span></span>

<span data-ttu-id="9075c-142">Inclui módulos marcados como um pré-lançamento nos resultados.</span><span class="sxs-lookup"><span data-stu-id="9075c-142">Includes modules marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="9075c-143">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="9075c-143">-AllVersions</span></span>

<span data-ttu-id="9075c-144">Indica que este cmdlet obtém todas as versões de um módulo.</span><span class="sxs-lookup"><span data-stu-id="9075c-144">Indicates that this cmdlet gets all versions of a module.</span></span>

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

### <span data-ttu-id="9075c-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="9075c-145">-Filter</span></span>

<span data-ttu-id="9075c-146">Localiza módulos com base na sintaxe de pesquisa do provedor de **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="9075c-146">Finds modules based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="9075c-147">Por exemplo, especifique as palavras a serem pesquisadas nas propriedades **ModuleName** e **Description** .</span><span class="sxs-lookup"><span data-stu-id="9075c-147">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="9075c-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9075c-148">-MaximumVersion</span></span>

<span data-ttu-id="9075c-149">Especifica a versão máxima do módulo a ser incluída nos resultados.</span><span class="sxs-lookup"><span data-stu-id="9075c-149">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="9075c-150">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="9075c-150">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="9075c-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9075c-151">-MinimumVersion</span></span>

<span data-ttu-id="9075c-152">Especifica a versão mínima do módulo a ser incluída nos resultados.</span><span class="sxs-lookup"><span data-stu-id="9075c-152">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="9075c-153">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="9075c-153">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="9075c-154">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="9075c-154">-ModuleName</span></span>

<span data-ttu-id="9075c-155">Especifica o nome de um módulo para procurar por comandos.</span><span class="sxs-lookup"><span data-stu-id="9075c-155">Specifies the name of a module to search for commands.</span></span> <span data-ttu-id="9075c-156">O padrão é todos os módulos.</span><span class="sxs-lookup"><span data-stu-id="9075c-156">The default is all modules.</span></span>

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

### <span data-ttu-id="9075c-157">-Name</span><span class="sxs-lookup"><span data-stu-id="9075c-157">-Name</span></span>

<span data-ttu-id="9075c-158">Especifica o nome do comando a ser pesquisado em um repositório.</span><span class="sxs-lookup"><span data-stu-id="9075c-158">Specifies the command name to search for in a repository.</span></span> <span data-ttu-id="9075c-159">Use vírgulas para separar uma matriz de nomes de comando.</span><span class="sxs-lookup"><span data-stu-id="9075c-159">Use commas to separate an array of command names.</span></span>

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

### <span data-ttu-id="9075c-160">-Proxy</span><span class="sxs-lookup"><span data-stu-id="9075c-160">-Proxy</span></span>

<span data-ttu-id="9075c-161">Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="9075c-161">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="9075c-162">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="9075c-162">-ProxyCredential</span></span>

<span data-ttu-id="9075c-163">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="9075c-163">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="9075c-164">-Repositório</span><span class="sxs-lookup"><span data-stu-id="9075c-164">-Repository</span></span>

<span data-ttu-id="9075c-165">Especifica o repositório para procurar por comandos.</span><span class="sxs-lookup"><span data-stu-id="9075c-165">Specifies the repository to search for commands.</span></span> <span data-ttu-id="9075c-166">Use vírgulas para separar uma matriz de nomes de repositório.</span><span class="sxs-lookup"><span data-stu-id="9075c-166">Use commas to separate an array of repository names.</span></span> <span data-ttu-id="9075c-167">O padrão é todos os repositórios.</span><span class="sxs-lookup"><span data-stu-id="9075c-167">The default is all repositories.</span></span>

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

### <span data-ttu-id="9075c-168">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9075c-168">-RequiredVersion</span></span>

<span data-ttu-id="9075c-169">Especifica a versão do módulo a ser incluída nos resultados.</span><span class="sxs-lookup"><span data-stu-id="9075c-169">Specifies the version of the module to include in the results.</span></span>

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

### <span data-ttu-id="9075c-170">-Tag</span><span class="sxs-lookup"><span data-stu-id="9075c-170">-Tag</span></span>

<span data-ttu-id="9075c-171">Especifica as marcas que categorizam os módulos em um repositório.</span><span class="sxs-lookup"><span data-stu-id="9075c-171">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="9075c-172">Use vírgulas para separar uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="9075c-172">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="9075c-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9075c-173">CommonParameters</span></span>

<span data-ttu-id="9075c-174">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9075c-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9075c-175">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9075c-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9075c-176">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9075c-176">INPUTS</span></span>

## <span data-ttu-id="9075c-177">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9075c-177">OUTPUTS</span></span>

### <span data-ttu-id="9075c-178">PSGetCommandInfo</span><span class="sxs-lookup"><span data-stu-id="9075c-178">PSGetCommandInfo</span></span>

<span data-ttu-id="9075c-179">`Find-Command` gera um objeto **PSGetCommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="9075c-179">`Find-Command` outputs a **PSGetCommandInfo** object.</span></span>

## <span data-ttu-id="9075c-180">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9075c-180">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9075c-181">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="9075c-181">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="9075c-182">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9075c-182">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="9075c-183">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="9075c-183">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="9075c-184">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9075c-184">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="9075c-185">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9075c-185">RELATED LINKS</span></span>

[<span data-ttu-id="9075c-186">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="9075c-186">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="9075c-187">Install-Module</span><span class="sxs-lookup"><span data-stu-id="9075c-187">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="9075c-188">Save-Module</span><span class="sxs-lookup"><span data-stu-id="9075c-188">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="9075c-189">Select-Object</span><span class="sxs-lookup"><span data-stu-id="9075c-189">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="9075c-190">Desinstalar-módulo</span><span class="sxs-lookup"><span data-stu-id="9075c-190">Uninstall-Module</span></span>](Uninstall-Module.md)
