---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)
description: Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)
ms.openlocfilehash: 5af4abe081ca268699d281a1b586a584107b9a83
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652353"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="12a29-103">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-103">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="12a29-104">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="12a29-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="12a29-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="12a29-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="12a29-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy elemento para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="12a29-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="12a29-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="12a29-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12a29-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="12a29-108">Attributes and Elements</span></span>

<span data-ttu-id="12a29-109">As seções a seguir descrevem atributos, elementos filho e elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="12a29-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="12a29-110">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma definição.</span><span class="sxs-lookup"><span data-stu-id="12a29-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="12a29-111">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="12a29-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="12a29-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="12a29-112">Attributes</span></span>

<span data-ttu-id="12a29-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="12a29-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="12a29-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="12a29-114">Child Elements</span></span>

|<span data-ttu-id="12a29-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="12a29-115">Element</span></span>|<span data-ttu-id="12a29-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="12a29-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12a29-117">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="12a29-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="12a29-118">Optional element.</span></span><br /><br /> <span data-ttu-id="12a29-119">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="12a29-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="12a29-120">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-120">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="12a29-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="12a29-121">Optional element.</span></span><br /><br /> <span data-ttu-id="12a29-122">Especifica um conjunto de tipos .NET que usam essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="12a29-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="12a29-123">Elemento TypeName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-123">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="12a29-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="12a29-124">Optional element.</span></span><br /><br /> <span data-ttu-id="12a29-125">Especifica um tipo .NET que usa essa definição do controle.</span><span class="sxs-lookup"><span data-stu-id="12a29-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="12a29-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="12a29-126">Parent Elements</span></span>

|<span data-ttu-id="12a29-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="12a29-127">Element</span></span>|<span data-ttu-id="12a29-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="12a29-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="12a29-129">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="12a29-130">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="12a29-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12a29-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="12a29-131">Remarks</span></span>

<span data-ttu-id="12a29-132">As condições de seleção são usadas para definir uma condição que deve existir para a definição a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor ou script de propriedade específica é avaliado como `true` .</span><span class="sxs-lookup"><span data-stu-id="12a29-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="12a29-133">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="12a29-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="12a29-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12a29-134">See Also</span></span>

[<span data-ttu-id="12a29-135">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="12a29-136">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-136">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="12a29-137">Elemento TypeName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-137">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="12a29-138">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="12a29-138">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="12a29-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="12a29-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
