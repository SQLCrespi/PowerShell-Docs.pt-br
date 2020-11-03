---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: cf03ad884121c6cf8cf65cdb791cbdc4e587c3b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193430"
---
# <span data-ttu-id="ec62c-103">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="ec62c-103">Export-BinaryMiLog</span></span>

## <span data-ttu-id="ec62c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ec62c-104">SYNOPSIS</span></span>
<span data-ttu-id="ec62c-105">Cria uma representação binária codificada de um objeto ou objetos e a armazena em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ec62c-105">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="ec62c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec62c-106">SYNTAX</span></span>

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="ec62c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec62c-107">DESCRIPTION</span></span>

<span data-ttu-id="ec62c-108">O `Export-BinaryMILog` cmdlet cria uma representação baseada em binário de um objeto ou objetos e o armazena em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ec62c-108">The `Export-BinaryMILog` cmdlet creates a binary-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="ec62c-109">Você pode usar o `Import-BinaryMiLog` cmdlet para recriar o objeto salvo com base no conteúdo desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="ec62c-109">You can then use the `Import-BinaryMiLog` cmdlet to re-create the saved object based on the contents of that file.</span></span>

<span data-ttu-id="ec62c-110">Esse cmdlet é semelhante a `Import-Clixml` , exceto que `Export-BinaryMILog` armazena o objeto resultante em um arquivo binário codificado.</span><span class="sxs-lookup"><span data-stu-id="ec62c-110">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="ec62c-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ec62c-111">EXAMPLES</span></span>

### <span data-ttu-id="ec62c-112">Exemplo 1-criar uma representação binária de CimInstances</span><span class="sxs-lookup"><span data-stu-id="ec62c-112">Example 1 - Create a binary representation of CimInstances</span></span>

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

<span data-ttu-id="ec62c-113">Esse comando exporta **CimInstances** para um arquivo de log mi binário especificado pelo parâmetro Path.</span><span class="sxs-lookup"><span data-stu-id="ec62c-113">This command exports **CimInstances** to a binary MI log file specified by the Path parameter.</span></span> <span data-ttu-id="ec62c-114">Consulte o exemplo de Import-BinaryMiLog para ver como recriar o **CimInstances** importando esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="ec62c-114">See the example for Import-BinaryMiLog to see how to recreate the **CimInstances** by importing this file.</span></span>

## <span data-ttu-id="ec62c-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec62c-115">PARAMETERS</span></span>

### <span data-ttu-id="ec62c-116">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ec62c-116">-InputObject</span></span>

<span data-ttu-id="ec62c-117">Especifica a entrada para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec62c-117">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="ec62c-118">Você pode usar esse parâmetro ou é possível canalizar a entrada para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec62c-118">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ec62c-119">-Path</span><span class="sxs-lookup"><span data-stu-id="ec62c-119">-Path</span></span>

<span data-ttu-id="ec62c-120">Especifica o caminho do arquivo no qual armazenar a representação binária do objeto.</span><span class="sxs-lookup"><span data-stu-id="ec62c-120">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="ec62c-121">O parâmetro **path** dá suporte a curingas e caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="ec62c-121">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="ec62c-122">Esse cmdlet gera um erro se o caminho for resolvido para mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ec62c-122">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="ec62c-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec62c-123">CommonParameters</span></span>

<span data-ttu-id="ec62c-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec62c-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec62c-125">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec62c-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec62c-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ec62c-126">INPUTS</span></span>

### <span data-ttu-id="ec62c-127">Microsoft. Management. Infrastructure. CimInstance</span><span class="sxs-lookup"><span data-stu-id="ec62c-127">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="ec62c-128">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ec62c-128">OUTPUTS</span></span>

### <span data-ttu-id="ec62c-129">System.Object</span><span class="sxs-lookup"><span data-stu-id="ec62c-129">System.Object</span></span>

## <span data-ttu-id="ec62c-130">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ec62c-130">NOTES</span></span>

## <span data-ttu-id="ec62c-131">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ec62c-131">RELATED LINKS</span></span>

[<span data-ttu-id="ec62c-132">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="ec62c-132">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="ec62c-133">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="ec62c-133">Import-BinaryMiLog</span></span>](import-binarymilog.md)

[<span data-ttu-id="ec62c-134">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="ec62c-134">Import-Clixml</span></span>](../microsoft.powershell.utility/import-clixml.md)
