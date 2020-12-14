---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: c1cf126e41a5e918afffbc41d30f957e650efdf5
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564492"
---
# <span data-ttu-id="0e6e6-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="0e6e6-102">Set-Clipboard</span></span>

## <span data-ttu-id="0e6e6-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0e6e6-103">SYNOPSIS</span></span>
<span data-ttu-id="0e6e6-104">Define a entrada atual da área de transferência do Windows.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-104">Sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="0e6e6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e6e6-105">SYNTAX</span></span>

### <span data-ttu-id="0e6e6-106">Cadeia de caracteres (padrão)</span><span class="sxs-lookup"><span data-stu-id="0e6e6-106">String (Default)</span></span>

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e6e6-107">Valor</span><span class="sxs-lookup"><span data-stu-id="0e6e6-107">Value</span></span>

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e6e6-108">Caminho</span><span class="sxs-lookup"><span data-stu-id="0e6e6-108">Path</span></span>

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0e6e6-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0e6e6-109">LiteralPath</span></span>

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0e6e6-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0e6e6-110">DESCRIPTION</span></span>

<span data-ttu-id="0e6e6-111">O `Set-Clipboard` cmdlet define a entrada atual da área de transferência do Windows.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-111">The `Set-Clipboard` cmdlet sets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="0e6e6-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0e6e6-112">EXAMPLES</span></span>

### <span data-ttu-id="0e6e6-113">Exemplo 1: copiar texto para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="0e6e6-113">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="0e6e6-114">Exemplo 2: copiar o conteúdo de um diretório para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="0e6e6-114">Example 2: Copy the contents of a directory to the clipboard</span></span>

<span data-ttu-id="0e6e6-115">Este exemplo copia o conteúdo da pasta especificada para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-115">This example copies the content of the specified folder to the clipboard.</span></span>

```powershell
Set-Clipboard -Path "C:\Staging\"
```

### <span data-ttu-id="0e6e6-116">Exemplo 3: copiar o conteúdo de um arquivo para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="0e6e6-116">Example 3: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="0e6e6-117">Este exemplo canaliza o conteúdo de um arquivo para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-117">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="0e6e6-118">Neste exemplo, estamos obtendo uma chave SSH pública para que ela possa ser colada em outro aplicativo, como o GitHub.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-118">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="0e6e6-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e6e6-119">PARAMETERS</span></span>

### <span data-ttu-id="0e6e6-120">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="0e6e6-120">-Append</span></span>

<span data-ttu-id="0e6e6-121">Indica que o cmdlet não limpa a área de transferência e anexa o conteúdo a ela.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-121">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="0e6e6-122">-Ashtml</span><span class="sxs-lookup"><span data-stu-id="0e6e6-122">-AsHtml</span></span>

<span data-ttu-id="0e6e6-123">Indica que o cmdlet renderiza o conteúdo como HTML para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-123">Indicates that the cmdlet renders the content as HTML to the clipboard.</span></span>

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

### <span data-ttu-id="0e6e6-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0e6e6-124">-LiteralPath</span></span>

<span data-ttu-id="0e6e6-125">Especifica o caminho para o item que é copiado para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-125">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="0e6e6-126">Ao contrário de **Path**, o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-126">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0e6e6-127">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-127">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0e6e6-128">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-128">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0e6e6-129">As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-129">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="0e6e6-130">-Path</span><span class="sxs-lookup"><span data-stu-id="0e6e6-130">-Path</span></span>

<span data-ttu-id="0e6e6-131">Especifica o caminho para o item que é copiado para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-131">Specifies the path to the item that is copied to the clipboard.</span></span> <span data-ttu-id="0e6e6-132">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0e6e6-133">-Value</span><span class="sxs-lookup"><span data-stu-id="0e6e6-133">-Value</span></span>

<span data-ttu-id="0e6e6-134">Especifica, como uma matriz de cadeia de caracteres, o conteúdo a ser copiado para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-134">Specifies, as a string array, the content to copy to the clipboard.</span></span>

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

### <span data-ttu-id="0e6e6-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0e6e6-135">-Confirm</span></span>

<span data-ttu-id="0e6e6-136">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0e6e6-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0e6e6-137">-WhatIf</span></span>

<span data-ttu-id="0e6e6-138">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-138">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0e6e6-139">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0e6e6-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0e6e6-140">CommonParameters</span></span>

<span data-ttu-id="0e6e6-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e6e6-142">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0e6e6-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e6e6-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0e6e6-143">INPUTS</span></span>

### <span data-ttu-id="0e6e6-144">System.String[]</span><span class="sxs-lookup"><span data-stu-id="0e6e6-144">System.String[]</span></span>

## <span data-ttu-id="0e6e6-145">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0e6e6-145">OUTPUTS</span></span>

## <span data-ttu-id="0e6e6-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0e6e6-146">NOTES</span></span>

<span data-ttu-id="0e6e6-147">Em casos raros ao usar `Set-Clipboard` com um grande número de valores em uma rápida sucessão, como em um loop, você pode obter esporadicamente um valor em branco da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-147">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="0e6e6-148">Isso pode ser corrigido usando `Start-Sleep -Milliseconds 1` o no loop.</span><span class="sxs-lookup"><span data-stu-id="0e6e6-148">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="0e6e6-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0e6e6-149">RELATED LINKS</span></span>

[<span data-ttu-id="0e6e6-150">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="0e6e6-150">Get-Clipboard</span></span>](Get-Clipboard.md)
