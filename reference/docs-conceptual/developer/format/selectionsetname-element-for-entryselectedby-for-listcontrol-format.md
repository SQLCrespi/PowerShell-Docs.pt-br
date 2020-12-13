---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)
description: Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: 413a77f7ba06fe952e574061e58d0b5d80c5b3c4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651823"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="57b48-103">Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="57b48-103">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="57b48-104">Especifica um conjunto de objetos .NET para a entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="57b48-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="57b48-105">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="57b48-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="57b48-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries elemento (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="57b48-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="57b48-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="57b48-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="57b48-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="57b48-108">Attributes and Elements</span></span>

<span data-ttu-id="57b48-109">As seções a seguir descrevem atributos, elementos filho e elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="57b48-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="57b48-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="57b48-110">Attributes</span></span>

<span data-ttu-id="57b48-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="57b48-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="57b48-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="57b48-112">Child Elements</span></span>

<span data-ttu-id="57b48-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="57b48-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="57b48-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="57b48-114">Parent Elements</span></span>

|<span data-ttu-id="57b48-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="57b48-115">Element</span></span>|<span data-ttu-id="57b48-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="57b48-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="57b48-117">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="57b48-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="57b48-118">Define os tipos .NET que usam essa entrada de lista ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="57b48-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="57b48-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="57b48-119">Text Value</span></span>

<span data-ttu-id="57b48-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="57b48-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="57b48-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="57b48-121">Remarks</span></span>

<span data-ttu-id="57b48-122">Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="57b48-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="57b48-123">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="57b48-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="57b48-124">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="57b48-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="57b48-125">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="57b48-125">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="57b48-126">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="57b48-126">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="57b48-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="57b48-127">Example</span></span>

<span data-ttu-id="57b48-128">O exemplo a seguir mostra como especificar um conjunto de seleção para uma entrada de uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="57b48-128">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="57b48-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="57b48-129">See Also</span></span>

[<span data-ttu-id="57b48-130">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="57b48-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="57b48-131">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="57b48-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="57b48-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="57b48-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
