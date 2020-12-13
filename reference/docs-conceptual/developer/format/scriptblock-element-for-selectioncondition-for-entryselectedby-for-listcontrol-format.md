---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)
description: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: ec7691358d0ff3758411317a349221e1704a1895
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659901"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="70f72-103">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="70f72-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="70f72-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="70f72-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="70f72-105">Quando esse script é avaliado como `true` , a condição é atendida e a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="70f72-105">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="70f72-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) ListControl Element (Format) o elemento ListEntries (Format) ListEntry Element (Format) o elemento EntrySelectedBy para SelectionCondition para EntrySelectedBy (Format) ListEntry Element for SelectionCondition for EntrySelectedBy (Format) o elemento do ScriptBlock para ListEntry para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="70f72-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="70f72-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="70f72-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="70f72-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="70f72-108">Attributes and Elements</span></span>

<span data-ttu-id="70f72-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="70f72-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="70f72-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="70f72-110">Attributes</span></span>

<span data-ttu-id="70f72-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="70f72-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="70f72-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="70f72-112">Child Elements</span></span>

<span data-ttu-id="70f72-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="70f72-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="70f72-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="70f72-114">Parent Elements</span></span>

|<span data-ttu-id="70f72-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="70f72-115">Element</span></span>|<span data-ttu-id="70f72-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="70f72-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70f72-117">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="70f72-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="70f72-118">Define a condição que deve existir para que essa entrada de lista seja usada.</span><span class="sxs-lookup"><span data-stu-id="70f72-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="70f72-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="70f72-119">Text Value</span></span>

<span data-ttu-id="70f72-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="70f72-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="70f72-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="70f72-121">Remarks</span></span>

<span data-ttu-id="70f72-122">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="70f72-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="70f72-123">(Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando uma entrada ou item de exibição é usado](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="70f72-123">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="70f72-124">Para obter mais informações sobre os outros componentes de um modo de exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="70f72-124">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="70f72-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70f72-125">See Also</span></span>

[<span data-ttu-id="70f72-126">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="70f72-126">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="70f72-127">Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="70f72-127">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="70f72-128">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="70f72-128">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="70f72-129">Exibição de lista</span><span class="sxs-lookup"><span data-stu-id="70f72-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="70f72-130">Definindo condições para quando uma entrada ou item de exibição é usado</span><span class="sxs-lookup"><span data-stu-id="70f72-130">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="70f72-131">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f72-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
