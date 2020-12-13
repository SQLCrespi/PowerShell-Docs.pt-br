---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 3ecf7fde99b9ee66a153eea416792f351ff62af3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647913"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="08bfd-103">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="08bfd-103">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="08bfd-104">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="08bfd-104">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="08bfd-105">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="08bfd-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="08bfd-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="08bfd-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="08bfd-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="08bfd-107">Attributes and Elements</span></span>

<span data-ttu-id="08bfd-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="08bfd-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="08bfd-109">Você deve especificar um único `PropertyName` `ScriptBlock` elemento ou.</span><span class="sxs-lookup"><span data-stu-id="08bfd-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="08bfd-110">Os `SelectionSetName` `TypeName` elementos e são opcionais.</span><span class="sxs-lookup"><span data-stu-id="08bfd-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="08bfd-111">Você pode especificar um de ambos os elementos.</span><span class="sxs-lookup"><span data-stu-id="08bfd-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="08bfd-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="08bfd-112">Attributes</span></span>

<span data-ttu-id="08bfd-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="08bfd-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="08bfd-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="08bfd-114">Child Elements</span></span>

|<span data-ttu-id="08bfd-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="08bfd-115">Element</span></span>|<span data-ttu-id="08bfd-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="08bfd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="08bfd-117">Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="08bfd-117">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="08bfd-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="08bfd-118">Optional element.</span></span><br /><br /> <span data-ttu-id="08bfd-119">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="08bfd-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="08bfd-120">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="08bfd-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="08bfd-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="08bfd-121">Optional element.</span></span><br /><br /> <span data-ttu-id="08bfd-122">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="08bfd-122">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="08bfd-123">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="08bfd-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="08bfd-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="08bfd-124">Optional element.</span></span><br /><br /> <span data-ttu-id="08bfd-125">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="08bfd-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="08bfd-126">Elemento TypeName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="08bfd-126">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="08bfd-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="08bfd-127">Optional element.</span></span><br /><br /> <span data-ttu-id="08bfd-128">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="08bfd-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="08bfd-129">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="08bfd-129">Parent Elements</span></span>

|<span data-ttu-id="08bfd-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="08bfd-130">Element</span></span>|<span data-ttu-id="08bfd-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="08bfd-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="08bfd-132">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="08bfd-132">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="08bfd-133">Define quais objetos de coleção .NET são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="08bfd-133">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="08bfd-134">Comentários</span><span class="sxs-lookup"><span data-stu-id="08bfd-134">Remarks</span></span>

<span data-ttu-id="08bfd-135">Cada definição deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="08bfd-135">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="08bfd-136">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="08bfd-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="08bfd-137">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="08bfd-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="08bfd-138">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="08bfd-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="08bfd-139">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para a reprodução de dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="08bfd-139">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="08bfd-140">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="08bfd-140">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="08bfd-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08bfd-141">See Also</span></span>

[<span data-ttu-id="08bfd-142">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="08bfd-142">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="08bfd-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="08bfd-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
