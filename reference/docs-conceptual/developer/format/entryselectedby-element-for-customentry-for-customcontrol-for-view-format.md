---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)
description: Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)
ms.openlocfilehash: 4821f22560f35034f90d018e5a109004f331441f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655344"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="77e2f-103">Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="77e2f-103">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="77e2f-104">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="77e2f-104">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="77e2f-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="77e2f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="77e2f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="77e2f-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="77e2f-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="77e2f-107">Attributes and Elements</span></span>

<span data-ttu-id="77e2f-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="77e2f-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="77e2f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="77e2f-109">Attributes</span></span>

<span data-ttu-id="77e2f-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="77e2f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="77e2f-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="77e2f-111">Child Elements</span></span>

|<span data-ttu-id="77e2f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="77e2f-112">Element</span></span>|<span data-ttu-id="77e2f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="77e2f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="77e2f-114">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="77e2f-114">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="77e2f-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="77e2f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="77e2f-116">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="77e2f-116">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="77e2f-117">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="77e2f-117">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="77e2f-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="77e2f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="77e2f-119">Especifica um conjunto de tipos .NET que usam essa definição do modo de exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="77e2f-119">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="77e2f-120">Elemento TypeName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="77e2f-120">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="77e2f-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="77e2f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="77e2f-122">Especifica um tipo .NET que usa essa definição do modo de exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="77e2f-122">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="77e2f-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="77e2f-123">Parent Elements</span></span>

|<span data-ttu-id="77e2f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="77e2f-124">Element</span></span>|<span data-ttu-id="77e2f-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="77e2f-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="77e2f-126">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="77e2f-126">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="77e2f-127">Define os controles usados por objetos .NET específicos.</span><span class="sxs-lookup"><span data-stu-id="77e2f-127">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="77e2f-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="77e2f-128">Remarks</span></span>

<span data-ttu-id="77e2f-129">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="77e2f-129">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="77e2f-130">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="77e2f-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="77e2f-131">As condições de seleção são usadas para definir uma condição que deve existir para a entrada a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="77e2f-131">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="77e2f-132">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="77e2f-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="77e2f-133">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [modo de exibição de controle personalizado](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="77e2f-133">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="77e2f-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="77e2f-134">See Also</span></span>

[<span data-ttu-id="77e2f-135">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="77e2f-135">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="77e2f-136">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="77e2f-136">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="77e2f-137">Elemento TypeName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="77e2f-137">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="77e2f-138">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="77e2f-138">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="77e2f-139">Exibição de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="77e2f-139">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="77e2f-140">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e2f-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
