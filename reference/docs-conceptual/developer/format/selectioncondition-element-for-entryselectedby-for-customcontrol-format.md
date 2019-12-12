---
title: Elemento SelectionCondition para EntrySelectedBy para CustomControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 231e9c6d-09ec-4e68-80ee-0c8f7fe1b9f5
caps.latest.revision: 7
ms.openlocfilehash: 49e2c0cf09dfa55b535effcd431e980daf12fac3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368435"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="8ff9f-102">Elemento SelectionCondition para EntrySelectedBy para CustomControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="8ff9f-103">Define uma condição que deve existir para que uma definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="8ff9f-104">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="8ff9f-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl for View ( Format) elemento CustomItem para CustomEntry para CustomControl para o elemento View (Format) EntrySelectedBy para CustomEntry para CustomControl para o elemento View (Format) SelectionCondition para EntrySelectedBy para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8ff9f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8ff9f-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8ff9f-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8ff9f-107">Attributes and Elements</span></span>

<span data-ttu-id="8ff9f-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8ff9f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="8ff9f-109">Attributes</span></span>

<span data-ttu-id="8ff9f-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8ff9f-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="8ff9f-111">Child Elements</span></span>

|<span data-ttu-id="8ff9f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ff9f-112">Element</span></span>|<span data-ttu-id="8ff9f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ff9f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ff9f-114">Elemento PropertyName para SelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="8ff9f-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8ff9f-116">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="8ff9f-117">Elemento ScriptBlock para SelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="8ff9f-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="8ff9f-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="8ff9f-120">Elemento SelectionSetName para SelectionCondition para controle personalizado para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-120">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="8ff9f-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="8ff9f-122">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="8ff9f-123">Elemento TypeName para SelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-123">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="8ff9f-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-124">Optional element.</span></span><br /><br /> <span data-ttu-id="8ff9f-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8ff9f-126">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="8ff9f-126">Parent Elements</span></span>

|<span data-ttu-id="8ff9f-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ff9f-127">Element</span></span>|<span data-ttu-id="8ff9f-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ff9f-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ff9f-129">Elemento EntrySelectedBy para CustomEntry para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="8ff9f-130">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8ff9f-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="8ff9f-131">Remarks</span></span>

<span data-ttu-id="8ff9f-132">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="8ff9f-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="8ff9f-133">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="8ff9f-134">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="8ff9f-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="8ff9f-135">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8ff9f-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ff9f-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ff9f-136">See Also</span></span>

[<span data-ttu-id="8ff9f-137">Elemento PropertyName para SelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8ff9f-138">Elemento ScriptBlock para SelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8ff9f-139">Elemento SelectionSetName para SelectionCondition para controle personalizado para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8ff9f-140">Elemento TypeName para SelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-140">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8ff9f-141">Elemento EntrySelectedBy para CustomEntry para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="8ff9f-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8ff9f-142">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ff9f-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
