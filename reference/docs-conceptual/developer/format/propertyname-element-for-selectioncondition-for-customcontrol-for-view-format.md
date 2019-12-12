---
title: Elemento PropertyName para SelectionCondition para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48a417-2083-46d4-ac38-16c12e65b6b9
caps.latest.revision: 7
ms.openlocfilehash: e08037d5d051d3be51e90193c7e87cc2e738f78a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362345"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="d7bb6-102">Elemento PropertyName para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="d7bb6-102">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="d7bb6-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="d7bb6-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="d7bb6-105">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="d7bb6-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl for View ( Format) elemento CustomItem para CustomEntry para CustomControl para o elemento View (Format) EntrySelectedBy para CustomEntry para CustomControl para o elemento View (Format) SelectionCondition para EntrySelectedBy para CustomControl para View (Format) PropertyName Elemento para SelectionCondition para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="d7bb6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d7bb6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d7bb6-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d7bb6-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d7bb6-108">Attributes and Elements</span></span>

<span data-ttu-id="d7bb6-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d7bb6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d7bb6-110">Attributes</span></span>

<span data-ttu-id="d7bb6-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d7bb6-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="d7bb6-112">Child Elements</span></span>

<span data-ttu-id="d7bb6-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d7bb6-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="d7bb6-114">Parent Elements</span></span>

|<span data-ttu-id="d7bb6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7bb6-115">Element</span></span>|<span data-ttu-id="d7bb6-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7bb6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d7bb6-117">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="d7bb6-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="d7bb6-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d7bb6-119">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="d7bb6-119">Text Value</span></span>

<span data-ttu-id="d7bb6-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7bb6-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="d7bb6-121">Remarks</span></span>

<span data-ttu-id="d7bb6-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="d7bb6-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="d7bb6-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d7bb6-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7bb6-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7bb6-124">See Also</span></span>

[<span data-ttu-id="d7bb6-125">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="d7bb6-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="d7bb6-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7bb6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
