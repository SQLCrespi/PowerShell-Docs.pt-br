---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para WideControl (formato)
description: Elemento SelectionCondition para EntrySelectedBy para WideControl (formato)
ms.openlocfilehash: 8c51ca72edc6ad174dc289c61a8987e8f9495d19
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655106"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="970fa-103">Elemento SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="970fa-103">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="970fa-104">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="970fa-104">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="970fa-105">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de entrada ampla.</span><span class="sxs-lookup"><span data-stu-id="970fa-105">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="970fa-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="970fa-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="970fa-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="970fa-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="970fa-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="970fa-108">Attributes and Elements</span></span>

<span data-ttu-id="970fa-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="970fa-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="970fa-110">Você deve especificar um único `PropertyName` `ScriptBlock` elemento ou.</span><span class="sxs-lookup"><span data-stu-id="970fa-110">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="970fa-111">Os `SelectionSetName` `TypeName` elementos e são opcionais.</span><span class="sxs-lookup"><span data-stu-id="970fa-111">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="970fa-112">Você pode especificar um de ambos os elementos.</span><span class="sxs-lookup"><span data-stu-id="970fa-112">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="970fa-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="970fa-113">Attributes</span></span>

<span data-ttu-id="970fa-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="970fa-114">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="970fa-115">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="970fa-115">Child Elements</span></span>

|<span data-ttu-id="970fa-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="970fa-116">Element</span></span>|<span data-ttu-id="970fa-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="970fa-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="970fa-118">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="970fa-118">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="970fa-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="970fa-119">Optional element.</span></span><br /><br /> <span data-ttu-id="970fa-120">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="970fa-120">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="970fa-121">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="970fa-121">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="970fa-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="970fa-122">Optional element.</span></span><br /><br /> <span data-ttu-id="970fa-123">Especifica o bloco de script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="970fa-123">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="970fa-124">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="970fa-124">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="970fa-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="970fa-125">Optional element.</span></span><br /><br /> <span data-ttu-id="970fa-126">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="970fa-126">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="970fa-127">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="970fa-127">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="970fa-128">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="970fa-128">Optional element.</span></span><br /><br /> <span data-ttu-id="970fa-129">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="970fa-129">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="970fa-130">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="970fa-130">Parent Elements</span></span>

|<span data-ttu-id="970fa-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="970fa-131">Element</span></span>|<span data-ttu-id="970fa-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="970fa-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="970fa-133">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="970fa-133">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="970fa-134">Define os tipos .NET que usam essa entrada ampla ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="970fa-134">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="970fa-135">Comentários</span><span class="sxs-lookup"><span data-stu-id="970fa-135">Remarks</span></span>

<span data-ttu-id="970fa-136">Cada entrada larga deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="970fa-136">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="970fa-137">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="970fa-137">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="970fa-138">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="970fa-138">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="970fa-139">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="970fa-139">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="970fa-140">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="970fa-140">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="970fa-141">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="970fa-141">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="970fa-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="970fa-142">See Also</span></span>

[<span data-ttu-id="970fa-143">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="970fa-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="970fa-144">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="970fa-144">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="970fa-145">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="970fa-145">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="970fa-146">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="970fa-146">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="970fa-147">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="970fa-147">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="970fa-148">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="970fa-148">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="970fa-149">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="970fa-149">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="970fa-150">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="970fa-150">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
