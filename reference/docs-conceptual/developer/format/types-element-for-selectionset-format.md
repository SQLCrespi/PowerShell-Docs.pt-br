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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367955"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="5e514-102">Elemento Types para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="5e514-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="5e514-103">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="5e514-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="5e514-104">Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) elemento Types (Format)</span><span class="sxs-lookup"><span data-stu-id="5e514-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5e514-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5e514-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="5e514-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5e514-106">Attributes and Elements</span></span>

<span data-ttu-id="5e514-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Types`.</span><span class="sxs-lookup"><span data-stu-id="5e514-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="5e514-108">Deve haver pelo menos um elemento filho, mas não há um limite máximo para o número de elementos filho que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="5e514-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="5e514-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5e514-109">Attributes</span></span>

<span data-ttu-id="5e514-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5e514-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5e514-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="5e514-111">Child Elements</span></span>

|<span data-ttu-id="5e514-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e514-112">Element</span></span>|<span data-ttu-id="5e514-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e514-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5e514-114">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="5e514-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="5e514-115">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5e514-115">Required element.</span></span><br /><br /> <span data-ttu-id="5e514-116">Especifica o objeto .NET que pertence ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="5e514-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5e514-117">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="5e514-117">Parent Elements</span></span>

|<span data-ttu-id="5e514-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e514-118">Element</span></span>|<span data-ttu-id="5e514-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e514-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5e514-120">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="5e514-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="5e514-121">Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="5e514-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5e514-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="5e514-122">Remarks</span></span>

<span data-ttu-id="5e514-123">Os objetos definidos por esse elemento compõem um conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="5e514-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="5e514-124">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="5e514-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="5e514-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5e514-125">Example</span></span>

<span data-ttu-id="5e514-126">Este exemplo mostra um elemento `SelectionSet` que define quatro tipos .NET.</span><span class="sxs-lookup"><span data-stu-id="5e514-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5e514-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5e514-127">See Also</span></span>

[<span data-ttu-id="5e514-128">Definindo conjuntos de objetos</span><span class="sxs-lookup"><span data-stu-id="5e514-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="5e514-129">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="5e514-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="5e514-130">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="5e514-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="5e514-131">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e514-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
