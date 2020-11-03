---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: c3ae9fa2189b3c8b41f092b1f2ac2dfca54aebc6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194058"
---
# <span data-ttu-id="7e8be-103">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="7e8be-103">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="7e8be-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7e8be-104">SYNOPSIS</span></span>
<span data-ttu-id="7e8be-105">Importa valores de um `.PSD1` arquivo sem invocar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7e8be-105">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="7e8be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e8be-106">SYNTAX</span></span>

### <span data-ttu-id="7e8be-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="7e8be-107">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="7e8be-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="7e8be-108">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="7e8be-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e8be-109">DESCRIPTION</span></span>

<span data-ttu-id="7e8be-110">O `Import-PowerShellDataFile` cmdlet importa com segurança pares de chave-valor de Hashtables definidos em `.PSD1` um arquivo.</span><span class="sxs-lookup"><span data-stu-id="7e8be-110">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="7e8be-111">Os valores podem ser importados usando `Invoke-Expression` o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7e8be-111">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="7e8be-112">No entanto, o `Invoke-Expression` executa qualquer código contido no arquivo.</span><span class="sxs-lookup"><span data-stu-id="7e8be-112">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="7e8be-113">Isso pode produzir resultados indesejados ou executar código não seguro.</span><span class="sxs-lookup"><span data-stu-id="7e8be-113">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="7e8be-114">`Import-PowerShellDataFile` importa os dados sem invocar o código.</span><span class="sxs-lookup"><span data-stu-id="7e8be-114">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span>

## <span data-ttu-id="7e8be-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7e8be-115">EXAMPLES</span></span>

### <span data-ttu-id="7e8be-116">Exemplo 1: recuperar valores de PSD1</span><span class="sxs-lookup"><span data-stu-id="7e8be-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="7e8be-117">Este exemplo recupera os pares chave-valor armazenados na tabela de hash mantidos dentro do `Configuration.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="7e8be-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="7e8be-118">`Get-Content` é usado para mostrar o conteúdo do `Configuration.psd1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="7e8be-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

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

## <span data-ttu-id="7e8be-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e8be-119">PARAMETERS</span></span>

### <span data-ttu-id="7e8be-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7e8be-120">-LiteralPath</span></span>

<span data-ttu-id="7e8be-121">O caminho para o arquivo que está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="7e8be-121">The path to the file being imported.</span></span> <span data-ttu-id="7e8be-122">Todos os caracteres no caminho são tratados como valores literais.</span><span class="sxs-lookup"><span data-stu-id="7e8be-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="7e8be-123">Os caracteres curinga não são processados.</span><span class="sxs-lookup"><span data-stu-id="7e8be-123">Wildcard characters are not processed.</span></span>

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

### <span data-ttu-id="7e8be-124">-Path</span><span class="sxs-lookup"><span data-stu-id="7e8be-124">-Path</span></span>

<span data-ttu-id="7e8be-125">O caminho para o arquivo que está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="7e8be-125">The path to the file being imported.</span></span> <span data-ttu-id="7e8be-126">Caracteres curinga são permitidos, mas apenas o primeiro arquivo correspondente é importado.</span><span class="sxs-lookup"><span data-stu-id="7e8be-126">Wildcards are allowed but only the first matching file is imported.</span></span>

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

### <span data-ttu-id="7e8be-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e8be-127">CommonParameters</span></span>

<span data-ttu-id="7e8be-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e8be-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e8be-129">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="7e8be-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7e8be-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7e8be-130">INPUTS</span></span>

## <span data-ttu-id="7e8be-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7e8be-131">OUTPUTS</span></span>

### <span data-ttu-id="7e8be-132">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="7e8be-132">System.Collections.Hashtable</span></span>

## <span data-ttu-id="7e8be-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7e8be-133">NOTES</span></span>

## <span data-ttu-id="7e8be-134">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7e8be-134">RELATED LINKS</span></span>

[<span data-ttu-id="7e8be-135">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="7e8be-135">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="7e8be-136">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="7e8be-136">Import-LocalizedData</span></span>](Import-LocalizedData.md)
