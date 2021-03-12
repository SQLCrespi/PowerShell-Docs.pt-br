---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MarkdownOption
ms.openlocfilehash: 0da0c869216fd2a044fe03faad25e3de6f3fb8fd
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195697"
---
# <span data-ttu-id="a4a38-102">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="a4a38-102">Get-MarkdownOption</span></span>

## <span data-ttu-id="a4a38-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a4a38-103">SYNOPSIS</span></span>
<span data-ttu-id="a4a38-104">Retorna as cores e os estilos atuais usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="a4a38-104">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="a4a38-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4a38-105">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="a4a38-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a4a38-106">DESCRIPTION</span></span>

<span data-ttu-id="a4a38-107">Retorna as cores e os estilos atuais usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="a4a38-107">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="a4a38-108">As cadeias de caracteres exibidas na saída desse cmdlet contêm os códigos de escape ANSI usados para alterar a cor e o estilo do texto de redução que está sendo renderizado.</span><span class="sxs-lookup"><span data-stu-id="a4a38-108">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="a4a38-109">Para obter mais informações sobre a redução, consulte o site do [CommonMark](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="a4a38-109">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="a4a38-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a4a38-110">EXAMPLES</span></span>

### <span data-ttu-id="a4a38-111">Exemplo 1-obter as cores e o estilo atuais</span><span class="sxs-lookup"><span data-stu-id="a4a38-111">Example 1 - Get the current colors and style</span></span>

```powershell
Get-MarkdownOption
```

```Output
Header1         : [7m
Header2         : [4;93m
Header3         : [4;94m
Header4         : [4;95m
Header5         : [4;96m
Header6         : [4;97m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

> [!NOTE]
> <span data-ttu-id="a4a38-112">Os valores de cadeia de caracteres mostrados na saída são os caracteres que seguem o caractere de **escape** ( `[char]0x1B` ) para a sequência de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="a4a38-112">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="a4a38-113">Para obter mais informações sobre os códigos de escape ANSI funcionam, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="a4a38-113">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="a4a38-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4a38-114">PARAMETERS</span></span>

### <span data-ttu-id="a4a38-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a4a38-115">CommonParameters</span></span>

<span data-ttu-id="a4a38-116">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a4a38-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4a38-117">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a4a38-117">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4a38-118">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a4a38-118">INPUTS</span></span>

### <span data-ttu-id="a4a38-119">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a4a38-119">None</span></span>

## <span data-ttu-id="a4a38-120">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a4a38-120">OUTPUTS</span></span>

### <span data-ttu-id="a4a38-121">Microsoft. PowerShell. MarkdownRender. PSMarkdownOptionInfo</span><span class="sxs-lookup"><span data-stu-id="a4a38-121">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="a4a38-122">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a4a38-122">NOTES</span></span>

## <span data-ttu-id="a4a38-123">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a4a38-123">RELATED LINKS</span></span>

[<span data-ttu-id="a4a38-124">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="a4a38-124">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="a4a38-125">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="a4a38-125">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="a4a38-126">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="a4a38-126">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="a4a38-127">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="a4a38-127">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="a4a38-128">CommonMark</span><span class="sxs-lookup"><span data-stu-id="a4a38-128">CommonMark</span></span>](https://commonmark.org/)

