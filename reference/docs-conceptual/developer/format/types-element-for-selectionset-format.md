---
title: Elemento types para SelectionSet (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9978daefb3e97ab131774ca4dff633dde6b4dfbf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772511"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="1cbe2-102">Elemento Types para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="1cbe2-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="1cbe2-103">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="1cbe2-104">Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) elemento Types (Format)</span><span class="sxs-lookup"><span data-stu-id="1cbe2-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1cbe2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1cbe2-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="1cbe2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1cbe2-106">Attributes and Elements</span></span>

<span data-ttu-id="1cbe2-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Types` elemento.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="1cbe2-108">Deve haver pelo menos um elemento filho, mas não há um limite máximo para o número de elementos filho que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="1cbe2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1cbe2-109">Attributes</span></span>

<span data-ttu-id="1cbe2-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1cbe2-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1cbe2-111">Child Elements</span></span>

|<span data-ttu-id="1cbe2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cbe2-112">Element</span></span>|<span data-ttu-id="1cbe2-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="1cbe2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1cbe2-114">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="1cbe2-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="1cbe2-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-115">Required element.</span></span><br /><br /> <span data-ttu-id="1cbe2-116">Especifica o objeto .NET que pertence ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1cbe2-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1cbe2-117">Parent Elements</span></span>

|<span data-ttu-id="1cbe2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cbe2-118">Element</span></span>|<span data-ttu-id="1cbe2-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="1cbe2-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1cbe2-120">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="1cbe2-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="1cbe2-121">Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1cbe2-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="1cbe2-122">Remarks</span></span>

<span data-ttu-id="1cbe2-123">Os objetos definidos por esse elemento compõem um conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="1cbe2-124">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="1cbe2-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="1cbe2-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1cbe2-125">Example</span></span>

<span data-ttu-id="1cbe2-126">Este exemplo mostra um `SelectionSet` elemento que define quatro tipos .net.</span><span class="sxs-lookup"><span data-stu-id="1cbe2-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1cbe2-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1cbe2-127">See Also</span></span>

[<span data-ttu-id="1cbe2-128">Definindo conjuntos de objetos</span><span class="sxs-lookup"><span data-stu-id="1cbe2-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="1cbe2-129">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="1cbe2-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="1cbe2-130">Elemento TypeName de tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="1cbe2-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="1cbe2-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1cbe2-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
