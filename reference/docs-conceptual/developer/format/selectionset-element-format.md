---
title: Elemento SelectionSet (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368375"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="157b7-102">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="157b7-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="157b7-103">Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="157b7-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="157b7-104">Elemento de configuração (Format) elemento SelectionSets (Format) SelectionSet elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="157b7-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="157b7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="157b7-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="157b7-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="157b7-106">Attributes and Elements</span></span>

<span data-ttu-id="157b7-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `SelectionSet`.</span><span class="sxs-lookup"><span data-stu-id="157b7-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="157b7-108">Cada conjunto de seleção deve ter um nome e deve especificar os objetos .NET do conjunto.</span><span class="sxs-lookup"><span data-stu-id="157b7-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="157b7-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="157b7-109">Attributes</span></span>

<span data-ttu-id="157b7-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="157b7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="157b7-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="157b7-111">Child Elements</span></span>

|<span data-ttu-id="157b7-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="157b7-112">Element</span></span>|<span data-ttu-id="157b7-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="157b7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="157b7-114">Elemento Name para SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="157b7-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="157b7-115">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="157b7-115">Required element.</span></span><br /><br /> <span data-ttu-id="157b7-116">Especifica o nome usado para fazer referência ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="157b7-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="157b7-117">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="157b7-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="157b7-118">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="157b7-118">Required element.</span></span><br /><br /> <span data-ttu-id="157b7-119">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="157b7-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="157b7-120">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="157b7-120">Parent Elements</span></span>

|<span data-ttu-id="157b7-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="157b7-121">Element</span></span>|<span data-ttu-id="157b7-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="157b7-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="157b7-123">Formato do elemento SelectionSets</span><span class="sxs-lookup"><span data-stu-id="157b7-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="157b7-124">Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="157b7-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="157b7-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="157b7-125">Remarks</span></span>

<span data-ttu-id="157b7-126">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="157b7-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="157b7-127">Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.</span><span class="sxs-lookup"><span data-stu-id="157b7-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="157b7-128">Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação ou as definições das exibições.</span><span class="sxs-lookup"><span data-stu-id="157b7-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="157b7-129">Nesses casos, o elemento filho `SelectionSetName` dos elementos `ViewSelectedBy` e `EntrySelectedBy` especifica o conjunto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="157b7-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="157b7-130">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="157b7-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="157b7-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="157b7-131">Example</span></span>

<span data-ttu-id="157b7-132">O exemplo a seguir mostra um elemento `SelectionSet` que define quatro tipos .NET.</span><span class="sxs-lookup"><span data-stu-id="157b7-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="157b7-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="157b7-133">See Also</span></span>

[<span data-ttu-id="157b7-134">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="157b7-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="157b7-135">Elemento Name de SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="157b7-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="157b7-136">Elemento SelectionSets (Format)</span><span class="sxs-lookup"><span data-stu-id="157b7-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="157b7-137">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="157b7-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="157b7-138">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="157b7-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
