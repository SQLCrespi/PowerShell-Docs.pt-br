---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento SelectionSetName para ViewSelectedBy (formato)
description: Elemento SelectionSetName para ViewSelectedBy (formato)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654902"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="14d53-103">Elemento SelectionSetName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="14d53-103">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="14d53-104">Especifica um conjunto de objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="14d53-104">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="14d53-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento ViewSelectedBy Element (Format) SelectionSetName elemento para ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="14d53-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="14d53-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="14d53-106">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="14d53-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="14d53-107">Attributes and Elements</span></span>

<span data-ttu-id="14d53-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="14d53-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="14d53-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="14d53-109">Attributes</span></span>

<span data-ttu-id="14d53-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="14d53-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="14d53-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="14d53-111">Child Elements</span></span>

<span data-ttu-id="14d53-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="14d53-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="14d53-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="14d53-113">Parent Elements</span></span>

|<span data-ttu-id="14d53-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="14d53-114">Element</span></span>|<span data-ttu-id="14d53-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="14d53-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="14d53-116">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="14d53-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="14d53-117">Define os objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="14d53-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="14d53-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="14d53-118">Text Value</span></span>

<span data-ttu-id="14d53-119">Especifique o nome do conjunto de seleção definido pelo `Name` elemento para o conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="14d53-119">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="14d53-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="14d53-120">Remarks</span></span>

<span data-ttu-id="14d53-121">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="14d53-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="14d53-122">Para obter mais informações sobre como definir e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="14d53-122">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="14d53-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="14d53-123">Example</span></span>

<span data-ttu-id="14d53-124">O exemplo a seguir mostra como especificar um conjunto de seleção para uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="14d53-124">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="14d53-125">O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="14d53-125">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="14d53-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14d53-126">See Also</span></span>

[<span data-ttu-id="14d53-127">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="14d53-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="14d53-128">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="14d53-128">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="14d53-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="14d53-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
