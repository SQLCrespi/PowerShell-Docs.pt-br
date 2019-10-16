---
title: Elemento SelectionSetName para SelectionCondition para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7dcaeadb-4e79-47a0-96e2-8952af26abbe
caps.latest.revision: 7
ms.openlocfilehash: 5db35a8094ea2bb966c8d6a96802c72f64c05c17
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368275"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="c7cd3-102">Elemento SelectionSetName para SelectionCondition para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="c7cd3-102">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c7cd3-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="c7cd3-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="c7cd3-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c7cd3-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para controles para Configuração (Format) elemento CustomEntry para CustomControl para controles para o elemento de configuração (Format) EntrySelectedBy para CustomEntry para controles para o elemento de configuração (Format) SelectionCondition para EntrySelectedBy para controles para Configuração (Format) elemento SelectionSetName para SelectionCondition para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="c7cd3-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format) SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c7cd3-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c7cd3-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c7cd3-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="c7cd3-108">Attributes and Elements</span></span>

<span data-ttu-id="c7cd3-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c7cd3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c7cd3-110">Attributes</span></span>

<span data-ttu-id="c7cd3-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c7cd3-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="c7cd3-112">Child Elements</span></span>

<span data-ttu-id="c7cd3-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c7cd3-114">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="c7cd3-114">Parent Elements</span></span>

|<span data-ttu-id="c7cd3-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7cd3-115">Element</span></span>|<span data-ttu-id="c7cd3-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7cd3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c7cd3-117">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="c7cd3-117">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="c7cd3-118">Define uma condição que deve existir para que a definição de controle seja usada.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c7cd3-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="c7cd3-119">Text Value</span></span>

<span data-ttu-id="c7cd3-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7cd3-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="c7cd3-121">Remarks</span></span>

<span data-ttu-id="c7cd3-122">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="c7cd3-123">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="c7cd3-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="c7cd3-124">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="c7cd3-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="c7cd3-125">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para exibir dados](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c7cd3-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7cd3-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7cd3-126">See Also</span></span>

[<span data-ttu-id="c7cd3-127">Elemento SelectionCondition para EntrySelectedBy para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="c7cd3-127">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="c7cd3-128">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="c7cd3-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c7cd3-129">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="c7cd3-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c7cd3-130">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7cd3-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
