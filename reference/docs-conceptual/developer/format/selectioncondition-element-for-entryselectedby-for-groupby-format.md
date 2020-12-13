---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)
description: Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)
ms.openlocfilehash: 14c293b6bc6d6accc201de35be9219349079801d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664745"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="0aa45-103">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-103">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="0aa45-104">Define uma condição que deve existir para que uma definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="0aa45-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="0aa45-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="0aa45-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="0aa45-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element for CustomEntry para o elemento SelectionCondition GroupBy (Format) para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0aa45-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0aa45-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0aa45-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0aa45-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0aa45-108">Attributes and Elements</span></span>

<span data-ttu-id="0aa45-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="0aa45-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0aa45-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0aa45-110">Attributes</span></span>

<span data-ttu-id="0aa45-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0aa45-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0aa45-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0aa45-112">Child Elements</span></span>

|<span data-ttu-id="0aa45-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0aa45-113">Element</span></span>|<span data-ttu-id="0aa45-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="0aa45-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0aa45-115">Elemento PropertyName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-115">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="0aa45-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0aa45-116">Optional element.</span></span><br /><br /> <span data-ttu-id="0aa45-117">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0aa45-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="0aa45-118">Elemento ScriptBlock para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0aa45-118">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="0aa45-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0aa45-119">Optional element.</span></span><br /><br /> <span data-ttu-id="0aa45-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0aa45-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="0aa45-121">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-121">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="0aa45-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0aa45-122">Optional element.</span></span><br /><br /> <span data-ttu-id="0aa45-123">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0aa45-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="0aa45-124">Elemento TypeName para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0aa45-124">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="0aa45-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0aa45-125">Optional element.</span></span><br /><br /> <span data-ttu-id="0aa45-126">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0aa45-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0aa45-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0aa45-127">Parent Elements</span></span>

|<span data-ttu-id="0aa45-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="0aa45-128">Element</span></span>|<span data-ttu-id="0aa45-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="0aa45-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0aa45-130">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-130">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="0aa45-131">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="0aa45-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0aa45-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="0aa45-132">Remarks</span></span>

<span data-ttu-id="0aa45-133">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="0aa45-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="0aa45-134">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="0aa45-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="0aa45-135">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="0aa45-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="0aa45-136">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0aa45-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0aa45-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0aa45-137">See Also</span></span>

[<span data-ttu-id="0aa45-138">Elemento PropertyName para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="0aa45-139">Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="0aa45-140">Elemento SelectionSetName para SelectionCondition para controle personalizado para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="0aa45-141">Elemento TypeName para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="0aa45-141">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="0aa45-142">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="0aa45-142">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="0aa45-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aa45-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
