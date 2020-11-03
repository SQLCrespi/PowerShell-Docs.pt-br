---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: e3c762f1d88efce9e7a126840e2c4348abe3648c
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "93195348"
---
# <span data-ttu-id="b4807-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="b4807-103">Get-Clipboard</span></span>

## <span data-ttu-id="b4807-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b4807-104">SYNOPSIS</span></span>
<span data-ttu-id="b4807-105">Obtém o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b4807-105">Gets the contents of the clipboard.</span></span>

[!NOTE]
> <span data-ttu-id="b4807-106">No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho.</span><span class="sxs-lookup"><span data-stu-id="b4807-106">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="b4807-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4807-107">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="b4807-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b4807-108">DESCRIPTION</span></span>

<span data-ttu-id="b4807-109">O `Get-Clipboard` cmdlet obtém o conteúdo da área de transferência como texto.</span><span class="sxs-lookup"><span data-stu-id="b4807-109">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="b4807-110">Várias linhas de texto são retornadas como uma matriz de cadeias de caracteres semelhantes a `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="b4807-110">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

## <span data-ttu-id="b4807-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b4807-111">EXAMPLES</span></span>

### <span data-ttu-id="b4807-112">Exemplo 1: obter o conteúdo da área de transferência e exibi-lo para a linha de comando</span><span class="sxs-lookup"><span data-stu-id="b4807-112">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="b4807-113">Neste exemplo, copiamos o texto "Olá" para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b4807-113">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="b4807-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4807-114">PARAMETERS</span></span>

### <span data-ttu-id="b4807-115">-RAW</span><span class="sxs-lookup"><span data-stu-id="b4807-115">-Raw</span></span>

<span data-ttu-id="b4807-116">Obtém todo o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b4807-116">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="b4807-117">O texto multilinha é retornado como uma única cadeia de caracteres de várias linhas em vez de uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b4807-117">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="b4807-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b4807-118">CommonParameters</span></span>

<span data-ttu-id="b4807-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b4807-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4807-120">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b4807-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4807-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b4807-121">INPUTS</span></span>

## <span data-ttu-id="b4807-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b4807-122">OUTPUTS</span></span>

### <span data-ttu-id="b4807-123">System.String</span><span class="sxs-lookup"><span data-stu-id="b4807-123">System.String</span></span>

## <span data-ttu-id="b4807-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b4807-124">NOTES</span></span>

## <span data-ttu-id="b4807-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b4807-125">RELATED LINKS</span></span>

[<span data-ttu-id="b4807-126">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="b4807-126">Set-Clipboard</span></span>](Set-Clipboard.md)

