---
title: Elemento SelectionCondition para EntrySelectedBy para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1c14b2638249bdbfe25f7a96e917d66ea10ed239
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787573"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="e6f26-102">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="e6f26-103">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="e6f26-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="e6f26-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="e6f26-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e6f26-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="e6f26-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e6f26-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6f26-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e6f26-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e6f26-107">Attributes and Elements</span></span>

<span data-ttu-id="e6f26-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="e6f26-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e6f26-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6f26-109">Attributes</span></span>

<span data-ttu-id="e6f26-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e6f26-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e6f26-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e6f26-111">Child Elements</span></span>

|<span data-ttu-id="e6f26-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6f26-112">Element</span></span>|<span data-ttu-id="e6f26-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6f26-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e6f26-114">Elemento PropertyName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e6f26-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6f26-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e6f26-116">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="e6f26-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="e6f26-117">Elemento ScriptBlock para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e6f26-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6f26-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e6f26-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="e6f26-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="e6f26-120">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e6f26-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6f26-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e6f26-122">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="e6f26-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="e6f26-123">Elemento TypeName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e6f26-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6f26-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e6f26-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="e6f26-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e6f26-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e6f26-126">Parent Elements</span></span>

|<span data-ttu-id="e6f26-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6f26-127">Element</span></span>|<span data-ttu-id="e6f26-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6f26-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e6f26-129">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="e6f26-130">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="e6f26-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e6f26-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6f26-131">Remarks</span></span>

<span data-ttu-id="e6f26-132">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="e6f26-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="e6f26-133">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="e6f26-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="e6f26-134">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="e6f26-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="e6f26-135">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e6f26-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6f26-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6f26-136">See Also</span></span>

[<span data-ttu-id="e6f26-137">Elemento PropertyName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e6f26-138">Elemento ScriptBlock para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e6f26-139">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e6f26-140">Elemento TypeName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e6f26-141">Elemento EntrySelectedBy para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e6f26-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="e6f26-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6f26-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
