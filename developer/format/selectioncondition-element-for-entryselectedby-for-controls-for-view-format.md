---
title: Elemento SelectionCondition para EntrySelectedBy controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064215"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="1e733-102">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="1e733-103">Define uma condição que deve existir para a definição de controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="1e733-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="1e733-104">Esse elemento é usado durante a definição de controles que podem ser usados por um modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="1e733-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="1e733-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento controles elemento (formato) controle elemento de configuração para controles para exibição (formato) CustomControl elemento de controle para controles para elemento CustomEntries de exibição (formato) CustomControl para controles para elemento de exibição (formato) CustomEntry CustomEntries para controles para elemento de exibição (formato) EntrySelectedBy CustomEntry para controles para elemento de exibição (formato) SelectionCondition EntrySelectedBy para controles para exibição ( Formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1e733-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1e733-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e733-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="1e733-107">Attributes and Elements</span></span>

<span data-ttu-id="1e733-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="1e733-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e733-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e733-109">Attributes</span></span>

<span data-ttu-id="1e733-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1e733-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e733-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1e733-111">Child Elements</span></span>

|<span data-ttu-id="1e733-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e733-112">Element</span></span>|<span data-ttu-id="1e733-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e733-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e733-114">Elemento PropertyName para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="1e733-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e733-115">Optional element.</span></span><br /><br /> <span data-ttu-id="1e733-116">Especifica uma propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1e733-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="1e733-117">Elemento ScriptBlock para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="1e733-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e733-118">Optional element.</span></span><br /><br /> <span data-ttu-id="1e733-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1e733-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="1e733-120">Elemento SelectionSetName para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="1e733-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e733-121">Optional element.</span></span><br /><br /> <span data-ttu-id="1e733-122">Especifica o conjunto de tipos do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1e733-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="1e733-123">Elemento TypeName para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="1e733-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="1e733-124">Optional element.</span></span><br /><br /> <span data-ttu-id="1e733-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="1e733-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1e733-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1e733-126">Parent Elements</span></span>

|<span data-ttu-id="1e733-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e733-127">Element</span></span>|<span data-ttu-id="1e733-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e733-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e733-129">Elemento EntrySelectedBy para CustomEntry controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="1e733-130">Define os tipos de .NET que usam essa definição de controle ou a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="1e733-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1e733-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="1e733-131">Remarks</span></span>

<span data-ttu-id="1e733-132">Quando você estiver definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="1e733-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="1e733-133">A condição de seleção deve especificar um nome menos de uma propriedade ou um bloco de script, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="1e733-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="1e733-134">Os critérios de seleção podem especificar qualquer número de tipos do .NET ou seleção define, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="1e733-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="1e733-135">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1e733-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e733-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e733-136">See Also</span></span>

[<span data-ttu-id="1e733-137">Elemento PropertyName para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="1e733-138">Elemento ScriptBlock para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="1e733-139">Elemento SelectionSetName para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="1e733-140">Elemento TypeName para SelectionCondition controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="1e733-141">Elemento EntrySelectedBy para CustomEntry controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="1e733-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="1e733-142">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e733-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
