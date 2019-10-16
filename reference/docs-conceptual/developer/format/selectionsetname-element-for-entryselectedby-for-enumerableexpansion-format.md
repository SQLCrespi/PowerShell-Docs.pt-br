---
title: Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368325"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="58b54-102">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="58b54-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="58b54-103">Especifica o conjunto de tipos .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="58b54-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="58b54-104">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="58b54-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="58b54-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="58b54-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="58b54-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="58b54-106">Attributes and Elements</span></span>

<span data-ttu-id="58b54-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="58b54-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="58b54-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="58b54-108">Attributes</span></span>

<span data-ttu-id="58b54-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="58b54-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="58b54-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="58b54-110">Child Elements</span></span>

<span data-ttu-id="58b54-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="58b54-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58b54-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="58b54-112">Parent Elements</span></span>

|<span data-ttu-id="58b54-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="58b54-113">Element</span></span>|<span data-ttu-id="58b54-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="58b54-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58b54-115">Elemento EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="58b54-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="58b54-116">Define os objetos da coleção .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="58b54-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="58b54-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="58b54-117">Text Value</span></span>

<span data-ttu-id="58b54-118">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="58b54-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="58b54-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="58b54-119">Remarks</span></span>

<span data-ttu-id="58b54-120">Cada definição deve especificar um ou mais nomes de tipo, um conjunto de seleção ou uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="58b54-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="58b54-121">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="58b54-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="58b54-122">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="58b54-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="58b54-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="58b54-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58b54-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58b54-124">See Also</span></span>

[<span data-ttu-id="58b54-125">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="58b54-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="58b54-126">Elemento EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="58b54-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="58b54-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="58b54-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
