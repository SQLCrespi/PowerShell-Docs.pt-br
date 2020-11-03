---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: da1df360d7c471d925bd2f57f5258ecb2d60e631
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239977"
---
# <span data-ttu-id="6278a-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="6278a-103">Get-Clipboard</span></span>

## <span data-ttu-id="6278a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6278a-104">SYNOPSIS</span></span>
<span data-ttu-id="6278a-105">Obtém o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="6278a-105">Gets the contents of the clipboard.</span></span>

## <span data-ttu-id="6278a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6278a-106">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="6278a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6278a-107">DESCRIPTION</span></span>

<span data-ttu-id="6278a-108">O `Get-Clipboard` cmdlet obtém o conteúdo da área de transferência como texto.</span><span class="sxs-lookup"><span data-stu-id="6278a-108">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="6278a-109">Várias linhas de texto são retornadas como uma matriz de cadeias de caracteres semelhantes a `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="6278a-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="6278a-110">No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho.</span><span class="sxs-lookup"><span data-stu-id="6278a-110">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="6278a-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6278a-111">EXAMPLES</span></span>

### <span data-ttu-id="6278a-112">Exemplo 1: obter o conteúdo da área de transferência e exibi-lo para a linha de comando</span><span class="sxs-lookup"><span data-stu-id="6278a-112">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="6278a-113">Neste exemplo, copiamos o texto "Olá" para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="6278a-113">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="6278a-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6278a-114">PARAMETERS</span></span>

### <span data-ttu-id="6278a-115">-RAW</span><span class="sxs-lookup"><span data-stu-id="6278a-115">-Raw</span></span>

<span data-ttu-id="6278a-116">Obtém todo o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="6278a-116">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="6278a-117">O texto multilinha é retornado como uma única cadeia de caracteres de várias linhas em vez de uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6278a-117">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="6278a-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6278a-118">CommonParameters</span></span>

<span data-ttu-id="6278a-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6278a-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6278a-120">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6278a-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6278a-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6278a-121">INPUTS</span></span>

## <span data-ttu-id="6278a-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6278a-122">OUTPUTS</span></span>

### <span data-ttu-id="6278a-123">System.String</span><span class="sxs-lookup"><span data-stu-id="6278a-123">System.String</span></span>

## <span data-ttu-id="6278a-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6278a-124">NOTES</span></span>

## <span data-ttu-id="6278a-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6278a-125">RELATED LINKS</span></span>

[<span data-ttu-id="6278a-126">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="6278a-126">Set-Clipboard</span></span>](Set-Clipboard.md)

