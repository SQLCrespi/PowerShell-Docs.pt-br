---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: 3775cea92ee32a54921bd9441de2c3e0f5915d1d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "93194848"
---
# <span data-ttu-id="22ee3-103">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="22ee3-103">Expand-Archive</span></span>

## <span data-ttu-id="22ee3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="22ee3-104">SYNOPSIS</span></span>
<span data-ttu-id="22ee3-105">Extrai arquivos de um arquivo morto especificado (zipado).</span><span class="sxs-lookup"><span data-stu-id="22ee3-105">Extracts files from a specified archive (zipped) file.</span></span>

## <span data-ttu-id="22ee3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="22ee3-106">SYNTAX</span></span>

### <span data-ttu-id="22ee3-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="22ee3-107">Path (Default)</span></span>

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="22ee3-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="22ee3-108">LiteralPath</span></span>

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="22ee3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="22ee3-109">DESCRIPTION</span></span>

<span data-ttu-id="22ee3-110">O `Expand-Archive` cmdlet extrai arquivos de um arquivo compactado especificado para uma pasta de destino especificada.</span><span class="sxs-lookup"><span data-stu-id="22ee3-110">The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder.</span></span> <span data-ttu-id="22ee3-111">Um arquivo morto permite que vários arquivos sejam empacotados e, opcionalmente, compactados em um único arquivo compactado para distribuição e armazenamento mais fáceis.</span><span class="sxs-lookup"><span data-stu-id="22ee3-111">An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.</span></span>

## <span data-ttu-id="22ee3-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="22ee3-112">EXAMPLES</span></span>

### <span data-ttu-id="22ee3-113">Exemplo 1: extrair o conteúdo de um arquivo morto</span><span class="sxs-lookup"><span data-stu-id="22ee3-113">Example 1: Extract the contents of an archive</span></span>

<span data-ttu-id="22ee3-114">Este exemplo extrai o conteúdo de um arquivo morto existente na pasta especificada pelo parâmetro **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="22ee3-114">This example extracts the contents of an existing archive file into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

<span data-ttu-id="22ee3-115">Neste exemplo, o parâmetro **LiteralPath** é usado porque o nome do arquivo contém caracteres que podem ser interpretados como curingas.</span><span class="sxs-lookup"><span data-stu-id="22ee3-115">In this example, the **LiteralPath** parameter is used because the filename contains characters that could be interpreted as wildcards.</span></span>

### <span data-ttu-id="22ee3-116">Exemplo 2: extrair o conteúdo de um arquivo morto na pasta atual</span><span class="sxs-lookup"><span data-stu-id="22ee3-116">Example 2: Extract the contents of an archive in the current folder</span></span>

<span data-ttu-id="22ee3-117">Este exemplo extrai o conteúdo de um arquivo morto existente na pasta atual para a pasta especificada pelo parâmetro **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="22ee3-117">This example extracts the contents of an existing archive file in the current folder into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## <span data-ttu-id="22ee3-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="22ee3-118">PARAMETERS</span></span>

### <span data-ttu-id="22ee3-119">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="22ee3-119">-DestinationPath</span></span>

<span data-ttu-id="22ee3-120">Por padrão, `Expand-Archive` o cria uma pasta no local atual que é do mesmo nome que o arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="22ee3-120">By default, `Expand-Archive` creates a folder in the current location that is the same name as the ZIP file.</span></span> <span data-ttu-id="22ee3-121">O parâmetro permite que você especifique o caminho para uma pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="22ee3-121">The parameter allows you to specify the path to a different folder.</span></span> <span data-ttu-id="22ee3-122">A pasta de destino será criada se não existir.</span><span class="sxs-lookup"><span data-stu-id="22ee3-122">The target folder is created if it does not exist.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: A folder in the current location
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="22ee3-123">-Force</span><span class="sxs-lookup"><span data-stu-id="22ee3-123">-Force</span></span>

<span data-ttu-id="22ee3-124">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="22ee3-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="22ee3-125">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="22ee3-125">-LiteralPath</span></span>

<span data-ttu-id="22ee3-126">Especifica o caminho para um arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="22ee3-126">Specifies the path to an archive file.</span></span> <span data-ttu-id="22ee3-127">Ao contrário do parâmetro **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="22ee3-127">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="22ee3-128">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="22ee3-128">Wildcard characters are not supported.</span></span> <span data-ttu-id="22ee3-129">Se o caminho incluir caracteres de escape, coloque cada caractere de escape entre aspas simples, para instruir o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="22ee3-129">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="22ee3-130">-PassThru</span><span class="sxs-lookup"><span data-stu-id="22ee3-130">-PassThru</span></span>

<span data-ttu-id="22ee3-131">Faz com que o cmdlet gere uma lista dos arquivos expandidos do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="22ee3-131">Causes the cmdlet to output a list of the files expanded from the archive.</span></span>

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

### <span data-ttu-id="22ee3-132">-Path</span><span class="sxs-lookup"><span data-stu-id="22ee3-132">-Path</span></span>

<span data-ttu-id="22ee3-133">Especifica o caminho para o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="22ee3-133">Specifies the path to the archive file.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="22ee3-134">-Confirm</span><span class="sxs-lookup"><span data-stu-id="22ee3-134">-Confirm</span></span>

<span data-ttu-id="22ee3-135">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="22ee3-135">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="22ee3-136">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="22ee3-136">-WhatIf</span></span>

<span data-ttu-id="22ee3-137">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="22ee3-137">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="22ee3-138">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="22ee3-138">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="22ee3-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="22ee3-139">CommonParameters</span></span>
<span data-ttu-id="22ee3-140">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="22ee3-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="22ee3-141">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="22ee3-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="22ee3-142">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="22ee3-142">INPUTS</span></span>

### <span data-ttu-id="22ee3-143">System.String</span><span class="sxs-lookup"><span data-stu-id="22ee3-143">System.String</span></span>

<span data-ttu-id="22ee3-144">É possível canalizar uma cadeia de caracteres que contém um caminho para um arquivo morto existente.</span><span class="sxs-lookup"><span data-stu-id="22ee3-144">You can pipe a string that contains a path to an existing archive file.</span></span>

## <span data-ttu-id="22ee3-145">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="22ee3-145">OUTPUTS</span></span>

### <span data-ttu-id="22ee3-146">System. IO. FileSystemInfo</span><span class="sxs-lookup"><span data-stu-id="22ee3-146">System.IO.FileSystemInfo</span></span>

<span data-ttu-id="22ee3-147">Quando o `-PassThru` parâmetro é usado, o cmdlet gera uma lista de arquivos que foram expandidos do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="22ee3-147">When the `-PassThru` parameter is used, the cmdlet outputs a list of files that were expanded from the archive.</span></span>

## <span data-ttu-id="22ee3-148">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="22ee3-148">NOTES</span></span>

<span data-ttu-id="22ee3-149">A [especificação do arquivo zip](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) não especifica uma maneira padrão de codificar nomes de arquivos que contenham caracteres não ASCII.</span><span class="sxs-lookup"><span data-stu-id="22ee3-149">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="22ee3-150">O `Compress-Archive` cmdlet usa a codificação UTF-8.</span><span class="sxs-lookup"><span data-stu-id="22ee3-150">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="22ee3-151">Outras ferramentas de arquivo ZIP podem usar um esquema de codificação diferente.</span><span class="sxs-lookup"><span data-stu-id="22ee3-151">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="22ee3-152">Ao extrair arquivos com nomes de arquivo não armazenados usando a codificação UTF-8, `Expand-Archive` o usa o valor bruto encontrado no arquivamento.</span><span class="sxs-lookup"><span data-stu-id="22ee3-152">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="22ee3-153">Isso pode resultar em um nome de arquivo diferente do nome de arquivo de origem armazenado no arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="22ee3-153">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="22ee3-154">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="22ee3-154">RELATED LINKS</span></span>

[<span data-ttu-id="22ee3-155">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="22ee3-155">Compress-Archive</span></span>](compress-archive.md)
