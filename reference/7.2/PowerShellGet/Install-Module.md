---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: f4fcf349c439baf4813c37af4bf56c26a46c7877
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99596193"
---
# <span data-ttu-id="496a3-102">Install-Module</span><span class="sxs-lookup"><span data-stu-id="496a3-102">Install-Module</span></span>

## <span data-ttu-id="496a3-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="496a3-103">SYNOPSIS</span></span>
<span data-ttu-id="496a3-104">Baixa um ou mais módulos de um repositório e os instala no computador local.</span><span class="sxs-lookup"><span data-stu-id="496a3-104">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="496a3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="496a3-105">SYNTAX</span></span>

### <span data-ttu-id="496a3-106">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="496a3-106">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="496a3-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="496a3-107">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="496a3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="496a3-108">DESCRIPTION</span></span>

<span data-ttu-id="496a3-109">O `Install-Module` cmdlet obtém um ou mais módulos que atendem aos critérios especificados de um repositório online.</span><span class="sxs-lookup"><span data-stu-id="496a3-109">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="496a3-110">O cmdlet verifica se os resultados da pesquisa são módulos válidos e copia as pastas do módulo para o local de instalação.</span><span class="sxs-lookup"><span data-stu-id="496a3-110">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="496a3-111">Os módulos instalados não são importados automaticamente após a instalação.</span><span class="sxs-lookup"><span data-stu-id="496a3-111">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="496a3-112">Você pode filtrar qual módulo está instalado com base nas versões mínima, máxima e exata dos módulos especificados.</span><span class="sxs-lookup"><span data-stu-id="496a3-112">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="496a3-113">Se o módulo que está sendo instalado tiver o mesmo nome ou versão, ou contiver comandos em um módulo existente, as mensagens de aviso serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="496a3-113">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="496a3-114">Depois de confirmar que deseja instalar o módulo e substituir os avisos, use os `-Force` `-AllowClobber` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="496a3-114">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="496a3-115">Dependendo das configurações do repositório, talvez seja necessário responder a um prompt para que a instalação do módulo continue.</span><span class="sxs-lookup"><span data-stu-id="496a3-115">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="496a3-116">Esses exemplos usam o [Galeria do PowerShell](https://www.powershellgallery.com/) como o único repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="496a3-116">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="496a3-117">`Get-PSRepository` exibe os repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="496a3-117">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="496a3-118">Se você tiver vários repositórios registrados, use o `-Repository` parâmetro para especificar o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="496a3-118">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="496a3-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="496a3-119">EXAMPLES</span></span>

### <span data-ttu-id="496a3-120">Exemplo 1: localizar e instalar um módulo</span><span class="sxs-lookup"><span data-stu-id="496a3-120">Example 1: Find and install a module</span></span>

<span data-ttu-id="496a3-121">Este exemplo localiza um módulo no repositório e instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-121">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="496a3-122">O `Find-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="496a3-122">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="496a3-123">Por padrão, a versão mais recente do módulo é baixada do repositório.</span><span class="sxs-lookup"><span data-stu-id="496a3-123">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="496a3-124">O objeto é enviado ao pipeline para o `Install-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="496a3-124">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="496a3-125">`Install-Module` instala o módulo para todos os usuários no `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="496a3-125">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="496a3-126">Exemplo 2: instalar um módulo por nome</span><span class="sxs-lookup"><span data-stu-id="496a3-126">Example 2: Install a module by name</span></span>

<span data-ttu-id="496a3-127">Neste exemplo, a versão mais recente do módulo **PowerShellGet** está instalada.</span><span class="sxs-lookup"><span data-stu-id="496a3-127">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="496a3-128">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="496a3-128">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="496a3-129">Por padrão, a versão mais recente do módulo é baixada do repositório e instalada.</span><span class="sxs-lookup"><span data-stu-id="496a3-129">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="496a3-130">Exemplo 3: instalar um módulo usando sua versão mínima</span><span class="sxs-lookup"><span data-stu-id="496a3-130">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="496a3-131">Neste exemplo, a versão mínima do módulo **PowerShellGet** está instalada.</span><span class="sxs-lookup"><span data-stu-id="496a3-131">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="496a3-132">O parâmetro **MinimumVersion** especifica a versão mais baixa do módulo que deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="496a3-132">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="496a3-133">Se uma versão mais recente do módulo estiver disponível, essa versão será baixada e instalada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="496a3-133">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="496a3-134">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="496a3-134">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="496a3-135">O parâmetro **MinimumVersion** especifica que a versão **2.0.1** é baixada do repositório e instalada.</span><span class="sxs-lookup"><span data-stu-id="496a3-135">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="496a3-136">Como a versão **2.0.4** está disponível, essa versão é baixada e instalada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="496a3-136">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="496a3-137">Exemplo 4: instalar uma versão específica de um módulo</span><span class="sxs-lookup"><span data-stu-id="496a3-137">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="496a3-138">Neste exemplo, uma versão específica do módulo **PowerShellGet** está instalada.</span><span class="sxs-lookup"><span data-stu-id="496a3-138">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="496a3-139">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="496a3-139">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="496a3-140">O parâmetro **RequiredVersion** especifica que a versão **2.0.0** é baixada e instalada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="496a3-140">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="496a3-141">Exemplo 5: instalar um módulo somente para o usuário atual</span><span class="sxs-lookup"><span data-stu-id="496a3-141">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="496a3-142">Este exemplo baixa e instala a versão mais recente de um módulo, somente para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="496a3-142">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="496a3-143">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="496a3-143">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="496a3-144">`Install-Module` baixa e instala a versão mais recente do **PowerShellGet** no diretório do usuário atual, `$home\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="496a3-144">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="496a3-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="496a3-145">PARAMETERS</span></span>

### <span data-ttu-id="496a3-146">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="496a3-146">-AcceptLicense</span></span>

<span data-ttu-id="496a3-147">Para módulos que exigem uma licença, o **AcceptLicense** automaticamente aceita o contrato de licença durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="496a3-147">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="496a3-148">Para obter mais informações, consulte [módulos que exigem a aceitação da licença](/powershell/scripting/gallery/concepts/module-license-acceptance).</span><span class="sxs-lookup"><span data-stu-id="496a3-148">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="496a3-149">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="496a3-149">-AllowClobber</span></span>

<span data-ttu-id="496a3-150">Substitui mensagens de aviso sobre conflitos de instalação sobre comandos existentes em um computador.</span><span class="sxs-lookup"><span data-stu-id="496a3-150">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="496a3-151">Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados por um módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-151">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="496a3-152">**AllowClobber** e **Force** podem ser usados juntos em um `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="496a3-152">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="496a3-153">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="496a3-153">-AllowPrerelease</span></span>

<span data-ttu-id="496a3-154">Permite que você instale um módulo marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="496a3-154">Allows you to install a module marked as a pre-release.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="496a3-155">-Confirm</span></span>

<span data-ttu-id="496a3-156">Solicita a confirmação antes de executar o `Install-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="496a3-156">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="496a3-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="496a3-157">-Credential</span></span>

<span data-ttu-id="496a3-158">Especifica uma conta de usuário que tem direitos para instalar um módulo para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="496a3-158">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="496a3-159">-Force</span><span class="sxs-lookup"><span data-stu-id="496a3-159">-Force</span></span>

<span data-ttu-id="496a3-160">Instala um módulo e substitui mensagens de aviso sobre conflitos de instalação de módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-160">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="496a3-161">Se um módulo com o mesmo nome já existir no computador, **Force** permitirá que várias versões sejam instaladas.</span><span class="sxs-lookup"><span data-stu-id="496a3-161">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="496a3-162">Se houver um módulo existente com o mesmo nome e versão, **Force** substitui essa versão.</span><span class="sxs-lookup"><span data-stu-id="496a3-162">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="496a3-163">**Force** e **AllowClobber** podem ser usados juntos em um `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="496a3-163">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="496a3-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="496a3-164">-InputObject</span></span>

<span data-ttu-id="496a3-165">Usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="496a3-165">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-166">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="496a3-166">-MaximumVersion</span></span>

<span data-ttu-id="496a3-167">Especifica a versão máxima de um único módulo a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="496a3-167">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="496a3-168">A versão instalada deve ser menor ou igual a **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="496a3-168">The version installed must be less than or equal to **MaximumVersion**.</span></span> <span data-ttu-id="496a3-169">Se você quiser instalar vários módulos, não poderá usar **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="496a3-169">If you want to install multiple modules, you cannot use **MaximumVersion**.</span></span> <span data-ttu-id="496a3-170">**MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="496a3-170">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-171">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="496a3-171">-MinimumVersion</span></span>

<span data-ttu-id="496a3-172">Especifica a versão mínima de um único módulo a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="496a3-172">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="496a3-173">A versão instalada deve ser maior ou igual a **MinimumVersion**.</span><span class="sxs-lookup"><span data-stu-id="496a3-173">The version installed must be greater than or equal to **MinimumVersion**.</span></span> <span data-ttu-id="496a3-174">Se houver uma versão mais recente do módulo disponível, a versão mais recente será instalada.</span><span class="sxs-lookup"><span data-stu-id="496a3-174">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="496a3-175">Se você quiser instalar vários módulos, não poderá usar **MinimumVersion**.</span><span class="sxs-lookup"><span data-stu-id="496a3-175">If you want to install multiple modules, you cannot use **MinimumVersion**.</span></span>
<span data-ttu-id="496a3-176">**MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="496a3-176">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-177">-Name</span><span class="sxs-lookup"><span data-stu-id="496a3-177">-Name</span></span>

<span data-ttu-id="496a3-178">Especifica os nomes exatos dos módulos a serem instalados na galeria online.</span><span class="sxs-lookup"><span data-stu-id="496a3-178">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="496a3-179">Uma lista separada por vírgulas de nomes de módulo é aceita.</span><span class="sxs-lookup"><span data-stu-id="496a3-179">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="496a3-180">O nome do módulo deve corresponder ao nome do módulo no repositório.</span><span class="sxs-lookup"><span data-stu-id="496a3-180">The module name must match the module name in the repository.</span></span> <span data-ttu-id="496a3-181">Use `Find-Module` para obter uma lista de nomes de módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-181">Use `Find-Module` to get a list of module names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-182">-PassThru</span><span class="sxs-lookup"><span data-stu-id="496a3-182">-PassThru</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-183">-Proxy</span><span class="sxs-lookup"><span data-stu-id="496a3-183">-Proxy</span></span>

<span data-ttu-id="496a3-184">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="496a3-184">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="496a3-185">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="496a3-185">-ProxyCredential</span></span>

<span data-ttu-id="496a3-186">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="496a3-186">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="496a3-187">-Repositório</span><span class="sxs-lookup"><span data-stu-id="496a3-187">-Repository</span></span>

<span data-ttu-id="496a3-188">Use o parâmetro **Repository** para especificar qual repositório é usado para baixar e instalar um módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-188">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="496a3-189">Usado quando vários repositórios são registrados.</span><span class="sxs-lookup"><span data-stu-id="496a3-189">Used when multiple repositories are registered.</span></span> <span data-ttu-id="496a3-190">Especifica o nome de um repositório registrado no `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="496a3-190">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="496a3-191">Para registrar um repositório, use `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="496a3-191">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="496a3-192">Para exibir repositórios registrados, use `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="496a3-192">To display registered repositories, use `Get-PSRepository`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-193">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="496a3-193">-RequiredVersion</span></span>

<span data-ttu-id="496a3-194">Especifica a versão exata de um único módulo a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="496a3-194">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="496a3-195">Se não houver nenhuma correspondência no repositório para a versão especificada, será exibido um erro.</span><span class="sxs-lookup"><span data-stu-id="496a3-195">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="496a3-196">Se você quiser instalar vários módulos, não poderá usar **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="496a3-196">If you want to install multiple modules, you cannot use **RequiredVersion**.</span></span> <span data-ttu-id="496a3-197">**RequiredVersion** não pode ser usado no mesmo `Install-Module` comando que **MinimumVersion** ou **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="496a3-197">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion**.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="496a3-198">-Escopo</span><span class="sxs-lookup"><span data-stu-id="496a3-198">-Scope</span></span>

<span data-ttu-id="496a3-199">Especifica o escopo de instalação do módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-199">Specifies the installation scope of the module.</span></span> <span data-ttu-id="496a3-200">Os valores aceitáveis para esse parâmetro são **AllUsers** e **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="496a3-200">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span>

<span data-ttu-id="496a3-201">O escopo **AllUsers** instala módulos em um local que pode ser acessado por todos os usuários do computador:</span><span class="sxs-lookup"><span data-stu-id="496a3-201">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="496a3-202">O **CurrentUser** instala módulos em um local que é acessível somente para o usuário atual do computador.</span><span class="sxs-lookup"><span data-stu-id="496a3-202">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="496a3-203">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="496a3-203">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="496a3-204">Quando nenhum **escopo** é definido, o padrão é definido com base na versão do PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="496a3-204">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="496a3-205">No PowerShellGet versões 2.0.0 e superiores, o padrão é **CurrentUser**, que não requer elevação para a instalação.</span><span class="sxs-lookup"><span data-stu-id="496a3-205">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser**, which does not require elevation for install.</span></span>
- <span data-ttu-id="496a3-206">Nas versões do PowerShellGet 1. x, o padrão é **AllUsers**, o que requer elevação para a instalação.</span><span class="sxs-lookup"><span data-stu-id="496a3-206">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

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

### <span data-ttu-id="496a3-207">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="496a3-207">-SkipPublisherCheck</span></span>

<span data-ttu-id="496a3-208">Permite que você instale uma versão mais recente de um módulo que já existe em seu computador.</span><span class="sxs-lookup"><span data-stu-id="496a3-208">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="496a3-209">Por exemplo, quando um módulo existente é assinado digitalmente por um fornecedor confiável, mas a nova versão não é assinada digitalmente por um fornecedor confiável.</span><span class="sxs-lookup"><span data-stu-id="496a3-209">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="496a3-210">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="496a3-210">-WhatIf</span></span>

<span data-ttu-id="496a3-211">Mostra o que aconteceria se um `Install-Module` comando fosse executado.</span><span class="sxs-lookup"><span data-stu-id="496a3-211">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="496a3-212">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="496a3-212">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="496a3-213">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="496a3-213">CommonParameters</span></span>

<span data-ttu-id="496a3-214">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="496a3-214">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="496a3-215">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="496a3-215">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="496a3-216">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="496a3-216">INPUTS</span></span>

### <span data-ttu-id="496a3-217">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="496a3-217">PSRepositoryItemInfo</span></span>

<span data-ttu-id="496a3-218">`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para o `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="496a3-218">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="496a3-219">System.String[]</span><span class="sxs-lookup"><span data-stu-id="496a3-219">System.String[]</span></span>

### <span data-ttu-id="496a3-220">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="496a3-220">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="496a3-221">System.String</span><span class="sxs-lookup"><span data-stu-id="496a3-221">System.String</span></span>

### <span data-ttu-id="496a3-222">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="496a3-222">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="496a3-223">System.Uri</span><span class="sxs-lookup"><span data-stu-id="496a3-223">System.Uri</span></span>

## <span data-ttu-id="496a3-224">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="496a3-224">OUTPUTS</span></span>

### <span data-ttu-id="496a3-225">Microsoft. PowerShell. Commands. PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="496a3-225">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="496a3-226">Ao usar o parâmetro **PassThru** , o `Install-Module` gera um objeto **PSRepositoryItemInfo** para o módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-226">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="496a3-227">Essas são as mesmas informações que você obtém do `Find-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="496a3-227">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="496a3-228">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="496a3-228">NOTES</span></span>

<span data-ttu-id="496a3-229">`Install-Module` é executado no PowerShell 5,0 ou versões posteriores, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="496a3-229">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="496a3-230">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="496a3-230">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="496a3-231">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="496a3-231">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="496a3-232">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="496a3-232">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="496a3-233">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="496a3-233">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="496a3-234">Como prática recomendada de segurança, avalie o código de um módulo antes de executar quaisquer cmdlets ou funções pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="496a3-234">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="496a3-235">Para evitar a execução de módulos que contêm código mal-intencionado, os módulos instalados não são importados automaticamente após a instalação.</span><span class="sxs-lookup"><span data-stu-id="496a3-235">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="496a3-236">Se o nome do módulo especificado pelo parâmetro **Name** não existir no repositório, o `Install-Module` retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="496a3-236">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="496a3-237">Para instalar vários módulos, use o parâmetro **Name** e especifique uma matriz separada por vírgulas de nomes de módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-237">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="496a3-238">Se você especificar vários nomes de módulo, não poderá usar **MinimumVersion**, **MaximumVersion** ou **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="496a3-238">If you specify multiple module names, you cannot use **MinimumVersion**, **MaximumVersion**, or **RequiredVersion**.</span></span> <span data-ttu-id="496a3-239">`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para o `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="496a3-239">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="496a3-240">O pipeline é outra maneira de especificar vários módulos a serem instalados em um único comando.</span><span class="sxs-lookup"><span data-stu-id="496a3-240">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="496a3-241">Por padrão, os módulos para o escopo do **AllUsers** são instalados no `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="496a3-241">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="496a3-242">O padrão evita confusão quando você instala recursos de DSC (configuração de estado desejado) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="496a3-242">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="496a3-243">Uma instalação de módulo falha e não pode ser importada se não tiver um `.psm1` , `.psd1` ou `.dll` de mesmo nome dentro da pasta.</span><span class="sxs-lookup"><span data-stu-id="496a3-243">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="496a3-244">Use o parâmetro **Force** para instalar o módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-244">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="496a3-245">Se a versão de um módulo existente corresponder ao nome especificado pelo parâmetro **Name** , e o parâmetro **MinimumVersion** ou **RequiredVersion** não for usado, o `Install-Module` continuará silenciosamente, mas não instalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-245">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="496a3-246">Se a versão de um módulo existente for maior que o valor do parâmetro **MinimumVersion** ou igual ao valor do parâmetro **RequiredVersion** , `Install-Module` o continuará silenciosamente, mas não instalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-246">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="496a3-247">Se o módulo existente não corresponder aos valores especificados pelos parâmetros **MinimumVersion** ou **RequiredVersion** , ocorrerá um erro no `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="496a3-247">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="496a3-248">Por exemplo, se a versão do módulo instalado existente for menor do que o valor **MinimumVersion** ou não for igual ao valor **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="496a3-248">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="496a3-249">Uma instalação de módulo também instalará quaisquer módulos dependentes especificados conforme exigido pelo editor de módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-249">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="496a3-250">O Publicador especificará os módulos necessários e suas versões no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="496a3-250">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="496a3-251">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="496a3-251">RELATED LINKS</span></span>

[<span data-ttu-id="496a3-252">Find-Module</span><span class="sxs-lookup"><span data-stu-id="496a3-252">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="496a3-253">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="496a3-253">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="496a3-254">Import-Module</span><span class="sxs-lookup"><span data-stu-id="496a3-254">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="496a3-255">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="496a3-255">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="496a3-256">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="496a3-256">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="496a3-257">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="496a3-257">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="496a3-258">Update-Module</span><span class="sxs-lookup"><span data-stu-id="496a3-258">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="496a3-259">about_Module</span><span class="sxs-lookup"><span data-stu-id="496a3-259">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
