---
title: Elemento SelectionSetName para ViewSelectedBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f6410b463bcb00d2758849c2f7e13cd839277e50
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772596"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="f8765-102">Elemento SelectionSetName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f8765-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="f8765-103">Especifica um conjunto de objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="f8765-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="f8765-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento ViewSelectedBy Element (Format) SelectionSetName elemento para ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f8765-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f8765-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f8765-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8765-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f8765-106">Attributes and Elements</span></span>

<span data-ttu-id="f8765-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `SelectionSetName` elemento.</span><span class="sxs-lookup"><span data-stu-id="f8765-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8765-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f8765-108">Attributes</span></span>

<span data-ttu-id="f8765-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f8765-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8765-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f8765-110">Child Elements</span></span>

<span data-ttu-id="f8765-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f8765-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f8765-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f8765-112">Parent Elements</span></span>

|<span data-ttu-id="f8765-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8765-113">Element</span></span>|<span data-ttu-id="f8765-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="f8765-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8765-115">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f8765-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="f8765-116">Define os objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="f8765-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f8765-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f8765-117">Text Value</span></span>

<span data-ttu-id="f8765-118">Especifique o nome do conjunto de seleção definido pelo `Name` elemento para o conjunto de seleção.</span><span class="sxs-lookup"><span data-stu-id="f8765-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8765-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="f8765-119">Remarks</span></span>

<span data-ttu-id="f8765-120">Você pode usar conjuntos de seleção quando tiver um conjunto de objetos relacionados que deseja referenciar usando um único nome, como um conjunto de objetos que estão relacionados por meio de herança.</span><span class="sxs-lookup"><span data-stu-id="f8765-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="f8765-121">Para obter mais informações sobre como definir e referenciar conjuntos de seleção, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f8765-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="f8765-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f8765-122">Example</span></span>

<span data-ttu-id="f8765-123">O exemplo a seguir mostra como especificar um conjunto de seleção para uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="f8765-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="f8765-124">O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f8765-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="f8765-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f8765-125">See Also</span></span>

[<span data-ttu-id="f8765-126">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="f8765-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f8765-127">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="f8765-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="f8765-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8765-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
