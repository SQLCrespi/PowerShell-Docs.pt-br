---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 8e28118894661b50e90a5ccc86a36fbbe77e4b03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665831"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="96aad-103">Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="96aad-103">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="96aad-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="96aad-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="96aad-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="96aad-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="96aad-106">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName elemento para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="96aad-106">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="96aad-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="96aad-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96aad-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="96aad-108">Attributes and Elements</span></span>

<span data-ttu-id="96aad-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="96aad-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="96aad-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="96aad-110">Attributes</span></span>

<span data-ttu-id="96aad-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="96aad-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="96aad-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="96aad-112">Child Elements</span></span>

<span data-ttu-id="96aad-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="96aad-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="96aad-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="96aad-114">Parent Elements</span></span>

|<span data-ttu-id="96aad-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="96aad-115">Element</span></span>|<span data-ttu-id="96aad-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="96aad-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96aad-117">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="96aad-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="96aad-118">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="96aad-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="96aad-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="96aad-119">Text Value</span></span>

<span data-ttu-id="96aad-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="96aad-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="96aad-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="96aad-121">Remarks</span></span>

<span data-ttu-id="96aad-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="96aad-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="96aad-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="96aad-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96aad-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96aad-124">See Also</span></span>

[<span data-ttu-id="96aad-125">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="96aad-125">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="96aad-126">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="96aad-126">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="96aad-127">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="96aad-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="96aad-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="96aad-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
