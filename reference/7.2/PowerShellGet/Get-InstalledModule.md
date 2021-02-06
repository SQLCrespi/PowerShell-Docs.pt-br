---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 33621a89f846ca277c21aaf0ad8cd788b428da33
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595989"
---
# <span data-ttu-id="8bcd7-102">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="8bcd7-102">Get-InstalledModule</span></span>

## <span data-ttu-id="8bcd7-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8bcd7-103">SYNOPSIS</span></span>
<span data-ttu-id="8bcd7-104">Obtém uma lista de módulos no computador que foram instalados pelo PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-104">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="8bcd7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8bcd7-105">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="8bcd7-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8bcd7-106">DESCRIPTION</span></span>

<span data-ttu-id="8bcd7-107">O `Get-InstalledModule` cmdlet obtém os módulos do PowerShell que estão instalados em um computador usando o PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-107">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="8bcd7-108">Para ver todos os módulos instalados no sistema, use o `Get-Module -ListAvailable` comando.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-108">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="8bcd7-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8bcd7-109">EXAMPLES</span></span>

### <span data-ttu-id="8bcd7-110">Exemplo 1: obter todos os módulos instalados</span><span class="sxs-lookup"><span data-stu-id="8bcd7-110">Example 1: Get all installed modules</span></span>

```powershell
Get-InstalledModule
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
2.0.0      PSGTEST-UploadMultipleVersionOfP... Module     GalleryINT     Module for DAC functionality
1.3.5      AzureAutomationDebug                Module     PSGallery      Module for debugging Azure Automation runbooks, emulating AA native cmdlets
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="8bcd7-111">Este comando obtém todos os módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-111">This command gets all installed modules.</span></span>

### <span data-ttu-id="8bcd7-112">Exemplo 2: obter versões específicas de um módulo</span><span class="sxs-lookup"><span data-stu-id="8bcd7-112">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="8bcd7-113">Este comando obtém as versões do módulo AzureRM. Automation da versão 1,0 até a versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-113">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="8bcd7-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8bcd7-114">PARAMETERS</span></span>

### <span data-ttu-id="8bcd7-115">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="8bcd7-115">-AllowPrerelease</span></span>

<span data-ttu-id="8bcd7-116">Inclui nos módulos de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-116">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="8bcd7-117">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="8bcd7-117">-AllVersions</span></span>

<span data-ttu-id="8bcd7-118">Indica que você deseja obter todas as versões disponíveis de um módulo.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-118">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="8bcd7-119">Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="8bcd7-119">You cannot use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="8bcd7-120">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8bcd7-120">-MaximumVersion</span></span>

<span data-ttu-id="8bcd7-121">Especifica a versão máxima ou mais recente de um módulo a ser obtida.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-121">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="8bcd7-122">Os parâmetros **MaximumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-122">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="8bcd7-123">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8bcd7-123">-MinimumVersion</span></span>

<span data-ttu-id="8bcd7-124">Especifica a versão mínima de um único módulo a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-124">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="8bcd7-125">Os parâmetros **MinimumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-125">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="8bcd7-126">-Name</span><span class="sxs-lookup"><span data-stu-id="8bcd7-126">-Name</span></span>

<span data-ttu-id="8bcd7-127">Especifica uma matriz de nomes de módulos a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-127">Specifies an array of names of modules to get.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8bcd7-128">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8bcd7-128">-RequiredVersion</span></span>

<span data-ttu-id="8bcd7-129">Especifica a versão exata de um módulo a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-129">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="8bcd7-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8bcd7-130">CommonParameters</span></span>

<span data-ttu-id="8bcd7-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8bcd7-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8bcd7-132">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8bcd7-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8bcd7-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8bcd7-133">INPUTS</span></span>

### <span data-ttu-id="8bcd7-134">System.String[]</span><span class="sxs-lookup"><span data-stu-id="8bcd7-134">System.String[]</span></span>

### <span data-ttu-id="8bcd7-135">System.String</span><span class="sxs-lookup"><span data-stu-id="8bcd7-135">System.String</span></span>

## <span data-ttu-id="8bcd7-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8bcd7-136">OUTPUTS</span></span>

### <span data-ttu-id="8bcd7-137">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="8bcd7-137">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="8bcd7-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8bcd7-138">NOTES</span></span>

## <span data-ttu-id="8bcd7-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8bcd7-139">RELATED LINKS</span></span>

