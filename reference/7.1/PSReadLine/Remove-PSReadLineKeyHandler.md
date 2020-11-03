---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: a13677035581a081df51917bc6b82efec0ff2156
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196590"
---
# <span data-ttu-id="ffd2b-103">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ffd2b-103">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="ffd2b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ffd2b-104">SYNOPSIS</span></span>
<span data-ttu-id="ffd2b-105">Remove uma associação de chave.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-105">Removes a key binding.</span></span>

## <span data-ttu-id="ffd2b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ffd2b-106">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="ffd2b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ffd2b-107">DESCRIPTION</span></span>

<span data-ttu-id="ffd2b-108">O `Remove-PSReadLineKeyHandler` cmdlet Remove uma associação de chave especificada.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-108">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="ffd2b-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ffd2b-109">EXAMPLES</span></span>

### <span data-ttu-id="ffd2b-110">Exemplo 1: remover uma associação</span><span class="sxs-lookup"><span data-stu-id="ffd2b-110">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="ffd2b-111">Esse comando Remove a associação da combinação de teclas, ou corda, `Ctrl+B` .</span><span class="sxs-lookup"><span data-stu-id="ffd2b-111">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="ffd2b-112">A `Ctrl+B` corda é criada no `Set-PSReadLineKeyHandler` artigo.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-112">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="ffd2b-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ffd2b-113">PARAMETERS</span></span>

### <span data-ttu-id="ffd2b-114">-Corda</span><span class="sxs-lookup"><span data-stu-id="ffd2b-114">-Chord</span></span>

<span data-ttu-id="ffd2b-115">Especifica uma matriz de chaves ou sequências de chaves a serem removidas.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-115">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="ffd2b-116">Uma única associação é especificada usando uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-116">A single binding is specified by using a single string.</span></span> <span data-ttu-id="ffd2b-117">Se a associação for uma sequência de chaves, separe as chaves por uma vírgula, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="ffd2b-117">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="ffd2b-118">Esse parâmetro aceita uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-118">This parameter accepts an array of strings.</span></span> <span data-ttu-id="ffd2b-119">Cada cadeia de caracteres é uma associação separada, não uma sequência de chaves para uma única associação.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-119">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="ffd2b-120">-ViMode</span><span class="sxs-lookup"><span data-stu-id="ffd2b-120">-ViMode</span></span>

<span data-ttu-id="ffd2b-121">Especifique a qual modo vi a associação se aplica.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-121">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="ffd2b-122">Os valores possíveis são: inserir, comando.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-122">Possible values are: Insert, Command.</span></span>

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

### <span data-ttu-id="ffd2b-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ffd2b-123">CommonParameters</span></span>

<span data-ttu-id="ffd2b-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ffd2b-125">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ffd2b-125">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ffd2b-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ffd2b-126">INPUTS</span></span>

### <span data-ttu-id="ffd2b-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ffd2b-127">None</span></span>

<span data-ttu-id="ffd2b-128">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ffd2b-128">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ffd2b-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ffd2b-129">OUTPUTS</span></span>

### <span data-ttu-id="ffd2b-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ffd2b-130">None</span></span>

## <span data-ttu-id="ffd2b-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ffd2b-131">NOTES</span></span>

## <span data-ttu-id="ffd2b-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ffd2b-132">RELATED LINKS</span></span>

[<span data-ttu-id="ffd2b-133">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ffd2b-133">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="ffd2b-134">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="ffd2b-134">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="ffd2b-135">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="ffd2b-135">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="ffd2b-136">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="ffd2b-136">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

