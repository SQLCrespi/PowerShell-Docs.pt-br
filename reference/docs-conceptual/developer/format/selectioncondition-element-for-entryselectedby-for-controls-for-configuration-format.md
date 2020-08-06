---
title: Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 748aa1aa0ba603a44334d9401e9e2c0e68f14e03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783408"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="82757-102">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="82757-103">Define uma condição que deve existir para que uma definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="82757-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="82757-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="82757-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="82757-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para o elemento de configuração (Format) CustomEntry para CustomControl para controles para EntrySelectedBy para CustomEntry para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="82757-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82757-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82757-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82757-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="82757-107">Attributes and Elements</span></span>

<span data-ttu-id="82757-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionCondition` elemento.</span><span class="sxs-lookup"><span data-stu-id="82757-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82757-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="82757-109">Attributes</span></span>

<span data-ttu-id="82757-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="82757-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82757-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="82757-111">Child Elements</span></span>

|<span data-ttu-id="82757-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="82757-112">Element</span></span>|<span data-ttu-id="82757-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="82757-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82757-114">Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="82757-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="82757-115">Optional element.</span></span><br /><br /> <span data-ttu-id="82757-116">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="82757-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="82757-117">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="82757-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="82757-118">Optional element.</span></span><br /><br /> <span data-ttu-id="82757-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="82757-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="82757-120">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="82757-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="82757-121">Optional element.</span></span><br /><br /> <span data-ttu-id="82757-122">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="82757-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="82757-123">Elemento TypeName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="82757-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="82757-124">Optional element.</span></span><br /><br /> <span data-ttu-id="82757-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="82757-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="82757-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="82757-126">Parent Elements</span></span>

|<span data-ttu-id="82757-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="82757-127">Element</span></span>|<span data-ttu-id="82757-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="82757-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82757-129">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="82757-130">Define os tipos .NET que usam essa entrada da definição de controle comum.</span><span class="sxs-lookup"><span data-stu-id="82757-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="82757-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="82757-131">Remarks</span></span>

<span data-ttu-id="82757-132">As diretrizes a seguir devem ser seguidas ao definir uma condição de seleção:</span><span class="sxs-lookup"><span data-stu-id="82757-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="82757-133">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="82757-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="82757-134">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="82757-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="82757-135">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="82757-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82757-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="82757-136">See Also</span></span>

[<span data-ttu-id="82757-137">Elemento PropertyName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="82757-138">Elemento ScriptBlock para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="82757-139">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="82757-140">Elemento TypeName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="82757-141">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="82757-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="82757-142">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82757-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
