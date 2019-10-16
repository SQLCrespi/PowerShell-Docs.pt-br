---
title: Elemento PropertyName para SelectionCondition para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1707317-6c26-4866-bcc1-8924103c9014
caps.latest.revision: 6
ms.openlocfilehash: 7241ea0ea364befa7ad4ab0af4c4209be72214a7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364945"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="f55c6-102">Elemento PropertyName para SelectionCondition para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f55c6-102">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="f55c6-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="f55c6-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f55c6-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="f55c6-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="f55c6-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="f55c6-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f55c6-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para GroupBy (Format) EntrySelectedBy Element para CustomEntry para GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName elemento para SelectionCondition para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f55c6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f55c6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f55c6-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f55c6-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f55c6-108">Attributes and Elements</span></span>

<span data-ttu-id="f55c6-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="f55c6-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f55c6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f55c6-110">Attributes</span></span>

<span data-ttu-id="f55c6-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f55c6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f55c6-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="f55c6-112">Child Elements</span></span>

<span data-ttu-id="f55c6-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f55c6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f55c6-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="f55c6-114">Parent Elements</span></span>

|<span data-ttu-id="f55c6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f55c6-115">Element</span></span>|<span data-ttu-id="f55c6-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f55c6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f55c6-117">Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f55c6-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="f55c6-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="f55c6-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f55c6-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f55c6-119">Text Value</span></span>

<span data-ttu-id="f55c6-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="f55c6-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="f55c6-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="f55c6-121">Remarks</span></span>

<span data-ttu-id="f55c6-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="f55c6-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="f55c6-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f55c6-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f55c6-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f55c6-124">See Also</span></span>

[<span data-ttu-id="f55c6-125">Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f55c6-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="f55c6-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f55c6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
