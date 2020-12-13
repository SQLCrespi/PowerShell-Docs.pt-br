---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSets (formato)
description: Elemento SelectionSets (formato)
ms.openlocfilehash: e5c928dfb82bc6963b4a87aef9ec06d34cacfdcb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654930"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="bbf15-103">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="bbf15-103">SelectionSets Element (Format)</span></span>

<span data-ttu-id="bbf15-104">Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="bbf15-104">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="bbf15-105">As exibições e os controles do arquivo de formatação podem fazer referência ao conjunto completo de objetos usando apenas o nome do conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="bbf15-105">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="bbf15-106">Formato do elemento SelectionSets do elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="bbf15-106">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="bbf15-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bbf15-107">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bbf15-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bbf15-108">Attributes and Elements</span></span>

<span data-ttu-id="bbf15-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSets` elemento.</span><span class="sxs-lookup"><span data-stu-id="bbf15-109">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="bbf15-110">Cada elemento filho define um conjunto de objetos que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="bbf15-110">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="bbf15-111">A ordem dos elementos filho não é significativa.</span><span class="sxs-lookup"><span data-stu-id="bbf15-111">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="bbf15-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="bbf15-112">Attributes</span></span>

<span data-ttu-id="bbf15-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bbf15-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bbf15-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bbf15-114">Child Elements</span></span>

|<span data-ttu-id="bbf15-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="bbf15-115">Element</span></span>|<span data-ttu-id="bbf15-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="bbf15-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbf15-117">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="bbf15-117">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="bbf15-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="bbf15-118">Required element.</span></span><br /><br /> <span data-ttu-id="bbf15-119">Define um único conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="bbf15-119">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bbf15-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bbf15-120">Parent Elements</span></span>

|<span data-ttu-id="bbf15-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="bbf15-121">Element</span></span>|<span data-ttu-id="bbf15-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="bbf15-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbf15-123">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="bbf15-123">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="bbf15-124">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="bbf15-124">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bbf15-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="bbf15-125">Remarks</span></span>

<span data-ttu-id="bbf15-126">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="bbf15-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="bbf15-127">Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.</span><span class="sxs-lookup"><span data-stu-id="bbf15-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="bbf15-128">Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação ou as definições das exibições.</span><span class="sxs-lookup"><span data-stu-id="bbf15-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="bbf15-129">Nesses casos, o `SelectionSetName` elemento filho dos `ViewSelectedBy` `EntrySelectedBy` elementos e especifica o conjunto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="bbf15-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="bbf15-130">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="bbf15-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bbf15-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bbf15-131">See Also</span></span>

[<span data-ttu-id="bbf15-132">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="bbf15-132">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="bbf15-133">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="bbf15-133">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="bbf15-134">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="bbf15-134">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="bbf15-135">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbf15-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
