---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)
description: Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: a5a395f718d0e1a2d7f33d120ce4fd2ff787cc34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651775"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="971d5-103">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="971d5-103">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="971d5-104">Especifica um conjunto de tipos .NET que usam esta entrada da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="971d5-104">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="971d5-105">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="971d5-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="971d5-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format) SelectionSetName elemento de EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="971d5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="971d5-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="971d5-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="971d5-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="971d5-108">Attributes and Elements</span></span>

<span data-ttu-id="971d5-109">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="971d5-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="971d5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="971d5-110">Attributes</span></span>

<span data-ttu-id="971d5-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="971d5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="971d5-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="971d5-112">Child Elements</span></span>

<span data-ttu-id="971d5-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="971d5-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="971d5-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="971d5-114">Parent Elements</span></span>

|<span data-ttu-id="971d5-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="971d5-115">Element</span></span>|<span data-ttu-id="971d5-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="971d5-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="971d5-117">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="971d5-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="971d5-118">Define os tipos .NET que usam essa entrada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="971d5-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="971d5-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="971d5-119">Text Value</span></span>

<span data-ttu-id="971d5-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="971d5-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="971d5-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="971d5-121">Remarks</span></span>

<span data-ttu-id="971d5-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="971d5-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="971d5-123">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="971d5-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="971d5-124">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="971d5-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="971d5-125">Se você especificar um conjunto de seleção para uma entrada, não poderá especificar um nome de tipo.</span><span class="sxs-lookup"><span data-stu-id="971d5-125">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="971d5-126">Para obter mais informações sobre como especificar um tipo .NET, consulte o [elemento TypeName para EntrySelectedBy para TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span><span class="sxs-lookup"><span data-stu-id="971d5-126">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="971d5-127">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="971d5-127">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="971d5-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="971d5-128">See Also</span></span>

[<span data-ttu-id="971d5-129">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="971d5-129">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="971d5-130">Definindo conjuntos de objetos para uma exibição</span><span class="sxs-lookup"><span data-stu-id="971d5-130">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="971d5-131">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="971d5-131">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="971d5-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="971d5-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
