---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)
description: Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)
ms.openlocfilehash: 78b977548243b6f3a658f15a0249d8cad12e2f1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664918"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="59ee2-103">Elemento ScriptBlock para SelectionCondition para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="59ee2-103">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="59ee2-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="59ee2-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="59ee2-105">Quando esse script é avaliado como `true` , a condição é atendida e a definição é usada.</span><span class="sxs-lookup"><span data-stu-id="59ee2-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="59ee2-106">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="59ee2-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="59ee2-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for CustomControl para o elemento View (Format) CustomItem para CustomEntry para CustomControl para o elemento View (Format) SelectionCondition para EntrySelectedBy para CustomControl para View (Format) elementar para SelectionCondition para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="59ee2-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="59ee2-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="59ee2-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="59ee2-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="59ee2-109">Attributes and Elements</span></span>

<span data-ttu-id="59ee2-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="59ee2-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="59ee2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="59ee2-111">Attributes</span></span>

<span data-ttu-id="59ee2-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="59ee2-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="59ee2-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="59ee2-113">Child Elements</span></span>

<span data-ttu-id="59ee2-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="59ee2-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="59ee2-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="59ee2-115">Parent Elements</span></span>

|<span data-ttu-id="59ee2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="59ee2-116">Element</span></span>|<span data-ttu-id="59ee2-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="59ee2-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59ee2-118">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="59ee2-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="59ee2-119">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="59ee2-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="59ee2-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="59ee2-120">Text Value</span></span>

<span data-ttu-id="59ee2-121">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="59ee2-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="59ee2-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="59ee2-122">Remarks</span></span>

<span data-ttu-id="59ee2-123">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="59ee2-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="59ee2-124">Para obter mais informações sobre como as condições de seleção podem ser usadas, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="59ee2-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="59ee2-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="59ee2-125">See Also</span></span>

[<span data-ttu-id="59ee2-126">Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="59ee2-126">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="59ee2-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="59ee2-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
