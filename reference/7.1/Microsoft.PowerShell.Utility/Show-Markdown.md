---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: f4740bca33bd70d4d8eca51ed45ba6204b5d2acb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193258"
---
# <span data-ttu-id="101e4-103">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="101e4-103">Show-Markdown</span></span>

## <span data-ttu-id="101e4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="101e4-104">SYNOPSIS</span></span>
<span data-ttu-id="101e4-105">Mostra um arquivo ou uma cadeia de caracteres de redução no console de forma amigável usando sequências de escape VT100 ou em um navegador usando HTML.</span><span class="sxs-lookup"><span data-stu-id="101e4-105">Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in a browser using HTML.</span></span>

## <span data-ttu-id="101e4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="101e4-106">SYNTAX</span></span>

### <span data-ttu-id="101e4-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="101e4-107">Path (Default)</span></span>

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="101e4-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="101e4-108">InputObject</span></span>

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="101e4-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="101e4-109">LiteralPath</span></span>

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## <span data-ttu-id="101e4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="101e4-110">DESCRIPTION</span></span>

<span data-ttu-id="101e4-111">O `Show-Markdown` cmdlet é usado para renderizar a redução em um formato legível por humanos, seja em um terminal ou em um navegador.</span><span class="sxs-lookup"><span data-stu-id="101e4-111">The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.</span></span>

<span data-ttu-id="101e4-112">`Show-Markdown` pode retornar uma cadeia de caracteres que inclui as sequências de escape VT100 que o terminal renderiza (se ele der suporte a sequências de escape VT100).</span><span class="sxs-lookup"><span data-stu-id="101e4-112">`Show-Markdown` can return a string that includes the VT100 escape sequences which the terminal renders (if it supports VT100 escape sequences).</span></span> <span data-ttu-id="101e4-113">Isso é usado principalmente para exibir arquivos de redução em um terminal.</span><span class="sxs-lookup"><span data-stu-id="101e4-113">This is primarily used for viewing Markdown files in a terminal.</span></span> <span data-ttu-id="101e4-114">Você também pode obter essa cadeia de caracteres por meio da `ConvertFrom-Markdown` especificação do parâmetro **AsVT100EncodedString** .</span><span class="sxs-lookup"><span data-stu-id="101e4-114">You can also get this string via the `ConvertFrom-Markdown` by specifying the **AsVT100EncodedString** parameter.</span></span>

<span data-ttu-id="101e4-115">`Show-Markdown` também tem a capacidade de abrir um navegador e mostrar uma versão renderizada da redução.</span><span class="sxs-lookup"><span data-stu-id="101e4-115">`Show-Markdown` also has the ability to open a browser and show you a rendered version of the Markdown.</span></span> <span data-ttu-id="101e4-116">Ele renderiza a redução ao transformá-lo em HTML e abrir o arquivo HTML no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="101e4-116">It renders the Markdown by turning it into HTML and opening the HTML file in your default browser.</span></span>

<span data-ttu-id="101e4-117">Você pode alterar como os `Show-Markdown` renderizações são reparados em um terminal usando o `Set-MarkdownOption` .</span><span class="sxs-lookup"><span data-stu-id="101e4-117">You can change how `Show-Markdown` renders Markdown in a terminal by using `Set-MarkdownOption`.</span></span>

<span data-ttu-id="101e4-118">Esse cmdlet foi introduzido no PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="101e4-118">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="101e4-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="101e4-119">EXAMPLES</span></span>

### <span data-ttu-id="101e4-120">Exemplo 1: exemplo simples especificando um caminho</span><span class="sxs-lookup"><span data-stu-id="101e4-120">Example 1: Simple example specifying a path</span></span>

```powershell
Show-Markdown -Path ./README.md
```

### <span data-ttu-id="101e4-121">Exemplo 2: exemplo simples especificando uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="101e4-121">Example 2: Simple example specifying a string</span></span>

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### <span data-ttu-id="101e4-122">Exemplo 2: abrindo a redução em um navegador</span><span class="sxs-lookup"><span data-stu-id="101e4-122">Example 2: Opening Markdown in a browser</span></span>

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## <span data-ttu-id="101e4-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="101e4-123">PARAMETERS</span></span>

### <span data-ttu-id="101e4-124">-InputObject</span><span class="sxs-lookup"><span data-stu-id="101e4-124">-InputObject</span></span>

<span data-ttu-id="101e4-125">Uma cadeia de caracteres de redução que será mostrada no terminal.</span><span class="sxs-lookup"><span data-stu-id="101e4-125">A Markdown string that will be shown in the terminal.</span></span> <span data-ttu-id="101e4-126">Se você não passar um formato com suporte, o `Show-Markdown` emitirá um erro.</span><span class="sxs-lookup"><span data-stu-id="101e4-126">If you do not pass in a supported format, `Show-Markdown` will emit an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="101e4-127">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="101e4-127">-LiteralPath</span></span>

<span data-ttu-id="101e4-128">Especifica o caminho para um arquivo de redução.</span><span class="sxs-lookup"><span data-stu-id="101e4-128">Specifies the path to a Markdown file.</span></span> <span data-ttu-id="101e4-129">Ao contrário do parâmetro Path, o valor de LiteralPath é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="101e4-129">Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed.</span></span> <span data-ttu-id="101e4-130">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="101e4-130">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="101e4-131">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="101e4-131">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="101e4-132">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="101e4-132">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="101e4-133">-Path</span><span class="sxs-lookup"><span data-stu-id="101e4-133">-Path</span></span>

<span data-ttu-id="101e4-134">Especifica o caminho para um arquivo de redução a ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="101e4-134">Specifies the path to a Markdown file to be rendered.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="101e4-135">-UseBrowser</span><span class="sxs-lookup"><span data-stu-id="101e4-135">-UseBrowser</span></span>

<span data-ttu-id="101e4-136">Compila a entrada de redução como HTML e a abre no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="101e4-136">Compiles the Markdown input as HTML and opens it in your default browser.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="101e4-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="101e4-137">CommonParameters</span></span>

<span data-ttu-id="101e4-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="101e4-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="101e4-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="101e4-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="101e4-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="101e4-140">INPUTS</span></span>

### <span data-ttu-id="101e4-141">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="101e4-141">System.Management.Automation.PSObject</span></span>

### <span data-ttu-id="101e4-142">System.String[]</span><span class="sxs-lookup"><span data-stu-id="101e4-142">System.String[]</span></span>

## <span data-ttu-id="101e4-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="101e4-143">OUTPUTS</span></span>

### <span data-ttu-id="101e4-144">System.String</span><span class="sxs-lookup"><span data-stu-id="101e4-144">System.String</span></span>

## <span data-ttu-id="101e4-145">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="101e4-145">NOTES</span></span>

## <span data-ttu-id="101e4-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="101e4-146">RELATED LINKS</span></span>

[<span data-ttu-id="101e4-147">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="101e4-147">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

