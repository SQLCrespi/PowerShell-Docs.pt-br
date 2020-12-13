---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Types para SelectionSet (formato)
description: Elemento Types para SelectionSet (formato)
ms.openlocfilehash: ff3c24e7f52f862dc416b88d50983196ce907012
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645459"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="75bde-103">Elemento Types para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="75bde-103">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="75bde-104">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="75bde-104">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="75bde-105">Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) elemento Types (Format)</span><span class="sxs-lookup"><span data-stu-id="75bde-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="75bde-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="75bde-106">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="75bde-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="75bde-107">Attributes and Elements</span></span>

<span data-ttu-id="75bde-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Types` elemento.</span><span class="sxs-lookup"><span data-stu-id="75bde-108">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="75bde-109">Deve haver pelo menos um elemento filho, mas não há um limite máximo para o número de elementos filho que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="75bde-109">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="75bde-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="75bde-110">Attributes</span></span>

<span data-ttu-id="75bde-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="75bde-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="75bde-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="75bde-112">Child Elements</span></span>

|<span data-ttu-id="75bde-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="75bde-113">Element</span></span>|<span data-ttu-id="75bde-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="75bde-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="75bde-115">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="75bde-115">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="75bde-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="75bde-116">Required element.</span></span><br /><br /> <span data-ttu-id="75bde-117">Especifica o objeto .NET que pertence ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="75bde-117">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="75bde-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="75bde-118">Parent Elements</span></span>

|<span data-ttu-id="75bde-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="75bde-119">Element</span></span>|<span data-ttu-id="75bde-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="75bde-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="75bde-121">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="75bde-121">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="75bde-122">Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="75bde-122">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="75bde-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="75bde-123">Remarks</span></span>

<span data-ttu-id="75bde-124">Os objetos definidos por esse elemento compõem um conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="75bde-124">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="75bde-125">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="75bde-125">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="75bde-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="75bde-126">Example</span></span>

<span data-ttu-id="75bde-127">Este exemplo mostra um `SelectionSet` elemento que define quatro tipos .net.</span><span class="sxs-lookup"><span data-stu-id="75bde-127">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="75bde-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="75bde-128">See Also</span></span>

[<span data-ttu-id="75bde-129">Definindo conjuntos de objetos</span><span class="sxs-lookup"><span data-stu-id="75bde-129">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="75bde-130">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="75bde-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="75bde-131">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="75bde-131">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="75bde-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="75bde-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
