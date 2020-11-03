---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: 6a69108694d5ba614bb7f195004d2d37ac6de092
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194314"
---
# <span data-ttu-id="87224-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="87224-103">Get-InstalledScript</span></span>

## <span data-ttu-id="87224-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="87224-104">SYNOPSIS</span></span>
<span data-ttu-id="87224-105">Obtém um script instalado.</span><span class="sxs-lookup"><span data-stu-id="87224-105">Gets an installed script.</span></span>

## <span data-ttu-id="87224-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="87224-106">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="87224-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="87224-107">DESCRIPTION</span></span>

<span data-ttu-id="87224-108">O cmdlet **Get-InstalledScript** Obtém scripts instalados para escopos CurrentUser e AllUsers.</span><span class="sxs-lookup"><span data-stu-id="87224-108">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="87224-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="87224-109">EXAMPLES</span></span>

### <span data-ttu-id="87224-110">Exemplo 1: obter todos os scripts instalados</span><span class="sxs-lookup"><span data-stu-id="87224-110">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="87224-111">Este comando obtém todos os scripts instalados.</span><span class="sxs-lookup"><span data-stu-id="87224-111">This command gets all installed scripts.</span></span>

### <span data-ttu-id="87224-112">Exemplo 2: obter scripts instalados por nome</span><span class="sxs-lookup"><span data-stu-id="87224-112">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="87224-113">Esse comando obtém os scripts em que o nome começa com Required-Scri.</span><span class="sxs-lookup"><span data-stu-id="87224-113">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="87224-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="87224-114">PARAMETERS</span></span>

### <span data-ttu-id="87224-115">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="87224-115">-AllowPrerelease</span></span>

<span data-ttu-id="87224-116">Inclui nos scripts de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="87224-116">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="87224-117">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="87224-117">-MaximumVersion</span></span>

<span data-ttu-id="87224-118">Especifica a versão máxima ou mais recente de um script a ser obtida.</span><span class="sxs-lookup"><span data-stu-id="87224-118">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="87224-119">Os parâmetros *MaximumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="87224-119">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="87224-120">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="87224-120">-MinimumVersion</span></span>

<span data-ttu-id="87224-121">Especifica a versão mínima de um script a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="87224-121">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="87224-122">Os parâmetros *MinimumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="87224-122">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="87224-123">-Name</span><span class="sxs-lookup"><span data-stu-id="87224-123">-Name</span></span>

<span data-ttu-id="87224-124">Especifica uma matriz de nomes de scripts a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="87224-124">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="87224-125">Caracteres curinga são aceitos.</span><span class="sxs-lookup"><span data-stu-id="87224-125">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="87224-126">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="87224-126">-RequiredVersion</span></span>

<span data-ttu-id="87224-127">Especifica a versão exata de um script a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="87224-127">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="87224-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="87224-128">CommonParameters</span></span>

<span data-ttu-id="87224-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="87224-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="87224-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="87224-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="87224-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="87224-131">INPUTS</span></span>

### <span data-ttu-id="87224-132">System.String[]</span><span class="sxs-lookup"><span data-stu-id="87224-132">System.String[]</span></span>

### <span data-ttu-id="87224-133">System.String</span><span class="sxs-lookup"><span data-stu-id="87224-133">System.String</span></span>

## <span data-ttu-id="87224-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="87224-134">OUTPUTS</span></span>

### <span data-ttu-id="87224-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="87224-135">System.Object</span></span>

## <span data-ttu-id="87224-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="87224-136">NOTES</span></span>

## <span data-ttu-id="87224-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="87224-137">RELATED LINKS</span></span>

[<span data-ttu-id="87224-138">Install-Script</span><span class="sxs-lookup"><span data-stu-id="87224-138">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="87224-139">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="87224-139">Uninstall-Script</span></span>](Uninstall-Script.md)
