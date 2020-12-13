---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)
description: Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: e93499691dd0046265e43abd26497b2974546083
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655094"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="6378c-103">Elemento SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="6378c-103">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="6378c-104">Define a condição que deve existir para usar essa definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="6378c-104">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="6378c-105">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de lista.</span><span class="sxs-lookup"><span data-stu-id="6378c-105">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="6378c-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries elemento (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6378c-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6378c-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6378c-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6378c-108">Attributes and Elements</span></span>

<span data-ttu-id="6378c-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="6378c-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6378c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6378c-110">Attributes</span></span>

<span data-ttu-id="6378c-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="6378c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6378c-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6378c-112">Child Elements</span></span>

|<span data-ttu-id="6378c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6378c-113">Element</span></span>|<span data-ttu-id="6378c-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6378c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6378c-115">Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-115">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="6378c-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6378c-116">Optional element.</span></span><br /><br /> <span data-ttu-id="6378c-117">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6378c-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6378c-118">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="6378c-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6378c-119">Optional element.</span></span><br /><br /> <span data-ttu-id="6378c-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6378c-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="6378c-121">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="6378c-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="6378c-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6378c-122">Optional element.</span></span><br /><br /> <span data-ttu-id="6378c-123">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="6378c-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="6378c-124">Elemento TypeName para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-124">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="6378c-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6378c-125">Optional element.</span></span><br /><br /> <span data-ttu-id="6378c-126">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6378c-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6378c-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6378c-127">Parent Elements</span></span>

|<span data-ttu-id="6378c-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="6378c-128">Element</span></span>|<span data-ttu-id="6378c-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="6378c-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6378c-130">Elemento EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="6378c-131">Define os tipos .NET que usam essa entrada de tabela ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="6378c-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6378c-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="6378c-132">Remarks</span></span>

<span data-ttu-id="6378c-133">lWhen você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="6378c-133">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="6378c-134">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6378c-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="6378c-135">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6378c-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="6378c-136">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6378c-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="6378c-137">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="6378c-137">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6378c-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6378c-138">See Also</span></span>

[<span data-ttu-id="6378c-139">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="6378c-139">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="6378c-140">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="6378c-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="6378c-141">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-141">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="6378c-142">Elemento SelectionSetName para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-142">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="6378c-143">Elemento TypeName para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6378c-143">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="6378c-144">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6378c-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
