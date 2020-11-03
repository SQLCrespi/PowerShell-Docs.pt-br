---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: f3230c247296d5fd907d580e719cbbbc560183a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193933"
---
# <span data-ttu-id="60cfa-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="60cfa-103">Set-Clipboard</span></span>

## <span data-ttu-id="60cfa-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="60cfa-104">SYNOPSIS</span></span>
<span data-ttu-id="60cfa-105">Define a entrada atual da área de transferência do Windows.</span><span class="sxs-lookup"><span data-stu-id="60cfa-105">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="60cfa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="60cfa-106">SYNTAX</span></span>

### <span data-ttu-id="60cfa-107">Cadeia de caracteres (padrão)</span><span class="sxs-lookup"><span data-stu-id="60cfa-107">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="60cfa-108">Valor</span><span class="sxs-lookup"><span data-stu-id="60cfa-108">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="60cfa-109">Caminho</span><span class="sxs-lookup"><span data-stu-id="60cfa-109">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="60cfa-110">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="60cfa-110">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="60cfa-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="60cfa-111">DESCRIPTION</span></span>

<span data-ttu-id="60cfa-112">O `Set-Clipboard` cmdlet define a entrada atual da área de transferência do Windows.</span><span class="sxs-lookup"><span data-stu-id="60cfa-112">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="60cfa-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="60cfa-113">EXAMPLES</span></span>

### <span data-ttu-id="60cfa-114">Exemplo 1: copiar texto para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="60cfa-114">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="60cfa-115">Exemplo 2: copiar o conteúdo de um diretório para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="60cfa-115">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="60cfa-116">Este comando copia o conteúdo da pasta especificada para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="60cfa-116">This command copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

## <span data-ttu-id="60cfa-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="60cfa-117">PARAMETERS</span></span>

### <span data-ttu-id="60cfa-118">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="60cfa-118">-Append</span></span>

<span data-ttu-id="60cfa-119">Indica que o cmdlet não limpa a área de transferência e anexa o conteúdo a ela.</span><span class="sxs-lookup"><span data-stu-id="60cfa-119">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="60cfa-120">-Ashtml</span><span class="sxs-lookup"><span data-stu-id="60cfa-120">-AsHtml</span></span>

<span data-ttu-id="60cfa-121">Indica que o cmdlet renderiza o conteúdo como HTML para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="60cfa-121">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="60cfa-122">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="60cfa-122">-LiteralPath</span></span>

<span data-ttu-id="60cfa-123">Especifica o caminho para o item que é copiado para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="60cfa-123">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="60cfa-124">Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="60cfa-124">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="60cfa-125">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="60cfa-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="60cfa-126">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="60cfa-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="60cfa-127">As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="60cfa-127">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="60cfa-128">-Path</span><span class="sxs-lookup"><span data-stu-id="60cfa-128">-Path</span></span>

<span data-ttu-id="60cfa-129">Especifica o caminho para o item que é copiado para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="60cfa-129">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="60cfa-130">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="60cfa-130">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="60cfa-131">-Value</span><span class="sxs-lookup"><span data-stu-id="60cfa-131">-Value</span></span>

<span data-ttu-id="60cfa-132">Especifica, como uma matriz de cadeia de caracteres, o conteúdo a ser copiado para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="60cfa-132">Specifies, as a string array, the content to copy to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Value
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="60cfa-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="60cfa-133">-Confirm</span></span>

<span data-ttu-id="60cfa-134">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="60cfa-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="60cfa-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="60cfa-135">-WhatIf</span></span>

<span data-ttu-id="60cfa-136">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="60cfa-136">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="60cfa-137">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="60cfa-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="60cfa-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="60cfa-138">CommonParameters</span></span>

<span data-ttu-id="60cfa-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="60cfa-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="60cfa-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="60cfa-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="60cfa-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="60cfa-141">INPUTS</span></span>

### <span data-ttu-id="60cfa-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="60cfa-142">System.String[]</span></span>

## <span data-ttu-id="60cfa-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="60cfa-143">OUTPUTS</span></span>

## <span data-ttu-id="60cfa-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="60cfa-144">NOTES</span></span>

<span data-ttu-id="60cfa-145">Em casos raros ao usar `Set-Clipboard` com um grande número de valores em uma rápida sucessão, como em um loop, você pode obter esporadicamente um valor em branco da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="60cfa-145">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="60cfa-146">Isso pode ser corrigido usando `Start-Sleep -Milliseconds 1` o no loop.</span><span class="sxs-lookup"><span data-stu-id="60cfa-146">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="60cfa-147">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="60cfa-147">RELATED LINKS</span></span>

[<span data-ttu-id="60cfa-148">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="60cfa-148">Get-Clipboard</span></span>](Get-Clipboard.md)
