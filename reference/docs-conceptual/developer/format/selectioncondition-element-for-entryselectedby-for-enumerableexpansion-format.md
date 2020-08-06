---
title: Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d5858145e092dc962174a776889a4f62db366d71
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785329"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="bcffc-102">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="bcffc-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="bcffc-103">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="bcffc-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="bcffc-104">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="bcffc-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bcffc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bcffc-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bcffc-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bcffc-106">Attributes and Elements</span></span>

<span data-ttu-id="bcffc-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="bcffc-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="bcffc-108">Você deve especificar um único `PropertyName` `ScriptBlock` elemento ou.</span><span class="sxs-lookup"><span data-stu-id="bcffc-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="bcffc-109">Os `SelectionSetName` `TypeName` elementos e são opcionais.</span><span class="sxs-lookup"><span data-stu-id="bcffc-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="bcffc-110">Você pode especificar um de ambos os elementos.</span><span class="sxs-lookup"><span data-stu-id="bcffc-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bcffc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bcffc-111">Attributes</span></span>

<span data-ttu-id="bcffc-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bcffc-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bcffc-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bcffc-113">Child Elements</span></span>

|<span data-ttu-id="bcffc-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="bcffc-114">Element</span></span>|<span data-ttu-id="bcffc-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="bcffc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bcffc-116">Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="bcffc-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="bcffc-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bcffc-117">Optional element.</span></span><br /><br /> <span data-ttu-id="bcffc-118">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bcffc-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="bcffc-119">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="bcffc-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="bcffc-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bcffc-120">Optional element.</span></span><br /><br /> <span data-ttu-id="bcffc-121">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bcffc-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="bcffc-122">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="bcffc-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="bcffc-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bcffc-123">Optional element.</span></span><br /><br /> <span data-ttu-id="bcffc-124">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bcffc-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="bcffc-125">Elemento TypeName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="bcffc-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="bcffc-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bcffc-126">Optional element.</span></span><br /><br /> <span data-ttu-id="bcffc-127">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bcffc-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bcffc-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bcffc-128">Parent Elements</span></span>

|<span data-ttu-id="bcffc-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="bcffc-129">Element</span></span>|<span data-ttu-id="bcffc-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="bcffc-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bcffc-131">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="bcffc-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="bcffc-132">Define quais objetos de coleção .NET são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="bcffc-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bcffc-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="bcffc-133">Remarks</span></span>

<span data-ttu-id="bcffc-134">Cada definição deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="bcffc-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="bcffc-135">Quando você está definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="bcffc-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="bcffc-136">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="bcffc-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="bcffc-137">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="bcffc-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="bcffc-138">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para a reprodução de dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bcffc-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bcffc-139">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="bcffc-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcffc-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bcffc-140">See Also</span></span>

[<span data-ttu-id="bcffc-141">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="bcffc-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="bcffc-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcffc-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
