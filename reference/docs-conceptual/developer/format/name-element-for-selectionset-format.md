---
title: Elemento Name para SelectionSet (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362665"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="e5bd7-102">Elemento Name para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="e5bd7-102">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="e5bd7-103">Especifica o nome usado para fazer referência ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-103">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="e5bd7-104">Elemento de configuração (Format) elemento SelectionSets (Format) SelectionSet elemento (Format) nomear elemento de SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="e5bd7-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e5bd7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e5bd7-105">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e5bd7-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e5bd7-106">Attributes and Elements</span></span>

<span data-ttu-id="e5bd7-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Name`.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-107">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e5bd7-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5bd7-108">Attributes</span></span>

<span data-ttu-id="e5bd7-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e5bd7-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="e5bd7-110">Child Elements</span></span>

<span data-ttu-id="e5bd7-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e5bd7-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="e5bd7-112">Parent Elements</span></span>

|<span data-ttu-id="e5bd7-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5bd7-113">Element</span></span>|<span data-ttu-id="e5bd7-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5bd7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e5bd7-115">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="e5bd7-115">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="e5bd7-116">Define um único conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-116">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e5bd7-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="e5bd7-117">Text Value</span></span>

<span data-ttu-id="e5bd7-118">Especifique o nome para fazer referência ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-118">Specify the name to reference the selection set.</span></span> <span data-ttu-id="e5bd7-119">Não há restrições sobre quais caracteres podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-119">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5bd7-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="e5bd7-120">Remarks</span></span>

<span data-ttu-id="e5bd7-121">O nome especificado aqui é usado no elemento `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-121">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="e5bd7-122">O conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-122">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="e5bd7-123">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e5bd7-123">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="e5bd7-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e5bd7-124">Example</span></span>

<span data-ttu-id="e5bd7-125">Este exemplo mostra um elemento `SelectionSet` que define quatro tipos .NET.</span><span class="sxs-lookup"><span data-stu-id="e5bd7-125">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="e5bd7-126">O nome do conjunto de seleção é "FileSystemTypes".</span><span class="sxs-lookup"><span data-stu-id="e5bd7-126">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e5bd7-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5bd7-127">See Also</span></span>

[<span data-ttu-id="e5bd7-128">Definindo conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="e5bd7-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e5bd7-129">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="e5bd7-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="e5bd7-130">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bd7-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
