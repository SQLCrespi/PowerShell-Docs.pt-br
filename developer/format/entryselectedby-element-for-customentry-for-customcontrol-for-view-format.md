---
title: Elemento EntrySelectedBy para CustomEntry para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066270"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="e987b-102">Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="e987b-103">Define os tipos de .NET que usam essa entrada personalizada ou a condição que deve existir para essa entrada a ser usado.</span><span class="sxs-lookup"><span data-stu-id="e987b-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="e987b-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento CustomControl (formato) CustomEntries elemento de configuração para CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para EntrySelectedBy de exibição (formato) Elemento para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e987b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e987b-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e987b-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="e987b-106">Attributes and Elements</span></span>

<span data-ttu-id="e987b-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="e987b-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e987b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e987b-108">Attributes</span></span>

<span data-ttu-id="e987b-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e987b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e987b-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e987b-110">Child Elements</span></span>

|<span data-ttu-id="e987b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="e987b-111">Element</span></span>|<span data-ttu-id="e987b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e987b-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e987b-113">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="e987b-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e987b-114">Optional element.</span></span><br /><br /> <span data-ttu-id="e987b-115">Define a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="e987b-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="e987b-116">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="e987b-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e987b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e987b-118">Especifica um conjunto de tipos do .NET que usam essa definição da exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="e987b-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="e987b-119">Elemento TypeName para EntrySelectedBy para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e987b-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e987b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e987b-121">Especifica um tipo .NET que usa essa definição da exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="e987b-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e987b-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e987b-122">Parent Elements</span></span>

|<span data-ttu-id="e987b-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e987b-123">Element</span></span>|<span data-ttu-id="e987b-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="e987b-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e987b-125">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="e987b-126">Define os controles usados por objetos específicos do .NET.</span><span class="sxs-lookup"><span data-stu-id="e987b-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e987b-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="e987b-127">Remarks</span></span>

<span data-ttu-id="e987b-128">Você deve especificar pelo menos um critério de seleção para uma entrada, conjunto de seleção ou tipo.</span><span class="sxs-lookup"><span data-stu-id="e987b-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="e987b-129">Não há nenhum limite máximo ao número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="e987b-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="e987b-130">Condições de seleção são usadas para definir uma condição que deve existir para a entrada a ser usado, como quando um objeto tem uma propriedade específica ou quando um valor de propriedade específica ou script avalia para `true`.</span><span class="sxs-lookup"><span data-stu-id="e987b-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="e987b-131">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou o Item está sendo usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e987b-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e987b-132">Para obter mais informações sobre os componentes de uma exibição de controle personalizado, consulte [modo de exibição de controle personalizado](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e987b-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e987b-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e987b-133">See Also</span></span>

[<span data-ttu-id="e987b-134">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="e987b-135">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e987b-136">Elemento TypeName para EntrySelectedBy para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e987b-137">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="e987b-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e987b-138">Modo de exibição de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="e987b-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e987b-139">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e987b-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
