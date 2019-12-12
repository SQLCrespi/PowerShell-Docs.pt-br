---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ae11924-0072-451e-bf70-c5ffb25dccc0
caps.latest.revision: 13
ms.openlocfilehash: 0c20512e660c8d2b61d063dbd7078b55b23efeb8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362315"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="697ef-102">Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="697ef-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="697ef-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="697ef-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="697ef-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="697ef-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="697ef-105">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy para Elemento EnumerableExpansion (Format) PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="697ef-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="697ef-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="697ef-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="697ef-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="697ef-107">Attributes and Elements</span></span>

<span data-ttu-id="697ef-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="697ef-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="697ef-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="697ef-109">Attributes</span></span>

<span data-ttu-id="697ef-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="697ef-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="697ef-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="697ef-111">Child Elements</span></span>

<span data-ttu-id="697ef-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="697ef-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="697ef-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="697ef-113">Parent Elements</span></span>

|<span data-ttu-id="697ef-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="697ef-114">Element</span></span>|<span data-ttu-id="697ef-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="697ef-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="697ef-116">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="697ef-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="697ef-117">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="697ef-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="697ef-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="697ef-118">Text Value</span></span>

<span data-ttu-id="697ef-119">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="697ef-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="697ef-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="697ef-120">Remarks</span></span>

<span data-ttu-id="697ef-121">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="697ef-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="697ef-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="697ef-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="697ef-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="697ef-123">See Also</span></span>

[<span data-ttu-id="697ef-124">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="697ef-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="697ef-125">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="697ef-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="697ef-126">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="697ef-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="697ef-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="697ef-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
