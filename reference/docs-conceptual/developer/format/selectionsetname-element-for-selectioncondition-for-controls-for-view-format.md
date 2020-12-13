---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para Controls para View (formato)
description: Elemento SelectionSetName para SelectionCondition para Controls para View (formato)
ms.openlocfilehash: b23ee5310d415cf287bf99c73b1173f70ae15f4c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651644"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="7fbce-103">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7fbce-103">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="7fbce-104">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="7fbce-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="7fbce-105">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="7fbce-105">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="7fbce-106">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="7fbce-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="7fbce-107">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para View (Format) CustomEntries Element for CustomControl para controles para View (Format) elemento CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para o elemento View (Format) SelectionSetName para SelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="7fbce-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7fbce-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7fbce-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7fbce-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7fbce-109">Attributes and Elements</span></span>

<span data-ttu-id="7fbce-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="7fbce-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7fbce-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7fbce-111">Attributes</span></span>

<span data-ttu-id="7fbce-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7fbce-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7fbce-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="7fbce-113">Child Elements</span></span>

<span data-ttu-id="7fbce-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7fbce-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7fbce-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="7fbce-115">Parent Elements</span></span>

|<span data-ttu-id="7fbce-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7fbce-116">Element</span></span>|<span data-ttu-id="7fbce-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="7fbce-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7fbce-118">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7fbce-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="7fbce-119">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="7fbce-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7fbce-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="7fbce-120">Text Value</span></span>

<span data-ttu-id="7fbce-121">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="7fbce-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="7fbce-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="7fbce-122">Remarks</span></span>

<span data-ttu-id="7fbce-123">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="7fbce-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="7fbce-124">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7fbce-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="7fbce-125">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="7fbce-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="7fbce-126">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7fbce-126">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7fbce-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7fbce-127">See Also</span></span>

[<span data-ttu-id="7fbce-128">Elemento SelectionCondition para EntrySelectedBy para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="7fbce-128">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="7fbce-129">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="7fbce-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7fbce-130">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="7fbce-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="7fbce-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fbce-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
