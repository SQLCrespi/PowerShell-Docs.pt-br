---
external help file: Microsoft.PowerShell.Archive-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: a4cf8970156f524578f7c9747aef1ffbf9f3eb58
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598840"
---
# <span data-ttu-id="aa0bd-102">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="aa0bd-102">Expand-Archive</span></span>

## <span data-ttu-id="aa0bd-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="aa0bd-103">SYNOPSIS</span></span>
<span data-ttu-id="aa0bd-104">Extrai arquivos de um arquivo morto especificado (zipado).</span><span class="sxs-lookup"><span data-stu-id="aa0bd-104">Extracts files from a specified archive (zipped) file.</span></span>

## <span data-ttu-id="aa0bd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa0bd-105">SYNTAX</span></span>

### <span data-ttu-id="aa0bd-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="aa0bd-106">Path (Default)</span></span>

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="aa0bd-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="aa0bd-107">LiteralPath</span></span>

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="aa0bd-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa0bd-108">DESCRIPTION</span></span>

<span data-ttu-id="aa0bd-109">O `Expand-Archive` cmdlet extrai arquivos de um arquivo compactado especificado para uma pasta de destino especificada.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-109">The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder.</span></span> <span data-ttu-id="aa0bd-110">Um arquivo morto permite que vários arquivos sejam empacotados e, opcionalmente, compactados em um único arquivo compactado para distribuição e armazenamento mais fáceis.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-110">An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.</span></span>

## <span data-ttu-id="aa0bd-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="aa0bd-111">EXAMPLES</span></span>

### <span data-ttu-id="aa0bd-112">Exemplo 1: extrair o conteúdo de um arquivo morto</span><span class="sxs-lookup"><span data-stu-id="aa0bd-112">Example 1: Extract the contents of an archive</span></span>

<span data-ttu-id="aa0bd-113">Este exemplo extrai o conteúdo de um arquivo morto existente na pasta especificada pelo parâmetro **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="aa0bd-113">This example extracts the contents of an existing archive file into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

<span data-ttu-id="aa0bd-114">Neste exemplo, o parâmetro **LiteralPath** é usado porque o nome do arquivo contém caracteres que podem ser interpretados como curingas.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-114">In this example, the **LiteralPath** parameter is used because the filename contains characters that could be interpreted as wildcards.</span></span>

### <span data-ttu-id="aa0bd-115">Exemplo 2: extrair o conteúdo de um arquivo morto na pasta atual</span><span class="sxs-lookup"><span data-stu-id="aa0bd-115">Example 2: Extract the contents of an archive in the current folder</span></span>

<span data-ttu-id="aa0bd-116">Este exemplo extrai o conteúdo de um arquivo morto existente na pasta atual para a pasta especificada pelo parâmetro **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="aa0bd-116">This example extracts the contents of an existing archive file in the current folder into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## <span data-ttu-id="aa0bd-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa0bd-117">PARAMETERS</span></span>

### <span data-ttu-id="aa0bd-118">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="aa0bd-118">-DestinationPath</span></span>

<span data-ttu-id="aa0bd-119">Por padrão, `Expand-Archive` o cria uma pasta no local atual que é do mesmo nome que o arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-119">By default, `Expand-Archive` creates a folder in the current location that is the same name as the ZIP file.</span></span> <span data-ttu-id="aa0bd-120">O parâmetro permite que você especifique o caminho para uma pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-120">The parameter allows you to specify the path to a different folder.</span></span> <span data-ttu-id="aa0bd-121">A pasta de destino será criada se não existir.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-121">The target folder is created if it does not exist.</span></span>

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

### <span data-ttu-id="aa0bd-122">-Force</span><span class="sxs-lookup"><span data-stu-id="aa0bd-122">-Force</span></span>

<span data-ttu-id="aa0bd-123">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-123">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="aa0bd-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="aa0bd-124">-LiteralPath</span></span>

<span data-ttu-id="aa0bd-125">Especifica o caminho para um arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-125">Specifies the path to an archive file.</span></span> <span data-ttu-id="aa0bd-126">Ao contrário do parâmetro **Path**, o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-126">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="aa0bd-127">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-127">Wildcard characters are not supported.</span></span> <span data-ttu-id="aa0bd-128">Se o caminho incluir caracteres de escape, coloque cada caractere de escape entre aspas simples, para instruir o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-128">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="aa0bd-129">-PassThru</span><span class="sxs-lookup"><span data-stu-id="aa0bd-129">-PassThru</span></span>

<span data-ttu-id="aa0bd-130">Faz com que o cmdlet gere uma lista dos arquivos expandidos do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-130">Causes the cmdlet to output a list of the files expanded from the archive.</span></span>

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

### <span data-ttu-id="aa0bd-131">-Path</span><span class="sxs-lookup"><span data-stu-id="aa0bd-131">-Path</span></span>

<span data-ttu-id="aa0bd-132">Especifica o caminho para o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-132">Specifies the path to the archive file.</span></span>

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

### <span data-ttu-id="aa0bd-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="aa0bd-133">-Confirm</span></span>

<span data-ttu-id="aa0bd-134">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="aa0bd-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="aa0bd-135">-WhatIf</span></span>

<span data-ttu-id="aa0bd-136">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-136">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="aa0bd-137">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="aa0bd-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa0bd-138">CommonParameters</span></span>
<span data-ttu-id="aa0bd-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa0bd-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa0bd-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa0bd-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="aa0bd-141">INPUTS</span></span>

### <span data-ttu-id="aa0bd-142">System.String</span><span class="sxs-lookup"><span data-stu-id="aa0bd-142">System.String</span></span>

<span data-ttu-id="aa0bd-143">É possível canalizar uma cadeia de caracteres que contém um caminho para um arquivo morto existente.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-143">You can pipe a string that contains a path to an existing archive file.</span></span>

## <span data-ttu-id="aa0bd-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="aa0bd-144">OUTPUTS</span></span>

### <span data-ttu-id="aa0bd-145">System. IO. FileSystemInfo</span><span class="sxs-lookup"><span data-stu-id="aa0bd-145">System.IO.FileSystemInfo</span></span>

<span data-ttu-id="aa0bd-146">Quando o `-PassThru` parâmetro é usado, o cmdlet gera uma lista de arquivos que foram expandidos do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-146">When the `-PassThru` parameter is used, the cmdlet outputs a list of files that were expanded from the archive.</span></span>

## <span data-ttu-id="aa0bd-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="aa0bd-147">NOTES</span></span>

<span data-ttu-id="aa0bd-148">A [especificação do arquivo zip](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) não especifica uma maneira padrão de codificar nomes de arquivos que contenham caracteres não ASCII.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-148">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="aa0bd-149">O `Compress-Archive` cmdlet usa a codificação UTF-8.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-149">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="aa0bd-150">Outras ferramentas de arquivo ZIP podem usar um esquema de codificação diferente.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-150">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="aa0bd-151">Ao extrair arquivos com nomes de arquivo não armazenados usando a codificação UTF-8, `Expand-Archive` o usa o valor bruto encontrado no arquivamento.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-151">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="aa0bd-152">Isso pode resultar em um nome de arquivo diferente do nome de arquivo de origem armazenado no arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="aa0bd-152">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="aa0bd-153">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="aa0bd-153">RELATED LINKS</span></span>

[<span data-ttu-id="aa0bd-154">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="aa0bd-154">Compress-Archive</span></span>](compress-archive.md)
