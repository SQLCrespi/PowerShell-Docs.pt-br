---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: ce5dd31170bc47edaa04ca3c31deab62dc4ec354
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193422"
---
# <span data-ttu-id="974d5-103">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="974d5-103">Import-BinaryMiLog</span></span>

## <span data-ttu-id="974d5-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="974d5-104">SYNOPSIS</span></span>
<span data-ttu-id="974d5-105">Usado para recriar os objetos salvos com base no conteúdo de um arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="974d5-105">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="974d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="974d5-106">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="974d5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="974d5-107">DESCRIPTION</span></span>

<span data-ttu-id="974d5-108">Use este cmdlet para recriar objetos salvos com base no conteúdo de um arquivo de exportação criado pelo `Export-BinaryMILog` .</span><span class="sxs-lookup"><span data-stu-id="974d5-108">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="974d5-109">Esse cmdlet é semelhante a `Import-Clixml` , exceto que `Export-BinaryMILog` armazena o objeto resultante em um arquivo binário codificado.</span><span class="sxs-lookup"><span data-stu-id="974d5-109">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="974d5-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="974d5-110">EXAMPLES</span></span>

### <span data-ttu-id="974d5-111">Exemplo 1-restaurar objetos exportados para um arquivo</span><span class="sxs-lookup"><span data-stu-id="974d5-111">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="974d5-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="974d5-112">PARAMETERS</span></span>

### <span data-ttu-id="974d5-113">-Path</span><span class="sxs-lookup"><span data-stu-id="974d5-113">-Path</span></span>

<span data-ttu-id="974d5-114">Especifica o caminho do arquivo no qual armazenar a representação binária do objeto.</span><span class="sxs-lookup"><span data-stu-id="974d5-114">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="974d5-115">O parâmetro **path** dá suporte a curingas e caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="974d5-115">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="974d5-116">Esse cmdlet gera um erro se o caminho for resolvido para mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="974d5-116">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="974d5-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="974d5-117">CommonParameters</span></span>
<span data-ttu-id="974d5-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="974d5-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="974d5-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="974d5-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="974d5-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="974d5-120">INPUTS</span></span>

### <span data-ttu-id="974d5-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="974d5-121">None</span></span>

## <span data-ttu-id="974d5-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="974d5-122">OUTPUTS</span></span>

### <span data-ttu-id="974d5-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="974d5-123">System.Object</span></span>

## <span data-ttu-id="974d5-124">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="974d5-124">NOTES</span></span>

## <span data-ttu-id="974d5-125">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="974d5-125">RELATED LINKS</span></span>
