---
title: Elemento SelectionSetName para SelectionCondition para controles para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: daea8c6f-873a-4639-9eee-599642822958
caps.latest.revision: 6
ms.openlocfilehash: 697f2ea284393ebddd77a862c408f27f3d332900
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361965"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="48c91-102">Elemento SelectionSetName para SelectionCondition para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="48c91-102">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="48c91-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="48c91-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="48c91-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="48c91-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="48c91-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="48c91-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="48c91-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) controle elemento (Format) elemento Control para controles para o elemento View (Format) CustomControl para controle para controles para o elemento View (Format) CustomEntries para CustomControl para controles para o elemento View (Format) CustomEntry para CustomEntries para controles para o elemento View (Format) EntrySelectedBy para CustomEntry para controles para o elemento View (Format) SelectionCondition para EntrySelectedBy para controles para View ( Format) elemento SelectionSetName para SelectionCondition para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="48c91-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48c91-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="48c91-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="48c91-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="48c91-108">Attributes and Elements</span></span>

<span data-ttu-id="48c91-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="48c91-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="48c91-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="48c91-110">Attributes</span></span>

<span data-ttu-id="48c91-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="48c91-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48c91-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="48c91-112">Child Elements</span></span>

<span data-ttu-id="48c91-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="48c91-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="48c91-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="48c91-114">Parent Elements</span></span>

|<span data-ttu-id="48c91-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="48c91-115">Element</span></span>|<span data-ttu-id="48c91-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="48c91-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48c91-117">Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="48c91-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="48c91-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="48c91-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="48c91-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="48c91-119">Text Value</span></span>

<span data-ttu-id="48c91-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="48c91-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="48c91-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="48c91-121">Remarks</span></span>

<span data-ttu-id="48c91-122">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="48c91-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="48c91-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de seleção](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="48c91-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="48c91-124">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="48c91-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="48c91-125">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="48c91-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48c91-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48c91-126">See Also</span></span>

[<span data-ttu-id="48c91-127">Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="48c91-127">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="48c91-128">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="48c91-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="48c91-129">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="48c91-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="48c91-130">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="48c91-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
