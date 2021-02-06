---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: d14e6332a2da5c86c4f8ada0d110c64e080437e7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598836"
---
# <span data-ttu-id="3e231-102">Show-Markdown</span><span class="sxs-lookup"><span data-stu-id="3e231-102">Show-Markdown</span></span>

## <span data-ttu-id="3e231-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3e231-103">SYNOPSIS</span></span>
<span data-ttu-id="3e231-104">Mostra um arquivo ou uma cadeia de caracteres de redução no console de forma amigável usando sequências de escape VT100 ou em um navegador usando HTML.</span><span class="sxs-lookup"><span data-stu-id="3e231-104">Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in a browser using HTML.</span></span>

## <span data-ttu-id="3e231-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3e231-105">SYNTAX</span></span>

### <span data-ttu-id="3e231-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="3e231-106">Path (Default)</span></span>

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="3e231-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="3e231-107">InputObject</span></span>

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### <span data-ttu-id="3e231-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3e231-108">LiteralPath</span></span>

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## <span data-ttu-id="3e231-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e231-109">DESCRIPTION</span></span>

<span data-ttu-id="3e231-110">O `Show-Markdown` cmdlet é usado para renderizar a redução em um formato legível por humanos, seja em um terminal ou em um navegador.</span><span class="sxs-lookup"><span data-stu-id="3e231-110">The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.</span></span>

<span data-ttu-id="3e231-111">`Show-Markdown` pode retornar uma cadeia de caracteres que inclui as sequências de escape VT100 que o terminal renderiza (se ele der suporte a sequências de escape VT100).</span><span class="sxs-lookup"><span data-stu-id="3e231-111">`Show-Markdown` can return a string that includes the VT100 escape sequences which the terminal renders (if it supports VT100 escape sequences).</span></span> <span data-ttu-id="3e231-112">Isso é usado principalmente para exibir arquivos de redução em um terminal.</span><span class="sxs-lookup"><span data-stu-id="3e231-112">This is primarily used for viewing Markdown files in a terminal.</span></span> <span data-ttu-id="3e231-113">Você também pode obter essa cadeia de caracteres por meio da `ConvertFrom-Markdown` especificação do parâmetro **AsVT100EncodedString** .</span><span class="sxs-lookup"><span data-stu-id="3e231-113">You can also get this string via the `ConvertFrom-Markdown` by specifying the **AsVT100EncodedString** parameter.</span></span>

<span data-ttu-id="3e231-114">`Show-Markdown` também tem a capacidade de abrir um navegador e mostrar uma versão renderizada da redução.</span><span class="sxs-lookup"><span data-stu-id="3e231-114">`Show-Markdown` also has the ability to open a browser and show you a rendered version of the Markdown.</span></span> <span data-ttu-id="3e231-115">Ele renderiza a redução ao transformá-lo em HTML e abrir o arquivo HTML no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="3e231-115">It renders the Markdown by turning it into HTML and opening the HTML file in your default browser.</span></span>

<span data-ttu-id="3e231-116">Você pode alterar como os `Show-Markdown` renderizações são reparados em um terminal usando o `Set-MarkdownOption` .</span><span class="sxs-lookup"><span data-stu-id="3e231-116">You can change how `Show-Markdown` renders Markdown in a terminal by using `Set-MarkdownOption`.</span></span>

<span data-ttu-id="3e231-117">Esse cmdlet foi introduzido no PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="3e231-117">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="3e231-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3e231-118">EXAMPLES</span></span>

### <span data-ttu-id="3e231-119">Exemplo 1: exemplo simples especificando um caminho</span><span class="sxs-lookup"><span data-stu-id="3e231-119">Example 1: Simple example specifying a path</span></span>

```powershell
Show-Markdown -Path ./README.md
```

### <span data-ttu-id="3e231-120">Exemplo 2: exemplo simples especificando uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3e231-120">Example 2: Simple example specifying a string</span></span>

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### <span data-ttu-id="3e231-121">Exemplo 2: abrindo a redução em um navegador</span><span class="sxs-lookup"><span data-stu-id="3e231-121">Example 2: Opening Markdown in a browser</span></span>

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## <span data-ttu-id="3e231-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3e231-122">PARAMETERS</span></span>

### <span data-ttu-id="3e231-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3e231-123">-InputObject</span></span>

<span data-ttu-id="3e231-124">Uma cadeia de caracteres de redução que será mostrada no terminal.</span><span class="sxs-lookup"><span data-stu-id="3e231-124">A Markdown string that will be shown in the terminal.</span></span> <span data-ttu-id="3e231-125">Se você não passar um formato com suporte, o `Show-Markdown` emitirá um erro.</span><span class="sxs-lookup"><span data-stu-id="3e231-125">If you do not pass in a supported format, `Show-Markdown` will emit an error.</span></span>

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

### <span data-ttu-id="3e231-126">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3e231-126">-LiteralPath</span></span>

<span data-ttu-id="3e231-127">Especifica o caminho para um arquivo de redução.</span><span class="sxs-lookup"><span data-stu-id="3e231-127">Specifies the path to a Markdown file.</span></span> <span data-ttu-id="3e231-128">Ao contrário do parâmetro Path, o valor de LiteralPath é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="3e231-128">Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed.</span></span> <span data-ttu-id="3e231-129">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="3e231-129">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3e231-130">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="3e231-130">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3e231-131">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="3e231-131">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3e231-132">-Path</span><span class="sxs-lookup"><span data-stu-id="3e231-132">-Path</span></span>

<span data-ttu-id="3e231-133">Especifica o caminho para um arquivo de redução a ser renderizado.</span><span class="sxs-lookup"><span data-stu-id="3e231-133">Specifies the path to a Markdown file to be rendered.</span></span>

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

### <span data-ttu-id="3e231-134">-UseBrowser</span><span class="sxs-lookup"><span data-stu-id="3e231-134">-UseBrowser</span></span>

<span data-ttu-id="3e231-135">Compila a entrada de redução como HTML e a abre no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="3e231-135">Compiles the Markdown input as HTML and opens it in your default browser.</span></span>

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

### <span data-ttu-id="3e231-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3e231-136">CommonParameters</span></span>

<span data-ttu-id="3e231-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3e231-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3e231-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3e231-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3e231-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3e231-139">INPUTS</span></span>

### <span data-ttu-id="3e231-140">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="3e231-140">System.Management.Automation.PSObject</span></span>

### <span data-ttu-id="3e231-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="3e231-141">System.String[]</span></span>

## <span data-ttu-id="3e231-142">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3e231-142">OUTPUTS</span></span>

### <span data-ttu-id="3e231-143">System.String</span><span class="sxs-lookup"><span data-stu-id="3e231-143">System.String</span></span>

## <span data-ttu-id="3e231-144">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3e231-144">NOTES</span></span>

## <span data-ttu-id="3e231-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3e231-145">RELATED LINKS</span></span>

[<span data-ttu-id="3e231-146">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="3e231-146">ConvertFrom-Markdown</span></span>](ConvertFrom-Markdown.md)

