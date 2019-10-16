---
title: Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae67e47-6c60-4741-8430-78d2cb6067b1
caps.latest.revision: 10
ms.openlocfilehash: ccfc0b772ad3b2d1979c7c832a5153de870035d7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368395"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="71cce-102">Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="71cce-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="71cce-103">Especifica o conjunto de tipos .NET que disparam a condição.</span><span class="sxs-lookup"><span data-stu-id="71cce-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="71cce-104">Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando essa definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="71cce-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="71cce-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl elemento (Format) ListEntries Element (Format) o elemento ListEntry (Format) o elemento EntrySelectedBy para o elemento ListEntry (Format) SelectionCondition para EntrySelectedBy para ListEntry (Format) SelectionSetName elemento para SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="71cce-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="71cce-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="71cce-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="71cce-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="71cce-107">Attributes and Elements</span></span>

<span data-ttu-id="71cce-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="71cce-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="71cce-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="71cce-109">Attributes</span></span>

<span data-ttu-id="71cce-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="71cce-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="71cce-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="71cce-111">Child Elements</span></span>

<span data-ttu-id="71cce-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="71cce-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="71cce-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="71cce-113">Parent Elements</span></span>

|<span data-ttu-id="71cce-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="71cce-114">Element</span></span>|<span data-ttu-id="71cce-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="71cce-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="71cce-116">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="71cce-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="71cce-117">Define a condição que deve existir para usar essa definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="71cce-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="71cce-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="71cce-118">Text Value</span></span>

<span data-ttu-id="71cce-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="71cce-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="71cce-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="71cce-120">Remarks</span></span>

<span data-ttu-id="71cce-121">A condição de seleção pode especificar um conjunto de seleção ou um tipo .NET, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="71cce-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="71cce-122">Para obter mais informações sobre como usar condições de seleção, consulte [definindo condições para quando os dados são exibidos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="71cce-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="71cce-123">Os conjuntos de seleção são grupos comuns de objetos .NET que podem ser usados por qualquer exibição que o arquivo de formatação define.</span><span class="sxs-lookup"><span data-stu-id="71cce-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="71cce-124">Para obter mais informações sobre como criar e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="71cce-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="71cce-125">Para obter mais informações sobre outros componentes de um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="71cce-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="71cce-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="71cce-126">See Also</span></span>

[<span data-ttu-id="71cce-127">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="71cce-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="71cce-128">Definindo condições para quando os dados são exibidos</span><span class="sxs-lookup"><span data-stu-id="71cce-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="71cce-129">Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="71cce-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="71cce-130">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="71cce-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
