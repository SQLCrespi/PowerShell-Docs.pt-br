---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (formato)
description: Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (formato)
ms.openlocfilehash: 1e318e3a29f07b157b9ae7343ba08759db8efbb5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665814"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="0b106-103">Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="0b106-103">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="0b106-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="0b106-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="0b106-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada da lista é usada.</span><span class="sxs-lookup"><span data-stu-id="0b106-105">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="0b106-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) o elemento EntrySelectedBy para ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName elemento para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0b106-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0b106-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0b106-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b106-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0b106-108">Attributes and Elements</span></span>

<span data-ttu-id="0b106-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="0b106-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b106-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b106-110">Attributes</span></span>

<span data-ttu-id="0b106-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0b106-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0b106-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0b106-112">Child Elements</span></span>

<span data-ttu-id="0b106-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0b106-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0b106-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0b106-114">Parent Elements</span></span>

|<span data-ttu-id="0b106-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b106-115">Element</span></span>|<span data-ttu-id="0b106-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b106-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b106-117">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0b106-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="0b106-118">Define a condição que deve existir para que essa entrada de lista seja usada.</span><span class="sxs-lookup"><span data-stu-id="0b106-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0b106-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0b106-119">Text Value</span></span>

<span data-ttu-id="0b106-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="0b106-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b106-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="0b106-121">Remarks</span></span>

<span data-ttu-id="0b106-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um bloco de script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="0b106-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="0b106-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando uma entrada de exibição ou um item é usado](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0b106-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="0b106-124">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="0b106-124">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b106-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0b106-125">See Also</span></span>

[<span data-ttu-id="0b106-126">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="0b106-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="0b106-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="0b106-127">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0b106-128">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0b106-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="0b106-129">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0b106-129">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="0b106-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b106-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
