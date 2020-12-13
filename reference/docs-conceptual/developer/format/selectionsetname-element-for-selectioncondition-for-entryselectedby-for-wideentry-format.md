---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)
description: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)
ms.openlocfilehash: c6466e3ac6e1f194df9172468d26448f9630da6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655015"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="fd223-103">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="fd223-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="fd223-104">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="fd223-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="fd223-105">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando essa definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="fd223-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="fd223-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy para WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fd223-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fd223-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fd223-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fd223-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fd223-108">Attributes and Elements</span></span>

<span data-ttu-id="fd223-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="fd223-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fd223-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="fd223-110">Attributes</span></span>

<span data-ttu-id="fd223-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="fd223-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fd223-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="fd223-112">Child Elements</span></span>

<span data-ttu-id="fd223-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="fd223-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fd223-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="fd223-114">Parent Elements</span></span>

|<span data-ttu-id="fd223-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd223-115">Element</span></span>|<span data-ttu-id="fd223-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="fd223-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fd223-117">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fd223-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="fd223-118">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="fd223-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fd223-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="fd223-119">Text Value</span></span>

<span data-ttu-id="fd223-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="fd223-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd223-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="fd223-121">Remarks</span></span>

<span data-ttu-id="fd223-122">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fd223-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="fd223-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="fd223-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="fd223-124">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="fd223-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="fd223-125">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="fd223-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="fd223-126">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="fd223-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd223-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd223-127">See Also</span></span>

[<span data-ttu-id="fd223-128">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="fd223-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="fd223-129">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="fd223-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="fd223-130">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="fd223-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="fd223-131">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fd223-131">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="fd223-132">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fd223-132">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="fd223-133">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd223-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
