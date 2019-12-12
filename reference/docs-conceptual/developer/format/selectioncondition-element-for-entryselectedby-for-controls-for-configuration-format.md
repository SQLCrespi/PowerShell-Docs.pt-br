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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368445"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="5d5eb-102">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="5d5eb-103">Define uma condição que deve existir para que uma definição de controle comum seja usada.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="5d5eb-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="5d5eb-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para Configuração (Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para CustomEntry para Configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5d5eb-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5d5eb-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d5eb-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5d5eb-107">Attributes and Elements</span></span>

<span data-ttu-id="5d5eb-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d5eb-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d5eb-109">Attributes</span></span>

<span data-ttu-id="5d5eb-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5d5eb-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="5d5eb-111">Child Elements</span></span>

|<span data-ttu-id="5d5eb-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d5eb-112">Element</span></span>|<span data-ttu-id="5d5eb-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d5eb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d5eb-114">Elemento PropertyName para SelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="5d5eb-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="5d5eb-116">Especifica uma propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="5d5eb-117">Elemento ScriptBlock para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="5d5eb-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="5d5eb-119">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="5d5eb-120">Elemento SelectionSetName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="5d5eb-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="5d5eb-122">Especifica o conjunto de tipos .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="5d5eb-123">Elemento TypeName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="5d5eb-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="5d5eb-125">Especifica um tipo .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5d5eb-126">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="5d5eb-126">Parent Elements</span></span>

|<span data-ttu-id="5d5eb-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d5eb-127">Element</span></span>|<span data-ttu-id="5d5eb-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d5eb-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d5eb-129">Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="5d5eb-130">Define os tipos .NET que usam essa entrada da definição de controle comum.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5d5eb-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="5d5eb-131">Remarks</span></span>

<span data-ttu-id="5d5eb-132">As diretrizes a seguir devem ser seguidas ao definir uma condição de seleção:</span><span class="sxs-lookup"><span data-stu-id="5d5eb-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="5d5eb-133">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="5d5eb-134">A condição de seleção pode especificar qualquer número de tipos .NET ou conjuntos de seleção, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="5d5eb-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="5d5eb-135">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="5d5eb-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d5eb-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5d5eb-136">See Also</span></span>

[<span data-ttu-id="5d5eb-137">Elemento PropertyName para SelectionCondition para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="5d5eb-138">Elemento ScriptBlock para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="5d5eb-139">Elemento SelectionSetName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="5d5eb-140">Elemento TypeName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="5d5eb-141">Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5d5eb-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="5d5eb-142">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d5eb-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
