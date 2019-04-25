---
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b7af0b2-68e6-43c3-adcc-7c58007fced8
caps.latest.revision: 13
ms.openlocfilehash: 6f7c8d9af3c1c2fbda0208148b0088161701fdbe
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063853"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="9477b-102">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9477b-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="9477b-103">Especifica o conjunto de tipos do .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="9477b-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="9477b-104">Quando qualquer um dos tipos neste conjunto estiver presente, a condição for atendida.</span><span class="sxs-lookup"><span data-stu-id="9477b-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="9477b-105">Elemento DefaultSettings elemento (formato) elemento EnumerableExpansions (formato) elemento EnumerableExpansions (formato) EntrySelectedBy elemento de configuração para elemento de SelectionCondition EnumerableExpansion (formato) EntrySelectedBy para Elemento de SelectionSetName EnumerableExpansion (formato) para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9477b-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9477b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9477b-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9477b-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="9477b-107">Attributes and Elements</span></span>

<span data-ttu-id="9477b-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="9477b-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9477b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9477b-109">Attributes</span></span>

<span data-ttu-id="9477b-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9477b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9477b-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9477b-111">Child Elements</span></span>

<span data-ttu-id="9477b-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9477b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9477b-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9477b-113">Parent Elements</span></span>

|<span data-ttu-id="9477b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9477b-114">Element</span></span>|<span data-ttu-id="9477b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="9477b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9477b-116">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9477b-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9477b-117">Define a condição que deve existir para expandir os objetos da coleção desta definição.</span><span class="sxs-lookup"><span data-stu-id="9477b-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9477b-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9477b-118">Text Value</span></span>

<span data-ttu-id="9477b-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="9477b-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="9477b-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="9477b-120">Remarks</span></span>

<span data-ttu-id="9477b-121">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="9477b-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="9477b-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9477b-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9477b-123">Conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que define o arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="9477b-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="9477b-124">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo seleção define](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9477b-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9477b-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9477b-125">See Also</span></span>

[<span data-ttu-id="9477b-126">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="9477b-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="9477b-127">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9477b-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="9477b-128">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9477b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
