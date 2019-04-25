---
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064337"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="92523-102">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="92523-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="92523-103">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="92523-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="92523-104">Quando esse script é avaliado para `true`, a condição for atendida e a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="92523-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="92523-105">Elemento (formato) elemento ViewDefinitions (formato) exibição elemento (formato) elemento ListControl (formato) ListEntries elemento (formato) ListEntry elemento (formato) EntrySelectedBy elemento de configuração para elemento de SelectionCondition ListEntry (formato) EntrySelectedBy para elemento de ScriptBlock ListEntry (formato) SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="92523-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92523-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92523-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92523-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="92523-107">Attributes and Elements</span></span>

<span data-ttu-id="92523-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="92523-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92523-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="92523-109">Attributes</span></span>

<span data-ttu-id="92523-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="92523-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92523-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="92523-111">Child Elements</span></span>

<span data-ttu-id="92523-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="92523-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92523-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="92523-113">Parent Elements</span></span>

|<span data-ttu-id="92523-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="92523-114">Element</span></span>|<span data-ttu-id="92523-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="92523-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92523-116">Elemento SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="92523-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="92523-117">Define a condição que deve existir para essa entrada de lista a ser usado.</span><span class="sxs-lookup"><span data-stu-id="92523-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92523-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="92523-118">Text Value</span></span>

<span data-ttu-id="92523-119">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="92523-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="92523-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="92523-120">Remarks</span></span>

<span data-ttu-id="92523-121">A condição de seleção deve especificar pelo menos um script ou a propriedade nome para avaliar, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="92523-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="92523-122">(Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para quando uma entrada de exibição ou o Item está sendo usado](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="92523-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="92523-123">Para obter mais informações sobre os outros componentes de uma exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="92523-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92523-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92523-124">See Also</span></span>

[<span data-ttu-id="92523-125">Elemento ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="92523-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="92523-126">Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="92523-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="92523-127">Elemento SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="92523-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="92523-128">Exibição de lista</span><span class="sxs-lookup"><span data-stu-id="92523-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="92523-129">Definir condições para quando uma entrada de exibição ou um Item é usado</span><span class="sxs-lookup"><span data-stu-id="92523-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="92523-130">Escrevendo um formatação do Windows PowerShell e tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="92523-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
