---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
schema: 2.0.0
ms.openlocfilehash: 775b11db79b9ca8290864b757e5cd1a0615f89e4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598620"
---
# <span data-ttu-id="a2163-101">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="a2163-101">Get-MarkdownOption</span></span>

## <span data-ttu-id="a2163-102">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a2163-102">SYNOPSIS</span></span>
<span data-ttu-id="a2163-103">Retorna as cores e os estilos atuais usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="a2163-103">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="a2163-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2163-104">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="a2163-105">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2163-105">DESCRIPTION</span></span>

<span data-ttu-id="a2163-106">Retorna as cores e os estilos atuais usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="a2163-106">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="a2163-107">As cadeias de caracteres exibidas na saída desse cmdlet contêm os códigos de escape ANSI usados para alterar a cor e o estilo do texto de redução que está sendo renderizado.</span><span class="sxs-lookup"><span data-stu-id="a2163-107">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="a2163-108">Para obter mais informações sobre a redução, consulte o site do [CommonMark](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="a2163-108">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="a2163-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a2163-109">EXAMPLES</span></span>

### <span data-ttu-id="a2163-110">Exemplo 1-obter as cores e o estilo atuais</span><span class="sxs-lookup"><span data-stu-id="a2163-110">Example 1 - Get the current colors and style</span></span>

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
> <span data-ttu-id="a2163-111">Os valores de cadeia de caracteres mostrados na saída são os caracteres que seguem o caractere de **escape** ( `[char]0x1B` ) para a sequência de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="a2163-111">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="a2163-112">Para obter mais informações sobre os códigos de escape ANSI funcionam, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="a2163-112">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="a2163-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2163-113">PARAMETERS</span></span>

### <span data-ttu-id="a2163-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a2163-114">CommonParameters</span></span>

<span data-ttu-id="a2163-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2163-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2163-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2163-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2163-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a2163-117">INPUTS</span></span>

### <span data-ttu-id="a2163-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a2163-118">None</span></span>

## <span data-ttu-id="a2163-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a2163-119">OUTPUTS</span></span>

### <span data-ttu-id="a2163-120">Microsoft. PowerShell. MarkdownRender. PSMarkdownOptionInfo</span><span class="sxs-lookup"><span data-stu-id="a2163-120">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="a2163-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a2163-121">NOTES</span></span>

## <span data-ttu-id="a2163-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a2163-122">RELATED LINKS</span></span>

[<span data-ttu-id="a2163-123">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="a2163-123">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="a2163-124">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="a2163-124">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="a2163-125">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="a2163-125">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="a2163-126">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="a2163-126">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="a2163-127">CommonMark</span><span class="sxs-lookup"><span data-stu-id="a2163-127">CommonMark</span></span>](https://commonmark.org/)

