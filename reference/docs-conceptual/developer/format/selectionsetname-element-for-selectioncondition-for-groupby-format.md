---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para GroupBy (formato)
description: Elemento SelectionSetName para SelectionCondition para GroupBy (formato)
ms.openlocfilehash: a4f28c1caba3790718b99f63659cb0cbed8def16
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654999"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="b68ed-103">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b68ed-103">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="b68ed-104">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="b68ed-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="b68ed-105">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="b68ed-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="b68ed-106">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="b68ed-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b68ed-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento EntrySelectedBy de GroupBy (Format) para CustomEntry para GroupBy (Format) SelectionCondition para EntrySelectedBy para o elemento SelectionSetName de GroupBy (formato</span><span class="sxs-lookup"><span data-stu-id="b68ed-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b68ed-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b68ed-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b68ed-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b68ed-109">Attributes and Elements</span></span>

<span data-ttu-id="b68ed-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="b68ed-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b68ed-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b68ed-111">Attributes</span></span>

<span data-ttu-id="b68ed-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b68ed-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b68ed-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b68ed-113">Child Elements</span></span>

<span data-ttu-id="b68ed-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b68ed-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b68ed-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b68ed-115">Parent Elements</span></span>

|<span data-ttu-id="b68ed-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b68ed-116">Element</span></span>|<span data-ttu-id="b68ed-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="b68ed-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b68ed-118">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b68ed-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="b68ed-119">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="b68ed-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b68ed-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b68ed-120">Text Value</span></span>

<span data-ttu-id="b68ed-121">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="b68ed-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b68ed-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="b68ed-122">Remarks</span></span>

<span data-ttu-id="b68ed-123">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="b68ed-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="b68ed-124">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b68ed-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="b68ed-125">Quando esse elemento é especificado, você não pode especificar o elemento [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="b68ed-125">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="b68ed-126">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b68ed-126">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b68ed-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b68ed-127">See Also</span></span>

[<span data-ttu-id="b68ed-128">Elemento TypeName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b68ed-128">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="b68ed-129">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b68ed-129">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="b68ed-130">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="b68ed-130">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b68ed-131">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="b68ed-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b68ed-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b68ed-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
