---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: d280eba2e717ccfb0b896d62f42079390d1db848
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596172"
---
# <span data-ttu-id="10774-102">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="10774-102">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="10774-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="10774-103">SYNOPSIS</span></span>
<span data-ttu-id="10774-104">Remove uma associação de chave.</span><span class="sxs-lookup"><span data-stu-id="10774-104">Removes a key binding.</span></span>

## <span data-ttu-id="10774-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10774-105">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="10774-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10774-106">DESCRIPTION</span></span>

<span data-ttu-id="10774-107">O `Remove-PSReadLineKeyHandler` cmdlet Remove uma associação de chave especificada.</span><span class="sxs-lookup"><span data-stu-id="10774-107">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="10774-108">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="10774-108">EXAMPLES</span></span>

### <span data-ttu-id="10774-109">Exemplo 1: remover uma associação</span><span class="sxs-lookup"><span data-stu-id="10774-109">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="10774-110">Esse comando Remove a associação da combinação de teclas, ou corda, `Ctrl+B` .</span><span class="sxs-lookup"><span data-stu-id="10774-110">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="10774-111">A `Ctrl+B` corda é criada no `Set-PSReadLineKeyHandler` artigo.</span><span class="sxs-lookup"><span data-stu-id="10774-111">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="10774-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10774-112">PARAMETERS</span></span>

### <span data-ttu-id="10774-113">-Corda</span><span class="sxs-lookup"><span data-stu-id="10774-113">-Chord</span></span>

<span data-ttu-id="10774-114">Especifica uma matriz de chaves ou sequências de chaves a serem removidas.</span><span class="sxs-lookup"><span data-stu-id="10774-114">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="10774-115">Uma única associação é especificada usando uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="10774-115">A single binding is specified by using a single string.</span></span> <span data-ttu-id="10774-116">Se a associação for uma sequência de chaves, separe as chaves por uma vírgula, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="10774-116">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="10774-117">Esse parâmetro aceita uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="10774-117">This parameter accepts an array of strings.</span></span> <span data-ttu-id="10774-118">Cada cadeia de caracteres é uma associação separada, não uma sequência de chaves para uma única associação.</span><span class="sxs-lookup"><span data-stu-id="10774-118">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="10774-119">-ViMode</span><span class="sxs-lookup"><span data-stu-id="10774-119">-ViMode</span></span>

<span data-ttu-id="10774-120">Especifique a qual modo vi a associação se aplica.</span><span class="sxs-lookup"><span data-stu-id="10774-120">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="10774-121">Os valores possíveis são: inserir, comando.</span><span class="sxs-lookup"><span data-stu-id="10774-121">Possible values are: Insert, Command.</span></span>

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

### <span data-ttu-id="10774-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10774-122">CommonParameters</span></span>

<span data-ttu-id="10774-123">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="10774-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10774-124">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="10774-124">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10774-125">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="10774-125">INPUTS</span></span>

### <span data-ttu-id="10774-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="10774-126">None</span></span>

<span data-ttu-id="10774-127">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="10774-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="10774-128">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="10774-128">OUTPUTS</span></span>

### <span data-ttu-id="10774-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="10774-129">None</span></span>

## <span data-ttu-id="10774-130">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="10774-130">NOTES</span></span>

## <span data-ttu-id="10774-131">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="10774-131">RELATED LINKS</span></span>

[<span data-ttu-id="10774-132">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="10774-132">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="10774-133">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="10774-133">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="10774-134">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="10774-134">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="10774-135">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="10774-135">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

