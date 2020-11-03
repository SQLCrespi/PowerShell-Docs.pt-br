---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: eb753ea7713f3a8577aba6751a284b989c798d18
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193408"
---
# <span data-ttu-id="431b1-103">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="431b1-103">New-FileCatalog</span></span>

## <span data-ttu-id="431b1-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="431b1-104">SYNOPSIS</span></span>
<span data-ttu-id="431b1-105">`New-FileCatalog` Cria um arquivo de catálogo de hashes de arquivo que pode ser usado para validar a autenticidade de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="431b1-105">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="431b1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="431b1-106">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="431b1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="431b1-107">DESCRIPTION</span></span>

<span data-ttu-id="431b1-108">`New-FileCatalog` Cria um [arquivo de catálogo do Windows](/windows-hardware/drivers/install/catalog-files) para um conjunto de pastas e arquivos.</span><span class="sxs-lookup"><span data-stu-id="431b1-108">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span>
<span data-ttu-id="431b1-109">Esse arquivo de catálogo contém hashes para todos os arquivos nos caminhos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="431b1-109">This catalog file contains hashes for all files in the provided paths.</span></span>
<span data-ttu-id="431b1-110">Os usuários podem então distribuir o catálogo com seus arquivos para que os usuários possam validar se alguma alteração foi feita nas pastas desde a hora de criação do catálogo.</span><span class="sxs-lookup"><span data-stu-id="431b1-110">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="431b1-111">Há suporte para as versões 1 e 2 do catálogo.</span><span class="sxs-lookup"><span data-stu-id="431b1-111">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="431b1-112">A versão 1 usa o algoritmo de hash SHA1 (preterido) para criar hashes de arquivo, e a versão 2 usa SHA256.</span><span class="sxs-lookup"><span data-stu-id="431b1-112">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span>
<span data-ttu-id="431b1-113">Não há suporte para a versão 2 do catálogo no Windows Server 2008 R2 ou no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="431b1-113">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span>
<span data-ttu-id="431b1-114">Você deve usar a versão 2 do catálogo no Windows 8, no Windows Server 2012 e nos sistemas operacionais posteriores.</span><span class="sxs-lookup"><span data-stu-id="431b1-114">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="431b1-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="431b1-115">EXAMPLES</span></span>

### <span data-ttu-id="431b1-116">Exemplo 1: criar um catálogo de arquivos para `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="431b1-116">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="431b1-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="431b1-117">PARAMETERS</span></span>

### <span data-ttu-id="431b1-118">-CatalogFilePath</span><span class="sxs-lookup"><span data-stu-id="431b1-118">-CatalogFilePath</span></span>

<span data-ttu-id="431b1-119">Um caminho para um arquivo ou pasta onde o arquivo de catálogo (. cat) deve ser colocado.</span><span class="sxs-lookup"><span data-stu-id="431b1-119">A path to a file or folder where the catalog file (.cat) should be placed.</span></span>
<span data-ttu-id="431b1-120">Se um caminho de pasta for especificado, o nome de arquivo padrão `catalog.cat` será usado.</span><span class="sxs-lookup"><span data-stu-id="431b1-120">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

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

### <span data-ttu-id="431b1-121">-CatalogVersion</span><span class="sxs-lookup"><span data-stu-id="431b1-121">-CatalogVersion</span></span>

<span data-ttu-id="431b1-122">Aceita `1.0` ou `2.0` como valores possíveis para especificar a versão do catálogo.</span><span class="sxs-lookup"><span data-stu-id="431b1-122">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span>
<span data-ttu-id="431b1-123">`1.0` deve ser usado evitado sempre que possível, pois ele usa o algoritmo de hash SHA-1 inseguro, enquanto `2.0` usa o algoritmo Secure SHA-256 no entanto, `1.0` é o único algoritmo com suporte no Windows 7 e no Server 2008r2.</span><span class="sxs-lookup"><span data-stu-id="431b1-123">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

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

### <span data-ttu-id="431b1-124">-Path</span><span class="sxs-lookup"><span data-stu-id="431b1-124">-Path</span></span>

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

### <span data-ttu-id="431b1-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="431b1-125">-Confirm</span></span>

<span data-ttu-id="431b1-126">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="431b1-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="431b1-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="431b1-127">-WhatIf</span></span>

<span data-ttu-id="431b1-128">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="431b1-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="431b1-129">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="431b1-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="431b1-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="431b1-130">CommonParameters</span></span>

<span data-ttu-id="431b1-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="431b1-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="431b1-132">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="431b1-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="431b1-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="431b1-133">INPUTS</span></span>

### <span data-ttu-id="431b1-134">System.String</span><span class="sxs-lookup"><span data-stu-id="431b1-134">System.String</span></span>

<span data-ttu-id="431b1-135">O pipeline usa uma cadeia de caracteres que é usada como o nome de arquivo do catálogo.</span><span class="sxs-lookup"><span data-stu-id="431b1-135">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="431b1-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="431b1-136">OUTPUTS</span></span>

### <span data-ttu-id="431b1-137">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="431b1-137">System.IO.FileInfo</span></span>

## <span data-ttu-id="431b1-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="431b1-138">NOTES</span></span>

## <span data-ttu-id="431b1-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="431b1-139">RELATED LINKS</span></span>

[<span data-ttu-id="431b1-140">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="431b1-140">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="431b1-141">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="431b1-141">PowerShellGet</span></span>](/powerShell/module/powershellget)

