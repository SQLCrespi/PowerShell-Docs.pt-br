---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: fe5fc0feb34fda87dab987f33140992a346017a1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598234"
---
# <span data-ttu-id="5c1bd-102">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="5c1bd-102">Get-InstalledScript</span></span>

## <span data-ttu-id="5c1bd-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5c1bd-103">SYNOPSIS</span></span>
<span data-ttu-id="5c1bd-104">Obtém um script instalado.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-104">Gets an installed script.</span></span>

## <span data-ttu-id="5c1bd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c1bd-105">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="5c1bd-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c1bd-106">DESCRIPTION</span></span>

<span data-ttu-id="5c1bd-107">O cmdlet **Get-InstalledScript** Obtém scripts instalados para escopos CurrentUser e AllUsers.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-107">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="5c1bd-108">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5c1bd-108">EXAMPLES</span></span>

### <span data-ttu-id="5c1bd-109">Exemplo 1: obter todos os scripts instalados</span><span class="sxs-lookup"><span data-stu-id="5c1bd-109">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="5c1bd-110">Este comando obtém todos os scripts instalados.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-110">This command gets all installed scripts.</span></span>

### <span data-ttu-id="5c1bd-111">Exemplo 2: obter scripts instalados por nome</span><span class="sxs-lookup"><span data-stu-id="5c1bd-111">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="5c1bd-112">Esse comando obtém os scripts em que o nome começa com Required-Scri.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-112">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="5c1bd-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c1bd-113">PARAMETERS</span></span>

### <span data-ttu-id="5c1bd-114">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="5c1bd-114">-AllowPrerelease</span></span>

<span data-ttu-id="5c1bd-115">Inclui nos scripts de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-115">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="5c1bd-116">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="5c1bd-116">-MaximumVersion</span></span>

<span data-ttu-id="5c1bd-117">Especifica a versão máxima ou mais recente de um script a ser obtida.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-117">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="5c1bd-118">Os parâmetros *MaximumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-118">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="5c1bd-119">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="5c1bd-119">-MinimumVersion</span></span>

<span data-ttu-id="5c1bd-120">Especifica a versão mínima de um script a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-120">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="5c1bd-121">Os parâmetros *MinimumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-121">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="5c1bd-122">-Name</span><span class="sxs-lookup"><span data-stu-id="5c1bd-122">-Name</span></span>

<span data-ttu-id="5c1bd-123">Especifica uma matriz de nomes de scripts a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-123">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="5c1bd-124">Caracteres curinga são aceitos.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-124">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="5c1bd-125">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="5c1bd-125">-RequiredVersion</span></span>

<span data-ttu-id="5c1bd-126">Especifica a versão exata de um script a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-126">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="5c1bd-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5c1bd-127">CommonParameters</span></span>

<span data-ttu-id="5c1bd-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5c1bd-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c1bd-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5c1bd-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c1bd-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5c1bd-130">INPUTS</span></span>

### <span data-ttu-id="5c1bd-131">System.String[]</span><span class="sxs-lookup"><span data-stu-id="5c1bd-131">System.String[]</span></span>

### <span data-ttu-id="5c1bd-132">System.String</span><span class="sxs-lookup"><span data-stu-id="5c1bd-132">System.String</span></span>

## <span data-ttu-id="5c1bd-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5c1bd-133">OUTPUTS</span></span>

### <span data-ttu-id="5c1bd-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="5c1bd-134">System.Object</span></span>

## <span data-ttu-id="5c1bd-135">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5c1bd-135">NOTES</span></span>

## <span data-ttu-id="5c1bd-136">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5c1bd-136">RELATED LINKS</span></span>

[<span data-ttu-id="5c1bd-137">Install-Script</span><span class="sxs-lookup"><span data-stu-id="5c1bd-137">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="5c1bd-138">Desinstalar-script</span><span class="sxs-lookup"><span data-stu-id="5c1bd-138">Uninstall-Script</span></span>](Uninstall-Script.md)

