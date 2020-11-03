---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: a90ece844d5a271402537f17c601bf2e36b5ed8c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192875"
---
# <span data-ttu-id="bd502-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="bd502-103">Get-InstalledScript</span></span>

## <span data-ttu-id="bd502-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bd502-104">SYNOPSIS</span></span>
<span data-ttu-id="bd502-105">Obtém um script instalado.</span><span class="sxs-lookup"><span data-stu-id="bd502-105">Gets an installed script.</span></span>

## <span data-ttu-id="bd502-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd502-106">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="bd502-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd502-107">DESCRIPTION</span></span>

<span data-ttu-id="bd502-108">O cmdlet **Get-InstalledScript** Obtém scripts instalados para escopos CurrentUser e AllUsers.</span><span class="sxs-lookup"><span data-stu-id="bd502-108">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="bd502-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bd502-109">EXAMPLES</span></span>

### <span data-ttu-id="bd502-110">Exemplo 1: obter todos os scripts instalados</span><span class="sxs-lookup"><span data-stu-id="bd502-110">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="bd502-111">Este comando obtém todos os scripts instalados.</span><span class="sxs-lookup"><span data-stu-id="bd502-111">This command gets all installed scripts.</span></span>

### <span data-ttu-id="bd502-112">Exemplo 2: obter scripts instalados por nome</span><span class="sxs-lookup"><span data-stu-id="bd502-112">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="bd502-113">Esse comando obtém os scripts em que o nome começa com Required-Scri.</span><span class="sxs-lookup"><span data-stu-id="bd502-113">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="bd502-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd502-114">PARAMETERS</span></span>

### <span data-ttu-id="bd502-115">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="bd502-115">-AllowPrerelease</span></span>

<span data-ttu-id="bd502-116">Inclui nos scripts de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="bd502-116">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="bd502-117">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="bd502-117">-MaximumVersion</span></span>

<span data-ttu-id="bd502-118">Especifica a versão máxima ou mais recente de um script a ser obtida.</span><span class="sxs-lookup"><span data-stu-id="bd502-118">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="bd502-119">Os parâmetros *MaximumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="bd502-119">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="bd502-120">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="bd502-120">-MinimumVersion</span></span>

<span data-ttu-id="bd502-121">Especifica a versão mínima de um script a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="bd502-121">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="bd502-122">Os parâmetros *MinimumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="bd502-122">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="bd502-123">-Name</span><span class="sxs-lookup"><span data-stu-id="bd502-123">-Name</span></span>

<span data-ttu-id="bd502-124">Especifica uma matriz de nomes de scripts a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="bd502-124">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="bd502-125">Caracteres curinga são aceitos.</span><span class="sxs-lookup"><span data-stu-id="bd502-125">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="bd502-126">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="bd502-126">-RequiredVersion</span></span>

<span data-ttu-id="bd502-127">Especifica a versão exata de um script a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="bd502-127">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="bd502-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd502-128">CommonParameters</span></span>

<span data-ttu-id="bd502-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd502-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd502-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd502-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd502-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bd502-131">INPUTS</span></span>

### <span data-ttu-id="bd502-132">System.String[]</span><span class="sxs-lookup"><span data-stu-id="bd502-132">System.String[]</span></span>

### <span data-ttu-id="bd502-133">System.String</span><span class="sxs-lookup"><span data-stu-id="bd502-133">System.String</span></span>

## <span data-ttu-id="bd502-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bd502-134">OUTPUTS</span></span>

### <span data-ttu-id="bd502-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="bd502-135">System.Object</span></span>

## <span data-ttu-id="bd502-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bd502-136">NOTES</span></span>

## <span data-ttu-id="bd502-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bd502-137">RELATED LINKS</span></span>

[<span data-ttu-id="bd502-138">Install-Script</span><span class="sxs-lookup"><span data-stu-id="bd502-138">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="bd502-139">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="bd502-139">Uninstall-Script</span></span>](Uninstall-Script.md)
