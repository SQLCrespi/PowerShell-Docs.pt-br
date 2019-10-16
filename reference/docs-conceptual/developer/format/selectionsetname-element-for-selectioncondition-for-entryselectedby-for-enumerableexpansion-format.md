---
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b7af0b2-68e6-43c3-adcc-7c58007fced8
caps.latest.revision: 13
ms.openlocfilehash: 6f7c8d9af3c1c2fbda0208148b0088161701fdbe
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361985"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="9f939-102">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9f939-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="9f939-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="9f939-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="9f939-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida.</span><span class="sxs-lookup"><span data-stu-id="9f939-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="9f939-105">Elemento de configuração DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansions Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format) SelectionCondition Element para EntrySelectedBy para Elemento EnumerableExpansion (Format) SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="9f939-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9f939-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f939-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f939-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9f939-107">Attributes and Elements</span></span>

<span data-ttu-id="9f939-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="9f939-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f939-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9f939-109">Attributes</span></span>

<span data-ttu-id="9f939-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9f939-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f939-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="9f939-111">Child Elements</span></span>

<span data-ttu-id="9f939-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9f939-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9f939-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="9f939-113">Parent Elements</span></span>

|<span data-ttu-id="9f939-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f939-114">Element</span></span>|<span data-ttu-id="9f939-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f939-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f939-116">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="9f939-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9f939-117">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="9f939-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9f939-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9f939-118">Text Value</span></span>

<span data-ttu-id="9f939-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="9f939-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f939-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="9f939-120">Remarks</span></span>

<span data-ttu-id="9f939-121">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="9f939-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="9f939-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9f939-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9f939-123">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="9f939-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="9f939-124">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9f939-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9f939-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f939-125">See Also</span></span>

[<span data-ttu-id="9f939-126">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="9f939-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="9f939-127">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="9f939-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="9f939-128">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f939-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
