---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: 5e210a626c0b64884bb95807a51d712061276122
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2020
ms.locfileid: "93195111"
---
# <span data-ttu-id="9e9be-103">Install-Module</span><span class="sxs-lookup"><span data-stu-id="9e9be-103">Install-Module</span></span>

## <span data-ttu-id="9e9be-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9e9be-104">SYNOPSIS</span></span>
<span data-ttu-id="9e9be-105">Baixa um ou mais módulos de um repositório e os instala no computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9be-105">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="9e9be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e9be-106">SYNTAX</span></span>

### <span data-ttu-id="9e9be-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="9e9be-107">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9e9be-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="9e9be-108">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9e9be-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9e9be-109">DESCRIPTION</span></span>

<span data-ttu-id="9e9be-110">O `Install-Module` cmdlet obtém um ou mais módulos que atendem aos critérios especificados de um repositório online.</span><span class="sxs-lookup"><span data-stu-id="9e9be-110">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="9e9be-111">O cmdlet verifica se os resultados da pesquisa são módulos válidos e copia as pastas do módulo para o local de instalação.</span><span class="sxs-lookup"><span data-stu-id="9e9be-111">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="9e9be-112">Os módulos instalados não são importados automaticamente após a instalação.</span><span class="sxs-lookup"><span data-stu-id="9e9be-112">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="9e9be-113">Você pode filtrar qual módulo está instalado com base nas versões mínima, máxima e exata dos módulos especificados.</span><span class="sxs-lookup"><span data-stu-id="9e9be-113">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="9e9be-114">Se o módulo que está sendo instalado tiver o mesmo nome ou versão, ou contiver comandos em um módulo existente, as mensagens de aviso serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="9e9be-114">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="9e9be-115">Depois de confirmar que deseja instalar o módulo e substituir os avisos, use os `-Force` `-AllowClobber` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="9e9be-115">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="9e9be-116">Dependendo das configurações do repositório, talvez seja necessário responder a um prompt para que a instalação do módulo continue.</span><span class="sxs-lookup"><span data-stu-id="9e9be-116">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="9e9be-117">Esses exemplos usam o [Galeria do PowerShell](https://www.powershellgallery.com/) como o único repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="9e9be-117">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="9e9be-118">`Get-PSRepository` exibe os repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="9e9be-118">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="9e9be-119">Se você tiver vários repositórios registrados, use o `-Repository` parâmetro para especificar o nome do repositório.</span><span class="sxs-lookup"><span data-stu-id="9e9be-119">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="9e9be-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9e9be-120">EXAMPLES</span></span>

### <span data-ttu-id="9e9be-121">Exemplo 1: localizar e instalar um módulo</span><span class="sxs-lookup"><span data-stu-id="9e9be-121">Example 1: Find and install a module</span></span>

<span data-ttu-id="9e9be-122">Este exemplo localiza um módulo no repositório e instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-122">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="9e9be-123">O `Find-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-123">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="9e9be-124">Por padrão, a versão mais recente do módulo é baixada do repositório.</span><span class="sxs-lookup"><span data-stu-id="9e9be-124">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="9e9be-125">O objeto é enviado ao pipeline para o `Install-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e9be-125">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="9e9be-126">`Install-Module` instala o módulo para todos os usuários no `$env:ProgramFiles\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="9e9be-126">`Install-Module` installs the module for all users in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

### <span data-ttu-id="9e9be-127">Exemplo 2: instalar um módulo por nome</span><span class="sxs-lookup"><span data-stu-id="9e9be-127">Example 2: Install a module by name</span></span>

<span data-ttu-id="9e9be-128">Neste exemplo, a versão mais recente do módulo **PowerShellGet** está instalada.</span><span class="sxs-lookup"><span data-stu-id="9e9be-128">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="9e9be-129">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-129">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="9e9be-130">Por padrão, a versão mais recente do módulo é baixada do repositório e instalada.</span><span class="sxs-lookup"><span data-stu-id="9e9be-130">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="9e9be-131">Exemplo 3: instalar um módulo usando sua versão mínima</span><span class="sxs-lookup"><span data-stu-id="9e9be-131">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="9e9be-132">Neste exemplo, a versão mínima do módulo **PowerShellGet** está instalada.</span><span class="sxs-lookup"><span data-stu-id="9e9be-132">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="9e9be-133">O parâmetro **MinimumVersion** especifica a versão mais baixa do módulo que deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="9e9be-133">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="9e9be-134">Se uma versão mais recente do módulo estiver disponível, essa versão será baixada e instalada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="9e9be-134">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="9e9be-135">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-135">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="9e9be-136">O parâmetro **MinimumVersion** especifica que a versão **2.0.1** é baixada do repositório e instalada.</span><span class="sxs-lookup"><span data-stu-id="9e9be-136">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="9e9be-137">Como a versão **2.0.4** está disponível, essa versão é baixada e instalada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="9e9be-137">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="9e9be-138">Exemplo 4: instalar uma versão específica de um módulo</span><span class="sxs-lookup"><span data-stu-id="9e9be-138">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="9e9be-139">Neste exemplo, uma versão específica do módulo **PowerShellGet** está instalada.</span><span class="sxs-lookup"><span data-stu-id="9e9be-139">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="9e9be-140">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-140">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="9e9be-141">O parâmetro **RequiredVersion** especifica que a versão **2.0.0** é baixada e instalada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="9e9be-141">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="9e9be-142">Exemplo 5: instalar um módulo somente para o usuário atual</span><span class="sxs-lookup"><span data-stu-id="9e9be-142">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="9e9be-143">Este exemplo baixa e instala a versão mais recente de um módulo, somente para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="9e9be-143">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="9e9be-144">O `Install-Module` usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-144">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="9e9be-145">`Install-Module` baixa e instala a versão mais recente do **PowerShellGet** no diretório do usuário atual, `$home\Documents\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="9e9be-145">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\WindowsPowerShell\Modules`.</span></span>

## <span data-ttu-id="9e9be-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e9be-146">PARAMETERS</span></span>

### <span data-ttu-id="9e9be-147">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="9e9be-147">-AcceptLicense</span></span>

<span data-ttu-id="9e9be-148">Para módulos que exigem uma licença, o **AcceptLicense** automaticamente aceita o contrato de licença durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="9e9be-148">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="9e9be-149">Para obter mais informações, consulte [módulos que exigem a aceitação da licença](/powershell/scripting/gallery/concepts/module-license-acceptance).</span><span class="sxs-lookup"><span data-stu-id="9e9be-149">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="9e9be-150">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="9e9be-150">-AllowClobber</span></span>

<span data-ttu-id="9e9be-151">Substitui mensagens de aviso sobre conflitos de instalação sobre comandos existentes em um computador.</span><span class="sxs-lookup"><span data-stu-id="9e9be-151">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="9e9be-152">Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados por um módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-152">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="9e9be-153">**AllowClobber** e **Force** podem ser usados juntos em um `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="9e9be-153">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="9e9be-154">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="9e9be-154">-AllowPrerelease</span></span>

<span data-ttu-id="9e9be-155">Permite que você instale um módulo marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="9e9be-155">Allows you to install a module marked as a pre-release.</span></span>

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

### <span data-ttu-id="9e9be-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9e9be-156">-Confirm</span></span>

<span data-ttu-id="9e9be-157">Solicita a confirmação antes de executar o `Install-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e9be-157">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="9e9be-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="9e9be-158">-Credential</span></span>

<span data-ttu-id="9e9be-159">Especifica uma conta de usuário que tem direitos para instalar um módulo para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="9e9be-159">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="9e9be-160">-Force</span><span class="sxs-lookup"><span data-stu-id="9e9be-160">-Force</span></span>

<span data-ttu-id="9e9be-161">Instala um módulo e substitui mensagens de aviso sobre conflitos de instalação de módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-161">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="9e9be-162">Se um módulo com o mesmo nome já existir no computador, **Force** permitirá que várias versões sejam instaladas.</span><span class="sxs-lookup"><span data-stu-id="9e9be-162">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="9e9be-163">Se houver um módulo existente com o mesmo nome e versão, **Force** substitui essa versão.</span><span class="sxs-lookup"><span data-stu-id="9e9be-163">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="9e9be-164">**Force** e **AllowClobber** podem ser usados juntos em um `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="9e9be-164">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="9e9be-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9e9be-165">-InputObject</span></span>

<span data-ttu-id="9e9be-166">Usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="9e9be-166">Used for pipeline input.</span></span>

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

### <span data-ttu-id="9e9be-167">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9e9be-167">-MaximumVersion</span></span>

<span data-ttu-id="9e9be-168">Especifica a versão máxima de um único módulo a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="9e9be-168">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="9e9be-169">A versão instalada deve ser menor ou igual a **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-169">The version installed must be less than or equal to **MaximumVersion** .</span></span> <span data-ttu-id="9e9be-170">Se você quiser instalar vários módulos, não poderá usar **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-170">If you want to install multiple modules, you cannot use **MaximumVersion** .</span></span> <span data-ttu-id="9e9be-171">**MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="9e9be-171">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="9e9be-172">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9e9be-172">-MinimumVersion</span></span>

<span data-ttu-id="9e9be-173">Especifica a versão mínima de um único módulo a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="9e9be-173">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="9e9be-174">A versão instalada deve ser maior ou igual a **MinimumVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-174">The version installed must be greater than or equal to **MinimumVersion** .</span></span> <span data-ttu-id="9e9be-175">Se houver uma versão mais recente do módulo disponível, a versão mais recente será instalada.</span><span class="sxs-lookup"><span data-stu-id="9e9be-175">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="9e9be-176">Se você quiser instalar vários módulos, não poderá usar **MinimumVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-176">If you want to install multiple modules, you cannot use **MinimumVersion** .</span></span>
<span data-ttu-id="9e9be-177">**MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="9e9be-177">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="9e9be-178">-Name</span><span class="sxs-lookup"><span data-stu-id="9e9be-178">-Name</span></span>

<span data-ttu-id="9e9be-179">Especifica os nomes exatos dos módulos a serem instalados na galeria online.</span><span class="sxs-lookup"><span data-stu-id="9e9be-179">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="9e9be-180">Uma lista separada por vírgulas de nomes de módulo é aceita.</span><span class="sxs-lookup"><span data-stu-id="9e9be-180">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="9e9be-181">O nome do módulo deve corresponder ao nome do módulo no repositório.</span><span class="sxs-lookup"><span data-stu-id="9e9be-181">The module name must match the module name in the repository.</span></span> <span data-ttu-id="9e9be-182">Use `Find-Module` para obter uma lista de nomes de módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-182">Use `Find-Module` to get a list of module names.</span></span>

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

### <span data-ttu-id="9e9be-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9e9be-183">-PassThru</span></span>

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

### <span data-ttu-id="9e9be-184">-Proxy</span><span class="sxs-lookup"><span data-stu-id="9e9be-184">-Proxy</span></span>

<span data-ttu-id="9e9be-185">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="9e9be-185">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="9e9be-186">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="9e9be-186">-ProxyCredential</span></span>

<span data-ttu-id="9e9be-187">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-187">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="9e9be-188">-Repositório</span><span class="sxs-lookup"><span data-stu-id="9e9be-188">-Repository</span></span>

<span data-ttu-id="9e9be-189">Use o parâmetro **Repository** para especificar qual repositório é usado para baixar e instalar um módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-189">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="9e9be-190">Usado quando vários repositórios são registrados.</span><span class="sxs-lookup"><span data-stu-id="9e9be-190">Used when multiple repositories are registered.</span></span> <span data-ttu-id="9e9be-191">Especifica o nome de um repositório registrado no `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="9e9be-191">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="9e9be-192">Para registrar um repositório, use `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="9e9be-192">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="9e9be-193">Para exibir repositórios registrados, use `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="9e9be-193">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="9e9be-194">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9e9be-194">-RequiredVersion</span></span>

<span data-ttu-id="9e9be-195">Especifica a versão exata de um único módulo a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="9e9be-195">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="9e9be-196">Se não houver nenhuma correspondência no repositório para a versão especificada, será exibido um erro.</span><span class="sxs-lookup"><span data-stu-id="9e9be-196">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="9e9be-197">Se você quiser instalar vários módulos, não poderá usar **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-197">If you want to install multiple modules, you cannot use **RequiredVersion** .</span></span> <span data-ttu-id="9e9be-198">**RequiredVersion** não pode ser usado no mesmo `Install-Module` comando que **MinimumVersion** ou **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-198">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion** .</span></span>

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

### <span data-ttu-id="9e9be-199">-Escopo</span><span class="sxs-lookup"><span data-stu-id="9e9be-199">-Scope</span></span>

<span data-ttu-id="9e9be-200">Especifica o escopo de instalação do módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-200">Specifies the installation scope of the module.</span></span> <span data-ttu-id="9e9be-201">Os valores aceitáveis para esse parâmetro são **AllUsers** e **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-201">The acceptable values for this parameter are **AllUsers** and **CurrentUser** .</span></span>

<span data-ttu-id="9e9be-202">O escopo **AllUsers** instala módulos em um local que pode ser acessado por todos os usuários do computador:</span><span class="sxs-lookup"><span data-stu-id="9e9be-202">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\WindowsPowerShell\Modules`

<span data-ttu-id="9e9be-203">O **CurrentUser** instala módulos em um local que é acessível somente para o usuário atual do computador.</span><span class="sxs-lookup"><span data-stu-id="9e9be-203">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="9e9be-204">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9e9be-204">For example:</span></span>

`$home\Documents\WindowsPowerShell\Modules`

<span data-ttu-id="9e9be-205">Quando nenhum **escopo** é definido, o padrão é definido com base na versão do PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="9e9be-205">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="9e9be-206">No PowerShellGet versões 2.0.0 e superiores, o padrão é **CurrentUser** , que não requer elevação para a instalação.</span><span class="sxs-lookup"><span data-stu-id="9e9be-206">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser** , which does not require elevation for install.</span></span>
- <span data-ttu-id="9e9be-207">Nas versões do PowerShellGet 1. x, o padrão é **AllUsers** , o que requer elevação para a instalação.</span><span class="sxs-lookup"><span data-stu-id="9e9be-207">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

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

### <span data-ttu-id="9e9be-208">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="9e9be-208">-SkipPublisherCheck</span></span>

<span data-ttu-id="9e9be-209">Permite que você instale uma versão mais recente de um módulo que já existe em seu computador.</span><span class="sxs-lookup"><span data-stu-id="9e9be-209">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="9e9be-210">Por exemplo, quando um módulo existente é assinado digitalmente por um fornecedor confiável, mas a nova versão não é assinada digitalmente por um fornecedor confiável.</span><span class="sxs-lookup"><span data-stu-id="9e9be-210">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="9e9be-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9e9be-211">-WhatIf</span></span>

<span data-ttu-id="9e9be-212">Mostra o que aconteceria se um `Install-Module` comando fosse executado.</span><span class="sxs-lookup"><span data-stu-id="9e9be-212">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="9e9be-213">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="9e9be-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9e9be-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e9be-214">CommonParameters</span></span>

<span data-ttu-id="9e9be-215">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9e9be-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e9be-216">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9e9be-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e9be-217">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9e9be-217">INPUTS</span></span>

### <span data-ttu-id="9e9be-218">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="9e9be-218">PSRepositoryItemInfo</span></span>

<span data-ttu-id="9e9be-219">`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para o `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="9e9be-219">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="9e9be-220">System.String[]</span><span class="sxs-lookup"><span data-stu-id="9e9be-220">System.String[]</span></span>

### <span data-ttu-id="9e9be-221">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="9e9be-221">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="9e9be-222">System.String</span><span class="sxs-lookup"><span data-stu-id="9e9be-222">System.String</span></span>

### <span data-ttu-id="9e9be-223">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="9e9be-223">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="9e9be-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="9e9be-224">System.Uri</span></span>

## <span data-ttu-id="9e9be-225">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9e9be-225">OUTPUTS</span></span>

### <span data-ttu-id="9e9be-226">Microsoft. PowerShell. Commands. PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="9e9be-226">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="9e9be-227">Ao usar o parâmetro **PassThru** , o `Install-Module` gera um objeto **PSRepositoryItemInfo** para o módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-227">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="9e9be-228">Essas são as mesmas informações que você obtém do `Find-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e9be-228">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="9e9be-229">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9e9be-229">NOTES</span></span>

<span data-ttu-id="9e9be-230">`Install-Module` é executado no PowerShell 5,0 ou versões posteriores, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="9e9be-230">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="9e9be-231">Como prática recomendada de segurança, avalie o código de um módulo antes de executar quaisquer cmdlets ou funções pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="9e9be-231">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="9e9be-232">Para evitar a execução de módulos que contêm código mal-intencionado, os módulos instalados não são importados automaticamente após a instalação.</span><span class="sxs-lookup"><span data-stu-id="9e9be-232">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="9e9be-233">Se o nome do módulo especificado pelo parâmetro **Name** não existir no repositório, o `Install-Module` retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="9e9be-233">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="9e9be-234">Para instalar vários módulos, use o parâmetro **Name** e especifique uma matriz separada por vírgulas de nomes de módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-234">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="9e9be-235">Se você especificar vários nomes de módulo, não poderá usar **MinimumVersion** , **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-235">If you specify multiple module names, you cannot use **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** .</span></span> <span data-ttu-id="9e9be-236">`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para o `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="9e9be-236">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="9e9be-237">O pipeline é outra maneira de especificar vários módulos a serem instalados em um único comando.</span><span class="sxs-lookup"><span data-stu-id="9e9be-237">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="9e9be-238">Por padrão, os módulos para o escopo do **AllUsers** são instalados no `$env:ProgramFiles\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="9e9be-238">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span> <span data-ttu-id="9e9be-239">O padrão evita confusão quando você instala recursos de DSC (configuração de estado desejado) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e9be-239">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="9e9be-240">Uma instalação de módulo falha e não pode ser importada se não tiver um `.psm1` , `.psd1` ou `.dll` de mesmo nome dentro da pasta.</span><span class="sxs-lookup"><span data-stu-id="9e9be-240">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="9e9be-241">Use o parâmetro **Force** para instalar o módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-241">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="9e9be-242">Se a versão de um módulo existente corresponder ao nome especificado pelo parâmetro **Name** , e o parâmetro **MinimumVersion** ou **RequiredVersion** não for usado, o `Install-Module` continuará silenciosamente, mas não instalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-242">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="9e9be-243">Se a versão de um módulo existente for maior que o valor do parâmetro **MinimumVersion** ou igual ao valor do parâmetro **RequiredVersion** , `Install-Module` o continuará silenciosamente, mas não instalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-243">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="9e9be-244">Se o módulo existente não corresponder aos valores especificados pelos parâmetros **MinimumVersion** ou **RequiredVersion** , ocorrerá um erro no `Install-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="9e9be-244">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="9e9be-245">Por exemplo, se a versão do módulo instalado existente for menor do que o valor **MinimumVersion** ou não for igual ao valor **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="9e9be-245">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="9e9be-246">Uma instalação de módulo também instalará quaisquer módulos dependentes especificados conforme exigido pelo editor de módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-246">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="9e9be-247">O Publicador especificará os módulos necessários e suas versões no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="9e9be-247">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="9e9be-248">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9e9be-248">RELATED LINKS</span></span>

[<span data-ttu-id="9e9be-249">Find-Module</span><span class="sxs-lookup"><span data-stu-id="9e9be-249">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="9e9be-250">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9e9be-250">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="9e9be-251">Import-Module</span><span class="sxs-lookup"><span data-stu-id="9e9be-251">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="9e9be-252">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="9e9be-252">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="9e9be-253">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9e9be-253">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="9e9be-254">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="9e9be-254">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="9e9be-255">Update-Module</span><span class="sxs-lookup"><span data-stu-id="9e9be-255">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="9e9be-256">about_Module</span><span class="sxs-lookup"><span data-stu-id="9e9be-256">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
