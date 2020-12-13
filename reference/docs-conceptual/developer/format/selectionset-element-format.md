---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSet (formato)
description: Elemento SelectionSet (formato)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647874"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="0410f-103">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="0410f-103">SelectionSet Element (Format)</span></span>

<span data-ttu-id="0410f-104">Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="0410f-104">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="0410f-105">Elemento de configuração (Format) elemento SelectionSets (Format) SelectionSet elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="0410f-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0410f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0410f-106">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0410f-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0410f-107">Attributes and Elements</span></span>

<span data-ttu-id="0410f-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSet` elemento.</span><span class="sxs-lookup"><span data-stu-id="0410f-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="0410f-109">Cada conjunto de seleção deve ter um nome e deve especificar os objetos .NET do conjunto.</span><span class="sxs-lookup"><span data-stu-id="0410f-109">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="0410f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0410f-110">Attributes</span></span>

<span data-ttu-id="0410f-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0410f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0410f-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0410f-112">Child Elements</span></span>

|<span data-ttu-id="0410f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0410f-113">Element</span></span>|<span data-ttu-id="0410f-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="0410f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0410f-115">Elemento Name para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="0410f-115">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="0410f-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="0410f-116">Required element.</span></span><br /><br /> <span data-ttu-id="0410f-117">Especifica o nome usado para fazer referência ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="0410f-117">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="0410f-118">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="0410f-118">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="0410f-119">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="0410f-119">Required element.</span></span><br /><br /> <span data-ttu-id="0410f-120">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="0410f-120">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0410f-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0410f-121">Parent Elements</span></span>

|<span data-ttu-id="0410f-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="0410f-122">Element</span></span>|<span data-ttu-id="0410f-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="0410f-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0410f-124">Formato do elemento SelectionSets</span><span class="sxs-lookup"><span data-stu-id="0410f-124">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="0410f-125">Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="0410f-125">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0410f-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="0410f-126">Remarks</span></span>

<span data-ttu-id="0410f-127">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="0410f-127">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="0410f-128">Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.</span><span class="sxs-lookup"><span data-stu-id="0410f-128">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="0410f-129">Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação ou as definições das exibições.</span><span class="sxs-lookup"><span data-stu-id="0410f-129">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="0410f-130">Nesses casos, o `SelectionSetName` elemento filho dos `ViewSelectedBy` `EntrySelectedBy` elementos e especifica o conjunto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="0410f-130">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="0410f-131">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0410f-131">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="0410f-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0410f-132">Example</span></span>

<span data-ttu-id="0410f-133">O exemplo a seguir mostra um `SelectionSet` elemento que define quatro tipos .net.</span><span class="sxs-lookup"><span data-stu-id="0410f-133">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0410f-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0410f-134">See Also</span></span>

[<span data-ttu-id="0410f-135">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="0410f-135">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0410f-136">Elemento Name de SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="0410f-136">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="0410f-137">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="0410f-137">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="0410f-138">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="0410f-138">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="0410f-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0410f-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
