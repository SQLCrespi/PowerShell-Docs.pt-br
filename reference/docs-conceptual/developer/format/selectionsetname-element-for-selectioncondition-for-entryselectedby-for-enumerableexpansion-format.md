---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 0c9372113a79f75cfbda67acf869164fde894ee3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651585"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="96519-103">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="96519-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="96519-104">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="96519-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="96519-105">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida.</span><span class="sxs-lookup"><span data-stu-id="96519-105">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="96519-106">Elemento de configuração DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansions Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy para EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="96519-106">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="96519-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="96519-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96519-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="96519-108">Attributes and Elements</span></span>

<span data-ttu-id="96519-109">As seções a seguir descrevem atributos, elementos filho e elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="96519-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="96519-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="96519-110">Attributes</span></span>

<span data-ttu-id="96519-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="96519-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="96519-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="96519-112">Child Elements</span></span>

<span data-ttu-id="96519-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="96519-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="96519-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="96519-114">Parent Elements</span></span>

|<span data-ttu-id="96519-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="96519-115">Element</span></span>|<span data-ttu-id="96519-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="96519-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96519-117">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="96519-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="96519-118">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="96519-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="96519-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="96519-119">Text Value</span></span>

<span data-ttu-id="96519-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="96519-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="96519-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="96519-121">Remarks</span></span>

<span data-ttu-id="96519-122">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="96519-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="96519-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="96519-123">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="96519-124">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="96519-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="96519-125">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="96519-125">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96519-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96519-126">See Also</span></span>

[<span data-ttu-id="96519-127">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="96519-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="96519-128">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="96519-128">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="96519-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="96519-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
