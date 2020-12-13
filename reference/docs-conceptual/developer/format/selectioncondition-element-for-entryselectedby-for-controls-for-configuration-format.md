---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)
description: Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645774"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="a07eb-103">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-103">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="a07eb-104">Define uma condição que deve existir para que uma definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="a07eb-104">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="a07eb-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="a07eb-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="a07eb-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para o elemento de configuração (Format) CustomEntry para CustomControl para controles para EntrySelectedBy para CustomEntry para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="a07eb-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a07eb-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a07eb-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a07eb-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a07eb-108">Attributes and Elements</span></span>

<span data-ttu-id="a07eb-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="a07eb-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a07eb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a07eb-110">Attributes</span></span>

<span data-ttu-id="a07eb-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="a07eb-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a07eb-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a07eb-112">Child Elements</span></span>

|<span data-ttu-id="a07eb-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a07eb-113">Element</span></span>|<span data-ttu-id="a07eb-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="a07eb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a07eb-115">Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-115">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a07eb-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a07eb-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a07eb-117">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="a07eb-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a07eb-118">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-118">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a07eb-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a07eb-119">Optional element.</span></span><br /><br /> <span data-ttu-id="a07eb-120">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="a07eb-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="a07eb-121">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-121">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a07eb-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a07eb-122">Optional element.</span></span><br /><br /> <span data-ttu-id="a07eb-123">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="a07eb-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="a07eb-124">Elemento TypeName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-124">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a07eb-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a07eb-125">Optional element.</span></span><br /><br /> <span data-ttu-id="a07eb-126">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="a07eb-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a07eb-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a07eb-127">Parent Elements</span></span>

|<span data-ttu-id="a07eb-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="a07eb-128">Element</span></span>|<span data-ttu-id="a07eb-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="a07eb-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a07eb-130">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-130">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="a07eb-131">Define os tipos .NET que usam essa entrada da definição de controle comum.</span><span class="sxs-lookup"><span data-stu-id="a07eb-131">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a07eb-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="a07eb-132">Remarks</span></span>

<span data-ttu-id="a07eb-133">As diretrizes a seguir devem ser seguidas ao definir uma condição de seleção:</span><span class="sxs-lookup"><span data-stu-id="a07eb-133">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="a07eb-134">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a07eb-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="a07eb-135">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a07eb-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="a07eb-136">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a07eb-136">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a07eb-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a07eb-137">See Also</span></span>

[<span data-ttu-id="a07eb-138">Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-138">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a07eb-139">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-139">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a07eb-140">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-140">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a07eb-141">Elemento TypeName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-141">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a07eb-142">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="a07eb-142">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="a07eb-143">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a07eb-143">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
