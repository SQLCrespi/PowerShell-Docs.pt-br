---
title: Parâmetros de filtro de entrada | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e45929d1-bbb4-4dc6-892f-f9eacdb1c84c
caps.latest.revision: 8
ms.openlocfilehash: 7a1582031d27f78bad069f5539408312ccabb3f2
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563883"
---
# <a name="input-filter-parameters"></a><span data-ttu-id="28660-102">Parâmetros de filtro de entrada</span><span class="sxs-lookup"><span data-stu-id="28660-102">Input Filter Parameters</span></span>

<span data-ttu-id="28660-103">Um cmdlet pode definir `Filter` , `Include` e `Exclude` parâmetros que filtram o conjunto de objetos de entrada que o cmdlet afeta.</span><span class="sxs-lookup"><span data-stu-id="28660-103">A cmdlet can define `Filter`, `Include`, and `Exclude` parameters that filter the set of input objects that the cmdlet affects.</span></span>

<span data-ttu-id="28660-104">Normalmente, o conjunto de objetos de entrada é especificado por `InputObject` um `Path` parâmetro, ou `Name` .</span><span class="sxs-lookup"><span data-stu-id="28660-104">Typically, the set of input objects is specified by an `InputObject`, `Path`, or `Name` parameter.</span></span> <span data-ttu-id="28660-105">Por exemplo, um cmdlet pode ter um `Path` parâmetro que aceita vários caminhos usando caracteres curinga e cada caminho aponta para um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="28660-105">For example, a cmdlet can have a `Path` parameter that accepts multiple paths by using wildcard characters, and each path points to an input object.</span></span> <span data-ttu-id="28660-106">Usados juntos, os `Filter` `Include` parâmetros, e `Exclude` qualificam ainda mais os caminhos em que o cmdlet funciona sempre que é invocado.</span><span class="sxs-lookup"><span data-stu-id="28660-106">Used together, the `Filter`, `Include`, and `Exclude` parameters further qualify the paths the cmdlet works on each time it is invoked.</span></span>

## <a name="include-and-exclude-parameters"></a><span data-ttu-id="28660-107">Incluir e excluir parâmetros</span><span class="sxs-lookup"><span data-stu-id="28660-107">Include and Exclude Parameters</span></span>

<span data-ttu-id="28660-108">Os `Include` `Exclude` parâmetros e identificam os objetos que são incluídos ou excluídos do conjunto de objetos de entrada passados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="28660-108">The `Include` and `Exclude` parameters identify the objects that are included or excluded from the set of input objects passed to the cmdlet.</span></span> <span data-ttu-id="28660-109">Use esses parâmetros quando o filtro puder ser expresso na linguagem padrão de curinga.</span><span class="sxs-lookup"><span data-stu-id="28660-109">Use these parameters when the filter can be expressed in the standard wildcard language.</span></span> <span data-ttu-id="28660-110">(Para obter mais informações sobre caracteres curinga, consulte [suportando curingas em parâmetros de cmdlet](./supporting-wildcard-characters-in-cmdlet-parameters.md).) O `Include` parâmetro inclui todos os objetos cujos nomes correspondem ao filtro de inclusão.</span><span class="sxs-lookup"><span data-stu-id="28660-110">(For more information about wildcard characters, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).) The `Include` parameter includes all the objects whose names match the inclusion filter.</span></span> <span data-ttu-id="28660-111">O `Exclude` parâmetro exclui todos os objetos cujos nomes correspondem ao filtro.</span><span class="sxs-lookup"><span data-stu-id="28660-111">The `Exclude` parameter excludes all the objects whose names match the filter.</span></span>

## <a name="filter-parameter"></a><span data-ttu-id="28660-112">Parâmetro de filtro</span><span class="sxs-lookup"><span data-stu-id="28660-112">Filter Parameter</span></span>

<span data-ttu-id="28660-113">O `Filter` parâmetro especifica um filtro que não é expresso na linguagem curinga padrão.</span><span class="sxs-lookup"><span data-stu-id="28660-113">The `Filter` parameter specifies a filter that is not expressed in the standard wildcard language.</span></span> <span data-ttu-id="28660-114">Por exemplo, as interfaces de serviço Active Directory (ADSI) ou filtros SQL podem ser passados para o cmdlet por meio de seu `Filter` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="28660-114">For example, Active Directory Service Interfaces (ADSI) or SQL filters might be passed to the cmdlet through its `Filter` parameter.</span></span> <span data-ttu-id="28660-115">Nos cmdlets fornecidos pelo Windows PowerShell, esses filtros são especificados pelos provedores do Windows PowerShell que usam o cmdlet para acessar um armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="28660-115">In the cmdlets provided by Windows PowerShell, these filters are specified by the Windows PowerShell providers that use the cmdlet to access a data store.</span></span> <span data-ttu-id="28660-116">Cada provedor normalmente define seu próprio filtro.</span><span class="sxs-lookup"><span data-stu-id="28660-116">Each provider typically defines its own filter.</span></span>

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a><span data-ttu-id="28660-117">Filtragem se nenhum conjunto de objetos de entrada for especificado</span><span class="sxs-lookup"><span data-stu-id="28660-117">Filtering If No Set of Input Objects Is Specified</span></span>

<span data-ttu-id="28660-118">Se nenhum conjunto de objetos de entrada for especificado, isso geralmente significa filtrar em relação a todos os objetos.</span><span class="sxs-lookup"><span data-stu-id="28660-118">If no set of input objects is specified, this typically means to filter against all objects.</span></span> <span data-ttu-id="28660-119">Para obter mais informações, consulte[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span><span class="sxs-lookup"><span data-stu-id="28660-119">For more information, see[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).</span></span>

## <a name="see-also"></a><span data-ttu-id="28660-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28660-120">See Also</span></span>

[<span data-ttu-id="28660-121">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28660-121">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
