---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: ee94ba7808cb364306826325cfbc3df2cf9834a5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892579"
---
# <span data-ttu-id="37948-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="37948-103">Update-Module</span></span>

## <span data-ttu-id="37948-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="37948-104">SYNOPSIS</span></span>
<span data-ttu-id="37948-105">Baixa e instala a versão mais recente dos módulos especificados de uma galeria online para o computador local.</span><span class="sxs-lookup"><span data-stu-id="37948-105">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="37948-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="37948-106">SYNTAX</span></span>

### <span data-ttu-id="37948-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="37948-107">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="37948-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37948-108">DESCRIPTION</span></span>

<span data-ttu-id="37948-109">O `Update-Module` cmdlet instala a versão mais recente de um módulo de uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="37948-109">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="37948-110">Você será solicitado a confirmar a atualização antes de ela ser instalada.</span><span class="sxs-lookup"><span data-stu-id="37948-110">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="37948-111">As atualizações são instaladas somente para módulos que foram instalados no computador local com o `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="37948-111">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="37948-112">`Update-Module` procura `$env:PSModulePath` módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="37948-112">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="37948-113">`Update-Module` sem parâmetros especificados atualiza todos os módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="37948-113">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="37948-114">Para especificar um módulo a ser atualizado, use o parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="37948-114">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="37948-115">Você pode atualizar para a versão específica de um módulo usando o parâmetro **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="37948-115">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="37948-116">Se um módulo instalado já for a versão mais recente, o módulo não será atualizado.</span><span class="sxs-lookup"><span data-stu-id="37948-116">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="37948-117">Se o módulo não for encontrado em `$env:PSModulePath` , um erro será exibido.</span><span class="sxs-lookup"><span data-stu-id="37948-117">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="37948-118">Para exibir os módulos instalados, use `Get-InstalledModule` .</span><span class="sxs-lookup"><span data-stu-id="37948-118">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="37948-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="37948-119">EXAMPLES</span></span>

### <span data-ttu-id="37948-120">Exemplo 1: atualizar todos os módulos</span><span class="sxs-lookup"><span data-stu-id="37948-120">Example 1: Update all modules</span></span>

<span data-ttu-id="37948-121">Este exemplo atualiza todos os módulos instalados para a versão mais recente em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="37948-121">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="37948-122">Exemplo 2: atualizar um módulo por nome</span><span class="sxs-lookup"><span data-stu-id="37948-122">Example 2: Update a module by name</span></span>

<span data-ttu-id="37948-123">Este exemplo atualiza um módulo específico para a versão mais recente em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="37948-123">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="37948-124">`Update-Module` usa o parâmetro **Name** para atualizar um módulo específico, **SpeculationControl**.</span><span class="sxs-lookup"><span data-stu-id="37948-124">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl**.</span></span>

### <span data-ttu-id="37948-125">Exemplo 3: exibir as execuções de Update-Module de hipóteses</span><span class="sxs-lookup"><span data-stu-id="37948-125">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="37948-126">Este exemplo faz um cenário de hipóteses para mostrar o que acontece se `Update-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="37948-126">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="37948-127">O comando não é executado.</span><span class="sxs-lookup"><span data-stu-id="37948-127">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="37948-128">`Update-Module` usa o parâmetro **WhatIf** exibir o que aconteceria se `Update-Module` fosse executado.</span><span class="sxs-lookup"><span data-stu-id="37948-128">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="37948-129">Exemplo 4: atualizar um módulo para uma versão especificada</span><span class="sxs-lookup"><span data-stu-id="37948-129">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="37948-130">Neste exemplo, um módulo é atualizado para uma versão específica.</span><span class="sxs-lookup"><span data-stu-id="37948-130">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="37948-131">A versão deve existir na galeria online ou um erro é exibido.</span><span class="sxs-lookup"><span data-stu-id="37948-131">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="37948-132">`Update-Module` usa o parâmetro **Name** para especificar o módulo, **SpeculationControl**.</span><span class="sxs-lookup"><span data-stu-id="37948-132">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="37948-133">O parâmetro **RequiredVersion** especifica a versão, **1.0.14**.</span><span class="sxs-lookup"><span data-stu-id="37948-133">The **RequiredVersion** parameter specifies the version, **1.0.14**.</span></span>

### <span data-ttu-id="37948-134">Exemplo 5: atualizar um módulo sem confirmação</span><span class="sxs-lookup"><span data-stu-id="37948-134">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="37948-135">Este exemplo não solicita confirmação para atualizar o módulo para a versão mais recente de uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="37948-135">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="37948-136">Se o módulo já estiver instalado, o parâmetro **Force** reinstalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="37948-136">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="37948-137">`Update-Module` usa o parâmetro **Name** para especificar o módulo, **SpeculationControl**.</span><span class="sxs-lookup"><span data-stu-id="37948-137">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="37948-138">O parâmetro **Force** atualiza o módulo sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="37948-138">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="37948-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="37948-139">PARAMETERS</span></span>

### <span data-ttu-id="37948-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="37948-140">-AcceptLicense</span></span>

<span data-ttu-id="37948-141">Aceite automaticamente o contrato de licença durante a instalação se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="37948-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="37948-142">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="37948-142">-AllowPrerelease</span></span>

<span data-ttu-id="37948-143">Permite que você atualize um módulo com o módulo mais recente marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="37948-143">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="37948-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="37948-144">-Confirm</span></span>

<span data-ttu-id="37948-145">Solicita a confirmação antes de executar `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="37948-145">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="37948-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="37948-146">-Credential</span></span>

<span data-ttu-id="37948-147">Especifica uma conta de usuário que tem permissão para atualizar um módulo.</span><span class="sxs-lookup"><span data-stu-id="37948-147">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="37948-148">-Force</span><span class="sxs-lookup"><span data-stu-id="37948-148">-Force</span></span>

<span data-ttu-id="37948-149">Força uma atualização de cada módulo especificado sem solicitar confirmação.</span><span class="sxs-lookup"><span data-stu-id="37948-149">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="37948-150">Se o módulo já estiver instalado, **Force** reinstalará o módulo.</span><span class="sxs-lookup"><span data-stu-id="37948-150">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="37948-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="37948-151">-MaximumVersion</span></span>

<span data-ttu-id="37948-152">Especifica a versão máxima de um único módulo a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="37948-152">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="37948-153">Você não poderá adicionar esse parâmetro se estiver tentando atualizar vários módulos.</span><span class="sxs-lookup"><span data-stu-id="37948-153">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="37948-154">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="37948-154">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="37948-155">-Name</span><span class="sxs-lookup"><span data-stu-id="37948-155">-Name</span></span>

<span data-ttu-id="37948-156">Especifica os nomes de um ou mais módulos a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="37948-156">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="37948-157">`Update-Module` pesquisa `$env:PSModulePath` os módulos a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="37948-157">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="37948-158">Se nenhuma correspondência for encontrada em `$env:PSModulePath` para o nome do módulo especificado, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="37948-158">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="37948-159">Caracteres curinga são aceitos em nomes de módulo.</span><span class="sxs-lookup"><span data-stu-id="37948-159">Wildcards are accepted in module names.</span></span> <span data-ttu-id="37948-160">Se você adicionar caracteres curinga ao nome especificado e nenhuma correspondência for encontrada, nenhum erro ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="37948-160">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="37948-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="37948-161">-PassThru</span></span>

<span data-ttu-id="37948-162">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="37948-162">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="37948-163">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="37948-163">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="37948-164">O suporte ao parâmetro **PassThru** foi adicionado no **PowerShellGet** 2.0.0</span><span class="sxs-lookup"><span data-stu-id="37948-164">The **PassThru** parameter support was added in **PowerShellGet** 2.0.0</span></span>

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

### <span data-ttu-id="37948-165">-Proxy</span><span class="sxs-lookup"><span data-stu-id="37948-165">-Proxy</span></span>

<span data-ttu-id="37948-166">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="37948-166">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="37948-167">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="37948-167">-ProxyCredential</span></span>

<span data-ttu-id="37948-168">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="37948-168">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="37948-169">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="37948-169">-RequiredVersion</span></span>

<span data-ttu-id="37948-170">Especifica a versão exata para a qual o módulo instalado existente será atualizado.</span><span class="sxs-lookup"><span data-stu-id="37948-170">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="37948-171">A versão especificada por **RequiredVersion** deve existir na galeria online ou um erro é exibido.</span><span class="sxs-lookup"><span data-stu-id="37948-171">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="37948-172">Se mais de um módulo for atualizado em um único comando, você não poderá usar **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="37948-172">If more than one module is updated in a single command, you can't use **RequiredVersion**.</span></span>

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

### <span data-ttu-id="37948-173">-Escopo</span><span class="sxs-lookup"><span data-stu-id="37948-173">-Scope</span></span>

<span data-ttu-id="37948-174">Especifica o escopo de instalação do módulo.</span><span class="sxs-lookup"><span data-stu-id="37948-174">Specifies the installation scope of the module.</span></span> <span data-ttu-id="37948-175">Os valores aceitáveis para esse parâmetro são **AllUsers** e **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="37948-175">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span> <span data-ttu-id="37948-176">Se o **escopo** não for especificado, a atualização será instalada no escopo **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="37948-176">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="37948-177">O escopo **AllUsers** requer permissões elevadas e instala módulos em um local que pode ser acessado por todos os usuários do computador:</span><span class="sxs-lookup"><span data-stu-id="37948-177">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="37948-178">O **CurrentUser** não requer permissões elevadas e instala módulos em um local acessível somente para o usuário atual do computador:</span><span class="sxs-lookup"><span data-stu-id="37948-178">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="37948-179">Quando nenhum **escopo** é definido, o padrão é definido com base na versão do PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="37948-179">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="37948-180">No PowerShellGet versões 2.0.0 e superiores, o padrão é **AllUsers** ao executar uma sessão elevada e **CurrentUser** para todos os outros.</span><span class="sxs-lookup"><span data-stu-id="37948-180">In PowerShellGet versions 2.0.0 and above, the default is **AllUsers** when running an elevated session and **CurrentUser** for all others.</span></span>
- <span data-ttu-id="37948-181">Nas versões do PowerShellGet 1. x, o padrão é **AllUsers**, o que requer elevação para a instalação.</span><span class="sxs-lookup"><span data-stu-id="37948-181">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

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

### <span data-ttu-id="37948-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="37948-182">-WhatIf</span></span>

<span data-ttu-id="37948-183">Mostra o que aconteceria se `Update-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="37948-183">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="37948-184">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="37948-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="37948-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="37948-185">CommonParameters</span></span>

<span data-ttu-id="37948-186">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="37948-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="37948-187">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="37948-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="37948-188">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="37948-188">INPUTS</span></span>

### <span data-ttu-id="37948-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="37948-189">System.String[]</span></span>

### <span data-ttu-id="37948-190">System.String</span><span class="sxs-lookup"><span data-stu-id="37948-190">System.String</span></span>

### <span data-ttu-id="37948-191">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="37948-191">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="37948-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="37948-192">System.Uri</span></span>

## <span data-ttu-id="37948-193">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="37948-193">OUTPUTS</span></span>

### <span data-ttu-id="37948-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="37948-194">System.Object</span></span>

## <span data-ttu-id="37948-195">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="37948-195">NOTES</span></span>

<span data-ttu-id="37948-196">Para o PowerShell 5,1 ou abaixo, o escopo padrão em uma sessão com privilégios elevados é **AllUsers** e, em uma sessão não elevada, **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="37948-196">For PowerShell 5.1 or below, the default scope in an elevated session is **AllUsers**, and in a non-elevated session, **CurrentUser**.</span></span> <span data-ttu-id="37948-197">As atualizações de módulo para **AllUsers**, `$env:ProgramFiles\PowerShell\Modules` , precisam de permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="37948-197">Module updates for **AllUsers**, `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span> <span data-ttu-id="37948-198">Atualizações de módulo para **CurrentUser**, `$home\Documents\PowerShell\Modules` , não precisam de permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="37948-198">Module updates for **CurrentUser**, `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37948-199">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="37948-199">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="37948-200">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-200">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="37948-201">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="37948-201">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="37948-202">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-202">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="37948-203">`Update-Module` é executado no PowerShell 3,0 ou versões posteriores do PowerShell, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="37948-203">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="37948-204">Se o módulo especificado com o parâmetro **Name** não tiver sido instalado usando o `Install-Module` , ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="37948-204">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="37948-205">Você só pode executar `Update-Module` em módulos que você instalou da galeria online executando `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="37948-205">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="37948-206">Se `Update-Module` as tentativas de atualizar os binários que estão em uso, `Update-Module` o retorna um erro que identifica os processos de problema.</span><span class="sxs-lookup"><span data-stu-id="37948-206">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="37948-207">O usuário é informado para tentar novamente `Update-Module` depois que os processos são interrompidos.</span><span class="sxs-lookup"><span data-stu-id="37948-207">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="37948-208">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="37948-208">RELATED LINKS</span></span>

[<span data-ttu-id="37948-209">Find-Module</span><span class="sxs-lookup"><span data-stu-id="37948-209">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="37948-210">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="37948-210">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="37948-211">Install-Module</span><span class="sxs-lookup"><span data-stu-id="37948-211">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="37948-212">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="37948-212">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="37948-213">Desinstalar-módulo</span><span class="sxs-lookup"><span data-stu-id="37948-213">Uninstall-Module</span></span>](Uninstall-Module.md)
