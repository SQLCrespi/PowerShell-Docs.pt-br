---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)
description: Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)
ms.openlocfilehash: 4177aace5a6a9374900e7339167c69b531c1e2e7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651667"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="e09ff-103">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e09ff-103">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e09ff-104">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="e09ff-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="e09ff-105">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="e09ff-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="e09ff-106">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="e09ff-106">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e09ff-107">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para controles para o elemento de configuração (Format) SelectionSetName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e09ff-107">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e09ff-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e09ff-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e09ff-109">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e09ff-109">Attributes and Elements</span></span>

<span data-ttu-id="e09ff-110">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="e09ff-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e09ff-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e09ff-111">Attributes</span></span>

<span data-ttu-id="e09ff-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="e09ff-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e09ff-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e09ff-113">Child Elements</span></span>

<span data-ttu-id="e09ff-114">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="e09ff-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e09ff-115">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e09ff-115">Parent Elements</span></span>

|<span data-ttu-id="e09ff-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e09ff-116">Element</span></span>|<span data-ttu-id="e09ff-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="e09ff-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e09ff-118">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e09ff-118">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="e09ff-119">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="e09ff-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e09ff-120">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="e09ff-120">Text Value</span></span>

<span data-ttu-id="e09ff-121">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="e09ff-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e09ff-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="e09ff-122">Remarks</span></span>

<span data-ttu-id="e09ff-123">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="e09ff-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="e09ff-124">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e09ff-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e09ff-125">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="e09ff-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="e09ff-126">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e09ff-126">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e09ff-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e09ff-127">See Also</span></span>

[<span data-ttu-id="e09ff-128">Elemento SelectionCondition para EntrySelectedBy para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e09ff-128">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="e09ff-129">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="e09ff-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e09ff-130">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="e09ff-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e09ff-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e09ff-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
