---
title: Elemento SelectionSetName para EntrySelectedBy para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4315d81da4ceeb7a5b171087434ae15fb09e6592
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785261"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="90ad2-102">Elemento SelectionSetName para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="90ad2-102">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="90ad2-103">Especifica um conjunto de objetos .NET para a entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="90ad2-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="90ad2-104">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="90ad2-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="90ad2-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries elemento (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="90ad2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="90ad2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="90ad2-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90ad2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="90ad2-107">Attributes and Elements</span></span>

<span data-ttu-id="90ad2-108">As seções a seguir descrevem atributos, elementos filho e elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="90ad2-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="90ad2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="90ad2-109">Attributes</span></span>

<span data-ttu-id="90ad2-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="90ad2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="90ad2-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="90ad2-111">Child Elements</span></span>

<span data-ttu-id="90ad2-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="90ad2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="90ad2-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="90ad2-113">Parent Elements</span></span>

|<span data-ttu-id="90ad2-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="90ad2-114">Element</span></span>|<span data-ttu-id="90ad2-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="90ad2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90ad2-116">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="90ad2-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="90ad2-117">Define os tipos .NET que usam essa entrada de lista ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="90ad2-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="90ad2-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="90ad2-118">Text Value</span></span>

<span data-ttu-id="90ad2-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="90ad2-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="90ad2-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="90ad2-120">Remarks</span></span>

<span data-ttu-id="90ad2-121">Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="90ad2-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="90ad2-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="90ad2-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="90ad2-123">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="90ad2-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="90ad2-124">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="90ad2-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="90ad2-125">Para obter mais informações sobre os componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="90ad2-125">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="90ad2-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="90ad2-126">Example</span></span>

<span data-ttu-id="90ad2-127">O exemplo a seguir mostra como especificar um conjunto de seleção para uma entrada de uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="90ad2-127">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="90ad2-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90ad2-128">See Also</span></span>

[<span data-ttu-id="90ad2-129">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="90ad2-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="90ad2-130">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="90ad2-130">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="90ad2-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ad2-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
