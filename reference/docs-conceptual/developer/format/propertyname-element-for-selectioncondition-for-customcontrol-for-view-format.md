---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para SelectionCondition para CustomControl para View (formato)
description: Elemento PropertyName para SelectionCondition para CustomControl para View (formato)
ms.openlocfilehash: 1dd325a58b29a0f13b1341559c2a7dfe251c6b36
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665848"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="7758c-103">Elemento PropertyName para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7758c-103">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="7758c-104">Especifica a propriedade .NET que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="7758c-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="7758c-105">Quando essa propriedade está presente ou quando é avaliada como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="7758c-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="7758c-106">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="7758c-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="7758c-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl para o elemento View (Format) CustomItem para CustomEntry para CustomControl para o elemento View (Format) EntrySelectedBy para CustomEntry para CustomControl para o elemento View (Format) SelectionCondition para EntrySelectedBy para CustomControl para o elemento View (Format) PropertyName para SelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7758c-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7758c-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7758c-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7758c-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7758c-109">Attributes and Elements</span></span>

<span data-ttu-id="7758c-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="7758c-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7758c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7758c-111">Attributes</span></span>

<span data-ttu-id="7758c-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7758c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7758c-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="7758c-113">Child Elements</span></span>

<span data-ttu-id="7758c-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7758c-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7758c-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="7758c-115">Parent Elements</span></span>

|<span data-ttu-id="7758c-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7758c-116">Element</span></span>|<span data-ttu-id="7758c-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="7758c-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7758c-118">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="7758c-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="7758c-119">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="7758c-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7758c-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="7758c-120">Text Value</span></span>

<span data-ttu-id="7758c-121">Especifique o nome da propriedade .NET.</span><span class="sxs-lookup"><span data-stu-id="7758c-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="7758c-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="7758c-122">Remarks</span></span>

<span data-ttu-id="7758c-123">A condição de seleção deve especificar pelo menos um nome de propriedade ou um script, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="7758c-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="7758c-124">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7758c-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7758c-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7758c-125">See Also</span></span>

[<span data-ttu-id="7758c-126">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="7758c-126">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="7758c-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7758c-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
