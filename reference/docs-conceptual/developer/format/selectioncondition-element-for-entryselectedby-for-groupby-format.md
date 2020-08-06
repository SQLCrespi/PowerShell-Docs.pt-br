---
title: Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0930d8076c314c12cac6cdfa2b33716b7efeb6a9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772834"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="6e7b3-102">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="6e7b3-103">Define uma condição que deve existir para que uma definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="6e7b3-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="6e7b3-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element for CustomControl para GroupBy (Format) EntrySelectedBy Element for CustomEntry para o elemento SelectionCondition GroupBy (Format) para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e7b3-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e7b3-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e7b3-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6e7b3-107">Attributes and Elements</span></span>

<span data-ttu-id="6e7b3-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e7b3-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e7b3-109">Attributes</span></span>

<span data-ttu-id="6e7b3-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e7b3-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6e7b3-111">Child Elements</span></span>

|<span data-ttu-id="6e7b3-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e7b3-112">Element</span></span>|<span data-ttu-id="6e7b3-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e7b3-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e7b3-114">Elemento PropertyName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="6e7b3-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6e7b3-116">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6e7b3-117">Elemento ScriptBlock para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="6e7b3-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-118">Optional element.</span></span><br /><br /> <span data-ttu-id="6e7b3-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="6e7b3-120">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="6e7b3-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-121">Optional element.</span></span><br /><br /> <span data-ttu-id="6e7b3-122">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="6e7b3-123">Elemento TypeName para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="6e7b3-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-124">Optional element.</span></span><br /><br /> <span data-ttu-id="6e7b3-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6e7b3-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6e7b3-126">Parent Elements</span></span>

|<span data-ttu-id="6e7b3-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e7b3-127">Element</span></span>|<span data-ttu-id="6e7b3-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e7b3-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e7b3-129">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="6e7b3-130">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e7b3-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e7b3-131">Remarks</span></span>

<span data-ttu-id="6e7b3-132">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="6e7b3-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="6e7b3-133">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="6e7b3-134">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="6e7b3-135">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e7b3-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e7b3-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e7b3-136">See Also</span></span>

[<span data-ttu-id="6e7b3-137">Elemento PropertyName para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6e7b3-138">Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6e7b3-139">Elemento SelectionSetName para SelectionCondition para controle personalizado para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6e7b3-140">Elemento TypeName para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="6e7b3-141">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="6e7b3-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e7b3-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
