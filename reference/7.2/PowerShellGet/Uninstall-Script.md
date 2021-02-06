---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 2cd8b51e1d4ef11a0a5f9e3542ff89e094854d8c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597633"
---
# <span data-ttu-id="d79be-102">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="d79be-102">Uninstall-Script</span></span>

## <span data-ttu-id="d79be-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d79be-103">SYNOPSIS</span></span>
<span data-ttu-id="d79be-104">Desinstala um script.</span><span class="sxs-lookup"><span data-stu-id="d79be-104">Uninstalls a script.</span></span>

## <span data-ttu-id="d79be-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d79be-105">SYNTAX</span></span>

### <span data-ttu-id="d79be-106">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="d79be-106">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d79be-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="d79be-107">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d79be-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d79be-108">DESCRIPTION</span></span>

<span data-ttu-id="d79be-109">O `Uninstall-Script` cmdlet desinstala um script especificado do computador local.</span><span class="sxs-lookup"><span data-stu-id="d79be-109">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="d79be-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d79be-110">EXAMPLES</span></span>

### <span data-ttu-id="d79be-111">Exemplo 1: desinstalar um script</span><span class="sxs-lookup"><span data-stu-id="d79be-111">Example 1: Uninstall a script</span></span>

<span data-ttu-id="d79be-112">Este exemplo desinstala um script.</span><span class="sxs-lookup"><span data-stu-id="d79be-112">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="d79be-113">`Uninstall-Script` usa o parâmetro **Name** para especificar o script a ser desinstalado do computador local.</span><span class="sxs-lookup"><span data-stu-id="d79be-113">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="d79be-114">Exemplo 2: usar o pipeline para desinstalar um script</span><span class="sxs-lookup"><span data-stu-id="d79be-114">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="d79be-115">Neste exemplo, o pipeline é usado para desinstalar um script.</span><span class="sxs-lookup"><span data-stu-id="d79be-115">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="d79be-116">`Get-InstalledScript` usa o parâmetro **Name** para especificar o script.</span><span class="sxs-lookup"><span data-stu-id="d79be-116">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="d79be-117">O objeto é enviado ao pipeline para o `Uninstall-Script` e o script é desinstalado.</span><span class="sxs-lookup"><span data-stu-id="d79be-117">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="d79be-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d79be-118">PARAMETERS</span></span>

### <span data-ttu-id="d79be-119">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="d79be-119">-AllowPrerelease</span></span>

<span data-ttu-id="d79be-120">Permite desinstalar um script marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="d79be-120">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="d79be-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d79be-121">-Confirm</span></span>

<span data-ttu-id="d79be-122">Solicita a confirmação antes de executar `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="d79be-122">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="d79be-123">-Force</span><span class="sxs-lookup"><span data-stu-id="d79be-123">-Force</span></span>

<span data-ttu-id="d79be-124">Forças `Uninstall-Script` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="d79be-124">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d79be-125">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d79be-125">-InputObject</span></span>

<span data-ttu-id="d79be-126">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="d79be-126">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="d79be-127">Por exemplo, saída `Get-InstalledScript` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="d79be-127">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="d79be-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d79be-128">-MaximumVersion</span></span>

<span data-ttu-id="d79be-129">Especifica a versão máxima ou mais recente do script a ser desinstalada.</span><span class="sxs-lookup"><span data-stu-id="d79be-129">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="d79be-130">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="d79be-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="d79be-131">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d79be-131">-MinimumVersion</span></span>

<span data-ttu-id="d79be-132">Especifica a versão mínima do script a ser desinstalado.</span><span class="sxs-lookup"><span data-stu-id="d79be-132">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="d79be-133">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="d79be-133">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="d79be-134">-Name</span><span class="sxs-lookup"><span data-stu-id="d79be-134">-Name</span></span>

<span data-ttu-id="d79be-135">Especifica uma matriz de nomes de script a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="d79be-135">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="d79be-136">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="d79be-136">-RequiredVersion</span></span>

<span data-ttu-id="d79be-137">Especifica o número de versão exato do script a ser desinstalado.</span><span class="sxs-lookup"><span data-stu-id="d79be-137">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="d79be-138">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d79be-138">-WhatIf</span></span>

<span data-ttu-id="d79be-139">Mostra o que aconteceria se `Uninstall-Script` for executado.</span><span class="sxs-lookup"><span data-stu-id="d79be-139">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="d79be-140">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d79be-140">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="d79be-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d79be-141">CommonParameters</span></span>

<span data-ttu-id="d79be-142">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d79be-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d79be-143">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d79be-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d79be-144">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d79be-144">INPUTS</span></span>

### <span data-ttu-id="d79be-145">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d79be-145">System.String[]</span></span>

### <span data-ttu-id="d79be-146">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="d79be-146">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="d79be-147">System.String</span><span class="sxs-lookup"><span data-stu-id="d79be-147">System.String</span></span>

## <span data-ttu-id="d79be-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d79be-148">OUTPUTS</span></span>

### <span data-ttu-id="d79be-149">System.Object</span><span class="sxs-lookup"><span data-stu-id="d79be-149">System.Object</span></span>

## <span data-ttu-id="d79be-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d79be-150">NOTES</span></span>

## <span data-ttu-id="d79be-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d79be-151">RELATED LINKS</span></span>

[<span data-ttu-id="d79be-152">Find-Script</span><span class="sxs-lookup"><span data-stu-id="d79be-152">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="d79be-153">Install-Script</span><span class="sxs-lookup"><span data-stu-id="d79be-153">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="d79be-154">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="d79be-154">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="d79be-155">Save-Script</span><span class="sxs-lookup"><span data-stu-id="d79be-155">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="d79be-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="d79be-156">Update-Script</span></span>](Update-Script.md)

