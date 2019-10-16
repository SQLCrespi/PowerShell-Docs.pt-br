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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368775"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="500e1-102">Elemento EntrySelectedBy para CustomEntry para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="500e1-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="500e1-103">Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.</span><span class="sxs-lookup"><span data-stu-id="500e1-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="500e1-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Elemento para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="500e1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="500e1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="500e1-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="500e1-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="500e1-106">Attributes and Elements</span></span>

<span data-ttu-id="500e1-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="500e1-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="500e1-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="500e1-108">Attributes</span></span>

<span data-ttu-id="500e1-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="500e1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="500e1-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="500e1-110">Child Elements</span></span>

|<span data-ttu-id="500e1-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="500e1-111">Element</span></span>|<span data-ttu-id="500e1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="500e1-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="500e1-113">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="500e1-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="500e1-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="500e1-114">Optional element.</span></span><br /><br /> <span data-ttu-id="500e1-115">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="500e1-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="500e1-116">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="500e1-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="500e1-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="500e1-117">Optional element.</span></span><br /><br /> <span data-ttu-id="500e1-118">Especifica um conjunto de tipos .NET que usam essa definição do modo de exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="500e1-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="500e1-119">Elemento TypeName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="500e1-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="500e1-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="500e1-120">Optional element.</span></span><br /><br /> <span data-ttu-id="500e1-121">Especifica um tipo .NET que usa essa definição do modo de exibição de controle.</span><span class="sxs-lookup"><span data-stu-id="500e1-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="500e1-122">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="500e1-122">Parent Elements</span></span>

|<span data-ttu-id="500e1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="500e1-123">Element</span></span>|<span data-ttu-id="500e1-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="500e1-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="500e1-125">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="500e1-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="500e1-126">Define os controles usados por objetos .NET específicos.</span><span class="sxs-lookup"><span data-stu-id="500e1-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="500e1-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="500e1-127">Remarks</span></span>

<span data-ttu-id="500e1-128">Você deve especificar pelo menos um tipo, um conjunto de seleção ou uma condição de seleção para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="500e1-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="500e1-129">Não há nenhum limite máximo para o número de elementos filho que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="500e1-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="500e1-130">As condições de seleção são usadas para definir uma condição que deve existir para a entrada a ser usada, como quando um objeto tem uma propriedade específica ou quando um valor de propriedade ou script específico é avaliado como `true`.</span><span class="sxs-lookup"><span data-stu-id="500e1-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="500e1-131">Para obter mais informações sobre condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="500e1-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="500e1-132">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [modo de exibição de controle personalizado](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="500e1-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="500e1-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="500e1-133">See Also</span></span>

[<span data-ttu-id="500e1-134">Elemento SelectionCondition para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="500e1-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="500e1-135">Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="500e1-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="500e1-136">Elemento TypeName para EntrySelectedBy para CustomEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="500e1-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="500e1-137">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="500e1-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="500e1-138">Exibição de controle personalizado</span><span class="sxs-lookup"><span data-stu-id="500e1-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="500e1-139">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="500e1-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
