---
title: Elemento SelectionSetName para EntrySelectedBy para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364745"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="a831e-102">Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="a831e-102">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="a831e-103">Especifica um conjunto de objetos .NET para a entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="a831e-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="a831e-104">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="a831e-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="a831e-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Elemento para CustomEntry para exibição (Format) SelectionSetName elemento para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a831e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a831e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a831e-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a831e-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a831e-107">Attributes and Elements</span></span>

<span data-ttu-id="a831e-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="a831e-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a831e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a831e-109">Attributes</span></span>

<span data-ttu-id="a831e-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a831e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a831e-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="a831e-111">Child Elements</span></span>

<span data-ttu-id="a831e-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a831e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a831e-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="a831e-113">Parent Elements</span></span>

|<span data-ttu-id="a831e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="a831e-114">Element</span></span>|<span data-ttu-id="a831e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="a831e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a831e-116">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="a831e-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="a831e-117">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="a831e-117">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a831e-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="a831e-118">Text Value</span></span>

<span data-ttu-id="a831e-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="a831e-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="a831e-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="a831e-120">Remarks</span></span>

<span data-ttu-id="a831e-121">Cada entrada de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="a831e-121">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="a831e-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="a831e-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="a831e-123">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="a831e-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="a831e-124">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="a831e-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="a831e-125">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a831e-125">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a831e-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a831e-126">See Also</span></span>

[<span data-ttu-id="a831e-127">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="a831e-127">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a831e-128">Exibição de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="a831e-128">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="a831e-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a831e-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
