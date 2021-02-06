---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: 230f027a021017e948c8c53e5e6d0c092127ad85
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598637"
---
# <span data-ttu-id="11c01-102">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="11c01-102">New-FileCatalog</span></span>

## <span data-ttu-id="11c01-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="11c01-103">SYNOPSIS</span></span>
<span data-ttu-id="11c01-104">`New-FileCatalog` Cria um arquivo de catálogo de hashes de arquivo que pode ser usado para validar a autenticidade de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="11c01-104">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="11c01-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11c01-105">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="11c01-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="11c01-106">DESCRIPTION</span></span>

<span data-ttu-id="11c01-107">`New-FileCatalog` Cria um [arquivo de catálogo do Windows](/windows-hardware/drivers/install/catalog-files) para um conjunto de pastas e arquivos.</span><span class="sxs-lookup"><span data-stu-id="11c01-107">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span> <span data-ttu-id="11c01-108">Esse arquivo de catálogo contém hashes para todos os arquivos nos caminhos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="11c01-108">This catalog file contains hashes for all files in the provided paths.</span></span> <span data-ttu-id="11c01-109">Os usuários podem então distribuir o catálogo com seus arquivos para que os usuários possam validar se alguma alteração foi feita nas pastas desde a hora de criação do catálogo.</span><span class="sxs-lookup"><span data-stu-id="11c01-109">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="11c01-110">Há suporte para as versões 1 e 2 do catálogo.</span><span class="sxs-lookup"><span data-stu-id="11c01-110">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="11c01-111">A versão 1 usa o algoritmo de hash SHA1 (preterido) para criar hashes de arquivo, e a versão 2 usa SHA256.</span><span class="sxs-lookup"><span data-stu-id="11c01-111">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span> <span data-ttu-id="11c01-112">Não há suporte para a versão 2 do catálogo no Windows Server 2008 R2 ou no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="11c01-112">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="11c01-113">Você deve usar a versão 2 do catálogo no Windows 8, no Windows Server 2012 e nos sistemas operacionais posteriores.</span><span class="sxs-lookup"><span data-stu-id="11c01-113">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="11c01-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="11c01-114">EXAMPLES</span></span>

### <span data-ttu-id="11c01-115">Exemplo 1: criar um catálogo de arquivos para `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="11c01-115">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="11c01-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11c01-116">PARAMETERS</span></span>

### <span data-ttu-id="11c01-117">-CatalogFilePath</span><span class="sxs-lookup"><span data-stu-id="11c01-117">-CatalogFilePath</span></span>

<span data-ttu-id="11c01-118">Um caminho para um arquivo ou pasta onde o arquivo de catálogo (. cat) deve ser colocado.</span><span class="sxs-lookup"><span data-stu-id="11c01-118">A path to a file or folder where the catalog file (.cat) should be placed.</span></span> <span data-ttu-id="11c01-119">Se um caminho de pasta for especificado, o nome de arquivo padrão `catalog.cat` será usado.</span><span class="sxs-lookup"><span data-stu-id="11c01-119">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

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

### <span data-ttu-id="11c01-120">-CatalogVersion</span><span class="sxs-lookup"><span data-stu-id="11c01-120">-CatalogVersion</span></span>

<span data-ttu-id="11c01-121">Aceita `1.0` ou `2.0` como valores possíveis para especificar a versão do catálogo.</span><span class="sxs-lookup"><span data-stu-id="11c01-121">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span> <span data-ttu-id="11c01-122">`1.0` deve ser usado evitado sempre que possível, pois ele usa o algoritmo de hash SHA-1 inseguro, enquanto `2.0` usa o algoritmo Secure SHA-256 no entanto, `1.0` é o único algoritmo com suporte no Windows 7 e no Server 2008r2.</span><span class="sxs-lookup"><span data-stu-id="11c01-122">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

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

### <span data-ttu-id="11c01-123">-Path</span><span class="sxs-lookup"><span data-stu-id="11c01-123">-Path</span></span>

<span data-ttu-id="11c01-124">Aceita um caminho ou uma matriz de caminhos para arquivos ou pastas que devem ser incluídos no arquivo de catálogo.</span><span class="sxs-lookup"><span data-stu-id="11c01-124">Accepts a path or array of paths to files or folders that should be included in the catalog file.</span></span> <span data-ttu-id="11c01-125">Se uma pasta for especificada, todos os arquivos na pasta também serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="11c01-125">If a folder is specified, all the files in the folder will be included as well.</span></span>

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

### <span data-ttu-id="11c01-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="11c01-126">-Confirm</span></span>

<span data-ttu-id="11c01-127">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11c01-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="11c01-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="11c01-128">-WhatIf</span></span>

<span data-ttu-id="11c01-129">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="11c01-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="11c01-130">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="11c01-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="11c01-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="11c01-131">CommonParameters</span></span>

<span data-ttu-id="11c01-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="11c01-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11c01-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="11c01-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11c01-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="11c01-134">INPUTS</span></span>

### <span data-ttu-id="11c01-135">System.String</span><span class="sxs-lookup"><span data-stu-id="11c01-135">System.String</span></span>

<span data-ttu-id="11c01-136">O pipeline usa uma cadeia de caracteres que é usada como o nome de arquivo do catálogo.</span><span class="sxs-lookup"><span data-stu-id="11c01-136">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="11c01-137">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="11c01-137">OUTPUTS</span></span>

### <span data-ttu-id="11c01-138">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="11c01-138">System.IO.FileInfo</span></span>

## <span data-ttu-id="11c01-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="11c01-139">NOTES</span></span>

<span data-ttu-id="11c01-140">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="11c01-140">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="11c01-141">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="11c01-141">RELATED LINKS</span></span>

[<span data-ttu-id="11c01-142">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="11c01-142">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="11c01-143">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="11c01-143">PowerShellGet</span></span>](/powerShell/module/powershellget)
