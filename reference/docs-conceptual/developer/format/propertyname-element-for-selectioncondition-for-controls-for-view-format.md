---
title: Elemento PropertyName para SelectionCondition para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92c4237d-c2b2-4908-82ac-f36070f89d26
caps.latest.revision: 6
ms.openlocfilehash: 79859bed3d762948182e03babf71d4270278bae7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362355"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="92f95-102">Elemento PropertyName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="92f95-102">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="92f95-103">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="92f95-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="92f95-104">Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a entrada é usada.</span><span class="sxs-lookup"><span data-stu-id="92f95-104">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="92f95-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="92f95-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="92f95-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para View ( Format) elemento PropertyName para SelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="92f95-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92f95-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92f95-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92f95-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="92f95-108">Attributes and Elements</span></span>

<span data-ttu-id="92f95-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="92f95-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92f95-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="92f95-110">Attributes</span></span>

<span data-ttu-id="92f95-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="92f95-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92f95-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="92f95-112">Child Elements</span></span>

<span data-ttu-id="92f95-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="92f95-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92f95-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="92f95-114">Parent Elements</span></span>

|<span data-ttu-id="92f95-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="92f95-115">Element</span></span>|<span data-ttu-id="92f95-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="92f95-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92f95-117">Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="92f95-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="92f95-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="92f95-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92f95-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="92f95-119">Text Value</span></span>

<span data-ttu-id="92f95-120">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="92f95-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="92f95-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="92f95-121">Remarks</span></span>

<span data-ttu-id="92f95-122">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="92f95-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="92f95-123">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="92f95-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92f95-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92f95-124">See Also</span></span>

[<span data-ttu-id="92f95-125">Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="92f95-125">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="92f95-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="92f95-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
