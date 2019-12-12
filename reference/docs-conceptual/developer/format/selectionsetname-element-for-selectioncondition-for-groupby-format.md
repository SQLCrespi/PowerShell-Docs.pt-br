---
title: Elemento SelectionSetName para SelectionCondition para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9a4912-d755-42f3-8058-53c0797e28e4
caps.latest.revision: 6
ms.openlocfilehash: 371913eda2b09ff6788494b68738f2ad53ccb115
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361855"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="ae7ef-102">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="ae7ef-102">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="ae7ef-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="ae7ef-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="ae7ef-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ae7ef-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) EntrySelectedBy elemento para CustomEntry para GroupBy (Format) SelectionCondition elemento para EntrySelectedBy para o elemento de SelectionSetName GroupBy (Format) para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae7ef-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ae7ef-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ae7ef-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ae7ef-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ae7ef-108">Attributes and Elements</span></span>

<span data-ttu-id="ae7ef-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae7ef-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ae7ef-110">Attributes</span></span>

<span data-ttu-id="ae7ef-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ae7ef-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="ae7ef-112">Child Elements</span></span>

<span data-ttu-id="ae7ef-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ae7ef-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="ae7ef-114">Parent Elements</span></span>

|<span data-ttu-id="ae7ef-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae7ef-115">Element</span></span>|<span data-ttu-id="ae7ef-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="ae7ef-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae7ef-117">Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae7ef-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="ae7ef-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ae7ef-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="ae7ef-119">Text Value</span></span>

<span data-ttu-id="ae7ef-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae7ef-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="ae7ef-121">Remarks</span></span>

<span data-ttu-id="ae7ef-122">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="ae7ef-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="ae7ef-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ae7ef-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="ae7ef-124">Quando esse elemento é especificado, você não pode especificar o elemento [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="ae7ef-124">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="ae7ef-125">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae7ef-125">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae7ef-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae7ef-126">See Also</span></span>

[<span data-ttu-id="ae7ef-127">Elemento TypeName para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae7ef-127">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="ae7ef-128">Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae7ef-128">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="ae7ef-129">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="ae7ef-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ae7ef-130">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="ae7ef-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ae7ef-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae7ef-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
