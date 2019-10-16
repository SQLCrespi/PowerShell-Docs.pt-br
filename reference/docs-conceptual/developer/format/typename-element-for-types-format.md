---
title: Elemento TypeName para tipos (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368025"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="f36c3-102">Elemento TypeName para Types (formato)</span><span class="sxs-lookup"><span data-stu-id="f36c3-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="f36c3-103">Especifica o tipo .NET de um objeto que pertence ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="f36c3-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="f36c3-104">Elemento de configuração (Format) elemento SelectionSets (formato) elemento SelectionSet (Format) tipos de elemento de tipo (Format) elemento TypeName dos tipos (Format)</span><span class="sxs-lookup"><span data-stu-id="f36c3-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f36c3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f36c3-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f36c3-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f36c3-106">Attributes and Elements</span></span>

<span data-ttu-id="f36c3-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="f36c3-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="f36c3-108">Pelo menos um elemento `TypeName` deve ser incluído no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="f36c3-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="f36c3-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f36c3-109">Attributes</span></span>

<span data-ttu-id="f36c3-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f36c3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f36c3-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="f36c3-111">Child Elements</span></span>

<span data-ttu-id="f36c3-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f36c3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f36c3-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="f36c3-113">Parent Elements</span></span>

|<span data-ttu-id="f36c3-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f36c3-114">Element</span></span>|<span data-ttu-id="f36c3-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="f36c3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f36c3-116">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="f36c3-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="f36c3-117">Define os objetos .NET que estão no conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="f36c3-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f36c3-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f36c3-118">Text Value</span></span>

<span data-ttu-id="f36c3-119">Especifique o nome totalmente qualificado para o tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="f36c3-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="f36c3-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="f36c3-120">Remarks</span></span>

<span data-ttu-id="f36c3-121">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="f36c3-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="f36c3-122">Ao definir suas exibições, você pode especificar o conjunto de objetos usando o nome do conjunto de seleção em vez de listar todos os objetos dentro de cada exibição.</span><span class="sxs-lookup"><span data-stu-id="f36c3-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="f36c3-123">Conjuntos de seleção comuns são especificados por seu nome ao definir as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="f36c3-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="f36c3-124">Nesses casos, o elemento filho `SelectionSetName` do elemento `ViewSelectedBy` para a exibição especifica o conjunto.</span><span class="sxs-lookup"><span data-stu-id="f36c3-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="f36c3-125">No entanto, entradas diferentes de uma exibição também podem especificar um conjunto de seleção que se aplica somente a essa entrada da exibição.</span><span class="sxs-lookup"><span data-stu-id="f36c3-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="f36c3-126">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f36c3-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="f36c3-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f36c3-127">Example</span></span>

<span data-ttu-id="f36c3-128">O exemplo a seguir mostra um elemento `SelectionSet` que define quatro tipos .NET.</span><span class="sxs-lookup"><span data-stu-id="f36c3-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f36c3-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f36c3-129">See Also</span></span>

[<span data-ttu-id="f36c3-130">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="f36c3-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f36c3-131">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="f36c3-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="f36c3-132">Elemento SelectionSets (Format)</span><span class="sxs-lookup"><span data-stu-id="f36c3-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="f36c3-133">Elemento Types (formato)</span><span class="sxs-lookup"><span data-stu-id="f36c3-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="f36c3-134">Escrevendo um arquivo de formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36c3-134">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
