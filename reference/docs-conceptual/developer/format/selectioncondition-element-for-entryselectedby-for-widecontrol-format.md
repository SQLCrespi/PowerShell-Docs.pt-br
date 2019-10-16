---
title: Elemento SelectionCondition para EntrySelectedBy para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7a9f086-b1ca-4400-9be7-9ec1ec8880f3
caps.latest.revision: 11
ms.openlocfilehash: f20679e3392b99a049c075f24c7712262bab08e1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364775"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="3250b-102">Elemento SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3250b-102">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="3250b-103">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="3250b-103">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="3250b-104">Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de entrada ampla.</span><span class="sxs-lookup"><span data-stu-id="3250b-104">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="3250b-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="3250b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3250b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3250b-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3250b-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3250b-107">Attributes and Elements</span></span>

<span data-ttu-id="3250b-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="3250b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="3250b-109">Você deve especificar um único elemento `PropertyName` ou `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="3250b-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="3250b-110">Os elementos `SelectionSetName` e `TypeName` são opcionais.</span><span class="sxs-lookup"><span data-stu-id="3250b-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="3250b-111">Você pode especificar um de ambos os elementos.</span><span class="sxs-lookup"><span data-stu-id="3250b-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3250b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3250b-112">Attributes</span></span>

<span data-ttu-id="3250b-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3250b-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3250b-114">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="3250b-114">Child Elements</span></span>

|<span data-ttu-id="3250b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="3250b-115">Element</span></span>|<span data-ttu-id="3250b-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="3250b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3250b-117">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-117">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="3250b-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3250b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3250b-119">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3250b-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="3250b-120">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="3250b-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3250b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3250b-122">Especifica o bloco de script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3250b-122">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="3250b-123">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="3250b-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3250b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3250b-125">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3250b-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="3250b-126">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-126">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="3250b-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3250b-127">Optional element.</span></span><br /><br /> <span data-ttu-id="3250b-128">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="3250b-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3250b-129">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="3250b-129">Parent Elements</span></span>

|<span data-ttu-id="3250b-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="3250b-130">Element</span></span>|<span data-ttu-id="3250b-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="3250b-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3250b-132">Elemento EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-132">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="3250b-133">Define os tipos .NET que usam essa entrada ampla ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="3250b-133">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3250b-134">Comentários</span><span class="sxs-lookup"><span data-stu-id="3250b-134">Remarks</span></span>

<span data-ttu-id="3250b-135">Cada entrada larga deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="3250b-135">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="3250b-136">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="3250b-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="3250b-137">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="3250b-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="3250b-138">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="3250b-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="3250b-139">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="3250b-139">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="3250b-140">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="3250b-140">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3250b-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3250b-141">See Also</span></span>

[<span data-ttu-id="3250b-142">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="3250b-142">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="3250b-143">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="3250b-143">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="3250b-144">Elemento EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-144">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="3250b-145">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-145">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="3250b-146">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-146">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3250b-147">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-147">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="3250b-148">Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3250b-148">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3250b-149">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3250b-149">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
