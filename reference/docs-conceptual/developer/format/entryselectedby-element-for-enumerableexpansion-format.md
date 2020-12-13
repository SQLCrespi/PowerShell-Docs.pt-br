---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 8b2fff2d0b14d0622d0be2c5af3a95194c733a73
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652326"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="41c0f-103">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-103">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="41c0f-104">Define os tipos .NET que usam essa definição ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="41c0f-104">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="41c0f-105">Elemento de configuração (Format) DefaultSettings Element (Format) elemento EnumerableExpansions (Format) elemento EnumerableExpansion Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="41c0f-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41c0f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="41c0f-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41c0f-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="41c0f-107">Attributes and Elements</span></span>

<span data-ttu-id="41c0f-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="41c0f-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41c0f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="41c0f-109">Attributes</span></span>

<span data-ttu-id="41c0f-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="41c0f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41c0f-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="41c0f-111">Child Elements</span></span>

|<span data-ttu-id="41c0f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="41c0f-112">Element</span></span>|<span data-ttu-id="41c0f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="41c0f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41c0f-114">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-114">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="41c0f-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="41c0f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="41c0f-116">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="41c0f-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="41c0f-117">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-117">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="41c0f-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="41c0f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="41c0f-119">Especifica um conjunto de tipos .NET que usam essa definição de como os objetos de coleção são expandidos.</span><span class="sxs-lookup"><span data-stu-id="41c0f-119">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="41c0f-120">Elemento TypeName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-120">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="41c0f-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="41c0f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="41c0f-122">Especifica um tipo .NET que usa essa definição de como os objetos de coleção são expandidos.</span><span class="sxs-lookup"><span data-stu-id="41c0f-122">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="41c0f-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="41c0f-123">Parent Elements</span></span>

|<span data-ttu-id="41c0f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="41c0f-124">Element</span></span>|<span data-ttu-id="41c0f-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="41c0f-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41c0f-126">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-126">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="41c0f-127">Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="41c0f-127">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41c0f-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="41c0f-128">Remarks</span></span>

<span data-ttu-id="41c0f-129">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma entrada de definição.</span><span class="sxs-lookup"><span data-stu-id="41c0f-129">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="41c0f-130">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="41c0f-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="41c0f-131">As condições de seleção são usadas para definir uma condição que deve existir para que a definição seja usada, como quando um objeto tem uma propriedade específica ou que um valor de propriedade ou script específico é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="41c0f-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="41c0f-132">Para obter mais informações sobre condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="41c0f-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41c0f-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="41c0f-133">See Also</span></span>

[<span data-ttu-id="41c0f-134">Definir condições para a exibição de dados</span><span class="sxs-lookup"><span data-stu-id="41c0f-134">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="41c0f-135">Elemento EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-135">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="41c0f-136">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-136">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="41c0f-137">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-137">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="41c0f-138">Elemento TypeName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="41c0f-138">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="41c0f-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="41c0f-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
