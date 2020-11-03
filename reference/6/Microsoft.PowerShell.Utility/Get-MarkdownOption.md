---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-6&WT.mc_id=ps-gethelp
ms.date: 01/30/2020
schema: 2.0.0
ms.openlocfilehash: df141d99080a0d893d72691f6032684097dfd966
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "93192576"
---
# <span data-ttu-id="fa62e-101">Get-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="fa62e-101">Get-MarkdownOption</span></span>

## <span data-ttu-id="fa62e-102">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fa62e-102">SYNOPSIS</span></span>
<span data-ttu-id="fa62e-103">Retorna as cores e os estilos atuais usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="fa62e-103">Returns the current colors and styles used for rendering Markdown content in the console.</span></span>

## <span data-ttu-id="fa62e-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa62e-104">SYNTAX</span></span>

```
Get-MarkdownOption [<CommonParameters>]
```

## <span data-ttu-id="fa62e-105">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fa62e-105">DESCRIPTION</span></span>

<span data-ttu-id="fa62e-106">Retorna as cores e os estilos atuais usados para renderizar o conteúdo de redução no console.</span><span class="sxs-lookup"><span data-stu-id="fa62e-106">Returns the current colors and styles used for rendering Markdown content in the console.</span></span> <span data-ttu-id="fa62e-107">As cadeias de caracteres exibidas na saída desse cmdlet contêm os códigos de escape ANSI usados para alterar a cor e o estilo do texto de redução que está sendo renderizado.</span><span class="sxs-lookup"><span data-stu-id="fa62e-107">The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.</span></span>

<span data-ttu-id="fa62e-108">Para obter mais informações sobre a redução, consulte o site do [CommonMark](https://commonmark.org/) .</span><span class="sxs-lookup"><span data-stu-id="fa62e-108">For more information about Markdown, see the [CommonMark](https://commonmark.org/) website.</span></span>

## <span data-ttu-id="fa62e-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fa62e-109">EXAMPLES</span></span>

### <span data-ttu-id="fa62e-110">Exemplo 1-obter as cores e o estilo atuais</span><span class="sxs-lookup"><span data-stu-id="fa62e-110">Example 1 - Get the current colors and style</span></span>

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
> <span data-ttu-id="fa62e-111">Os valores de cadeia de caracteres mostrados na saída são os caracteres que seguem o caractere de **escape** ( `[char]0x1B` ) para a sequência de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="fa62e-111">The string values shown in the output are the characters that follow the **Escape** character (`[char]0x1B`) for the ANSI escape sequence.</span></span> <span data-ttu-id="fa62e-112">Para obter mais informações sobre os códigos de escape ANSI funcionam, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span><span class="sxs-lookup"><span data-stu-id="fa62e-112">For more information about ANSI escape codes work, see [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).</span></span>

## <span data-ttu-id="fa62e-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa62e-113">PARAMETERS</span></span>

### <span data-ttu-id="fa62e-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fa62e-114">CommonParameters</span></span>

<span data-ttu-id="fa62e-115">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fa62e-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa62e-116">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fa62e-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa62e-117">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fa62e-117">INPUTS</span></span>

### <span data-ttu-id="fa62e-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fa62e-118">None</span></span>

## <span data-ttu-id="fa62e-119">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fa62e-119">OUTPUTS</span></span>

### <span data-ttu-id="fa62e-120">Microsoft. PowerShell. MarkdownRender. PSMarkdownOptionInfo</span><span class="sxs-lookup"><span data-stu-id="fa62e-120">Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo</span></span>

## <span data-ttu-id="fa62e-121">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fa62e-121">NOTES</span></span>

## <span data-ttu-id="fa62e-122">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fa62e-122">RELATED LINKS</span></span>

[<span data-ttu-id="fa62e-123">Set-MarkdownOption</span><span class="sxs-lookup"><span data-stu-id="fa62e-123">Set-MarkdownOption</span></span>](Set-MarkdownOption.md)

[<span data-ttu-id="fa62e-124">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="fa62e-124">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

[<span data-ttu-id="fa62e-125">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="fa62e-125">Show-Markdown</span></span>](Show-Markdown.md)

[<span data-ttu-id="fa62e-126">ANSI_escape_code</span><span class="sxs-lookup"><span data-stu-id="fa62e-126">ANSI_escape_code</span></span>](https://en.wikipedia.org/wiki/ANSI_escape_code)

[<span data-ttu-id="fa62e-127">CommonMark</span><span class="sxs-lookup"><span data-stu-id="fa62e-127">CommonMark</span></span>](https://commonmark.org/)
