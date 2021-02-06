---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: b0a9e5d1707e0d2f46c25991ddceff27d1b85287
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596197"
---
# <span data-ttu-id="2e2ee-102">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="2e2ee-102">Get-Clipboard</span></span>

## <span data-ttu-id="2e2ee-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2e2ee-103">SYNOPSIS</span></span>
<span data-ttu-id="2e2ee-104">Obtém o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-104">Gets the contents of the clipboard.</span></span>

## <span data-ttu-id="2e2ee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e2ee-105">SYNTAX</span></span>

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="2e2ee-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e2ee-106">DESCRIPTION</span></span>

<span data-ttu-id="2e2ee-107">O `Get-Clipboard` cmdlet obtém o conteúdo da área de transferência como texto.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-107">The `Get-Clipboard` cmdlet gets the contents of the clipboard as text.</span></span> <span data-ttu-id="2e2ee-108">Várias linhas de texto são retornadas como uma matriz de cadeias de caracteres semelhantes a `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="2e2ee-108">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

> [!NOTE]
> <span data-ttu-id="2e2ee-109">No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span> <span data-ttu-id="2e2ee-110">Não há suporte para esse cmdlet no macOS.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-110">This cmdlet is not supported on macOS.</span></span>

## <span data-ttu-id="2e2ee-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2e2ee-111">EXAMPLES</span></span>

### <span data-ttu-id="2e2ee-112">Exemplo 1: obter o conteúdo da área de transferência e exibi-lo para a linha de comando</span><span class="sxs-lookup"><span data-stu-id="2e2ee-112">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="2e2ee-113">Neste exemplo, copiamos o texto "Olá" para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-113">In this example we have copied the text "hello" into the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
hello
```

## <span data-ttu-id="2e2ee-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e2ee-114">PARAMETERS</span></span>

### <span data-ttu-id="2e2ee-115">-RAW</span><span class="sxs-lookup"><span data-stu-id="2e2ee-115">-Raw</span></span>

<span data-ttu-id="2e2ee-116">Obtém todo o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-116">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="2e2ee-117">O texto multilinha é retornado como uma única cadeia de caracteres de várias linhas em vez de uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-117">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="2e2ee-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e2ee-118">CommonParameters</span></span>

<span data-ttu-id="2e2ee-119">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e2ee-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e2ee-120">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e2ee-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e2ee-121">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2e2ee-121">INPUTS</span></span>

## <span data-ttu-id="2e2ee-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2e2ee-122">OUTPUTS</span></span>

### <span data-ttu-id="2e2ee-123">System.String</span><span class="sxs-lookup"><span data-stu-id="2e2ee-123">System.String</span></span>

## <span data-ttu-id="2e2ee-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2e2ee-124">NOTES</span></span>

## <span data-ttu-id="2e2ee-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2e2ee-125">RELATED LINKS</span></span>

[<span data-ttu-id="2e2ee-126">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="2e2ee-126">Set-Clipboard</span></span>](Set-Clipboard.md)
