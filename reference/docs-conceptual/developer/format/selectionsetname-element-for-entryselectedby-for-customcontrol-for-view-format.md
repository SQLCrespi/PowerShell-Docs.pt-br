---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)
description: Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)
ms.openlocfilehash: a158c5476fb3a168a146ce67565c0ed6f7859519
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651922"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="57718-103">Elemento SelectionSetName para EntrySelectedBy para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="57718-103">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="57718-104">Especifica um conjunto de objetos .NET para a entrada de lista.</span><span class="sxs-lookup"><span data-stu-id="57718-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="57718-105">Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="57718-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="57718-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para o elemento View (Format) SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="57718-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="57718-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="57718-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="57718-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="57718-108">Attributes and Elements</span></span>

<span data-ttu-id="57718-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="57718-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="57718-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="57718-110">Attributes</span></span>

<span data-ttu-id="57718-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="57718-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="57718-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="57718-112">Child Elements</span></span>

<span data-ttu-id="57718-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="57718-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="57718-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="57718-114">Parent Elements</span></span>

|<span data-ttu-id="57718-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="57718-115">Element</span></span>|<span data-ttu-id="57718-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="57718-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="57718-117">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="57718-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="57718-118">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="57718-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="57718-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="57718-119">Text Value</span></span>

<span data-ttu-id="57718-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="57718-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="57718-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="57718-121">Remarks</span></span>

<span data-ttu-id="57718-122">Cada entrada de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="57718-122">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="57718-123">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="57718-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="57718-124">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="57718-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="57718-125">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="57718-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="57718-126">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="57718-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57718-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="57718-127">See Also</span></span>

[<span data-ttu-id="57718-128">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="57718-128">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="57718-129">Exibição de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="57718-129">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="57718-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="57718-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
