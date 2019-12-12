---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: 7d526372cf80327b3fb9b79b6e83429c57780183
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362285"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="fa1ba-102">Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="fa1ba-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="fa1ba-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="fa1ba-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="fa1ba-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl elemento (Format) ListEntries Element (Format) o elemento ListEntry (Format) o elemento EntrySelectedBy para o elemento ListEntry (Format) SelectionCondition para EntrySelectedBy para ListEntry (Format) PropertyName elemento para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fa1ba-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fa1ba-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fa1ba-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fa1ba-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fa1ba-107">Attributes and Elements</span></span>

<span data-ttu-id="fa1ba-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fa1ba-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa1ba-109">Attributes</span></span>

<span data-ttu-id="fa1ba-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fa1ba-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="fa1ba-111">Child Elements</span></span>

<span data-ttu-id="fa1ba-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fa1ba-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="fa1ba-113">Parent Elements</span></span>

|<span data-ttu-id="fa1ba-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa1ba-114">Element</span></span>|<span data-ttu-id="fa1ba-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="fa1ba-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fa1ba-116">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fa1ba-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="fa1ba-117">Define a condição que deve existir para que essa entrada de lista seja usada.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fa1ba-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="fa1ba-118">Text Value</span></span>

<span data-ttu-id="fa1ba-119">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa1ba-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="fa1ba-120">Remarks</span></span>

<span data-ttu-id="fa1ba-121">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="fa1ba-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="fa1ba-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="fa1ba-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="fa1ba-123">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="fa1ba-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa1ba-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa1ba-124">See Also</span></span>

[<span data-ttu-id="fa1ba-125">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="fa1ba-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="fa1ba-126">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="fa1ba-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="fa1ba-127">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fa1ba-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="fa1ba-128">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fa1ba-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="fa1ba-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa1ba-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
