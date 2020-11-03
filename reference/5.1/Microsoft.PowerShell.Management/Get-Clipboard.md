---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "93195342"
---
# <span data-ttu-id="e7821-103">Get-Clipboard</span><span class="sxs-lookup"><span data-stu-id="e7821-103">Get-Clipboard</span></span>

## <span data-ttu-id="e7821-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e7821-104">SYNOPSIS</span></span>
<span data-ttu-id="e7821-105">Obtém a entrada da área de transferência atual do Windows.</span><span class="sxs-lookup"><span data-stu-id="e7821-105">Gets the current Windows clipboard entry.</span></span>

## <span data-ttu-id="e7821-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7821-106">SYNTAX</span></span>

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="e7821-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7821-107">DESCRIPTION</span></span>

<span data-ttu-id="e7821-108">O `Get-Clipboard` cmdlet obtém a entrada da área de transferência atual do Windows.</span><span class="sxs-lookup"><span data-stu-id="e7821-108">The `Get-Clipboard` cmdlet gets the current Windows clipboard entry.</span></span> <span data-ttu-id="e7821-109">Várias linhas de texto são retornadas como uma matriz de cadeias de caracteres semelhantes a `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="e7821-109">Multiple lines of text are returned as an array of strings similar to `Get-Content`.</span></span>

## <span data-ttu-id="e7821-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e7821-110">EXAMPLES</span></span>

### <span data-ttu-id="e7821-111">Exemplo 1: obter o conteúdo da área de transferência e exibi-lo para a linha de comando</span><span class="sxs-lookup"><span data-stu-id="e7821-111">Example 1: Get the content of the clipboard and display it to the command-line</span></span>

<span data-ttu-id="e7821-112">Neste exemplo, clicamos com o botão direito do mouse em uma imagem em um navegador e escolhemos a ação de **cópia** .</span><span class="sxs-lookup"><span data-stu-id="e7821-112">In this example we have right-clicked on an image in a browser and chose the **Copy** action.</span></span> <span data-ttu-id="e7821-113">O comando a seguir exibe o link, como uma URL, da imagem que é armazenada na área de transferência.</span><span class="sxs-lookup"><span data-stu-id="e7821-113">The following command displays the link, as a URL, of the image that is stored in the clipboard.</span></span>

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### <span data-ttu-id="e7821-114">Exemplo 2: obter o conteúdo da área de transferência em um formato específico</span><span class="sxs-lookup"><span data-stu-id="e7821-114">Example 2: Get the content of the clipboard in a specific format</span></span>

<span data-ttu-id="e7821-115">Neste exemplo, copiamos arquivos para a área de transferência no Windows Explorerby selecionando-os e pressionando <kbd>Ctrl-C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e7821-115">In this example we copied files to the clipboard in Windows Explorerby selecting them and pressing <kbd>Ctrl-C</kbd>.</span></span> <span data-ttu-id="e7821-116">Usando o comando a seguir, você pode acessar o conteúdo da área de transferência como uma lista de arquivos:</span><span class="sxs-lookup"><span data-stu-id="e7821-116">Using the following command, you can access the contents of the clipboard as a list of files:</span></span>

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## <span data-ttu-id="e7821-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7821-117">PARAMETERS</span></span>

### <span data-ttu-id="e7821-118">-Formato</span><span class="sxs-lookup"><span data-stu-id="e7821-118">-Format</span></span>

<span data-ttu-id="e7821-119">Especifica o tipo, ou formato, da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="e7821-119">Specifies the type, or format, of the clipboard.</span></span> <span data-ttu-id="e7821-120">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="e7821-120">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e7821-121">Texto</span><span class="sxs-lookup"><span data-stu-id="e7821-121">Text</span></span>
- <span data-ttu-id="e7821-122">FileDropList</span><span class="sxs-lookup"><span data-stu-id="e7821-122">FileDropList</span></span>
- <span data-ttu-id="e7821-123">Imagem</span><span class="sxs-lookup"><span data-stu-id="e7821-123">Image</span></span>
- <span data-ttu-id="e7821-124">Áudio</span><span class="sxs-lookup"><span data-stu-id="e7821-124">Audio</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e7821-125">-RAW</span><span class="sxs-lookup"><span data-stu-id="e7821-125">-Raw</span></span>

<span data-ttu-id="e7821-126">Obtém todo o conteúdo da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="e7821-126">Gets the entire contents of the clipboard.</span></span> <span data-ttu-id="e7821-127">O texto multilinha é retornado como uma única cadeia de caracteres de várias linhas em vez de uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e7821-127">Multiline text is returned as a single multiline string rather than an array of strings.</span></span>

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

### <span data-ttu-id="e7821-128">-Textformatype</span><span class="sxs-lookup"><span data-stu-id="e7821-128">-TextFormatType</span></span>

<span data-ttu-id="e7821-129">Especifica o tipo de formato de dados de texto da área de transferência.</span><span class="sxs-lookup"><span data-stu-id="e7821-129">Specifies the text data format type of the clipboard.</span></span> <span data-ttu-id="e7821-130">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="e7821-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e7821-131">Texto</span><span class="sxs-lookup"><span data-stu-id="e7821-131">Text</span></span>
- <span data-ttu-id="e7821-132">UnicodeText</span><span class="sxs-lookup"><span data-stu-id="e7821-132">UnicodeText</span></span>
- <span data-ttu-id="e7821-133">RTF</span><span class="sxs-lookup"><span data-stu-id="e7821-133">Rtf</span></span>
- <span data-ttu-id="e7821-134">Html</span><span class="sxs-lookup"><span data-stu-id="e7821-134">Html</span></span>
- <span data-ttu-id="e7821-135">CommaSeparatedValue</span><span class="sxs-lookup"><span data-stu-id="e7821-135">CommaSeparatedValue</span></span>

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e7821-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e7821-136">CommonParameters</span></span>

<span data-ttu-id="e7821-137">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e7821-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e7821-138">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e7821-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e7821-139">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e7821-139">INPUTS</span></span>

## <span data-ttu-id="e7821-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e7821-140">OUTPUTS</span></span>

### <span data-ttu-id="e7821-141">System. String, System. IO. FileInfo, System. IO. Stream, System. Drawing. Image</span><span class="sxs-lookup"><span data-stu-id="e7821-141">System.String, System.IO.FileInfo, System.IO.Stream, System.Drawing.Image</span></span>

## <span data-ttu-id="e7821-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e7821-142">NOTES</span></span>

## <span data-ttu-id="e7821-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e7821-143">RELATED LINKS</span></span>

[<span data-ttu-id="e7821-144">Set-Clipboard</span><span class="sxs-lookup"><span data-stu-id="e7821-144">Set-Clipboard</span></span>](Set-Clipboard.md)
