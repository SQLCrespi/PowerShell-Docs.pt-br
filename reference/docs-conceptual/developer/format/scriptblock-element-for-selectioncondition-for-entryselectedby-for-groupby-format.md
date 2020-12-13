---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para GroupBy (formato)
description: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para GroupBy (formato)
ms.openlocfilehash: cc92aa642b42fa3e4c4f974e954d5eac73179de3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664893"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="e8e52-103">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="e8e52-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="e8e52-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="e8e52-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="e8e52-105">Quando esse script é avaliado como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="e8e52-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="e8e52-106">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="e8e52-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e8e52-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomEntry para CustomControl para o elemento de ScriptBlock (Format) EntrySelectedBy para CustomEntry para o elemento GroupBy (Format) SelectionCondition para EntrySelectedBy para o elemento GroupBy (Format) para SelectionCondition para GroupBy</span><span class="sxs-lookup"><span data-stu-id="e8e52-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8e52-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8e52-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8e52-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e8e52-109">Attributes and Elements</span></span>

<span data-ttu-id="e8e52-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="e8e52-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8e52-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8e52-111">Attributes</span></span>

<span data-ttu-id="e8e52-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="e8e52-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8e52-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e8e52-113">Child Elements</span></span>

<span data-ttu-id="e8e52-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="e8e52-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8e52-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e8e52-115">Parent Elements</span></span>

|<span data-ttu-id="e8e52-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8e52-116">Element</span></span>|<span data-ttu-id="e8e52-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8e52-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8e52-118">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="e8e52-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="e8e52-119">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="e8e52-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8e52-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="e8e52-120">Text Value</span></span>

<span data-ttu-id="e8e52-121">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="e8e52-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8e52-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="e8e52-122">Remarks</span></span>

<span data-ttu-id="e8e52-123">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="e8e52-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="e8e52-124">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e8e52-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8e52-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8e52-125">See Also</span></span>

[<span data-ttu-id="e8e52-126">Elemento SelectionCondition para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="e8e52-126">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="e8e52-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8e52-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
