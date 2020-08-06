---
title: Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c0081cb724ccaf1c04241aafa177880d7c0e5dbe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783459"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="484a6-102">Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="484a6-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="484a6-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="484a6-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="484a6-104">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="484a6-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="484a6-105">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName elemento para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="484a6-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="484a6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="484a6-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="484a6-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="484a6-107">Attributes and Elements</span></span>

<span data-ttu-id="484a6-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="484a6-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="484a6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="484a6-109">Attributes</span></span>

<span data-ttu-id="484a6-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="484a6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="484a6-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="484a6-111">Child Elements</span></span>

<span data-ttu-id="484a6-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="484a6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="484a6-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="484a6-113">Parent Elements</span></span>

|<span data-ttu-id="484a6-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="484a6-114">Element</span></span>|<span data-ttu-id="484a6-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="484a6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="484a6-116">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="484a6-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="484a6-117">Define a condição que deve existir para expandir os objetos de coleção dessa definição.</span><span class="sxs-lookup"><span data-stu-id="484a6-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="484a6-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="484a6-118">Text Value</span></span>

<span data-ttu-id="484a6-119">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="484a6-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="484a6-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="484a6-120">Remarks</span></span>

<span data-ttu-id="484a6-121">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="484a6-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="484a6-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="484a6-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="484a6-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="484a6-123">See Also</span></span>

[<span data-ttu-id="484a6-124">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="484a6-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="484a6-125">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="484a6-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="484a6-126">Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="484a6-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="484a6-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="484a6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
