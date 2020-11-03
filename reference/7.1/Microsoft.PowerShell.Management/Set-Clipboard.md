---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/09/2019
online version: https://go.microsoft.com/fwlink/?linkid=526220
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: e610678f0d6db62ccbdedf96f1315aa2e88eb5e2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193281"
---
# <span data-ttu-id="27e9c-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="27e9c-103">Set-Clipboard</span></span>

## <span data-ttu-id="27e9c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="27e9c-104">SYNOPSIS</span></span>
<span data-ttu-id="27e9c-105">Define o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="27e9c-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="27e9c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27e9c-106">SYNTAX</span></span>

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="27e9c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27e9c-107">DESCRIPTION</span></span>

<span data-ttu-id="27e9c-108">O `Set-Clipboard` cmdlet define o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="27e9c-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

[!NOTE]
> <span data-ttu-id="27e9c-109">No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho.</span><span class="sxs-lookup"><span data-stu-id="27e9c-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="27e9c-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="27e9c-110">EXAMPLES</span></span>

### <span data-ttu-id="27e9c-111">Exemplo 1: copiar texto para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="27e9c-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

## <span data-ttu-id="27e9c-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27e9c-112">PARAMETERS</span></span>

### <span data-ttu-id="27e9c-113">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="27e9c-113">-Append</span></span>

<span data-ttu-id="27e9c-114">Indica que o cmdlet não limpa a área de transferência e anexa o conteúdo a ela.</span><span class="sxs-lookup"><span data-stu-id="27e9c-114">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="27e9c-115">-Confirm</span><span class="sxs-lookup"><span data-stu-id="27e9c-115">-Confirm</span></span>

<span data-ttu-id="27e9c-116">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="27e9c-116">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="27e9c-117">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="27e9c-117">-WhatIf</span></span>

<span data-ttu-id="27e9c-118">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="27e9c-118">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="27e9c-119">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="27e9c-119">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="27e9c-120">-Value</span><span class="sxs-lookup"><span data-stu-id="27e9c-120">-Value</span></span>

<span data-ttu-id="27e9c-121">Os valores de cadeia de caracteres a serem adicionados à área de transferência.</span><span class="sxs-lookup"><span data-stu-id="27e9c-121">The string values to be added to the clipboard.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="27e9c-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27e9c-122">CommonParameters</span></span>

<span data-ttu-id="27e9c-123">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27e9c-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27e9c-124">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="27e9c-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27e9c-125">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="27e9c-125">INPUTS</span></span>

### <span data-ttu-id="27e9c-126">System.String[]</span><span class="sxs-lookup"><span data-stu-id="27e9c-126">System.String[]</span></span>

## <span data-ttu-id="27e9c-127">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="27e9c-127">OUTPUTS</span></span>

## <span data-ttu-id="27e9c-128">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="27e9c-128">NOTES</span></span>

<span data-ttu-id="27e9c-129">Em casos raros ao usar `Set-Clipboard` com um grande número de valores em uma rápida sucessão, como em um loop, você pode obter esporadicamente um valor em branco da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="27e9c-129">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="27e9c-130">Isso pode ser corrigido usando `Start-Sleep -Milliseconds 1` o no loop.</span><span class="sxs-lookup"><span data-stu-id="27e9c-130">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="27e9c-131">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="27e9c-131">RELATED LINKS</span></span>

[<span data-ttu-id="27e9c-132">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="27e9c-132">Get-Clipboard</span></span>](Get-Clipboard.md)
