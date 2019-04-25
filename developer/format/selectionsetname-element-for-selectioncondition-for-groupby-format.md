---
title: Elemento SelectionSetName para SelectionCondition para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9a4912-d755-42f3-8058-53c0797e28e4
caps.latest.revision: 6
ms.openlocfilehash: 371913eda2b09ff6788494b68738f2ad53ccb115
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063751"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="f4a99-102">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4a99-102">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="f4a99-103">Especifica o conjunto de tipos do .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="f4a99-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="f4a99-104">Quando qualquer um dos tipos neste conjunto estiver presente, a condição é atendida e o objeto é exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="f4a99-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="f4a99-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="f4a99-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f4a99-106">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) EntrySelectedBy CustomEntry para elemento de GroupBy (formato) SelectionCondition EntrySelectedBy para elemento de GroupBy (formato) SelectionSetName SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4a99-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4a99-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f4a99-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4a99-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="f4a99-108">Attributes and Elements</span></span>

<span data-ttu-id="f4a99-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="f4a99-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4a99-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f4a99-110">Attributes</span></span>

<span data-ttu-id="f4a99-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f4a99-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4a99-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f4a99-112">Child Elements</span></span>

<span data-ttu-id="f4a99-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f4a99-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4a99-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f4a99-114">Parent Elements</span></span>

|<span data-ttu-id="f4a99-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f4a99-115">Element</span></span>|<span data-ttu-id="f4a99-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4a99-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4a99-117">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4a99-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="f4a99-118">Define uma condição que deve existir para a definição de controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="f4a99-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f4a99-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f4a99-119">Text Value</span></span>

<span data-ttu-id="f4a99-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="f4a99-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4a99-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="f4a99-121">Remarks</span></span>

<span data-ttu-id="f4a99-122">Conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que define o arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="f4a99-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="f4a99-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo seleção define](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f4a99-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f4a99-124">Quando esse elemento for especificado, é possível especificar o [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f4a99-124">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="f4a99-125">Para obter mais informações sobre como definir as condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f4a99-125">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4a99-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f4a99-126">See Also</span></span>

[<span data-ttu-id="f4a99-127">Elemento TypeName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4a99-127">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="f4a99-128">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f4a99-128">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="f4a99-129">Definir condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="f4a99-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f4a99-130">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="f4a99-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f4a99-131">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4a99-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
