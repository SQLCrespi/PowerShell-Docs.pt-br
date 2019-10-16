---
title: Elemento SelectionCondition para EntrySelectedBy para TableControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368385"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="7cc67-102">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="7cc67-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="7cc67-103">Define a condição que deve existir para ser usada para esta definição da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="7cc67-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="7cc67-104">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de tabela.</span><span class="sxs-lookup"><span data-stu-id="7cc67-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="7cc67-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element for TableRowEntry (Format) Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7cc67-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7cc67-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7cc67-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7cc67-107">Attributes and Elements</span></span>

<span data-ttu-id="7cc67-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento SelectionCondition.</span><span class="sxs-lookup"><span data-stu-id="7cc67-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7cc67-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="7cc67-109">Attributes</span></span>

<span data-ttu-id="7cc67-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7cc67-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7cc67-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="7cc67-111">Child Elements</span></span>

|<span data-ttu-id="7cc67-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7cc67-112">Element</span></span>|<span data-ttu-id="7cc67-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="7cc67-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7cc67-114">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="7cc67-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="7cc67-115">Optional element.</span></span><br /><br /> <span data-ttu-id="7cc67-116">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="7cc67-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="7cc67-117">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7cc67-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="7cc67-118">Optional element.</span></span><br /><br /> <span data-ttu-id="7cc67-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="7cc67-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="7cc67-120">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7cc67-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="7cc67-121">Optional element.</span></span><br /><br /> <span data-ttu-id="7cc67-122">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="7cc67-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="7cc67-123">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7cc67-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="7cc67-124">Optional element.</span></span><br /><br /> <span data-ttu-id="7cc67-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="7cc67-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7cc67-126">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="7cc67-126">Parent Elements</span></span>

|<span data-ttu-id="7cc67-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="7cc67-127">Element</span></span>|<span data-ttu-id="7cc67-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="7cc67-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7cc67-129">Elemento EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="7cc67-130">Define os tipos .NET que usam essa entrada de tabela ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="7cc67-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7cc67-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="7cc67-131">Remarks</span></span>

<span data-ttu-id="7cc67-132">Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="7cc67-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="7cc67-133">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="7cc67-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="7cc67-134">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="7cc67-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="7cc67-135">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="7cc67-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="7cc67-136">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7cc67-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7cc67-137">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="7cc67-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7cc67-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7cc67-138">See Also</span></span>

[<span data-ttu-id="7cc67-139">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="7cc67-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7cc67-140">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="7cc67-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7cc67-141">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="7cc67-142">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="7cc67-143">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7cc67-144">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7cc67-145">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="7cc67-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7cc67-146">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cc67-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
