---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Name para SelectionSet (formato)
description: Elemento Name para SelectionSet (formato)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666444"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="2ddaf-103">Elemento Name para SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="2ddaf-103">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="2ddaf-104">Especifica o nome usado para fazer referência ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-104">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="2ddaf-105">Elemento de configuração (Format) elemento SelectionSets (Format) SelectionSet elemento (Format) nomear elemento de SelectionSet (Format)</span><span class="sxs-lookup"><span data-stu-id="2ddaf-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2ddaf-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2ddaf-106">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2ddaf-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2ddaf-107">Attributes and Elements</span></span>

<span data-ttu-id="2ddaf-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Name` elemento.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-108">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2ddaf-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="2ddaf-109">Attributes</span></span>

<span data-ttu-id="2ddaf-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2ddaf-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2ddaf-111">Child Elements</span></span>

<span data-ttu-id="2ddaf-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2ddaf-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2ddaf-113">Parent Elements</span></span>

|<span data-ttu-id="2ddaf-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ddaf-114">Element</span></span>|<span data-ttu-id="2ddaf-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ddaf-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2ddaf-116">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="2ddaf-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="2ddaf-117">Define um único conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-117">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2ddaf-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2ddaf-118">Text Value</span></span>

<span data-ttu-id="2ddaf-119">Especifique o nome para fazer referência ao conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-119">Specify the name to reference the selection set.</span></span> <span data-ttu-id="2ddaf-120">Não há restrições sobre quais caracteres podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-120">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="2ddaf-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="2ddaf-121">Remarks</span></span>

<span data-ttu-id="2ddaf-122">O nome especificado aqui é usado no `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-122">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="2ddaf-123">O conjunto de seleção que pode ser usado por uma exibição, por uma definição de uma exibição (exibições podem ter várias definições) ou ao especificar uma condição de seleção.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-123">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="2ddaf-124">Para obter mais informações sobre conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="2ddaf-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="2ddaf-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2ddaf-125">Example</span></span>

<span data-ttu-id="2ddaf-126">Este exemplo mostra um `SelectionSet` elemento que define quatro tipos .net.</span><span class="sxs-lookup"><span data-stu-id="2ddaf-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="2ddaf-127">O nome do conjunto de seleção é "FileSystemTypes".</span><span class="sxs-lookup"><span data-stu-id="2ddaf-127">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2ddaf-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2ddaf-128">See Also</span></span>

[<span data-ttu-id="2ddaf-129">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="2ddaf-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2ddaf-130">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="2ddaf-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="2ddaf-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ddaf-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
