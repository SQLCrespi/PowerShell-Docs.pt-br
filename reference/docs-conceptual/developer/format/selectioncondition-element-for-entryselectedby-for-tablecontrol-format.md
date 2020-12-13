---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)
description: Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)
ms.openlocfilehash: 22f304615c6433ffb67f3b4046b645d0c37be8a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645758"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="f43a3-103">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f43a3-103">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="f43a3-104">Define a condição que deve existir para ser usada para esta definição da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="f43a3-104">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="f43a3-105">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de tabela.</span><span class="sxs-lookup"><span data-stu-id="f43a3-105">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="f43a3-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f43a3-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f43a3-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f43a3-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f43a3-108">Attributes and Elements</span></span>

<span data-ttu-id="f43a3-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento SelectionCondition.</span><span class="sxs-lookup"><span data-stu-id="f43a3-109">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f43a3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f43a3-110">Attributes</span></span>

<span data-ttu-id="f43a3-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f43a3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f43a3-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f43a3-112">Child Elements</span></span>

|<span data-ttu-id="f43a3-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f43a3-113">Element</span></span>|<span data-ttu-id="f43a3-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="f43a3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f43a3-115">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="f43a3-115">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="f43a3-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f43a3-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f43a3-117">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f43a3-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f43a3-118">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f43a3-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f43a3-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f43a3-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f43a3-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="f43a3-121">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f43a3-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f43a3-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f43a3-123">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="f43a3-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="f43a3-124">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-124">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f43a3-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f43a3-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f43a3-126">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f43a3-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f43a3-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f43a3-127">Parent Elements</span></span>

|<span data-ttu-id="f43a3-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="f43a3-128">Element</span></span>|<span data-ttu-id="f43a3-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="f43a3-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f43a3-130">Elemento EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="f43a3-131">Define os tipos .NET que usam essa entrada de tabela ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="f43a3-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f43a3-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="f43a3-132">Remarks</span></span>

<span data-ttu-id="f43a3-133">Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="f43a3-133">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f43a3-134">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="f43a3-134">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="f43a3-135">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="f43a3-135">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="f43a3-136">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="f43a3-136">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="f43a3-137">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f43a3-137">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f43a3-138">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f43a3-138">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f43a3-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f43a3-139">See Also</span></span>

[<span data-ttu-id="f43a3-140">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="f43a3-140">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f43a3-141">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="f43a3-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f43a3-142">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-142">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="f43a3-143">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="f43a3-143">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="f43a3-144">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-144">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f43a3-145">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-145">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f43a3-146">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f43a3-146">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f43a3-147">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f43a3-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
