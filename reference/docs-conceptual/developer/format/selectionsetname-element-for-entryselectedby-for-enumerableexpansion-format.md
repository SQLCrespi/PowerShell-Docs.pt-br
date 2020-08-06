---
title: Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8745ef9e6f326c3e8a5dbf185a595bbe93e92414
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785312"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="1e4e8-102">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="1e4e8-103">Especifica o conjunto de tipos .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="1e4e8-104">Elemento de configuração (Format) DefaultSettings Element (Format) EnumerableExpansions elemento (Format) EnumerableExpansion Element (Format) o elemento EntrySelectedBy para EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1e4e8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1e4e8-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e4e8-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1e4e8-106">Attributes and Elements</span></span>

<span data-ttu-id="1e4e8-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e4e8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e4e8-108">Attributes</span></span>

<span data-ttu-id="1e4e8-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e4e8-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1e4e8-110">Child Elements</span></span>

<span data-ttu-id="1e4e8-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1e4e8-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1e4e8-112">Parent Elements</span></span>

|<span data-ttu-id="1e4e8-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e4e8-113">Element</span></span>|<span data-ttu-id="1e4e8-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e4e8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e4e8-115">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="1e4e8-116">Define os objetos da coleção .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1e4e8-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1e4e8-117">Text Value</span></span>

<span data-ttu-id="1e4e8-118">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e4e8-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="1e4e8-119">Remarks</span></span>

<span data-ttu-id="1e4e8-120">Cada definição deve especificar um ou mais nomes de tipo, um conjunto de seleção ou uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="1e4e8-121">Os conjuntos de seleção são normalmente usados quando você deseja definir um grupo de objetos que são usados em várias exibições.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="1e4e8-122">Por exemplo, talvez você queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="1e4e8-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo conjuntos de objetos para uma exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1e4e8-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e4e8-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e4e8-124">See Also</span></span>

[<span data-ttu-id="1e4e8-125">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="1e4e8-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="1e4e8-126">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="1e4e8-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e4e8-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
