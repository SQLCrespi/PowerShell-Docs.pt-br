---
title: Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064128"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="9efdb-102">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9efdb-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="9efdb-103">Define a condição que deve existir para expandir os objetos da coleção desta definição.</span><span class="sxs-lookup"><span data-stu-id="9efdb-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="9efdb-104">Elemento (formato) elemento DefaultSettings (formato) elemento EnumerableExpansions (formato) elemento EnumerableExpansion (formato) EntrySelectedBy elemento de configuração para elemento de SelectionCondition EnumerableExpansion (formato) EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9efdb-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9efdb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9efdb-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9efdb-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="9efdb-106">Attributes and Elements</span></span>

<span data-ttu-id="9efdb-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="9efdb-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="9efdb-108">Você deve especificar um único `PropertyName` ou `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="9efdb-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="9efdb-109">O `SelectionSetName` e `TypeName` elementos são opcionais.</span><span class="sxs-lookup"><span data-stu-id="9efdb-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="9efdb-110">Você pode especificar um dos qualquer elemento.</span><span class="sxs-lookup"><span data-stu-id="9efdb-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9efdb-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9efdb-111">Attributes</span></span>

<span data-ttu-id="9efdb-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9efdb-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9efdb-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9efdb-113">Child Elements</span></span>

|<span data-ttu-id="9efdb-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9efdb-114">Element</span></span>|<span data-ttu-id="9efdb-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="9efdb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9efdb-116">Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9efdb-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9efdb-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9efdb-117">Optional element.</span></span><br /><br /> <span data-ttu-id="9efdb-118">Especifica a propriedade do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="9efdb-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="9efdb-119">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9efdb-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9efdb-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9efdb-120">Optional element.</span></span><br /><br /> <span data-ttu-id="9efdb-121">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="9efdb-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="9efdb-122">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9efdb-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9efdb-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9efdb-123">Optional element.</span></span><br /><br /> <span data-ttu-id="9efdb-124">Especifica o conjunto de tipos do .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="9efdb-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="9efdb-125">Elemento TypeName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9efdb-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="9efdb-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9efdb-126">Optional element.</span></span><br /><br /> <span data-ttu-id="9efdb-127">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="9efdb-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9efdb-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9efdb-128">Parent Elements</span></span>

|<span data-ttu-id="9efdb-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="9efdb-129">Element</span></span>|<span data-ttu-id="9efdb-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="9efdb-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9efdb-131">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="9efdb-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="9efdb-132">Define quais objetos de coleção do .NET são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="9efdb-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9efdb-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="9efdb-133">Remarks</span></span>

<span data-ttu-id="9efdb-134">Cada definição deve ter pelo menos um nome de tipo, conjunto de seleção ou condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="9efdb-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="9efdb-135">Quando você estiver definindo uma condição de seleção, os seguintes requisitos se aplicam:</span><span class="sxs-lookup"><span data-stu-id="9efdb-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="9efdb-136">A condição de seleção deve especificar um nome menos de uma propriedade ou um bloco de script, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="9efdb-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="9efdb-137">Os critérios de seleção podem especificar qualquer número de tipos do .NET ou seleção define, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="9efdb-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="9efdb-138">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para dados Diplaying](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9efdb-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9efdb-139">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9efdb-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9efdb-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9efdb-140">See Also</span></span>

[<span data-ttu-id="9efdb-141">Definir condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="9efdb-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9efdb-142">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9efdb-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
