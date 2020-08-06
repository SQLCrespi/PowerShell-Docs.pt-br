---
title: Elemento SelectionSetName para SelectionCondition para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6d0263aa335287f20be5b94a8eb65696d06d82a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772613"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="d1aa4-102">Elemento SelectionSetName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d1aa4-102">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="d1aa4-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="d1aa4-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="d1aa4-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d1aa4-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento EntrySelectedBy de GroupBy (Format) para CustomEntry para GroupBy (Format) SelectionCondition para EntrySelectedBy para o elemento SelectionSetName de GroupBy (formato</span><span class="sxs-lookup"><span data-stu-id="d1aa4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d1aa4-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d1aa4-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d1aa4-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d1aa4-108">Attributes and Elements</span></span>

<span data-ttu-id="d1aa4-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d1aa4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1aa4-110">Attributes</span></span>

<span data-ttu-id="d1aa4-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d1aa4-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d1aa4-112">Child Elements</span></span>

<span data-ttu-id="d1aa4-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d1aa4-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d1aa4-114">Parent Elements</span></span>

|<span data-ttu-id="d1aa4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1aa4-115">Element</span></span>|<span data-ttu-id="d1aa4-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="d1aa4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d1aa4-117">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d1aa4-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="d1aa4-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d1aa4-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="d1aa4-119">Text Value</span></span>

<span data-ttu-id="d1aa4-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1aa4-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="d1aa4-121">Remarks</span></span>

<span data-ttu-id="d1aa4-122">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="d1aa4-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="d1aa4-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d1aa4-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="d1aa4-124">Quando esse elemento é especificado, você não pode especificar o elemento [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="d1aa4-124">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="d1aa4-125">Para obter mais informações sobre como definir condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d1aa4-125">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1aa4-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1aa4-126">See Also</span></span>

[<span data-ttu-id="d1aa4-127">Elemento TypeName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d1aa4-127">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="d1aa4-128">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="d1aa4-128">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="d1aa4-129">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="d1aa4-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d1aa4-130">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="d1aa4-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="d1aa4-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1aa4-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
