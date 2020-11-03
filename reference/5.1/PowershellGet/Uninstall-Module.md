---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 72cdbd26a909e4be33fa32f67019e4c1f02ce3de
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194110"
---
# <span data-ttu-id="238dd-103">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="238dd-103">Uninstall-Module</span></span>

## <span data-ttu-id="238dd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="238dd-104">SYNOPSIS</span></span>
<span data-ttu-id="238dd-105">Desinstala um módulo.</span><span class="sxs-lookup"><span data-stu-id="238dd-105">Uninstalls a module.</span></span>

## <span data-ttu-id="238dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="238dd-106">SYNTAX</span></span>

### <span data-ttu-id="238dd-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="238dd-107">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="238dd-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="238dd-108">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="238dd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="238dd-109">DESCRIPTION</span></span>

<span data-ttu-id="238dd-110">O `Uninstall-Module` cmdlet desinstala um módulo especificado do computador local.</span><span class="sxs-lookup"><span data-stu-id="238dd-110">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="238dd-111">Você não poderá desinstalar um módulo se ele tiver outros módulos como dependências.</span><span class="sxs-lookup"><span data-stu-id="238dd-111">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="238dd-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="238dd-112">EXAMPLES</span></span>

### <span data-ttu-id="238dd-113">Exemplo 1: desinstalar um módulo</span><span class="sxs-lookup"><span data-stu-id="238dd-113">Example 1: Uninstall a module</span></span>

<span data-ttu-id="238dd-114">Este exemplo desinstala um módulo.</span><span class="sxs-lookup"><span data-stu-id="238dd-114">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="238dd-115">`Uninstall-Module` usa o parâmetro **Name** para especificar o módulo a ser desinstalado do computador local.</span><span class="sxs-lookup"><span data-stu-id="238dd-115">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="238dd-116">Exemplo 2: usar o pipeline para desinstalar um módulo</span><span class="sxs-lookup"><span data-stu-id="238dd-116">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="238dd-117">Neste exemplo, o pipeline é usado para desinstalar um módulo.</span><span class="sxs-lookup"><span data-stu-id="238dd-117">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="238dd-118">`Get-InstalledModule` usa o parâmetro **Name** para especificar o módulo.</span><span class="sxs-lookup"><span data-stu-id="238dd-118">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="238dd-119">O objeto é enviado ao pipeline para `Uninstall-Module` e é desinstalado.</span><span class="sxs-lookup"><span data-stu-id="238dd-119">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="238dd-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="238dd-120">PARAMETERS</span></span>

### <span data-ttu-id="238dd-121">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="238dd-121">-AllowPrerelease</span></span>

<span data-ttu-id="238dd-122">Permite desinstalar um módulo marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="238dd-122">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="238dd-123">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="238dd-123">-AllVersions</span></span>

<span data-ttu-id="238dd-124">Especifica que você deseja incluir todas as versões disponíveis de um módulo.</span><span class="sxs-lookup"><span data-stu-id="238dd-124">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="238dd-125">Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion** , **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="238dd-125">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="238dd-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="238dd-126">-Confirm</span></span>

<span data-ttu-id="238dd-127">Solicita a confirmação antes de executar o `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="238dd-127">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="238dd-128">-Force</span><span class="sxs-lookup"><span data-stu-id="238dd-128">-Force</span></span>

<span data-ttu-id="238dd-129">Forças `Uninstall-Module` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="238dd-129">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="238dd-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="238dd-130">-InputObject</span></span>

<span data-ttu-id="238dd-131">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="238dd-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="238dd-132">Por exemplo, saída `Get-InstalledModule` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="238dd-132">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="238dd-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="238dd-133">-MaximumVersion</span></span>

<span data-ttu-id="238dd-134">Especifica a versão máxima ou mais recente do módulo a ser desinstalada.</span><span class="sxs-lookup"><span data-stu-id="238dd-134">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="238dd-135">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="238dd-135">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="238dd-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="238dd-136">-MinimumVersion</span></span>

<span data-ttu-id="238dd-137">Especifica a versão mínima do módulo a ser desinstalada.</span><span class="sxs-lookup"><span data-stu-id="238dd-137">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="238dd-138">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="238dd-138">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="238dd-139">-Name</span><span class="sxs-lookup"><span data-stu-id="238dd-139">-Name</span></span>

<span data-ttu-id="238dd-140">Especifica uma matriz de nomes de módulo a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="238dd-140">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="238dd-141">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="238dd-141">-RequiredVersion</span></span>

<span data-ttu-id="238dd-142">Especifica o número de versão exato do módulo a ser desinstalado.</span><span class="sxs-lookup"><span data-stu-id="238dd-142">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="238dd-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="238dd-143">-WhatIf</span></span>

<span data-ttu-id="238dd-144">Mostra o que aconteceria se `Uninstall-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="238dd-144">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="238dd-145">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="238dd-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="238dd-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="238dd-146">CommonParameters</span></span>

<span data-ttu-id="238dd-147">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="238dd-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="238dd-148">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="238dd-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="238dd-149">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="238dd-149">INPUTS</span></span>

### <span data-ttu-id="238dd-150">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="238dd-150">PSRepositoryItemInfo</span></span>

<span data-ttu-id="238dd-151">`Uninstall-Module` aceita objetos **PSRepositoryItemInfo** do pipeline.</span><span class="sxs-lookup"><span data-stu-id="238dd-151">`Uninstall-Module` accepts **PSRepositoryItemInfo** objects from the pipeline.</span></span>

## <span data-ttu-id="238dd-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="238dd-152">OUTPUTS</span></span>

## <span data-ttu-id="238dd-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="238dd-153">NOTES</span></span>

## <span data-ttu-id="238dd-154">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="238dd-154">RELATED LINKS</span></span>

[<span data-ttu-id="238dd-155">Find-Module</span><span class="sxs-lookup"><span data-stu-id="238dd-155">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="238dd-156">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="238dd-156">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="238dd-157">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="238dd-157">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="238dd-158">Save-Module</span><span class="sxs-lookup"><span data-stu-id="238dd-158">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="238dd-159">Update-Module</span><span class="sxs-lookup"><span data-stu-id="238dd-159">Update-Module</span></span>](Update-Module.md)
