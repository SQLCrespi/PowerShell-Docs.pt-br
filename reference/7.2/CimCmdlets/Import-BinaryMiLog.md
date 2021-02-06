---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: 646f3e0990ce451300a28ca0de58576c70c55a9b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597191"
---
# <span data-ttu-id="90526-102">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="90526-102">Import-BinaryMiLog</span></span>

## <span data-ttu-id="90526-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="90526-103">SYNOPSIS</span></span>
<span data-ttu-id="90526-104">Usado para recriar os objetos salvos com base no conteúdo de um arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="90526-104">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="90526-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90526-105">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="90526-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="90526-106">DESCRIPTION</span></span>

<span data-ttu-id="90526-107">Use este cmdlet para recriar objetos salvos com base no conteúdo de um arquivo de exportação criado pelo `Export-BinaryMILog` .</span><span class="sxs-lookup"><span data-stu-id="90526-107">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="90526-108">Esse cmdlet é semelhante a `Import-Clixml` , exceto que `Export-BinaryMILog` armazena o objeto resultante em um arquivo binário codificado.</span><span class="sxs-lookup"><span data-stu-id="90526-108">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="90526-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="90526-109">EXAMPLES</span></span>

### <span data-ttu-id="90526-110">Exemplo 1-restaurar objetos exportados para um arquivo</span><span class="sxs-lookup"><span data-stu-id="90526-110">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="90526-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90526-111">PARAMETERS</span></span>

### <span data-ttu-id="90526-112">-Path</span><span class="sxs-lookup"><span data-stu-id="90526-112">-Path</span></span>

<span data-ttu-id="90526-113">Especifica o caminho do arquivo no qual armazenar a representação binária do objeto.</span><span class="sxs-lookup"><span data-stu-id="90526-113">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="90526-114">O parâmetro **path** dá suporte a curingas e caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="90526-114">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="90526-115">Esse cmdlet gera um erro se o caminho for resolvido para mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="90526-115">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="90526-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="90526-116">CommonParameters</span></span>
<span data-ttu-id="90526-117">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="90526-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="90526-118">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="90526-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="90526-119">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="90526-119">INPUTS</span></span>

### <span data-ttu-id="90526-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="90526-120">None</span></span>

## <span data-ttu-id="90526-121">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="90526-121">OUTPUTS</span></span>

### <span data-ttu-id="90526-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="90526-122">System.Object</span></span>

## <span data-ttu-id="90526-123">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="90526-123">NOTES</span></span>

## <span data-ttu-id="90526-124">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="90526-124">RELATED LINKS</span></span>
