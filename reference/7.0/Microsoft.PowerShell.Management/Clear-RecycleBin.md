---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 85e4ac857135a6df8215dcfe415057dd8aacde86
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192913"
---
# <span data-ttu-id="6a150-103">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="6a150-103">Clear-RecycleBin</span></span>

## <span data-ttu-id="6a150-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6a150-104">SYNOPSIS</span></span>
<span data-ttu-id="6a150-105">Limpa o conteúdo de uma lixeira.</span><span class="sxs-lookup"><span data-stu-id="6a150-105">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="6a150-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a150-106">SYNTAX</span></span>

### <span data-ttu-id="6a150-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="6a150-107">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6a150-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6a150-108">DESCRIPTION</span></span>

<span data-ttu-id="6a150-109">O `Clear-RecycleBin` cmdlet exclui o conteúdo da lixeira de um computador.</span><span class="sxs-lookup"><span data-stu-id="6a150-109">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="6a150-110">Essa ação é como usar a **Lixeira vazia** do Windows.</span><span class="sxs-lookup"><span data-stu-id="6a150-110">This action is like using Windows **Empty Recycle Bin** .</span></span>

<span data-ttu-id="6a150-111">Esse cmdlet foi adicionado novamente no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="6a150-111">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="6a150-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6a150-112">EXAMPLES</span></span>

### <span data-ttu-id="6a150-113">1: limpar todas as lixeiras</span><span class="sxs-lookup"><span data-stu-id="6a150-113">1: Clear all recycle bins</span></span>

<span data-ttu-id="6a150-114">Neste exemplo, todas as lixeiras do computador local são limpas.</span><span class="sxs-lookup"><span data-stu-id="6a150-114">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="6a150-115">`Clear-RecycleBin` solicita ao usuário a confirmação para limpar todas as lixeiras no computador local.</span><span class="sxs-lookup"><span data-stu-id="6a150-115">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="6a150-116">2: limpar uma lixeira especificada</span><span class="sxs-lookup"><span data-stu-id="6a150-116">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="6a150-117">Este exemplo limpa a lixeira para uma letra de unidade especificada.</span><span class="sxs-lookup"><span data-stu-id="6a150-117">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="6a150-118">`Clear-RecycleBin` usa o parâmetro **DriveLetter** para especificar a lixeira no volume **C** .</span><span class="sxs-lookup"><span data-stu-id="6a150-118">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="6a150-119">O usuário receberá uma solicitação de confirmação para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="6a150-119">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="6a150-120">3: limpar todas as lixeiras sem confirmação</span><span class="sxs-lookup"><span data-stu-id="6a150-120">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="6a150-121">Este exemplo não solicita confirmação para limpar os compartimentos da lixeira do computador local.</span><span class="sxs-lookup"><span data-stu-id="6a150-121">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="6a150-122">`Clear-RecycleBin` usa o parâmetro **Force** e não solicita ao usuário a confirmação para limpar todas as lixeiras no computador local.</span><span class="sxs-lookup"><span data-stu-id="6a150-122">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="6a150-123">Uma alternativa é substituir `-Force` por `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="6a150-123">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="6a150-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a150-124">PARAMETERS</span></span>

### <span data-ttu-id="6a150-125">-DriveLetter</span><span class="sxs-lookup"><span data-stu-id="6a150-125">-DriveLetter</span></span>

<span data-ttu-id="6a150-126">Especifica a lixeira a ser desmarcada para uma única letra de unidade ou uma matriz de letras de unidade.</span><span class="sxs-lookup"><span data-stu-id="6a150-126">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="6a150-127">-Force</span><span class="sxs-lookup"><span data-stu-id="6a150-127">-Force</span></span>

<span data-ttu-id="6a150-128">Especifica que o usuário não é solicitado a confirmar para limpar uma lixeira.</span><span class="sxs-lookup"><span data-stu-id="6a150-128">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span>

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

### <span data-ttu-id="6a150-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6a150-129">-Confirm</span></span>

<span data-ttu-id="6a150-130">Solicita a confirmação do usuário antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6a150-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="6a150-131">O usuário será solicitado a confirmar, mesmo que o parâmetro **Confirm** não seja especificado.</span><span class="sxs-lookup"><span data-stu-id="6a150-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="6a150-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6a150-132">-WhatIf</span></span>

<span data-ttu-id="6a150-133">Mostra o que aconteceria se `Clear-RecycleBin` for executado.</span><span class="sxs-lookup"><span data-stu-id="6a150-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="6a150-134">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="6a150-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="6a150-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6a150-135">CommonParameters</span></span>

<span data-ttu-id="6a150-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6a150-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a150-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6a150-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a150-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6a150-138">INPUTS</span></span>

## <span data-ttu-id="6a150-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6a150-139">OUTPUTS</span></span>

### <span data-ttu-id="6a150-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6a150-140">None</span></span>

## <span data-ttu-id="6a150-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6a150-141">NOTES</span></span>

## <span data-ttu-id="6a150-142">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6a150-142">RELATED LINKS</span></span>
