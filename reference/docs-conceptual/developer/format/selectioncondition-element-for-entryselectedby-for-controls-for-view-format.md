---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)
description: Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)
ms.openlocfilehash: 16b048e73195b3d6168724714ff223851dc1b20b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664848"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="96b07-103">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-103">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="96b07-104">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="96b07-104">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="96b07-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="96b07-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="96b07-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="96b07-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="96b07-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="96b07-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96b07-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="96b07-108">Attributes and Elements</span></span>

<span data-ttu-id="96b07-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="96b07-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="96b07-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="96b07-110">Attributes</span></span>

<span data-ttu-id="96b07-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="96b07-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="96b07-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="96b07-112">Child Elements</span></span>

|<span data-ttu-id="96b07-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="96b07-113">Element</span></span>|<span data-ttu-id="96b07-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="96b07-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96b07-115">Elemento PropertyName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-115">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="96b07-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="96b07-116">Optional element.</span></span><br /><br /> <span data-ttu-id="96b07-117">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="96b07-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="96b07-118">Elemento ScriptBlock para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-118">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="96b07-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="96b07-119">Optional element.</span></span><br /><br /> <span data-ttu-id="96b07-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="96b07-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="96b07-121">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-121">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="96b07-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="96b07-122">Optional element.</span></span><br /><br /> <span data-ttu-id="96b07-123">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="96b07-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="96b07-124">Elemento TypeName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-124">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="96b07-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="96b07-125">Optional element.</span></span><br /><br /> <span data-ttu-id="96b07-126">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="96b07-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="96b07-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="96b07-127">Parent Elements</span></span>

|<span data-ttu-id="96b07-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="96b07-128">Element</span></span>|<span data-ttu-id="96b07-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="96b07-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96b07-130">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-130">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="96b07-131">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="96b07-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="96b07-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="96b07-132">Remarks</span></span>

<span data-ttu-id="96b07-133">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="96b07-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="96b07-134">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="96b07-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="96b07-135">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="96b07-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="96b07-136">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="96b07-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96b07-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96b07-137">See Also</span></span>

[<span data-ttu-id="96b07-138">Elemento PropertyName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-138">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="96b07-139">Elemento ScriptBlock para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-139">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="96b07-140">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-140">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="96b07-141">Elemento TypeName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-141">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="96b07-142">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="96b07-142">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="96b07-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="96b07-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
