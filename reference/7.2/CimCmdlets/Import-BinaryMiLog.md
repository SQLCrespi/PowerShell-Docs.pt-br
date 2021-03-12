---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: cf85999f01e12dd24fee0ce377f434446218b935
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195218"
---
# <span data-ttu-id="1dee4-102">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="1dee4-102">Import-BinaryMiLog</span></span>

## <span data-ttu-id="1dee4-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1dee4-103">SYNOPSIS</span></span>
<span data-ttu-id="1dee4-104">Usado para recriar os objetos salvos com base no conteúdo de um arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="1dee4-104">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="1dee4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1dee4-105">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="1dee4-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1dee4-106">DESCRIPTION</span></span>

<span data-ttu-id="1dee4-107">Use este cmdlet para recriar objetos salvos com base no conteúdo de um arquivo de exportação criado pelo `Export-BinaryMILog` .</span><span class="sxs-lookup"><span data-stu-id="1dee4-107">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="1dee4-108">Esse cmdlet é semelhante a `Import-Clixml` , exceto que `Export-BinaryMILog` armazena o objeto resultante em um arquivo binário codificado.</span><span class="sxs-lookup"><span data-stu-id="1dee4-108">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="1dee4-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1dee4-109">EXAMPLES</span></span>

### <span data-ttu-id="1dee4-110">Exemplo 1-restaurar objetos exportados para um arquivo</span><span class="sxs-lookup"><span data-stu-id="1dee4-110">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="1dee4-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1dee4-111">PARAMETERS</span></span>

### <span data-ttu-id="1dee4-112">-Path</span><span class="sxs-lookup"><span data-stu-id="1dee4-112">-Path</span></span>

<span data-ttu-id="1dee4-113">Especifica o caminho do arquivo no qual armazenar a representação binária do objeto.</span><span class="sxs-lookup"><span data-stu-id="1dee4-113">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="1dee4-114">O parâmetro **path** dá suporte a curingas e caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="1dee4-114">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="1dee4-115">Esse cmdlet gera um erro se o caminho for resolvido para mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1dee4-115">This cmdlet generates an error if the path resolves to more than one file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1dee4-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1dee4-116">CommonParameters</span></span>
<span data-ttu-id="1dee4-117">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1dee4-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1dee4-118">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1dee4-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1dee4-119">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1dee4-119">INPUTS</span></span>

### <span data-ttu-id="1dee4-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1dee4-120">None</span></span>

## <span data-ttu-id="1dee4-121">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1dee4-121">OUTPUTS</span></span>

### <span data-ttu-id="1dee4-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="1dee4-122">System.Object</span></span>

## <span data-ttu-id="1dee4-123">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1dee4-123">NOTES</span></span>

## <span data-ttu-id="1dee4-124">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1dee4-124">RELATED LINKS</span></span>
