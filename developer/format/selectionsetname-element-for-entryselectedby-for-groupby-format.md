---
title: Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569c623-2277-49e3-933e-c26262b91cd5
caps.latest.revision: 6
ms.openlocfilehash: 69cd113c444b4e3c5dceabcdfddb439cd1376f6b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064060"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="1afd6-102">Elemento SelectionSetName para EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1afd6-102">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="1afd6-103">Especifica um conjunto de objetos .NET para a entrada da lista.</span><span class="sxs-lookup"><span data-stu-id="1afd6-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="1afd6-104">Não há nenhum limite para o número de conjuntos de seleção que pode ser especificado para uma entrada.</span><span class="sxs-lookup"><span data-stu-id="1afd6-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="1afd6-105">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="1afd6-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1afd6-106">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para elemento de GroupBy (formato) EntrySelectedBy CustomEntry para elemento de GroupBy (formato) SelectionSetName EntrySelectedBy para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1afd6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1afd6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1afd6-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1afd6-108">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="1afd6-108">Attributes and Elements</span></span>

<span data-ttu-id="1afd6-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="1afd6-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1afd6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1afd6-110">Attributes</span></span>

<span data-ttu-id="1afd6-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1afd6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1afd6-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1afd6-112">Child Elements</span></span>

<span data-ttu-id="1afd6-113">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1afd6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1afd6-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1afd6-114">Parent Elements</span></span>

|<span data-ttu-id="1afd6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="1afd6-115">Element</span></span>|<span data-ttu-id="1afd6-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="1afd6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1afd6-117">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1afd6-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="1afd6-118">Define os tipos de .NET que usam essa entrada personalizada ou a condição que deve existir para essa entrada a ser usado.</span><span class="sxs-lookup"><span data-stu-id="1afd6-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1afd6-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1afd6-119">Text Value</span></span>

<span data-ttu-id="1afd6-120">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="1afd6-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="1afd6-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="1afd6-121">Remarks</span></span>

<span data-ttu-id="1afd6-122">Cada definição de controle personalizado deve ter pelo menos um nome de tipo, conjunto de seleção ou condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="1afd6-122">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="1afd6-123">Conjuntos de seleção normalmente são usados quando você deseja definir um grupo de objetos que são usados em vários modos de exibição.</span><span class="sxs-lookup"><span data-stu-id="1afd6-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="1afd6-124">Por exemplo, você talvez queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="1afd6-124">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="1afd6-125">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo seleção define](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1afd6-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="1afd6-126">Para obter mais informações sobre os componentes de uma exibição de controle personalizado, consulte [criação de controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="1afd6-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1afd6-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1afd6-127">See Also</span></span>

[<span data-ttu-id="1afd6-128">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="1afd6-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="1afd6-129">Criação de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="1afd6-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="1afd6-130">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1afd6-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
