---
title: Elemento types para SelectionSet (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367955"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="f9be5-102">Elemento Types para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="f9be5-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="f9be5-103">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="f9be5-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="f9be5-104">Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) elemento Types (Format)</span><span class="sxs-lookup"><span data-stu-id="f9be5-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f9be5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f9be5-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f9be5-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f9be5-106">Attributes and Elements</span></span>

<span data-ttu-id="f9be5-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Types`.</span><span class="sxs-lookup"><span data-stu-id="f9be5-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="f9be5-108">Deve haver pelo menos um elemento filho, mas não há um limite máximo para o número de elementos filho que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="f9be5-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="f9be5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9be5-109">Attributes</span></span>

<span data-ttu-id="f9be5-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f9be5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f9be5-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="f9be5-111">Child Elements</span></span>

|<span data-ttu-id="f9be5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9be5-112">Element</span></span>|<span data-ttu-id="f9be5-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f9be5-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9be5-114">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="f9be5-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="f9be5-115">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="f9be5-115">Required element.</span></span><br /><br /> <span data-ttu-id="f9be5-116">Especifica o objeto .NET que pertence ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="f9be5-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f9be5-117">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="f9be5-117">Parent Elements</span></span>

|<span data-ttu-id="f9be5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9be5-118">Element</span></span>|<span data-ttu-id="f9be5-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="f9be5-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9be5-120">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="f9be5-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="f9be5-121">Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="f9be5-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f9be5-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="f9be5-122">Remarks</span></span>

<span data-ttu-id="f9be5-123">Os objetos definidos por esse elemento compõem um conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="f9be5-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="f9be5-124">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f9be5-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="f9be5-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f9be5-125">Example</span></span>

<span data-ttu-id="f9be5-126">Este exemplo mostra um elemento `SelectionSet` que define quatro tipos .NET.</span><span class="sxs-lookup"><span data-stu-id="f9be5-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f9be5-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f9be5-127">See Also</span></span>

[<span data-ttu-id="f9be5-128">Definindo conjuntos de objetos</span><span class="sxs-lookup"><span data-stu-id="f9be5-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f9be5-129">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="f9be5-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="f9be5-130">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="f9be5-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="f9be5-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9be5-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
