---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 8f5e11fca51bf92386c19a77fa9a66503b2d47a5
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343230"
---
# <span data-ttu-id="84019-103">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="84019-103">Test-FileCatalog</span></span>

## <span data-ttu-id="84019-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="84019-104">SYNOPSIS</span></span>
<span data-ttu-id="84019-105">`Test-FileCatalog` Valida se os hashes contidos em um arquivo de catálogo (. cat) correspondem aos hashes dos arquivos reais a fim de validar sua autenticidade.</span><span class="sxs-lookup"><span data-stu-id="84019-105">`Test-FileCatalog` validates whether the hashes contained in a catalog file (.cat) matches the hashes of the actual files in order to validate their authenticity.</span></span>

<span data-ttu-id="84019-106">Só há suporte para esse cmdlet no Windows.</span><span class="sxs-lookup"><span data-stu-id="84019-106">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="84019-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="84019-107">SYNTAX</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="84019-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="84019-108">DESCRIPTION</span></span>

<span data-ttu-id="84019-109">`Test-FileCatalog` valida a autenticidade dos arquivos comparando os hashes de arquivo de um arquivo de catálogo (. cat) com os hashes dos arquivos reais no disco.</span><span class="sxs-lookup"><span data-stu-id="84019-109">`Test-FileCatalog` validates the authenticity of files by comparing the file hashes of a catalog file (.cat) with the hashes of actual files on disk.</span></span> <span data-ttu-id="84019-110">Se detectar qualquer incompatibilidade, ele retornará o status como ValidationFailed.</span><span class="sxs-lookup"><span data-stu-id="84019-110">If it detects any mismatches, it returns the status as ValidationFailed.</span></span> <span data-ttu-id="84019-111">Os usuários podem recuperar todas essas informações usando o parâmetro -Detailed.</span><span class="sxs-lookup"><span data-stu-id="84019-111">Users can retrieve all this information by using the -Detailed parameter.</span></span> <span data-ttu-id="84019-112">Ele também exibe o status de assinatura do catálogo na Propriedade Signature, que é equivalente a chamar `Get-AuthenticodeSignature` o cmdlet no arquivo de catálogo.</span><span class="sxs-lookup"><span data-stu-id="84019-112">It also displays signing status of catalog in Signature property which is equivalent to calling `Get-AuthenticodeSignature` cmdlet on the catalog file.</span></span> <span data-ttu-id="84019-113">Os usuários também podem ignorar qualquer arquivo durante a validação usando o parâmetro -FilesToSkip.</span><span class="sxs-lookup"><span data-stu-id="84019-113">Users can also skip any file during validation by using the -FilesToSkip parameter.</span></span>

<span data-ttu-id="84019-114">Só há suporte para esse cmdlet no Windows.</span><span class="sxs-lookup"><span data-stu-id="84019-114">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="84019-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="84019-115">EXAMPLES</span></span>

### <span data-ttu-id="84019-116">Exemplo 1: criar e validar um catálogo de arquivos</span><span class="sxs-lookup"><span data-stu-id="84019-116">Example 1: Create and validate a file catalog</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### <span data-ttu-id="84019-117">Exemplo 2: validar um catálogo de arquivos com saída detalhada</span><span class="sxs-lookup"><span data-stu-id="84019-117">Example 2: Validate a file catalog with detailed output</span></span>

```powershell
Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Status        : Valid
HashAlgorithm : SHA256
CatalogItems  : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
PathItems     : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
Signature     : System.Management.Automation.Signature
```

## <span data-ttu-id="84019-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="84019-118">PARAMETERS</span></span>

### <span data-ttu-id="84019-119">-CatalogFilePath</span><span class="sxs-lookup"><span data-stu-id="84019-119">-CatalogFilePath</span></span>

<span data-ttu-id="84019-120">Um caminho para um arquivo de catálogo (. cat) que contém os hashes a serem usados para validação.</span><span class="sxs-lookup"><span data-stu-id="84019-120">A path to a catalog file (.cat) that contains the hashes to be used for validation.</span></span>

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

### <span data-ttu-id="84019-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="84019-121">-Confirm</span></span>

<span data-ttu-id="84019-122">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="84019-122">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="84019-123">-Detailed</span><span class="sxs-lookup"><span data-stu-id="84019-123">-Detailed</span></span>

<span data-ttu-id="84019-124">Retorna mais informações um objeto mais detalhado `CatalogInformation` que contém os arquivos testados, seus hashes esperados/reais e uma assinatura Authenticode do arquivo de catálogo se ele estiver assinado.</span><span class="sxs-lookup"><span data-stu-id="84019-124">Returns more information a more detailed `CatalogInformation` object that contains the files tested, their expected/actual hashes, and an Authenticode signature of the catalog file if it's signed.</span></span>

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

### <span data-ttu-id="84019-125">-FilesToSkip</span><span class="sxs-lookup"><span data-stu-id="84019-125">-FilesToSkip</span></span>

<span data-ttu-id="84019-126">Uma matriz de caminhos que não devem ser testados como parte da validação.</span><span class="sxs-lookup"><span data-stu-id="84019-126">An array of paths that should not be tested as part of the validation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="84019-127">-Path</span><span class="sxs-lookup"><span data-stu-id="84019-127">-Path</span></span>

<span data-ttu-id="84019-128">Uma pasta ou matriz de arquivos que devem ser validados em relação ao arquivo de catálogo.</span><span class="sxs-lookup"><span data-stu-id="84019-128">A folder or array of files that should be validated against the catalog file.</span></span>

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

### <span data-ttu-id="84019-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="84019-129">-WhatIf</span></span>

<span data-ttu-id="84019-130">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="84019-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="84019-131">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="84019-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="84019-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="84019-132">CommonParameters</span></span>

<span data-ttu-id="84019-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="84019-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="84019-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="84019-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="84019-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="84019-135">INPUTS</span></span>

### <span data-ttu-id="84019-136">System. IO. DirectoryInfo [], System. String []</span><span class="sxs-lookup"><span data-stu-id="84019-136">System.IO.DirectoryInfo[], System.String[]</span></span>

<span data-ttu-id="84019-137">O pipeline aceita uma matriz de cadeias de caracteres ou `DirectoryInfo` objetos que representam caminhos para os arquivos que precisam ser validados.</span><span class="sxs-lookup"><span data-stu-id="84019-137">The pipeline accepts an array of strings or `DirectoryInfo` objects that represent paths to the files that need to be validated.</span></span>

## <span data-ttu-id="84019-138">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="84019-138">OUTPUTS</span></span>

### <span data-ttu-id="84019-139">System. Management. Automation. CatalogValidationStatus</span><span class="sxs-lookup"><span data-stu-id="84019-139">System.Management.Automation.CatalogValidationStatus</span></span>

<span data-ttu-id="84019-140">O tipo de retorno padrão que contém um valor de `Valid` ou `ValidationFailed` .</span><span class="sxs-lookup"><span data-stu-id="84019-140">The default return type containing a value of either `Valid` or `ValidationFailed`.</span></span>

### <span data-ttu-id="84019-141">System. Management. Automation. CatalogInformation</span><span class="sxs-lookup"><span data-stu-id="84019-141">System.Management.Automation.CatalogInformation</span></span>

<span data-ttu-id="84019-142">Um objeto mais detalhado retornado ao usar `-Detailed` o que pode ser usado para analisar arquivos específicos que podem ou não ter aprovado a validação, quais hashes eram esperados versus encontrados e o algoritmo usado no catálogo.</span><span class="sxs-lookup"><span data-stu-id="84019-142">A more detailed object returned when using `-Detailed` which can be used to analyze specific files that may or may not have passed validation, which hashes were expected vs. found, and the algorithm used in the catalog.</span></span>

## <span data-ttu-id="84019-143">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="84019-143">NOTES</span></span>

## <span data-ttu-id="84019-144">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="84019-144">RELATED LINKS</span></span>

[<span data-ttu-id="84019-145">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="84019-145">New-FileCatalog</span></span>](New-FileCatalog.md)

[<span data-ttu-id="84019-146">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="84019-146">PowerShellGet</span></span>](/powershell/module/PowerShellGet)
