---
title: Elemento SelectionSetName para SelectionCondition para controles de configuração (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7dcaeadb-4e79-47a0-96e2-8952af26abbe
caps.latest.revision: 7
ms.openlocfilehash: 5db35a8094ea2bb966c8d6a96802c72f64c05c17
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063985"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="0e452-102">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="0e452-102">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="0e452-103">Especifica o conjunto de tipos do .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="0e452-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="0e452-104">Quando qualquer um dos tipos neste conjunto estiver presente, a condição é atendida e o objeto é exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="0e452-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="0e452-105">Esse elemento é usado durante a definição de um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="0e452-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="0e452-106">Elemento de controles de (formato) do elemento de configuração do elemento de controle de configuração (formato) para controles para o elemento de CustomControl de configuração (formato) para o controle para o elemento de configuração (formato) de CustomEntries para CustomControl controles para Elemento de configuração (formato) de CustomEntry para CustomControl controles para o elemento de configuração (formato) de EntrySelectedBy para CustomEntry controles para o elemento de configuração (formato) de SelectionCondition para EntrySelectedBy controles para Elemento de configuração (formato) de SelectionSetName para SelectionCondition para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="0e452-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0e452-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0e452-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e452-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="0e452-108">Attributes and Elements</span></span>

<span data-ttu-id="0e452-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="0e452-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e452-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e452-110">Attributes</span></span>

<span data-ttu-id="0e452-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0e452-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0e452-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0e452-112">Child Elements</span></span>

<span data-ttu-id="0e452-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0e452-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0e452-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0e452-114">Parent Elements</span></span>

|<span data-ttu-id="0e452-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e452-115">Element</span></span>|<span data-ttu-id="0e452-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="0e452-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e452-117">Elemento SelectionCondition para EntrySelectedBy para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="0e452-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="0e452-118">Define uma condição que deve existir para a definição de controle a ser usado.</span><span class="sxs-lookup"><span data-stu-id="0e452-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0e452-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0e452-119">Text Value</span></span>

<span data-ttu-id="0e452-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="0e452-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e452-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="0e452-121">Remarks</span></span>

<span data-ttu-id="0e452-122">Conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que define o arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="0e452-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="0e452-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo define de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0e452-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="0e452-124">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="0e452-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="0e452-125">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0e452-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e452-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e452-126">See Also</span></span>

[<span data-ttu-id="0e452-127">Elemento SelectionCondition para EntrySelectedBy para controles de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="0e452-127">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="0e452-128">Definir condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="0e452-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0e452-129">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="0e452-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0e452-130">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e452-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
