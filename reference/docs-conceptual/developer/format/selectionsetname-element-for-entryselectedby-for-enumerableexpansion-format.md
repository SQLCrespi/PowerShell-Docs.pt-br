---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)
description: Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)
ms.openlocfilehash: 074f810f5a3cbad61ee8be69408967758f0591df
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651887"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="757e5-103">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="757e5-103">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="757e5-104">Especifica o conjunto de tipos .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="757e5-104">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="757e5-105">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="757e5-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="757e5-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="757e5-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="757e5-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="757e5-107">Attributes and Elements</span></span>

<span data-ttu-id="757e5-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="757e5-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="757e5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="757e5-109">Attributes</span></span>

<span data-ttu-id="757e5-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="757e5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="757e5-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="757e5-111">Child Elements</span></span>

<span data-ttu-id="757e5-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="757e5-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="757e5-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="757e5-113">Parent Elements</span></span>

|<span data-ttu-id="757e5-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="757e5-114">Element</span></span>|<span data-ttu-id="757e5-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="757e5-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="757e5-116">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="757e5-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="757e5-117">Define os objetos da coleção .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="757e5-117">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="757e5-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="757e5-118">Text Value</span></span>

<span data-ttu-id="757e5-119">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="757e5-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="757e5-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="757e5-120">Remarks</span></span>

<span data-ttu-id="757e5-121">Cada definição deve especificar um ou mais nomes de tipo, um conjunto de seleção ou uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="757e5-121">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="757e5-122">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="757e5-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="757e5-123">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="757e5-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="757e5-124">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="757e5-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="757e5-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="757e5-125">See Also</span></span>

[<span data-ttu-id="757e5-126">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="757e5-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="757e5-127">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="757e5-127">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="757e5-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="757e5-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
