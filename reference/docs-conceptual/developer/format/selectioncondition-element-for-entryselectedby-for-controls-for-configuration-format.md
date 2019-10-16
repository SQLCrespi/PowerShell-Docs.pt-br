---
title: Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368445"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="4889a-102">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="4889a-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4889a-103">Define uma condição que deve existir para que uma definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="4889a-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="4889a-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="4889a-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4889a-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para Configuração (Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para CustomEntry para Configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="4889a-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4889a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4889a-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4889a-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4889a-107">Attributes and Elements</span></span>

<span data-ttu-id="4889a-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="4889a-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4889a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4889a-109">Attributes</span></span>

<span data-ttu-id="4889a-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4889a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4889a-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="4889a-111">Child Elements</span></span>

|<span data-ttu-id="4889a-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4889a-112">Element</span></span>|<span data-ttu-id="4889a-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="4889a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4889a-114">Elemento PropertyName para SelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="4889a-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="4889a-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4889a-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4889a-116">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="4889a-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="4889a-117">Elemento ScriptBlock para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="4889a-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4889a-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4889a-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="4889a-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="4889a-120">Elemento SelectionSetName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="4889a-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4889a-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4889a-122">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="4889a-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="4889a-123">Elemento TypeName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="4889a-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4889a-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4889a-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="4889a-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4889a-126">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="4889a-126">Parent Elements</span></span>

|<span data-ttu-id="4889a-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="4889a-127">Element</span></span>|<span data-ttu-id="4889a-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="4889a-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4889a-129">Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="4889a-130">Define os tipos .NET que usam essa entrada da definição de controle comum.</span><span class="sxs-lookup"><span data-stu-id="4889a-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4889a-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="4889a-131">Remarks</span></span>

<span data-ttu-id="4889a-132">As diretrizes a seguir devem ser seguidas ao definir uma condição de seleção:</span><span class="sxs-lookup"><span data-stu-id="4889a-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="4889a-133">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="4889a-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="4889a-134">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="4889a-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="4889a-135">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4889a-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4889a-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4889a-136">See Also</span></span>

[<span data-ttu-id="4889a-137">Elemento PropertyName para SelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="4889a-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4889a-138">Elemento ScriptBlock para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4889a-139">Elemento SelectionSetName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4889a-140">Elemento TypeName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="4889a-141">Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="4889a-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="4889a-142">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4889a-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
