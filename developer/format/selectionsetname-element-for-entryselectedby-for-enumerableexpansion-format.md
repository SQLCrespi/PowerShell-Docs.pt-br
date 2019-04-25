---
title: Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076252"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="15992-102">Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="15992-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="15992-103">Especifica o conjunto de tipos .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="15992-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="15992-104">Elemento (formato) elemento DefaultSettings (formato) elemento EnumerableExpansions (formato) elemento EnumerableExpansion (formato) EntrySelectedBy elemento de configuração para elemento de SelectionSetName EnumerableExpansion (formato) EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="15992-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15992-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="15992-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="15992-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="15992-106">Attributes and Elements</span></span>

<span data-ttu-id="15992-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="15992-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="15992-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="15992-108">Attributes</span></span>

<span data-ttu-id="15992-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="15992-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15992-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="15992-110">Child Elements</span></span>

<span data-ttu-id="15992-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="15992-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="15992-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="15992-112">Parent Elements</span></span>

|<span data-ttu-id="15992-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="15992-113">Element</span></span>|<span data-ttu-id="15992-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="15992-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15992-115">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="15992-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="15992-116">Define os objetos de coleção do .NET que são expandidos por essa definição.</span><span class="sxs-lookup"><span data-stu-id="15992-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="15992-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="15992-117">Text Value</span></span>

<span data-ttu-id="15992-118">Especifique o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="15992-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="15992-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="15992-119">Remarks</span></span>

<span data-ttu-id="15992-120">Cada definição deve especificar um ou mais nomes de tipo, um conjunto de seleção ou uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="15992-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="15992-121">Conjuntos de seleção normalmente são usados quando você deseja definir um grupo de objetos que são usados em vários modos de exibição.</span><span class="sxs-lookup"><span data-stu-id="15992-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="15992-122">Por exemplo, você talvez queira criar uma exibição de tabela e uma exibição de lista para o mesmo conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="15992-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="15992-123">Para obter mais informações sobre como definir conjuntos de seleção, consulte [definindo define de objetos para um modo de exibição](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="15992-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15992-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15992-124">See Also</span></span>

[<span data-ttu-id="15992-125">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="15992-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="15992-126">Elemento EntrySelectedBy para EnumerableExpansion (formato)</span><span class="sxs-lookup"><span data-stu-id="15992-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="15992-127">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="15992-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
