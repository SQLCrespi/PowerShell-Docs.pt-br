---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: f83718f56a3c01ca59fcda697201ff4a3598b54a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193557"
---
# <span data-ttu-id="06f6a-103">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="06f6a-103">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="06f6a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="06f6a-104">SYNOPSIS</span></span>
<span data-ttu-id="06f6a-105">Importa valores de um `.PSD1` arquivo sem invocar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="06f6a-105">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="06f6a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06f6a-106">SYNTAX</span></span>

### <span data-ttu-id="06f6a-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="06f6a-107">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="06f6a-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="06f6a-108">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="06f6a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06f6a-109">DESCRIPTION</span></span>

<span data-ttu-id="06f6a-110">O `Import-PowerShellDataFile` cmdlet importa com segurança pares de chave-valor de Hashtables definidos em `.PSD1` um arquivo.</span><span class="sxs-lookup"><span data-stu-id="06f6a-110">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="06f6a-111">Os valores podem ser importados usando `Invoke-Expression` o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="06f6a-111">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="06f6a-112">No entanto, o `Invoke-Expression` executa qualquer código contido no arquivo.</span><span class="sxs-lookup"><span data-stu-id="06f6a-112">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="06f6a-113">Isso pode produzir resultados indesejados ou executar código não seguro.</span><span class="sxs-lookup"><span data-stu-id="06f6a-113">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="06f6a-114">`Import-PowerShellDataFile` importa os dados sem invocar o código.</span><span class="sxs-lookup"><span data-stu-id="06f6a-114">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span>

## <span data-ttu-id="06f6a-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="06f6a-115">EXAMPLES</span></span>

### <span data-ttu-id="06f6a-116">Exemplo 1: recuperar valores de PSD1</span><span class="sxs-lookup"><span data-stu-id="06f6a-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="06f6a-117">Este exemplo recupera os pares chave-valor armazenados na tabela de hash mantidos dentro do `Configuration.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="06f6a-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="06f6a-118">`Get-Content` é usado para mostrar o conteúdo do `Configuration.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="06f6a-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

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

## <span data-ttu-id="06f6a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06f6a-119">PARAMETERS</span></span>

### <span data-ttu-id="06f6a-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="06f6a-120">-LiteralPath</span></span>

<span data-ttu-id="06f6a-121">O caminho para o arquivo que está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="06f6a-121">The path to the file being imported.</span></span> <span data-ttu-id="06f6a-122">Todos os caracteres no caminho são tratados como valores literais.</span><span class="sxs-lookup"><span data-stu-id="06f6a-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="06f6a-123">Os caracteres curinga não são processados.</span><span class="sxs-lookup"><span data-stu-id="06f6a-123">Wildcard characters are not processed.</span></span>

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

### <span data-ttu-id="06f6a-124">-Path</span><span class="sxs-lookup"><span data-stu-id="06f6a-124">-Path</span></span>

<span data-ttu-id="06f6a-125">O caminho para o arquivo que está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="06f6a-125">The path to the file being imported.</span></span> <span data-ttu-id="06f6a-126">Caracteres curinga são permitidos, mas apenas o primeiro arquivo correspondente é importado.</span><span class="sxs-lookup"><span data-stu-id="06f6a-126">Wildcards are allowed but only the first matching file is imported.</span></span>

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

### <span data-ttu-id="06f6a-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="06f6a-127">CommonParameters</span></span>

<span data-ttu-id="06f6a-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="06f6a-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06f6a-129">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="06f6a-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="06f6a-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="06f6a-130">INPUTS</span></span>

## <span data-ttu-id="06f6a-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="06f6a-131">OUTPUTS</span></span>

### <span data-ttu-id="06f6a-132">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="06f6a-132">System.Collections.Hashtable</span></span>

## <span data-ttu-id="06f6a-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="06f6a-133">NOTES</span></span>

## <span data-ttu-id="06f6a-134">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="06f6a-134">RELATED LINKS</span></span>

[<span data-ttu-id="06f6a-135">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="06f6a-135">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="06f6a-136">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="06f6a-136">Import-LocalizedData</span></span>](Import-LocalizedData.md)

