---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: d7942abff2974064c52a8a9ac086a280959b3a63
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "99603540"
---
# <span data-ttu-id="89356-102">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="89356-102">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="89356-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="89356-103">SYNOPSIS</span></span>
<span data-ttu-id="89356-104">Importa valores de um `.PSD1` arquivo sem invocar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="89356-104">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="89356-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89356-105">SYNTAX</span></span>

### <span data-ttu-id="89356-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="89356-106">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

### <span data-ttu-id="89356-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="89356-107">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

## <span data-ttu-id="89356-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89356-108">DESCRIPTION</span></span>

<span data-ttu-id="89356-109">O `Import-PowerShellDataFile` cmdlet importa com segurança pares de chave-valor de Hashtables definidos em `.PSD1` um arquivo.</span><span class="sxs-lookup"><span data-stu-id="89356-109">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="89356-110">Os valores podem ser importados usando `Invoke-Expression` o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="89356-110">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="89356-111">No entanto, o `Invoke-Expression` executa qualquer código contido no arquivo.</span><span class="sxs-lookup"><span data-stu-id="89356-111">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="89356-112">Isso pode produzir resultados indesejados ou executar código não seguro.</span><span class="sxs-lookup"><span data-stu-id="89356-112">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="89356-113">`Import-PowerShellDataFile` importa os dados sem invocar o código.</span><span class="sxs-lookup"><span data-stu-id="89356-113">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span> <span data-ttu-id="89356-114">Por padrão, há um limite de chave de 500, mas pode ser ignorado com a opção **SkipLimitCheck**</span><span class="sxs-lookup"><span data-stu-id="89356-114">By default there is a 500 key limit but can be bypassed with the **SkipLimitCheck** switch.</span></span>

## <span data-ttu-id="89356-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="89356-115">EXAMPLES</span></span>

### <span data-ttu-id="89356-116">Exemplo 1: recuperar valores de PSD1</span><span class="sxs-lookup"><span data-stu-id="89356-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="89356-117">Este exemplo recupera os pares chave-valor armazenados na tabela de hash mantidos dentro do `Configuration.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="89356-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="89356-118">`Get-Content` é usado para mostrar o conteúdo do `Configuration.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="89356-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## <span data-ttu-id="89356-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89356-119">PARAMETERS</span></span>

### <span data-ttu-id="89356-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="89356-120">-LiteralPath</span></span>

<span data-ttu-id="89356-121">O caminho para o arquivo que está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="89356-121">The path to the file being imported.</span></span> <span data-ttu-id="89356-122">Todos os caracteres no caminho são tratados como valores literais.</span><span class="sxs-lookup"><span data-stu-id="89356-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="89356-123">Os caracteres curinga não são processados.</span><span class="sxs-lookup"><span data-stu-id="89356-123">Wildcard characters are not processed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="89356-124">-Path</span><span class="sxs-lookup"><span data-stu-id="89356-124">-Path</span></span>

<span data-ttu-id="89356-125">O caminho para o arquivo que está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="89356-125">The path to the file being imported.</span></span> <span data-ttu-id="89356-126">Caracteres curinga são permitidos, mas apenas o primeiro arquivo correspondente é importado.</span><span class="sxs-lookup"><span data-stu-id="89356-126">Wildcards are allowed but only the first matching file is imported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="89356-127">-SkipLimitCheck</span><span class="sxs-lookup"><span data-stu-id="89356-127">-SkipLimitCheck</span></span>

<span data-ttu-id="89356-128">Por padrão, `Import-PowerShellDataFile` o importa apenas 500 chaves de um `.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="89356-128">By default `Import-PowerShellDataFile` imports only 500 keys from a `.psd1` file.</span></span> <span data-ttu-id="89356-129">Use **SkipLimitCheck** para importar mais de 500 chaves.</span><span class="sxs-lookup"><span data-stu-id="89356-129">Use **SkipLimitCheck** to import more than 500 keys.</span></span>

```yaml
Type: Switch
Parameter Sets: All
Aliases:

Required: False
Position: 0
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89356-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="89356-130">CommonParameters</span></span>

<span data-ttu-id="89356-131">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="89356-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89356-132">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="89356-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="89356-133">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="89356-133">INPUTS</span></span>

## <span data-ttu-id="89356-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="89356-134">OUTPUTS</span></span>

### <span data-ttu-id="89356-135">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="89356-135">System.Collections.Hashtable</span></span>

## <span data-ttu-id="89356-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="89356-136">NOTES</span></span>

## <span data-ttu-id="89356-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="89356-137">RELATED LINKS</span></span>

[<span data-ttu-id="89356-138">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="89356-138">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="89356-139">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="89356-139">Import-LocalizedData</span></span>](Import-LocalizedData.md)
