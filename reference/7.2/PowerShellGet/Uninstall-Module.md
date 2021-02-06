---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 0df911ad8b1f7b4516eef4a1c2b0180893013e3e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598447"
---
# <span data-ttu-id="2727a-102">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="2727a-102">Uninstall-Module</span></span>

## <span data-ttu-id="2727a-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2727a-103">SYNOPSIS</span></span>
<span data-ttu-id="2727a-104">Desinstala um módulo.</span><span class="sxs-lookup"><span data-stu-id="2727a-104">Uninstalls a module.</span></span>

## <span data-ttu-id="2727a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2727a-105">SYNTAX</span></span>

### <span data-ttu-id="2727a-106">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="2727a-106">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2727a-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="2727a-107">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2727a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2727a-108">DESCRIPTION</span></span>

<span data-ttu-id="2727a-109">O `Uninstall-Module` cmdlet desinstala um módulo especificado do computador local.</span><span class="sxs-lookup"><span data-stu-id="2727a-109">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="2727a-110">Você não poderá desinstalar um módulo se ele tiver outros módulos como dependências.</span><span class="sxs-lookup"><span data-stu-id="2727a-110">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="2727a-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2727a-111">EXAMPLES</span></span>

### <span data-ttu-id="2727a-112">Exemplo 1: desinstalar um módulo</span><span class="sxs-lookup"><span data-stu-id="2727a-112">Example 1: Uninstall a module</span></span>

<span data-ttu-id="2727a-113">Este exemplo desinstala um módulo.</span><span class="sxs-lookup"><span data-stu-id="2727a-113">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="2727a-114">`Uninstall-Module` usa o parâmetro **Name** para especificar o módulo a ser desinstalado do computador local.</span><span class="sxs-lookup"><span data-stu-id="2727a-114">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="2727a-115">Exemplo 2: usar o pipeline para desinstalar um módulo</span><span class="sxs-lookup"><span data-stu-id="2727a-115">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="2727a-116">Neste exemplo, o pipeline é usado para desinstalar um módulo.</span><span class="sxs-lookup"><span data-stu-id="2727a-116">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="2727a-117">`Get-InstalledModule` usa o parâmetro **Name** para especificar o módulo.</span><span class="sxs-lookup"><span data-stu-id="2727a-117">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="2727a-118">O objeto é enviado ao pipeline para `Uninstall-Module` e é desinstalado.</span><span class="sxs-lookup"><span data-stu-id="2727a-118">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="2727a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2727a-119">PARAMETERS</span></span>

### <span data-ttu-id="2727a-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="2727a-120">-AllowPrerelease</span></span>

<span data-ttu-id="2727a-121">Permite desinstalar um módulo marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="2727a-121">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="2727a-122">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="2727a-122">-AllVersions</span></span>

<span data-ttu-id="2727a-123">Especifica que você deseja incluir todas as versões disponíveis de um módulo.</span><span class="sxs-lookup"><span data-stu-id="2727a-123">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="2727a-124">Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="2727a-124">You can't use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="2727a-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2727a-125">-Confirm</span></span>

<span data-ttu-id="2727a-126">Solicita a confirmação antes de executar o `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="2727a-126">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="2727a-127">-Force</span><span class="sxs-lookup"><span data-stu-id="2727a-127">-Force</span></span>

<span data-ttu-id="2727a-128">Forças `Uninstall-Module` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="2727a-128">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2727a-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2727a-129">-InputObject</span></span>

<span data-ttu-id="2727a-130">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="2727a-130">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="2727a-131">Por exemplo, saída `Get-InstalledModule` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="2727a-131">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="2727a-132">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2727a-132">-MaximumVersion</span></span>

<span data-ttu-id="2727a-133">Especifica a versão máxima ou mais recente do módulo a ser desinstalada.</span><span class="sxs-lookup"><span data-stu-id="2727a-133">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="2727a-134">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2727a-134">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="2727a-135">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="2727a-135">-MinimumVersion</span></span>

<span data-ttu-id="2727a-136">Especifica a versão mínima do módulo a ser desinstalada.</span><span class="sxs-lookup"><span data-stu-id="2727a-136">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="2727a-137">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2727a-137">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="2727a-138">-Name</span><span class="sxs-lookup"><span data-stu-id="2727a-138">-Name</span></span>

<span data-ttu-id="2727a-139">Especifica uma matriz de nomes de módulo a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="2727a-139">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="2727a-140">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2727a-140">-RequiredVersion</span></span>

<span data-ttu-id="2727a-141">Especifica o número de versão exato do módulo a ser desinstalado.</span><span class="sxs-lookup"><span data-stu-id="2727a-141">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="2727a-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2727a-142">-WhatIf</span></span>

<span data-ttu-id="2727a-143">Mostra o que aconteceria se `Uninstall-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="2727a-143">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="2727a-144">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2727a-144">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2727a-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2727a-145">CommonParameters</span></span>

<span data-ttu-id="2727a-146">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2727a-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2727a-147">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2727a-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2727a-148">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2727a-148">INPUTS</span></span>

### <span data-ttu-id="2727a-149">System.String[]</span><span class="sxs-lookup"><span data-stu-id="2727a-149">System.String[]</span></span>

### <span data-ttu-id="2727a-150">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="2727a-150">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="2727a-151">System.String</span><span class="sxs-lookup"><span data-stu-id="2727a-151">System.String</span></span>

## <span data-ttu-id="2727a-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2727a-152">OUTPUTS</span></span>

### <span data-ttu-id="2727a-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="2727a-153">System.Object</span></span>

## <span data-ttu-id="2727a-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2727a-154">NOTES</span></span>

## <span data-ttu-id="2727a-155">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2727a-155">RELATED LINKS</span></span>

[<span data-ttu-id="2727a-156">Find-Module</span><span class="sxs-lookup"><span data-stu-id="2727a-156">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="2727a-157">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="2727a-157">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="2727a-158">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="2727a-158">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="2727a-159">Save-Module</span><span class="sxs-lookup"><span data-stu-id="2727a-159">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="2727a-160">Update-Module</span><span class="sxs-lookup"><span data-stu-id="2727a-160">Update-Module</span></span>](Update-Module.md)

