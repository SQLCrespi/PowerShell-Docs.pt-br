---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: PowerShell, cmdlet, redução
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: 6f1ccedbd8443e1259b5695d1848979336727def
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193047"
---
# <span data-ttu-id="aa393-103">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="aa393-103">ConvertFrom-Markdown</span></span>

## <span data-ttu-id="aa393-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="aa393-104">SYNOPSIS</span></span>
<span data-ttu-id="aa393-105">Converta o conteúdo de uma cadeia de caracteres ou um arquivo em um objeto **MarkdownInfo** .</span><span class="sxs-lookup"><span data-stu-id="aa393-105">Convert the contents of a string or a file to a **MarkdownInfo** object.</span></span>

## <span data-ttu-id="aa393-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa393-106">SYNTAX</span></span>

### <span data-ttu-id="aa393-107">PathParamSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="aa393-107">PathParamSet (Default)</span></span>

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="aa393-108">LiteralParamSet</span><span class="sxs-lookup"><span data-stu-id="aa393-108">LiteralParamSet</span></span>

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="aa393-109">InputObjParamSet</span><span class="sxs-lookup"><span data-stu-id="aa393-109">InputObjParamSet</span></span>

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## <span data-ttu-id="aa393-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa393-110">DESCRIPTION</span></span>

<span data-ttu-id="aa393-111">Esse cmdlet converte o conteúdo especificado em um **MarkdownInfo** .</span><span class="sxs-lookup"><span data-stu-id="aa393-111">This cmdlet converts the specified content into a **MarkdownInfo** .</span></span> <span data-ttu-id="aa393-112">Quando um caminho de arquivo é especificado para o parâmetro **path** , o conteúdo no arquivo é convertido.</span><span class="sxs-lookup"><span data-stu-id="aa393-112">When a file path is specified for the **Path** parameter, the contents on the file are converted.</span></span> <span data-ttu-id="aa393-113">O objeto de saída tem três propriedades:</span><span class="sxs-lookup"><span data-stu-id="aa393-113">The output object has three properties:</span></span>

- <span data-ttu-id="aa393-114">A propriedade **token** tem a AST (árvore de sintaxe abstrata) do objeto convertido</span><span class="sxs-lookup"><span data-stu-id="aa393-114">The **Token** property has the abstract syntax tree (AST) of the the converted object</span></span>
- <span data-ttu-id="aa393-115">A propriedade **HTML** tem a conversão HTML da entrada especificada</span><span class="sxs-lookup"><span data-stu-id="aa393-115">The **Html** property has the HTML conversion of the specified input</span></span>
- <span data-ttu-id="aa393-116">A propriedade **VT100EncodedString** tem a cadeia de caracteres convertida com sequências de escape ANSI (vt100) se o parâmetro **AsVT100EncodedString** foi especificado</span><span class="sxs-lookup"><span data-stu-id="aa393-116">The **VT100EncodedString** property has the converted string with ANSI (VT100) escape sequences if the **AsVT100EncodedString** parameter was specified</span></span>

<span data-ttu-id="aa393-117">Esse cmdlet foi introduzido no PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="aa393-117">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="aa393-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="aa393-118">EXAMPLES</span></span>

### <span data-ttu-id="aa393-119">Exemplo 1: converter um arquivo que contém conteúdo de redução para HTML</span><span class="sxs-lookup"><span data-stu-id="aa393-119">Example 1: Convert a file containing Markdown content to HTML</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md
```

<span data-ttu-id="aa393-120">O objeto **MarkdownInfo** é retornado.</span><span class="sxs-lookup"><span data-stu-id="aa393-120">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="aa393-121">A propriedade **tokens** tem a AST do conteúdo convertido do `README.md` arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa393-121">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="aa393-122">A propriedade **HTML** tem o conteúdo convertido em HTML do `README.md` arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa393-122">The **Html** property has the HTML converted content of the `README.md` file.</span></span>

### <span data-ttu-id="aa393-123">Exemplo 2: converter um arquivo que contém conteúdo de redução para uma cadeia de caracteres codificada em VT100</span><span class="sxs-lookup"><span data-stu-id="aa393-123">Example 2: Convert a file containing Markdown content to a VT100-encoded string</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

<span data-ttu-id="aa393-124">O objeto **MarkdownInfo** é retornado.</span><span class="sxs-lookup"><span data-stu-id="aa393-124">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="aa393-125">A propriedade **tokens** tem a AST do conteúdo convertido do `README.md` arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa393-125">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="aa393-126">A propriedade **VT100EncodedString** tem o conteúdo da cadeia de caracteres codificada em vt100 convertido do `README.md` arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa393-126">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="aa393-127">Exemplo 3: converter o objeto de entrada que contém o conteúdo de redução em uma cadeia de caracteres codificada em VT100</span><span class="sxs-lookup"><span data-stu-id="aa393-127">Example 3: Convert input object containing Markdown content to a VT100-encoded string</span></span>

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="aa393-128">O objeto **MarkdownInfo** é retornado.</span><span class="sxs-lookup"><span data-stu-id="aa393-128">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="aa393-129">O objeto **FileInfo** de `Get-Item` é convertido em uma cadeia de caracteres codificada em VT100.</span><span class="sxs-lookup"><span data-stu-id="aa393-129">The **FileInfo** object from `Get-Item` is converted to a VT100-encoded string.</span></span> <span data-ttu-id="aa393-130">A propriedade **tokens** tem a AST do conteúdo convertido do `README.md` arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa393-130">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="aa393-131">A propriedade **VT100EncodedString** tem o conteúdo da cadeia de caracteres codificada em vt100 convertido do `README.md` arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa393-131">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="aa393-132">Exemplo 4: converter uma cadeia de caracteres que contém conteúdo de redução para uma cadeia de caracteres codificada em VT100</span><span class="sxs-lookup"><span data-stu-id="aa393-132">Example 4: Convert a string containing Markdown content to a VT100-encoded string</span></span>

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="aa393-133">O objeto **MarkdownInfo** é retornado.</span><span class="sxs-lookup"><span data-stu-id="aa393-133">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="aa393-134">A cadeia de caracteres especificada `**Bold text**` é convertida em uma cadeia de caracteres codificada em VT100 e disponível na propriedade **VT100EncodedString** .</span><span class="sxs-lookup"><span data-stu-id="aa393-134">The specified string `**Bold text**` is converted to a VT100-encoded string and available in **VT100EncodedString** property.</span></span>

## <span data-ttu-id="aa393-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa393-135">PARAMETERS</span></span>

### <span data-ttu-id="aa393-136">-AsVT100EncodedString</span><span class="sxs-lookup"><span data-stu-id="aa393-136">-AsVT100EncodedString</span></span>

<span data-ttu-id="aa393-137">Especifica se a saída deve ser codificada como uma cadeia de caracteres com códigos de escape VT100.</span><span class="sxs-lookup"><span data-stu-id="aa393-137">Specifies if the output should be encoded as a string with VT100 escape codes.</span></span>

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

### <span data-ttu-id="aa393-138">-InputObject</span><span class="sxs-lookup"><span data-stu-id="aa393-138">-InputObject</span></span>

<span data-ttu-id="aa393-139">Especifica o objeto a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="aa393-139">Specifies the object to be converted.</span></span> <span data-ttu-id="aa393-140">Quando um objeto do tipo **System. String** é especificado, a cadeia de caracteres é convertida.</span><span class="sxs-lookup"><span data-stu-id="aa393-140">When an object of type **System.String** is specified, the string is converted.</span></span> <span data-ttu-id="aa393-141">Quando um objeto do tipo **System. IO. FileInfo** é especificado, o conteúdo do arquivo especificado pelo objeto é convertido.</span><span class="sxs-lookup"><span data-stu-id="aa393-141">When an object of type **System.IO.FileInfo** is specified, the contents of the file specified by the object are converted.</span></span> <span data-ttu-id="aa393-142">Os objetos de qualquer outro tipo resultam em um erro.</span><span class="sxs-lookup"><span data-stu-id="aa393-142">Objects of any other type result in an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="aa393-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="aa393-143">-LiteralPath</span></span>

<span data-ttu-id="aa393-144">Especifica um caminho para o arquivo a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="aa393-144">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa393-145">-Path</span><span class="sxs-lookup"><span data-stu-id="aa393-145">-Path</span></span>

<span data-ttu-id="aa393-146">Especifica um caminho para o arquivo a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="aa393-146">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="aa393-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa393-147">CommonParameters</span></span>

<span data-ttu-id="aa393-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa393-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa393-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa393-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa393-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="aa393-150">INPUTS</span></span>

### <span data-ttu-id="aa393-151">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="aa393-151">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="aa393-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="aa393-152">OUTPUTS</span></span>

### <span data-ttu-id="aa393-153">Microsoft. PowerShell. MarkdownRender. MarkdownInfo</span><span class="sxs-lookup"><span data-stu-id="aa393-153">Microsoft.PowerShell.MarkdownRender.MarkdownInfo</span></span>

## <span data-ttu-id="aa393-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="aa393-154">NOTES</span></span>

## <span data-ttu-id="aa393-155">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="aa393-155">RELATED LINKS</span></span>

[<span data-ttu-id="aa393-156">Analisador de redução</span><span class="sxs-lookup"><span data-stu-id="aa393-156">Markdown Parser</span></span>](https://github.com/lunet-io/markdig)

[<span data-ttu-id="aa393-157">Código de escape ANSI</span><span class="sxs-lookup"><span data-stu-id="aa393-157">ANSI escape code</span></span>](https://wikipedia.org/wiki/ANSI_escape_code)
