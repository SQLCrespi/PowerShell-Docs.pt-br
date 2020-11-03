---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: 719eaa019dd721b156b26d2e38e8790e6b9af584
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194108"
---
# <span data-ttu-id="23af4-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="23af4-103">Update-Module</span></span>

## <span data-ttu-id="23af4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="23af4-104">SYNOPSIS</span></span>
<span data-ttu-id="23af4-105">Baixa e instala a versão mais recente dos módulos especificados de uma galeria online para o computador local.</span><span class="sxs-lookup"><span data-stu-id="23af4-105">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="23af4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23af4-106">SYNTAX</span></span>

### <span data-ttu-id="23af4-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="23af4-107">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="23af4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23af4-108">DESCRIPTION</span></span>

<span data-ttu-id="23af4-109">O `Update-Module` cmdlet instala a versão mais recente de um módulo de uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="23af4-109">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="23af4-110">Você será solicitado a confirmar a atualização antes de ela ser instalada.</span><span class="sxs-lookup"><span data-stu-id="23af4-110">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="23af4-111">As atualizações são instaladas somente para módulos que foram instalados no computador local com o `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="23af4-111">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="23af4-112">`Update-Module` procura `$env:PSModulePath` módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="23af4-112">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="23af4-113">`Update-Module` sem parâmetros especificados atualiza todos os módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="23af4-113">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="23af4-114">Para especificar um módulo a ser atualizado, use o parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="23af4-114">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="23af4-115">Você pode atualizar para a versão específica de um módulo usando o parâmetro **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="23af4-115">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="23af4-116">Se um módulo instalado já for a versão mais recente, o módulo não será atualizado.</span><span class="sxs-lookup"><span data-stu-id="23af4-116">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="23af4-117">Se o módulo não for encontrado em `$env:PSModulePath` , um erro será exibido.</span><span class="sxs-lookup"><span data-stu-id="23af4-117">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="23af4-118">Para exibir os módulos instalados, use `Get-InstalledModule` .</span><span class="sxs-lookup"><span data-stu-id="23af4-118">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="23af4-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="23af4-119">EXAMPLES</span></span>

### <span data-ttu-id="23af4-120">Exemplo 1: atualizar todos os módulos</span><span class="sxs-lookup"><span data-stu-id="23af4-120">Example 1: Update all modules</span></span>

<span data-ttu-id="23af4-121">Este exemplo atualiza todos os módulos instalados para a versão mais recente em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="23af4-121">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="23af4-122">Exemplo 2: atualizar um módulo por nome</span><span class="sxs-lookup"><span data-stu-id="23af4-122">Example 2: Update a module by name</span></span>

<span data-ttu-id="23af4-123">Este exemplo atualiza um módulo específico para a versão mais recente em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="23af4-123">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="23af4-124">`Update-Module` usa o parâmetro **Name** para atualizar um módulo específico, **SpeculationControl** .</span><span class="sxs-lookup"><span data-stu-id="23af4-124">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl** .</span></span>

### <span data-ttu-id="23af4-125">Exemplo 3: exibir as execuções de Update-Module de hipóteses</span><span class="sxs-lookup"><span data-stu-id="23af4-125">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="23af4-126">Este exemplo faz um cenário de hipóteses para mostrar o que acontece se `Update-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="23af4-126">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="23af4-127">O comando não é executado.</span><span class="sxs-lookup"><span data-stu-id="23af4-127">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="23af4-128">`Update-Module` usa o parâmetro **WhatIf** exibir o que aconteceria se `Update-Module` fosse executado.</span><span class="sxs-lookup"><span data-stu-id="23af4-128">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="23af4-129">Exemplo 4: atualizar um módulo para uma versão especificada</span><span class="sxs-lookup"><span data-stu-id="23af4-129">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="23af4-130">Neste exemplo, um módulo é atualizado para uma versão específica.</span><span class="sxs-lookup"><span data-stu-id="23af4-130">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="23af4-131">A versão deve existir na galeria online ou um erro é exibido.</span><span class="sxs-lookup"><span data-stu-id="23af4-131">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="23af4-132">`Update-Module` usa o parâmetro **Name** para especificar o módulo, **SpeculationControl** .</span><span class="sxs-lookup"><span data-stu-id="23af4-132">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="23af4-133">O parâmetro **RequiredVersion** especifica a versão, **1.0.14** .</span><span class="sxs-lookup"><span data-stu-id="23af4-133">The **RequiredVersion** parameter specifies the version, **1.0.14** .</span></span>

### <span data-ttu-id="23af4-134">Exemplo 5: atualizar um módulo sem confirmação</span><span class="sxs-lookup"><span data-stu-id="23af4-134">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="23af4-135">Este exemplo não solicita confirmação para atualizar o módulo para a versão mais recente de uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="23af4-135">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="23af4-136">Se o módulo já estiver instalado, o parâmetro **Force** reinstalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="23af4-136">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="23af4-137">`Update-Module` usa o parâmetro **Name** para especificar o módulo, **SpeculationControl** .</span><span class="sxs-lookup"><span data-stu-id="23af4-137">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="23af4-138">O parâmetro **Force** atualiza o módulo sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="23af4-138">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="23af4-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23af4-139">PARAMETERS</span></span>

### <span data-ttu-id="23af4-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="23af4-140">-AcceptLicense</span></span>

<span data-ttu-id="23af4-141">Aceite automaticamente o contrato de licença durante a instalação se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="23af4-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="23af4-142">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="23af4-142">-AllowPrerelease</span></span>

<span data-ttu-id="23af4-143">Permite que você atualize um módulo com o módulo mais recente marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="23af4-143">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="23af4-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="23af4-144">-Confirm</span></span>

<span data-ttu-id="23af4-145">Solicita a confirmação antes de executar `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="23af4-145">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="23af4-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="23af4-146">-Credential</span></span>

<span data-ttu-id="23af4-147">Especifica uma conta de usuário que tem permissão para atualizar um módulo.</span><span class="sxs-lookup"><span data-stu-id="23af4-147">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="23af4-148">-Force</span><span class="sxs-lookup"><span data-stu-id="23af4-148">-Force</span></span>

<span data-ttu-id="23af4-149">Força uma atualização de cada módulo especificado sem solicitar confirmação.</span><span class="sxs-lookup"><span data-stu-id="23af4-149">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="23af4-150">Se o módulo já estiver instalado, **Force** reinstalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="23af4-150">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="23af4-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="23af4-151">-MaximumVersion</span></span>

<span data-ttu-id="23af4-152">Especifica a versão máxima de um único módulo a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="23af4-152">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="23af4-153">Você não poderá adicionar esse parâmetro se estiver tentando atualizar vários módulos.</span><span class="sxs-lookup"><span data-stu-id="23af4-153">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="23af4-154">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="23af4-154">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23af4-155">-Name</span><span class="sxs-lookup"><span data-stu-id="23af4-155">-Name</span></span>

<span data-ttu-id="23af4-156">Especifica os nomes de um ou mais módulos a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="23af4-156">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="23af4-157">`Update-Module` pesquisa `$env:PSModulePath` os módulos a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="23af4-157">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="23af4-158">Se nenhuma correspondência for encontrada em `$env:PSModulePath` para o nome do módulo especificado, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="23af4-158">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="23af4-159">Caracteres curinga são aceitos em nomes de módulo.</span><span class="sxs-lookup"><span data-stu-id="23af4-159">Wildcards are accepted in module names.</span></span> <span data-ttu-id="23af4-160">Se você adicionar caracteres curinga ao nome especificado e nenhuma correspondência for encontrada, nenhum erro ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="23af4-160">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="23af4-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="23af4-161">-PassThru</span></span>

<span data-ttu-id="23af4-162">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="23af4-162">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="23af4-163">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="23af4-163">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="23af4-164">O suporte ao parâmetro **PassThru** foi adicionado no **PowerShellGet** 2.0.0</span><span class="sxs-lookup"><span data-stu-id="23af4-164">The **PassThru** parameter support was added in **PowerShellGet** 2.0.0</span></span>

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

### <span data-ttu-id="23af4-165">-Proxy</span><span class="sxs-lookup"><span data-stu-id="23af4-165">-Proxy</span></span>

<span data-ttu-id="23af4-166">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="23af4-166">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="23af4-167">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="23af4-167">-ProxyCredential</span></span>

<span data-ttu-id="23af4-168">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="23af4-168">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="23af4-169">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="23af4-169">-RequiredVersion</span></span>

<span data-ttu-id="23af4-170">Especifica a versão exata para a qual o módulo instalado existente será atualizado.</span><span class="sxs-lookup"><span data-stu-id="23af4-170">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="23af4-171">A versão especificada por **RequiredVersion** deve existir na galeria online ou um erro é exibido.</span><span class="sxs-lookup"><span data-stu-id="23af4-171">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="23af4-172">Se mais de um módulo for atualizado em um único comando, você não poderá usar **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="23af4-172">If more than one module is updated in a single command, you can't use **RequiredVersion** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="23af4-173">-Escopo</span><span class="sxs-lookup"><span data-stu-id="23af4-173">-Scope</span></span>

<span data-ttu-id="23af4-174">Especifica o escopo de instalação do módulo.</span><span class="sxs-lookup"><span data-stu-id="23af4-174">Specifies the installation scope of the module.</span></span> <span data-ttu-id="23af4-175">Os valores aceitáveis para esse parâmetro são **AllUsers** e **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="23af4-175">The acceptable values for this parameter are **AllUsers** and **CurrentUser** .</span></span> <span data-ttu-id="23af4-176">Se o **escopo** não for especificado, a atualização será instalada no escopo **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="23af4-176">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="23af4-177">O escopo **AllUsers** requer permissões elevadas e instala módulos em um local que pode ser acessado por todos os usuários do computador:</span><span class="sxs-lookup"><span data-stu-id="23af4-177">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="23af4-178">O **CurrentUser** não requer permissões elevadas e instala módulos em um local acessível somente para o usuário atual do computador:</span><span class="sxs-lookup"><span data-stu-id="23af4-178">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="23af4-179">Quando nenhum **escopo** é definido, o padrão é definido com base na versão do PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="23af4-179">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="23af4-180">No PowerShellGet versões 2.0.0 e superiores, o padrão é **AllUsers** ao executar uma sessão elevada e **CurrentUser** para todos os outros.</span><span class="sxs-lookup"><span data-stu-id="23af4-180">In PowerShellGet versions 2.0.0 and above, the default is **AllUsers** when running an elevated session and **CurrentUser** for all others.</span></span>
- <span data-ttu-id="23af4-181">Nas versões do PowerShellGet 1. x, o padrão é **AllUsers** , o que requer elevação para a instalação.</span><span class="sxs-lookup"><span data-stu-id="23af4-181">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23af4-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="23af4-182">-WhatIf</span></span>

<span data-ttu-id="23af4-183">Mostra o que aconteceria se `Update-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="23af4-183">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="23af4-184">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="23af4-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="23af4-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23af4-185">CommonParameters</span></span>

<span data-ttu-id="23af4-186">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23af4-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23af4-187">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23af4-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23af4-188">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="23af4-188">INPUTS</span></span>

### <span data-ttu-id="23af4-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="23af4-189">System.String[]</span></span>

### <span data-ttu-id="23af4-190">System.String</span><span class="sxs-lookup"><span data-stu-id="23af4-190">System.String</span></span>

### <span data-ttu-id="23af4-191">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="23af4-191">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="23af4-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="23af4-192">System.Uri</span></span>

## <span data-ttu-id="23af4-193">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="23af4-193">OUTPUTS</span></span>

### <span data-ttu-id="23af4-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="23af4-194">System.Object</span></span>

## <span data-ttu-id="23af4-195">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="23af4-195">NOTES</span></span>

<span data-ttu-id="23af4-196">Para o PowerShell 5,1 ou abaixo, o escopo padrão em uma sessão com privilégios elevados é **AllUsers** e, em uma sessão não elevada, **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="23af4-196">For PowerShell 5.1 or below, the default scope in an elevated session is **AllUsers** , and in a non-elevated session, **CurrentUser** .</span></span> <span data-ttu-id="23af4-197">As atualizações de módulo para **AllUsers** , `$env:ProgramFiles\PowerShell\Modules` , precisam de permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="23af4-197">Module updates for **AllUsers** , `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span> <span data-ttu-id="23af4-198">Atualizações de módulo para **CurrentUser** , `$home\Documents\PowerShell\Modules` , não precisam de permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="23af4-198">Module updates for **CurrentUser** , `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span>

<span data-ttu-id="23af4-199">`Update-Module` é executado no PowerShell 3,0 ou versões posteriores do PowerShell, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="23af4-199">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="23af4-200">Se o módulo especificado com o parâmetro **Name** não tiver sido instalado usando o `Install-Module` , ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="23af4-200">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="23af4-201">Você só pode executar `Update-Module` em módulos que você instalou da galeria online executando `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="23af4-201">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="23af4-202">Se `Update-Module` as tentativas de atualizar os binários que estão em uso, `Update-Module` o retorna um erro que identifica os processos de problema.</span><span class="sxs-lookup"><span data-stu-id="23af4-202">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="23af4-203">O usuário é informado para tentar novamente `Update-Module` depois que os processos são interrompidos.</span><span class="sxs-lookup"><span data-stu-id="23af4-203">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="23af4-204">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="23af4-204">RELATED LINKS</span></span>

[<span data-ttu-id="23af4-205">Find-Module</span><span class="sxs-lookup"><span data-stu-id="23af4-205">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="23af4-206">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="23af4-206">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="23af4-207">Install-Module</span><span class="sxs-lookup"><span data-stu-id="23af4-207">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="23af4-208">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="23af4-208">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="23af4-209">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="23af4-209">Uninstall-Module</span></span>](Uninstall-Module.md)
