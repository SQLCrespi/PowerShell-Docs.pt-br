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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368325"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="fe8d0-102">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="fe8d0-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="fe8d0-103">Especifica o conjunto de tipos .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="fe8d0-104">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) EntrySelectedBy elemento para EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="fe8d0-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fe8d0-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fe8d0-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe8d0-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fe8d0-106">Attributes and Elements</span></span>

<span data-ttu-id="fe8d0-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe8d0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="fe8d0-108">Attributes</span></span>

<span data-ttu-id="fe8d0-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fe8d0-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="fe8d0-110">Child Elements</span></span>

<span data-ttu-id="fe8d0-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fe8d0-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="fe8d0-112">Parent Elements</span></span>

|<span data-ttu-id="fe8d0-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe8d0-113">Element</span></span>|<span data-ttu-id="fe8d0-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe8d0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe8d0-115">Elemento EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="fe8d0-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="fe8d0-116">Define os objetos da coleção .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fe8d0-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="fe8d0-117">Text Value</span></span>

<span data-ttu-id="fe8d0-118">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe8d0-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="fe8d0-119">Remarks</span></span>

<span data-ttu-id="fe8d0-120">Cada definição deve especificar um ou mais nomes de tipo, um conjunto de seleção ou uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="fe8d0-121">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="fe8d0-122">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="fe8d0-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="fe8d0-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="fe8d0-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe8d0-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fe8d0-124">See Also</span></span>

[<span data-ttu-id="fe8d0-125">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="fe8d0-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="fe8d0-126">Elemento EntrySelectedBy para EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="fe8d0-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="fe8d0-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe8d0-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
