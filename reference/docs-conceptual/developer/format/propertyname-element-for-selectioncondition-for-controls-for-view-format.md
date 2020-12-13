---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para Controls para View (formato)
description: Elemento PropertyName para SelectionCondition para Controls para View (formato)
ms.openlocfilehash: 7783e5a9b7f8ec3d3077d87778e9f77ffe858a7f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665865"
---
# <a name="propertyname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="7d670-103">Elemento PropertyName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7d670-103">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="7d670-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="7d670-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="7d670-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a entrada é usada.</span><span class="sxs-lookup"><span data-stu-id="7d670-105">When this property is present or when it evaluates to `true`, the condition is met, and the entry is used.</span></span> <span data-ttu-id="7d670-106">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="7d670-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="7d670-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para controles para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para o elemento View (Format) PropertyName para SelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7d670-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d670-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7d670-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d670-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7d670-109">Attributes and Elements</span></span>

<span data-ttu-id="7d670-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="7d670-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d670-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7d670-111">Attributes</span></span>

<span data-ttu-id="7d670-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7d670-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d670-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="7d670-113">Child Elements</span></span>

<span data-ttu-id="7d670-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7d670-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d670-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="7d670-115">Parent Elements</span></span>

|<span data-ttu-id="7d670-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d670-116">Element</span></span>|<span data-ttu-id="7d670-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d670-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d670-118">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7d670-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="7d670-119">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="7d670-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7d670-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="7d670-120">Text Value</span></span>

<span data-ttu-id="7d670-121">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="7d670-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d670-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="7d670-122">Remarks</span></span>

<span data-ttu-id="7d670-123">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="7d670-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="7d670-124">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7d670-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d670-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d670-125">See Also</span></span>

[<span data-ttu-id="7d670-126">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7d670-126">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="7d670-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d670-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
