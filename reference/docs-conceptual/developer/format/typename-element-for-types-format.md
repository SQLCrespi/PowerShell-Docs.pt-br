---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para Types (formato)
description: Elemento TypeName para Types (formato)
ms.openlocfilehash: c656b8e7e5877b72ff2164e5b417857273cada61
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664611"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="0e943-103">Elemento TypeName para Types (formato)</span><span class="sxs-lookup"><span data-stu-id="0e943-103">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="0e943-104">Especifica o tipo .NET de um objeto que pertence ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="0e943-104">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="0e943-105">Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) tipos de elemento de tipo (Format) elemento TypeName dos tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="0e943-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0e943-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0e943-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e943-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0e943-107">Attributes and Elements</span></span>

<span data-ttu-id="0e943-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="0e943-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="0e943-109">Pelo menos um `TypeName` elemento deve ser incluído no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="0e943-109">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e943-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e943-110">Attributes</span></span>

<span data-ttu-id="0e943-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0e943-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0e943-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0e943-112">Child Elements</span></span>

<span data-ttu-id="0e943-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="0e943-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0e943-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0e943-114">Parent Elements</span></span>

|<span data-ttu-id="0e943-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e943-115">Element</span></span>|<span data-ttu-id="0e943-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="0e943-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e943-117">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="0e943-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="0e943-118">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="0e943-118">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0e943-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="0e943-119">Text Value</span></span>

<span data-ttu-id="0e943-120">Especifique o nome totalmente qualificado para o tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="0e943-120">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e943-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="0e943-121">Remarks</span></span>

<span data-ttu-id="0e943-122">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="0e943-122">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="0e943-123">Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.</span><span class="sxs-lookup"><span data-stu-id="0e943-123">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="0e943-124">Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="0e943-124">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="0e943-125">Nesses casos, o `SelectionSetName` elemento filho do elemento da `ViewSelectedBy` exibição especifica o conjunto.</span><span class="sxs-lookup"><span data-stu-id="0e943-125">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="0e943-126">No entanto, entradas diferentes de uma exibição também podem especificar um conjunto de seleção que se aplica somente a essa entrada da exibição.</span><span class="sxs-lookup"><span data-stu-id="0e943-126">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="0e943-127">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0e943-127">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="0e943-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0e943-128">Example</span></span>

<span data-ttu-id="0e943-129">O exemplo a seguir mostra um `SelectionSet` elemento que define quatro tipos .net.</span><span class="sxs-lookup"><span data-stu-id="0e943-129">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="0e943-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e943-130">See Also</span></span>

[<span data-ttu-id="0e943-131">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="0e943-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0e943-132">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="0e943-132">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="0e943-133">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="0e943-133">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="0e943-134">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="0e943-134">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="0e943-135">Escrever um arquivo de formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e943-135">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
