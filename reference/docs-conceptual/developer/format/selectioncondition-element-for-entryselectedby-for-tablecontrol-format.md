---
title: Elemento SelectionCondition para EntrySelectedBy para TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4a829f9daef22c4b3fd6b21dfb3af2f8539bdeb3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780280"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="35732-102">Elemento SelectionCondition para EntrySelectedBy para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="35732-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="35732-103">Define a condição que deve existir para ser usada para esta definição da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="35732-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="35732-104">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de tabela.</span><span class="sxs-lookup"><span data-stu-id="35732-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="35732-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format) TableRowEntries Element (Format) TableRowEntry elemento (Format) EntrySelectedBy Element para TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="35732-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="35732-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="35732-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="35732-107">Attributes and Elements</span></span>

<span data-ttu-id="35732-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento SelectionCondition.</span><span class="sxs-lookup"><span data-stu-id="35732-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="35732-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="35732-109">Attributes</span></span>

<span data-ttu-id="35732-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="35732-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="35732-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="35732-111">Child Elements</span></span>

|<span data-ttu-id="35732-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="35732-112">Element</span></span>|<span data-ttu-id="35732-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="35732-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35732-114">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="35732-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="35732-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="35732-115">Optional element.</span></span><br /><br /> <span data-ttu-id="35732-116">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="35732-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="35732-117">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="35732-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="35732-118">Optional element.</span></span><br /><br /> <span data-ttu-id="35732-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="35732-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="35732-120">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="35732-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="35732-121">Optional element.</span></span><br /><br /> <span data-ttu-id="35732-122">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="35732-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="35732-123">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="35732-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="35732-124">Optional element.</span></span><br /><br /> <span data-ttu-id="35732-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="35732-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="35732-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="35732-126">Parent Elements</span></span>

|<span data-ttu-id="35732-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="35732-127">Element</span></span>|<span data-ttu-id="35732-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="35732-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35732-129">Elemento EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="35732-130">Define os tipos .NET que usam essa entrada de tabela ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="35732-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="35732-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="35732-131">Remarks</span></span>

<span data-ttu-id="35732-132">Cada entrada de lista deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="35732-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="35732-133">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="35732-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="35732-134">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="35732-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="35732-135">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="35732-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="35732-136">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="35732-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="35732-137">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="35732-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35732-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="35732-138">See Also</span></span>

[<span data-ttu-id="35732-139">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="35732-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="35732-140">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="35732-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="35732-141">Elemento EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="35732-142">Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="35732-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="35732-143">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="35732-144">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="35732-145">Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="35732-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="35732-146">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35732-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
