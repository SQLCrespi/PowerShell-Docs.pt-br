---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 812ff0b9ea57e2aa3ccb1f24656a94d4de9c641b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194446"
---
# <span data-ttu-id="994dd-103">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="994dd-103">Uninstall-Script</span></span>

## <span data-ttu-id="994dd-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="994dd-104">SYNOPSIS</span></span>
<span data-ttu-id="994dd-105">Desinstala um script.</span><span class="sxs-lookup"><span data-stu-id="994dd-105">Uninstalls a script.</span></span>

## <span data-ttu-id="994dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="994dd-106">SYNTAX</span></span>

### <span data-ttu-id="994dd-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="994dd-107">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="994dd-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="994dd-108">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="994dd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="994dd-109">DESCRIPTION</span></span>

<span data-ttu-id="994dd-110">O `Uninstall-Script` cmdlet desinstala um script especificado do computador local.</span><span class="sxs-lookup"><span data-stu-id="994dd-110">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="994dd-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="994dd-111">EXAMPLES</span></span>

### <span data-ttu-id="994dd-112">Exemplo 1: desinstalar um script</span><span class="sxs-lookup"><span data-stu-id="994dd-112">Example 1: Uninstall a script</span></span>

<span data-ttu-id="994dd-113">Este exemplo desinstala um script.</span><span class="sxs-lookup"><span data-stu-id="994dd-113">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="994dd-114">`Uninstall-Script` usa o parâmetro **Name** para especificar o script a ser desinstalado do computador local.</span><span class="sxs-lookup"><span data-stu-id="994dd-114">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="994dd-115">Exemplo 2: usar o pipeline para desinstalar um script</span><span class="sxs-lookup"><span data-stu-id="994dd-115">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="994dd-116">Neste exemplo, o pipeline é usado para desinstalar um script.</span><span class="sxs-lookup"><span data-stu-id="994dd-116">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="994dd-117">`Get-InstalledScript` usa o parâmetro **Name** para especificar o script.</span><span class="sxs-lookup"><span data-stu-id="994dd-117">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="994dd-118">O objeto é enviado ao pipeline para o `Uninstall-Script` e o script é desinstalado.</span><span class="sxs-lookup"><span data-stu-id="994dd-118">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="994dd-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="994dd-119">PARAMETERS</span></span>

### <span data-ttu-id="994dd-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="994dd-120">-AllowPrerelease</span></span>

<span data-ttu-id="994dd-121">Permite desinstalar um script marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="994dd-121">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="994dd-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="994dd-122">-Confirm</span></span>

<span data-ttu-id="994dd-123">Solicita a confirmação antes de executar `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="994dd-123">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="994dd-124">-Force</span><span class="sxs-lookup"><span data-stu-id="994dd-124">-Force</span></span>

<span data-ttu-id="994dd-125">Forças `Uninstall-Script` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="994dd-125">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="994dd-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="994dd-126">-InputObject</span></span>

<span data-ttu-id="994dd-127">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="994dd-127">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="994dd-128">Por exemplo, saída `Get-InstalledScript` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="994dd-128">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="994dd-129">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="994dd-129">-MaximumVersion</span></span>

<span data-ttu-id="994dd-130">Especifica a versão máxima ou mais recente do script a ser desinstalada.</span><span class="sxs-lookup"><span data-stu-id="994dd-130">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="994dd-131">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="994dd-131">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="994dd-132">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="994dd-132">-MinimumVersion</span></span>

<span data-ttu-id="994dd-133">Especifica a versão mínima do script a ser desinstalado.</span><span class="sxs-lookup"><span data-stu-id="994dd-133">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="994dd-134">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="994dd-134">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="994dd-135">-Name</span><span class="sxs-lookup"><span data-stu-id="994dd-135">-Name</span></span>

<span data-ttu-id="994dd-136">Especifica uma matriz de nomes de script a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="994dd-136">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="994dd-137">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="994dd-137">-RequiredVersion</span></span>

<span data-ttu-id="994dd-138">Especifica o número de versão exato do script a ser desinstalado.</span><span class="sxs-lookup"><span data-stu-id="994dd-138">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="994dd-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="994dd-139">-WhatIf</span></span>

<span data-ttu-id="994dd-140">Mostra o que aconteceria se `Uninstall-Script` for executado.</span><span class="sxs-lookup"><span data-stu-id="994dd-140">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="994dd-141">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="994dd-141">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="994dd-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="994dd-142">CommonParameters</span></span>

<span data-ttu-id="994dd-143">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="994dd-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="994dd-144">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="994dd-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="994dd-145">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="994dd-145">INPUTS</span></span>

### <span data-ttu-id="994dd-146">System.String[]</span><span class="sxs-lookup"><span data-stu-id="994dd-146">System.String[]</span></span>

### <span data-ttu-id="994dd-147">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="994dd-147">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="994dd-148">System.String</span><span class="sxs-lookup"><span data-stu-id="994dd-148">System.String</span></span>

## <span data-ttu-id="994dd-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="994dd-149">OUTPUTS</span></span>

### <span data-ttu-id="994dd-150">System.Object</span><span class="sxs-lookup"><span data-stu-id="994dd-150">System.Object</span></span>

## <span data-ttu-id="994dd-151">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="994dd-151">NOTES</span></span>

## <span data-ttu-id="994dd-152">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="994dd-152">RELATED LINKS</span></span>

[<span data-ttu-id="994dd-153">Find-Script</span><span class="sxs-lookup"><span data-stu-id="994dd-153">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="994dd-154">Install-Script</span><span class="sxs-lookup"><span data-stu-id="994dd-154">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="994dd-155">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="994dd-155">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="994dd-156">Save-Script</span><span class="sxs-lookup"><span data-stu-id="994dd-156">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="994dd-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="994dd-157">Update-Script</span></span>](Update-Script.md)
