---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: 6a15e829f589fbccf0da3479a22f24cdf3fc81ae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194041"
---
# <span data-ttu-id="029a4-103">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="029a4-103">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="029a4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="029a4-104">SYNOPSIS</span></span>
<span data-ttu-id="029a4-105">Remove uma associação de chave.</span><span class="sxs-lookup"><span data-stu-id="029a4-105">Removes a key binding.</span></span>

## <span data-ttu-id="029a4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="029a4-106">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="029a4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="029a4-107">DESCRIPTION</span></span>

<span data-ttu-id="029a4-108">O `Remove-PSReadLineKeyHandler` cmdlet Remove uma associação de chave especificada.</span><span class="sxs-lookup"><span data-stu-id="029a4-108">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="029a4-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="029a4-109">EXAMPLES</span></span>

### <span data-ttu-id="029a4-110">Exemplo 1: remover uma associação</span><span class="sxs-lookup"><span data-stu-id="029a4-110">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="029a4-111">Esse comando Remove a associação da combinação de teclas, ou corda, `Ctrl+B` .</span><span class="sxs-lookup"><span data-stu-id="029a4-111">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="029a4-112">A `Ctrl+B` corda é criada no `Set-PSReadLineKeyHandler` artigo.</span><span class="sxs-lookup"><span data-stu-id="029a4-112">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="029a4-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="029a4-113">PARAMETERS</span></span>

### <span data-ttu-id="029a4-114">-Corda</span><span class="sxs-lookup"><span data-stu-id="029a4-114">-Chord</span></span>

<span data-ttu-id="029a4-115">Especifica uma matriz de chaves ou sequências de chaves a serem removidas.</span><span class="sxs-lookup"><span data-stu-id="029a4-115">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="029a4-116">Uma única associação é especificada usando uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="029a4-116">A single binding is specified by using a single string.</span></span> <span data-ttu-id="029a4-117">Se a associação for uma sequência de chaves, separe as chaves por uma vírgula, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="029a4-117">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="029a4-118">Esse parâmetro aceita uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="029a4-118">This parameter accepts an array of strings.</span></span> <span data-ttu-id="029a4-119">Cada cadeia de caracteres é uma associação separada, não uma sequência de chaves para uma única associação.</span><span class="sxs-lookup"><span data-stu-id="029a4-119">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="029a4-120">-ViMode</span><span class="sxs-lookup"><span data-stu-id="029a4-120">-ViMode</span></span>

<span data-ttu-id="029a4-121">Especifique a qual modo vi a associação se aplica.</span><span class="sxs-lookup"><span data-stu-id="029a4-121">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="029a4-122">Os valores possíveis são: inserir, comando.</span><span class="sxs-lookup"><span data-stu-id="029a4-122">Possible values are: Insert, Command.</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="029a4-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="029a4-123">CommonParameters</span></span>

<span data-ttu-id="029a4-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="029a4-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="029a4-125">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="029a4-125">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="029a4-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="029a4-126">INPUTS</span></span>

### <span data-ttu-id="029a4-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="029a4-127">None</span></span>

<span data-ttu-id="029a4-128">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="029a4-128">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="029a4-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="029a4-129">OUTPUTS</span></span>

### <span data-ttu-id="029a4-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="029a4-130">None</span></span>

## <span data-ttu-id="029a4-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="029a4-131">NOTES</span></span>

## <span data-ttu-id="029a4-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="029a4-132">RELATED LINKS</span></span>

[<span data-ttu-id="029a4-133">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="029a4-133">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="029a4-134">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="029a4-134">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="029a4-135">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="029a4-135">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="029a4-136">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="029a4-136">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
