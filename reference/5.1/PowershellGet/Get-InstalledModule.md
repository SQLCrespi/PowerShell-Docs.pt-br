---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: e894e2f71e0a76badd05b86b42903d49aab4af0b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193617"
---
# <span data-ttu-id="57948-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="57948-103">Get-InstalledModule</span></span>

## <span data-ttu-id="57948-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="57948-104">SYNOPSIS</span></span>
<span data-ttu-id="57948-105">Obtém uma lista de módulos no computador que foram instalados pelo PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="57948-105">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="57948-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57948-106">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="57948-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="57948-107">DESCRIPTION</span></span>

<span data-ttu-id="57948-108">O `Get-InstalledModule` cmdlet obtém os módulos do PowerShell que estão instalados em um computador usando o PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="57948-108">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="57948-109">Para ver todos os módulos instalados no sistema, use o `Get-Module -ListAvailable` comando.</span><span class="sxs-lookup"><span data-stu-id="57948-109">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="57948-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="57948-110">EXAMPLES</span></span>

### <span data-ttu-id="57948-111">Exemplo 1: obter todos os módulos instalados</span><span class="sxs-lookup"><span data-stu-id="57948-111">Example 1: Get all installed modules</span></span>

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

<span data-ttu-id="57948-112">Este comando obtém todos os módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="57948-112">This command gets all installed modules.</span></span>

### <span data-ttu-id="57948-113">Exemplo 2: obter versões específicas de um módulo</span><span class="sxs-lookup"><span data-stu-id="57948-113">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="57948-114">Este comando obtém as versões do módulo AzureRM. Automation da versão 1,0 até a versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="57948-114">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="57948-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="57948-115">PARAMETERS</span></span>

### <span data-ttu-id="57948-116">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="57948-116">-AllowPrerelease</span></span>

<span data-ttu-id="57948-117">Inclui nos módulos de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="57948-117">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="57948-118">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="57948-118">-AllVersions</span></span>

<span data-ttu-id="57948-119">Indica que você deseja obter todas as versões disponíveis de um módulo.</span><span class="sxs-lookup"><span data-stu-id="57948-119">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="57948-120">Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion** , **MaximumVersion** ou **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="57948-120">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="57948-121">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="57948-121">-MaximumVersion</span></span>

<span data-ttu-id="57948-122">Especifica a versão máxima ou mais recente de um módulo a ser obtida.</span><span class="sxs-lookup"><span data-stu-id="57948-122">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="57948-123">Os parâmetros **MaximumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="57948-123">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="57948-124">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="57948-124">-MinimumVersion</span></span>

<span data-ttu-id="57948-125">Especifica a versão mínima de um único módulo a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="57948-125">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="57948-126">Os parâmetros **MinimumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="57948-126">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="57948-127">-Name</span><span class="sxs-lookup"><span data-stu-id="57948-127">-Name</span></span>

<span data-ttu-id="57948-128">Especifica uma matriz de nomes de módulos a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="57948-128">Specifies an array of names of modules to get.</span></span>

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

### <span data-ttu-id="57948-129">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="57948-129">-RequiredVersion</span></span>

<span data-ttu-id="57948-130">Especifica a versão exata de um módulo a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="57948-130">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="57948-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="57948-131">CommonParameters</span></span>

<span data-ttu-id="57948-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="57948-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="57948-133">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="57948-133">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="57948-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="57948-134">INPUTS</span></span>

## <span data-ttu-id="57948-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="57948-135">OUTPUTS</span></span>

### <span data-ttu-id="57948-136">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="57948-136">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="57948-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="57948-137">NOTES</span></span>

## <span data-ttu-id="57948-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="57948-138">RELATED LINKS</span></span>
