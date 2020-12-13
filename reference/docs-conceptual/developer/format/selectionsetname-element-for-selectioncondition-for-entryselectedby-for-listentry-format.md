---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)
description: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)
ms.openlocfilehash: f3193799e67706eb07f0fe1c2cd42cce83f7af57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651539"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="9cff7-103">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="9cff7-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="9cff7-104">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="9cff7-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="9cff7-105">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando essa definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="9cff7-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="9cff7-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) ListControl Element (Format) o elemento ListEntries (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionCondition Element para EntrySelectedBy para ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="9cff7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9cff7-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9cff7-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9cff7-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9cff7-108">Attributes and Elements</span></span>

<span data-ttu-id="9cff7-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="9cff7-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9cff7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9cff7-110">Attributes</span></span>

<span data-ttu-id="9cff7-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="9cff7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9cff7-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9cff7-112">Child Elements</span></span>

<span data-ttu-id="9cff7-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="9cff7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9cff7-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9cff7-114">Parent Elements</span></span>

|<span data-ttu-id="9cff7-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9cff7-115">Element</span></span>|<span data-ttu-id="9cff7-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="9cff7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9cff7-117">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="9cff7-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="9cff7-118">Define a condição que deve existir para usar essa definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="9cff7-118">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9cff7-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9cff7-119">Text Value</span></span>

<span data-ttu-id="9cff7-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="9cff7-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="9cff7-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="9cff7-121">Remarks</span></span>

<span data-ttu-id="9cff7-122">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="9cff7-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="9cff7-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9cff7-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9cff7-124">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="9cff7-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="9cff7-125">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9cff7-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="9cff7-126">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="9cff7-126">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9cff7-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9cff7-127">See Also</span></span>

[<span data-ttu-id="9cff7-128">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="9cff7-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9cff7-129">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="9cff7-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9cff7-130">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="9cff7-130">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="9cff7-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cff7-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
