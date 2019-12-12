---
title: Elemento SelectionSetName para EntrySelectedBy para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368315"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="3fcb4-102">Elemento SelectionSetName para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3fcb4-102">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="3fcb4-103">Especifica um conjunto de tipos .NET que usam esta entrada da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-103">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="3fcb4-104">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="3fcb4-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element (Format) SelectionSetName elemento EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="3fcb4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3fcb4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3fcb4-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3fcb4-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3fcb4-107">Attributes and Elements</span></span>

<span data-ttu-id="3fcb4-108">As seções a seguir descrevem os atributos, bem como os elementos filhos e pais.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3fcb4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3fcb4-109">Attributes</span></span>

<span data-ttu-id="3fcb4-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3fcb4-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="3fcb4-111">Child Elements</span></span>

<span data-ttu-id="3fcb4-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3fcb4-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="3fcb4-113">Parent Elements</span></span>

|<span data-ttu-id="3fcb4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3fcb4-114">Element</span></span>|<span data-ttu-id="3fcb4-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="3fcb4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3fcb4-116">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3fcb4-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="3fcb4-117">Define os tipos .NET que usam essa entrada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3fcb4-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="3fcb4-118">Text Value</span></span>

<span data-ttu-id="3fcb4-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fcb4-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="3fcb4-120">Remarks</span></span>

<span data-ttu-id="3fcb4-121">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="3fcb4-122">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="3fcb4-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb4-123">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="3fcb4-124">Se você especificar um conjunto de seleção para uma entrada, não poderá especificar um nome de tipo.</span><span class="sxs-lookup"><span data-stu-id="3fcb4-124">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="3fcb4-125">Para obter mais informações sobre como especificar um tipo .NET, consulte o [elemento TypeName para EntrySelectedBy para TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb4-125">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="3fcb4-126">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="3fcb4-126">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fcb4-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3fcb4-127">See Also</span></span>

[<span data-ttu-id="3fcb4-128">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3fcb4-128">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="3fcb4-129">Definindo conjuntos de objetos para uma exibição</span><span class="sxs-lookup"><span data-stu-id="3fcb4-129">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="3fcb4-130">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="3fcb4-130">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3fcb4-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fcb4-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
