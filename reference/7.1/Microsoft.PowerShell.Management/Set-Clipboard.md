---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 1ee55dfaf4ecd3e46bedd8f356b1f677180c9c62
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564547"
---
# <span data-ttu-id="b92c4-103">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="b92c4-103">Set-Clipboard</span></span>

## <span data-ttu-id="b92c4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b92c4-104">SYNOPSIS</span></span>
<span data-ttu-id="b92c4-105">Define o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b92c4-105">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="b92c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b92c4-106">SYNTAX</span></span>

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b92c4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b92c4-107">DESCRIPTION</span></span>

<span data-ttu-id="b92c4-108">O `Set-Clipboard` cmdlet define o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b92c4-108">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="b92c4-109">No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho.</span><span class="sxs-lookup"><span data-stu-id="b92c4-109">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="b92c4-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b92c4-110">EXAMPLES</span></span>

### <span data-ttu-id="b92c4-111">Exemplo 1: copiar texto para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="b92c4-111">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="b92c4-112">Exemplo 2: copiar o conteúdo de um arquivo para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="b92c4-112">Example 2: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="b92c4-113">Este exemplo canaliza o conteúdo de um arquivo para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b92c4-113">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="b92c4-114">Neste exemplo, estamos obtendo uma chave SSH pública para que ela possa ser colada em outro aplicativo, como o GitHub.</span><span class="sxs-lookup"><span data-stu-id="b92c4-114">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="b92c4-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b92c4-115">PARAMETERS</span></span>

### <span data-ttu-id="b92c4-116">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="b92c4-116">-Append</span></span>

<span data-ttu-id="b92c4-117">Indica que o cmdlet não limpa a área de transferência e anexa o conteúdo a ela.</span><span class="sxs-lookup"><span data-stu-id="b92c4-117">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="b92c4-118">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b92c4-118">-Confirm</span></span>

<span data-ttu-id="b92c4-119">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b92c4-119">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b92c4-120">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b92c4-120">-WhatIf</span></span>

<span data-ttu-id="b92c4-121">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b92c4-121">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b92c4-122">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b92c4-122">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b92c4-123">-Value</span><span class="sxs-lookup"><span data-stu-id="b92c4-123">-Value</span></span>

<span data-ttu-id="b92c4-124">Os valores de cadeia de caracteres a serem adicionados à área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b92c4-124">The string values to be added to the clipboard.</span></span>

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

### <span data-ttu-id="b92c4-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b92c4-125">CommonParameters</span></span>

<span data-ttu-id="b92c4-126">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b92c4-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b92c4-127">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b92c4-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b92c4-128">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b92c4-128">INPUTS</span></span>

### <span data-ttu-id="b92c4-129">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b92c4-129">System.String[]</span></span>

## <span data-ttu-id="b92c4-130">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b92c4-130">OUTPUTS</span></span>

## <span data-ttu-id="b92c4-131">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b92c4-131">NOTES</span></span>

<span data-ttu-id="b92c4-132">Em casos raros ao usar `Set-Clipboard` com um grande número de valores em uma rápida sucessão, como em um loop, você pode obter esporadicamente um valor em branco da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="b92c4-132">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="b92c4-133">Isso pode ser corrigido usando `Start-Sleep -Milliseconds 1` o no loop.</span><span class="sxs-lookup"><span data-stu-id="b92c4-133">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="b92c4-134">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b92c4-134">RELATED LINKS</span></span>

[<span data-ttu-id="b92c4-135">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="b92c4-135">Get-Clipboard</span></span>](Get-Clipboard.md)
