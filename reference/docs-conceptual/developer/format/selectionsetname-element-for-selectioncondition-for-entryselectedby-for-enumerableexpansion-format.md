---
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e18c74bb95c658f2c3e7b7454628f78d523f7609
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787488"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="8b21e-102">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="8b21e-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="8b21e-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="8b21e-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="8b21e-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida.</span><span class="sxs-lookup"><span data-stu-id="8b21e-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="8b21e-105">Elemento de configuração DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansions Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy para EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="8b21e-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8b21e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8b21e-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8b21e-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8b21e-107">Attributes and Elements</span></span>

<span data-ttu-id="8b21e-108">As seções a seguir descrevem atributos, elementos filho e elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="8b21e-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8b21e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="8b21e-109">Attributes</span></span>

<span data-ttu-id="8b21e-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8b21e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8b21e-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="8b21e-111">Child Elements</span></span>

<span data-ttu-id="8b21e-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8b21e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8b21e-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="8b21e-113">Parent Elements</span></span>

|<span data-ttu-id="8b21e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b21e-114">Element</span></span>|<span data-ttu-id="8b21e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="8b21e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8b21e-116">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="8b21e-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="8b21e-117">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="8b21e-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8b21e-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="8b21e-118">Text Value</span></span>

<span data-ttu-id="8b21e-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="8b21e-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b21e-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="8b21e-120">Remarks</span></span>

<span data-ttu-id="8b21e-121">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="8b21e-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="8b21e-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8b21e-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8b21e-123">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="8b21e-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="8b21e-124">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="8b21e-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8b21e-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b21e-125">See Also</span></span>

[<span data-ttu-id="8b21e-126">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="8b21e-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="8b21e-127">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="8b21e-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="8b21e-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b21e-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
