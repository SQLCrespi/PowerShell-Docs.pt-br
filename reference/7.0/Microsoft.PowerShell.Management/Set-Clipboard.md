---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: efb24b14122ad37043636d999afaa4199eb3097b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564366"
---
# <span data-ttu-id="99f5e-102">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="99f5e-102">Set-Clipboard</span></span>

## <span data-ttu-id="99f5e-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="99f5e-103">SYNOPSIS</span></span>
<span data-ttu-id="99f5e-104">Define o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="99f5e-104">Sets the contents of the clipboard.</span></span>

## <span data-ttu-id="99f5e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99f5e-105">SYNTAX</span></span>

```
Set-Clipboard [-Value] <string[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="99f5e-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99f5e-106">DESCRIPTION</span></span>

<span data-ttu-id="99f5e-107">O `Set-Clipboard` cmdlet define o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="99f5e-107">The `Set-Clipboard` cmdlet sets the contents of the clipboard.</span></span>

> [!NOTE]
> <span data-ttu-id="99f5e-108">No Linux, esse cmdlet requer `xclip` que o utilitário esteja no caminho.</span><span class="sxs-lookup"><span data-stu-id="99f5e-108">On Linux, this cmdlet requires the `xclip` utility to be in the path.</span></span>

## <span data-ttu-id="99f5e-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="99f5e-109">EXAMPLES</span></span>

### <span data-ttu-id="99f5e-110">Exemplo 1: copiar texto para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="99f5e-110">Example 1: Copy text to the clipboard</span></span>

```powershell
Set-Clipboard -Value "This is a test string"
```

### <span data-ttu-id="99f5e-111">Exemplo 2: copiar o conteúdo de um arquivo para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="99f5e-111">Example 2: Copy the contents of a file to the clipboard</span></span>

<span data-ttu-id="99f5e-112">Este exemplo canaliza o conteúdo de um arquivo para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="99f5e-112">This example pipes the contents of a file to the clipboard.</span></span> <span data-ttu-id="99f5e-113">Neste exemplo, estamos obtendo uma chave SSH pública para que ela possa ser colada em outro aplicativo, como o GitHub.</span><span class="sxs-lookup"><span data-stu-id="99f5e-113">In this example, we are getting a public ssh key so that it can be pasted into another application, like GitHub.</span></span>

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## <span data-ttu-id="99f5e-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99f5e-114">PARAMETERS</span></span>

### <span data-ttu-id="99f5e-115">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="99f5e-115">-Append</span></span>

<span data-ttu-id="99f5e-116">Indica que o cmdlet não limpa a área de transferência e anexa o conteúdo a ela.</span><span class="sxs-lookup"><span data-stu-id="99f5e-116">Indicates that the cmdlet does not clear the clipboard and appends content to it.</span></span>

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

### <span data-ttu-id="99f5e-117">-Confirm</span><span class="sxs-lookup"><span data-stu-id="99f5e-117">-Confirm</span></span>

<span data-ttu-id="99f5e-118">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99f5e-118">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="99f5e-119">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="99f5e-119">-WhatIf</span></span>

<span data-ttu-id="99f5e-120">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="99f5e-120">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="99f5e-121">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="99f5e-121">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="99f5e-122">-Value</span><span class="sxs-lookup"><span data-stu-id="99f5e-122">-Value</span></span>

<span data-ttu-id="99f5e-123">Os valores de cadeia de caracteres a serem adicionados à área de transferência.</span><span class="sxs-lookup"><span data-stu-id="99f5e-123">The string values to be added to the clipboard.</span></span>

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

### <span data-ttu-id="99f5e-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="99f5e-124">CommonParameters</span></span>

<span data-ttu-id="99f5e-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99f5e-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99f5e-126">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="99f5e-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="99f5e-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="99f5e-127">INPUTS</span></span>

### <span data-ttu-id="99f5e-128">System.String[]</span><span class="sxs-lookup"><span data-stu-id="99f5e-128">System.String[]</span></span>

## <span data-ttu-id="99f5e-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="99f5e-129">OUTPUTS</span></span>

## <span data-ttu-id="99f5e-130">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="99f5e-130">NOTES</span></span>

<span data-ttu-id="99f5e-131">Em casos raros ao usar `Set-Clipboard` com um grande número de valores em uma rápida sucessão, como em um loop, você pode obter esporadicamente um valor em branco da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="99f5e-131">In rare cases when using `Set-Clipboard` with a high number of values in rapid succession, like in a loop, you might sporadically get a blank value from the clipboard.</span></span> <span data-ttu-id="99f5e-132">Isso pode ser corrigido usando `Start-Sleep -Milliseconds 1` o no loop.</span><span class="sxs-lookup"><span data-stu-id="99f5e-132">This can be fixed by using `Start-Sleep -Milliseconds 1` in the loop.</span></span>

## <span data-ttu-id="99f5e-133">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="99f5e-133">RELATED LINKS</span></span>

[<span data-ttu-id="99f5e-134">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="99f5e-134">Get-Clipboard</span></span>](Get-Clipboard.md)
