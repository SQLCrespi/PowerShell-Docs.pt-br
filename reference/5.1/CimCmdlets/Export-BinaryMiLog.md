---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: 1d202b7bbda359f859838475eb9f37730506bd1f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194356"
---
# <span data-ttu-id="9e1fb-103">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="9e1fb-103">Export-BinaryMiLog</span></span>

## <span data-ttu-id="9e1fb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9e1fb-104">SYNOPSIS</span></span>
<span data-ttu-id="9e1fb-105">Cria uma representação binária codificada de um objeto ou objetos e a armazena em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-105">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="9e1fb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e1fb-106">SYNTAX</span></span>

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="9e1fb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9e1fb-107">DESCRIPTION</span></span>

<span data-ttu-id="9e1fb-108">O `Export-BinaryMILog` cmdlet cria uma representação baseada em binário de um objeto ou objetos e o armazena em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-108">The `Export-BinaryMILog` cmdlet creates a binary-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="9e1fb-109">Você pode usar o `Import-BinaryMiLog` cmdlet para recriar o objeto salvo com base no conteúdo desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-109">You can then use the `Import-BinaryMiLog` cmdlet to re-create the saved object based on the contents of that file.</span></span>

<span data-ttu-id="9e1fb-110">Esse cmdlet é semelhante a `Import-Clixml` , exceto que `Export-BinaryMILog` armazena o objeto resultante em um arquivo binário codificado.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-110">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="9e1fb-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9e1fb-111">EXAMPLES</span></span>

### <span data-ttu-id="9e1fb-112">Exemplo 1-criar uma representação binária de CimInstances</span><span class="sxs-lookup"><span data-stu-id="9e1fb-112">Example 1 - Create a binary representation of CimInstances</span></span>

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

<span data-ttu-id="9e1fb-113">Esse comando exporta **CimInstances** para um arquivo de log mi binário especificado pelo parâmetro Path.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-113">This command exports **CimInstances** to a binary MI log file specified by the Path parameter.</span></span> <span data-ttu-id="9e1fb-114">Consulte o exemplo de Import-BinaryMiLog para ver como recriar o **CimInstances** importando esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-114">See the example for Import-BinaryMiLog to see how to recreate the **CimInstances** by importing this file.</span></span>

## <span data-ttu-id="9e1fb-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e1fb-115">PARAMETERS</span></span>

### <span data-ttu-id="9e1fb-116">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9e1fb-116">-InputObject</span></span>

<span data-ttu-id="9e1fb-117">Especifica a entrada para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-117">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="9e1fb-118">Você pode usar esse parâmetro ou é possível canalizar a entrada para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-118">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

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

### <span data-ttu-id="9e1fb-119">-Path</span><span class="sxs-lookup"><span data-stu-id="9e1fb-119">-Path</span></span>

<span data-ttu-id="9e1fb-120">Especifica o caminho do arquivo no qual armazenar a representação binária do objeto.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-120">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="9e1fb-121">O parâmetro **path** dá suporte a curingas e caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-121">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="9e1fb-122">Esse cmdlet gera um erro se o caminho for resolvido para mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-122">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="9e1fb-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e1fb-123">CommonParameters</span></span>

<span data-ttu-id="9e1fb-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9e1fb-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e1fb-125">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9e1fb-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e1fb-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9e1fb-126">INPUTS</span></span>

### <span data-ttu-id="9e1fb-127">Microsoft. Management. Infrastructure. CimInstance</span><span class="sxs-lookup"><span data-stu-id="9e1fb-127">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="9e1fb-128">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9e1fb-128">OUTPUTS</span></span>

### <span data-ttu-id="9e1fb-129">System.Object</span><span class="sxs-lookup"><span data-stu-id="9e1fb-129">System.Object</span></span>

## <span data-ttu-id="9e1fb-130">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9e1fb-130">NOTES</span></span>

## <span data-ttu-id="9e1fb-131">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9e1fb-131">RELATED LINKS</span></span>

[<span data-ttu-id="9e1fb-132">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="9e1fb-132">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="9e1fb-133">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="9e1fb-133">Import-BinaryMiLog</span></span>](import-binarymilog.md)

[<span data-ttu-id="9e1fb-134">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="9e1fb-134">Import-Clixml</span></span>](../microsoft.powershell.utility/import-clixml.md)
