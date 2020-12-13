---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para WideControl (formato)
description: Elemento SelectionSetName para EntrySelectedBy para WideControl (formato)
ms.openlocfilehash: bf6a44bb733421f36a9140d0ec10e61aedfbda6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651693"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="27e87-103">Elemento SelectionSetName para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="27e87-103">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="27e87-104">Especifica um conjunto de objetos .NET para a definição.</span><span class="sxs-lookup"><span data-stu-id="27e87-104">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="27e87-105">A definição é usada sempre que um desses objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="27e87-105">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="27e87-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="27e87-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="27e87-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="27e87-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="27e87-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="27e87-108">Attributes and Elements</span></span>

<span data-ttu-id="27e87-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="27e87-109">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="27e87-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="27e87-110">Attributes</span></span>

<span data-ttu-id="27e87-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="27e87-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="27e87-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="27e87-112">Child Elements</span></span>

<span data-ttu-id="27e87-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="27e87-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="27e87-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="27e87-114">Parent Elements</span></span>

|<span data-ttu-id="27e87-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="27e87-115">Element</span></span>|<span data-ttu-id="27e87-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="27e87-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="27e87-117">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="27e87-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="27e87-118">Define os tipos .NET que usam essa entrada ampla ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="27e87-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="27e87-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="27e87-119">Text Value</span></span>

<span data-ttu-id="27e87-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="27e87-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="27e87-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="27e87-121">Remarks</span></span>

<span data-ttu-id="27e87-122">Cada definição deve especificar um nome de tipo, um conjunto de seleção ou uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="27e87-122">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="27e87-123">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="27e87-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="27e87-124">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="27e87-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="27e87-125">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="27e87-125">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="27e87-126">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="27e87-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="27e87-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27e87-127">See Also</span></span>

[<span data-ttu-id="27e87-128">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="27e87-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="27e87-129">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="27e87-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="27e87-130">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="27e87-130">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="27e87-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="27e87-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
