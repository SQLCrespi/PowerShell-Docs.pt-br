---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: e7ce0f2bcd1ece0bb737aea1297641c37337f3e5
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99598639"
---
# <span data-ttu-id="e9f17-102">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="e9f17-102">Clear-RecycleBin</span></span>

## <span data-ttu-id="e9f17-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e9f17-103">SYNOPSIS</span></span>
<span data-ttu-id="e9f17-104">Limpa o conteúdo de uma lixeira.</span><span class="sxs-lookup"><span data-stu-id="e9f17-104">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="e9f17-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e9f17-105">SYNTAX</span></span>

### <span data-ttu-id="e9f17-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="e9f17-106">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e9f17-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e9f17-107">DESCRIPTION</span></span>

<span data-ttu-id="e9f17-108">O `Clear-RecycleBin` cmdlet exclui o conteúdo da lixeira de um computador.</span><span class="sxs-lookup"><span data-stu-id="e9f17-108">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="e9f17-109">Essa ação é como usar a **Lixeira vazia** do Windows.</span><span class="sxs-lookup"><span data-stu-id="e9f17-109">This action is like using Windows **Empty Recycle Bin**.</span></span>

<span data-ttu-id="e9f17-110">Esse cmdlet foi adicionado novamente no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="e9f17-110">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="e9f17-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e9f17-111">EXAMPLES</span></span>

### <span data-ttu-id="e9f17-112">1: limpar todas as lixeiras</span><span class="sxs-lookup"><span data-stu-id="e9f17-112">1: Clear all recycle bins</span></span>

<span data-ttu-id="e9f17-113">Neste exemplo, todas as lixeiras do computador local são limpas.</span><span class="sxs-lookup"><span data-stu-id="e9f17-113">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="e9f17-114">`Clear-RecycleBin` solicita ao usuário a confirmação para limpar todas as lixeiras no computador local.</span><span class="sxs-lookup"><span data-stu-id="e9f17-114">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="e9f17-115">2: limpar uma lixeira especificada</span><span class="sxs-lookup"><span data-stu-id="e9f17-115">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="e9f17-116">Este exemplo limpa a lixeira para uma letra de unidade especificada.</span><span class="sxs-lookup"><span data-stu-id="e9f17-116">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="e9f17-117">`Clear-RecycleBin` usa o parâmetro **DriveLetter** para especificar a lixeira no volume **C** .</span><span class="sxs-lookup"><span data-stu-id="e9f17-117">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="e9f17-118">O usuário receberá uma solicitação de confirmação para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="e9f17-118">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="e9f17-119">3: limpar todas as lixeiras sem confirmação</span><span class="sxs-lookup"><span data-stu-id="e9f17-119">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="e9f17-120">Este exemplo não solicita confirmação para limpar os compartimentos da lixeira do computador local.</span><span class="sxs-lookup"><span data-stu-id="e9f17-120">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="e9f17-121">`Clear-RecycleBin` usa o parâmetro **Force** e não solicita ao usuário a confirmação para limpar todas as lixeiras no computador local.</span><span class="sxs-lookup"><span data-stu-id="e9f17-121">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="e9f17-122">Uma alternativa é substituir `-Force` por `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="e9f17-122">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="e9f17-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e9f17-123">PARAMETERS</span></span>

### <span data-ttu-id="e9f17-124">-DriveLetter</span><span class="sxs-lookup"><span data-stu-id="e9f17-124">-DriveLetter</span></span>

<span data-ttu-id="e9f17-125">Especifica a lixeira a ser desmarcada para uma única letra de unidade ou uma matriz de letras de unidade.</span><span class="sxs-lookup"><span data-stu-id="e9f17-125">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="e9f17-126">-Force</span><span class="sxs-lookup"><span data-stu-id="e9f17-126">-Force</span></span>

<span data-ttu-id="e9f17-127">Especifica que o usuário não é solicitado a confirmar para limpar uma lixeira.</span><span class="sxs-lookup"><span data-stu-id="e9f17-127">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span> <span data-ttu-id="e9f17-128">O parâmetro **Force** também substitui os parâmetros **WhatIf** e **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="e9f17-128">The **Force** parameter also overrides the **WhatIf** and **Confirm** parameters.</span></span>

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

### <span data-ttu-id="e9f17-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e9f17-129">-Confirm</span></span>

<span data-ttu-id="e9f17-130">Solicita a confirmação do usuário antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e9f17-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="e9f17-131">O usuário será solicitado a confirmar, mesmo que o parâmetro **Confirm** não seja especificado.</span><span class="sxs-lookup"><span data-stu-id="e9f17-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="e9f17-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e9f17-132">-WhatIf</span></span>

<span data-ttu-id="e9f17-133">Mostra o que aconteceria se `Clear-RecycleBin` for executado.</span><span class="sxs-lookup"><span data-stu-id="e9f17-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="e9f17-134">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e9f17-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e9f17-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e9f17-135">CommonParameters</span></span>

<span data-ttu-id="e9f17-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e9f17-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e9f17-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e9f17-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e9f17-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e9f17-138">INPUTS</span></span>

## <span data-ttu-id="e9f17-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e9f17-139">OUTPUTS</span></span>

### <span data-ttu-id="e9f17-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e9f17-140">None</span></span>

## <span data-ttu-id="e9f17-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e9f17-141">NOTES</span></span>

<span data-ttu-id="e9f17-142">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="e9f17-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="e9f17-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e9f17-143">RELATED LINKS</span></span>
