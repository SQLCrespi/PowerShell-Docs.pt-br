---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: 23e74ae3e49d291b0ff6410c7d075a308b3d27e8
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343633"
---
# <span data-ttu-id="2e01c-103">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="2e01c-103">New-FileCatalog</span></span>

## <span data-ttu-id="2e01c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2e01c-104">SYNOPSIS</span></span>
<span data-ttu-id="2e01c-105">`New-FileCatalog` Cria um arquivo de catálogo de hashes de arquivo que pode ser usado para validar a autenticidade de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2e01c-105">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="2e01c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e01c-106">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2e01c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e01c-107">DESCRIPTION</span></span>

<span data-ttu-id="2e01c-108">`New-FileCatalog` Cria um [arquivo de catálogo do Windows](/windows-hardware/drivers/install/catalog-files) para um conjunto de pastas e arquivos.</span><span class="sxs-lookup"><span data-stu-id="2e01c-108">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span> <span data-ttu-id="2e01c-109">Esse arquivo de catálogo contém hashes para todos os arquivos nos caminhos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="2e01c-109">This catalog file contains hashes for all files in the provided paths.</span></span> <span data-ttu-id="2e01c-110">Os usuários podem então distribuir o catálogo com seus arquivos para que os usuários possam validar se alguma alteração foi feita nas pastas desde a hora de criação do catálogo.</span><span class="sxs-lookup"><span data-stu-id="2e01c-110">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="2e01c-111">Há suporte para as versões 1 e 2 do catálogo.</span><span class="sxs-lookup"><span data-stu-id="2e01c-111">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="2e01c-112">A versão 1 usa o algoritmo de hash SHA1 (preterido) para criar hashes de arquivo, e a versão 2 usa SHA256.</span><span class="sxs-lookup"><span data-stu-id="2e01c-112">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span> <span data-ttu-id="2e01c-113">Não há suporte para a versão 2 do catálogo no Windows Server 2008 R2 ou no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2e01c-113">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="2e01c-114">Você deve usar a versão 2 do catálogo no Windows 8, no Windows Server 2012 e nos sistemas operacionais posteriores.</span><span class="sxs-lookup"><span data-stu-id="2e01c-114">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="2e01c-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2e01c-115">EXAMPLES</span></span>

### <span data-ttu-id="2e01c-116">Exemplo 1: criar um catálogo de arquivos para `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="2e01c-116">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="2e01c-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e01c-117">PARAMETERS</span></span>

### <span data-ttu-id="2e01c-118">-CatalogFilePath</span><span class="sxs-lookup"><span data-stu-id="2e01c-118">-CatalogFilePath</span></span>

<span data-ttu-id="2e01c-119">Um caminho para um arquivo ou pasta onde o arquivo de catálogo (. cat) deve ser colocado.</span><span class="sxs-lookup"><span data-stu-id="2e01c-119">A path to a file or folder where the catalog file (.cat) should be placed.</span></span> <span data-ttu-id="2e01c-120">Se um caminho de pasta for especificado, o nome de arquivo padrão `catalog.cat` será usado.</span><span class="sxs-lookup"><span data-stu-id="2e01c-120">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2e01c-121">-CatalogVersion</span><span class="sxs-lookup"><span data-stu-id="2e01c-121">-CatalogVersion</span></span>

<span data-ttu-id="2e01c-122">Aceita `1.0` ou `2.0` como valores possíveis para especificar a versão do catálogo.</span><span class="sxs-lookup"><span data-stu-id="2e01c-122">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span> <span data-ttu-id="2e01c-123">`1.0` deve ser usado evitado sempre que possível, pois ele usa o algoritmo de hash SHA-1 inseguro, enquanto `2.0` usa o algoritmo Secure SHA-256 no entanto, `1.0` é o único algoritmo com suporte no Windows 7 e no Server 2008r2.</span><span class="sxs-lookup"><span data-stu-id="2e01c-123">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e01c-124">-Path</span><span class="sxs-lookup"><span data-stu-id="2e01c-124">-Path</span></span>

<span data-ttu-id="2e01c-125">Aceita um caminho ou uma matriz de caminhos para arquivos ou pastas que devem ser incluídos no arquivo de catálogo.</span><span class="sxs-lookup"><span data-stu-id="2e01c-125">Accepts a path or array of paths to files or folders that should be included in the catalog file.</span></span> <span data-ttu-id="2e01c-126">Se uma pasta for especificada, todos os arquivos na pasta também serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="2e01c-126">If a folder is specified, all the files in the folder will be included as well.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2e01c-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2e01c-127">-Confirm</span></span>

<span data-ttu-id="2e01c-128">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2e01c-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2e01c-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2e01c-129">-WhatIf</span></span>

<span data-ttu-id="2e01c-130">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2e01c-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2e01c-131">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2e01c-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2e01c-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e01c-132">CommonParameters</span></span>

<span data-ttu-id="2e01c-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e01c-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e01c-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e01c-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e01c-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2e01c-135">INPUTS</span></span>

### <span data-ttu-id="2e01c-136">System.String</span><span class="sxs-lookup"><span data-stu-id="2e01c-136">System.String</span></span>

<span data-ttu-id="2e01c-137">O pipeline usa uma cadeia de caracteres que é usada como o nome de arquivo do catálogo.</span><span class="sxs-lookup"><span data-stu-id="2e01c-137">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="2e01c-138">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2e01c-138">OUTPUTS</span></span>

### <span data-ttu-id="2e01c-139">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="2e01c-139">System.IO.FileInfo</span></span>

## <span data-ttu-id="2e01c-140">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2e01c-140">NOTES</span></span>

<span data-ttu-id="2e01c-141">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="2e01c-141">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="2e01c-142">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2e01c-142">RELATED LINKS</span></span>

[<span data-ttu-id="2e01c-143">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="2e01c-143">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="2e01c-144">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="2e01c-144">PowerShellGet</span></span>](/powerShell/module/powershellget)
