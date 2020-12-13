---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (formato)
description: Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (formato)
ms.openlocfilehash: 53d3eba9d453dbcc96afbe8f81a16b61573f2874
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651961"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="bb745-103">Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bb745-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="bb745-104">Especifica o script que dispara a condição.</span><span class="sxs-lookup"><span data-stu-id="bb745-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="bb745-105">Quando esse script é avaliado como `true` , a condição é atendida e a definição de entrada larga é usada.</span><span class="sxs-lookup"><span data-stu-id="bb745-105">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="bb745-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) EntrySelectedBy Element para WideEntry (Format) SelectionCondition Element para EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bb745-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bb745-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bb745-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bb745-108">Attributes and Elements</span></span>

<span data-ttu-id="bb745-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="bb745-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bb745-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="bb745-110">Attributes</span></span>

<span data-ttu-id="bb745-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bb745-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bb745-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bb745-112">Child Elements</span></span>

<span data-ttu-id="bb745-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bb745-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bb745-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bb745-114">Parent Elements</span></span>

|<span data-ttu-id="bb745-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb745-115">Element</span></span>|<span data-ttu-id="bb745-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb745-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bb745-117">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="bb745-118">Define a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="bb745-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bb745-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="bb745-119">Text Value</span></span>

<span data-ttu-id="bb745-120">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="bb745-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb745-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="bb745-121">Remarks</span></span>

<span data-ttu-id="bb745-122">A condição de seleção deve especificar pelo menos um nome de script ou propriedade a ser avaliado, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="bb745-122">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="bb745-123">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bb745-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bb745-124">Para obter mais informações sobre outros componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="bb745-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bb745-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb745-125">See Also</span></span>

[<span data-ttu-id="bb745-126">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="bb745-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="bb745-127">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="bb745-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="bb745-128">Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="bb745-128">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="bb745-129">Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bb745-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="bb745-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb745-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
