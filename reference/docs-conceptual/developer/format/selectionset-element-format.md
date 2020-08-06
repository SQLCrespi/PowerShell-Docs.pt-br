---
title: Elemento SelectionSet (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: cf47229993458492c712d28e04913e75d1bde386
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783391"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="4e0d5-102">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="4e0d5-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="4e0d5-103">Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="4e0d5-104">Elemento de configuração (Format) elemento SelectionSets (Format) SelectionSet elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="4e0d5-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4e0d5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4e0d5-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e0d5-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4e0d5-106">Attributes and Elements</span></span>

<span data-ttu-id="4e0d5-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSet` elemento.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="4e0d5-108">Cada conjunto de seleção deve ter um nome e deve especificar os objetos .NET do conjunto.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e0d5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4e0d5-109">Attributes</span></span>

<span data-ttu-id="4e0d5-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4e0d5-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="4e0d5-111">Child Elements</span></span>

|<span data-ttu-id="4e0d5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e0d5-112">Element</span></span>|<span data-ttu-id="4e0d5-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="4e0d5-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e0d5-114">Elemento Name para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="4e0d5-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="4e0d5-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-115">Required element.</span></span><br /><br /> <span data-ttu-id="4e0d5-116">Especifica o nome usado para fazer referência ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="4e0d5-117">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="4e0d5-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="4e0d5-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-118">Required element.</span></span><br /><br /> <span data-ttu-id="4e0d5-119">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4e0d5-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="4e0d5-120">Parent Elements</span></span>

|<span data-ttu-id="4e0d5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e0d5-121">Element</span></span>|<span data-ttu-id="4e0d5-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="4e0d5-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e0d5-123">Formato do elemento SelectionSets</span><span class="sxs-lookup"><span data-stu-id="4e0d5-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="4e0d5-124">Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4e0d5-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="4e0d5-125">Remarks</span></span>

<span data-ttu-id="4e0d5-126">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="4e0d5-127">Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="4e0d5-128">Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação ou as definições das exibições.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="4e0d5-129">Nesses casos, o `SelectionSetName` elemento filho dos `ViewSelectedBy` `EntrySelectedBy` elementos e especifica o conjunto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="4e0d5-130">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="4e0d5-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="4e0d5-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4e0d5-131">Example</span></span>

<span data-ttu-id="4e0d5-132">O exemplo a seguir mostra um `SelectionSet` elemento que define quatro tipos .net.</span><span class="sxs-lookup"><span data-stu-id="4e0d5-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4e0d5-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e0d5-133">See Also</span></span>

[<span data-ttu-id="4e0d5-134">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="4e0d5-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="4e0d5-135">Elemento Name de SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="4e0d5-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="4e0d5-136">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="4e0d5-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="4e0d5-137">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="4e0d5-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="4e0d5-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e0d5-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
