---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ViewSelectedBy (formato)
description: Elemento ViewSelectedBy (formato)
ms.openlocfilehash: ac3c7de299b3009a067a476a024c6a6fcb5dce02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667701"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="9b159-103">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9b159-103">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="9b159-104">Define os objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="9b159-104">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="9b159-105">Cada exibição deve especificar pelo menos um objeto .NET.</span><span class="sxs-lookup"><span data-stu-id="9b159-105">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="9b159-106">Elemento ViewDefinitions (Format) View element (Format) ViewSelectedBy elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="9b159-106">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b159-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b159-107">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b159-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9b159-108">Attributes and Elements</span></span>

<span data-ttu-id="9b159-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ViewSelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="9b159-109">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="9b159-110">Esse elemento deve conter pelo menos um `TypeName` `SelectionSetName` elemento filho.</span><span class="sxs-lookup"><span data-stu-id="9b159-110">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="9b159-111">Não há nenhum limite para o número de elementos filho que podem ser especificados, nem sua ordem significativa.</span><span class="sxs-lookup"><span data-stu-id="9b159-111">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b159-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b159-112">Attributes</span></span>

<span data-ttu-id="9b159-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="9b159-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b159-114">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9b159-114">Child Elements</span></span>

|<span data-ttu-id="9b159-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b159-115">Element</span></span>|<span data-ttu-id="9b159-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b159-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b159-117">Elemento TypeName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9b159-117">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="9b159-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9b159-118">Optional element.</span></span><br /><br /> <span data-ttu-id="9b159-119">Especifica um objeto .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="9b159-119">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="9b159-120">Elemento SelectionSetName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9b159-120">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="9b159-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9b159-121">Optional element.</span></span><br /><br /> <span data-ttu-id="9b159-122">Especifica um conjunto de objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="9b159-122">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9b159-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9b159-123">Parent Elements</span></span>

|<span data-ttu-id="9b159-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b159-124">Element</span></span>|<span data-ttu-id="9b159-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b159-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b159-126">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="9b159-126">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="9b159-127">Define uma exibição que exibe um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="9b159-127">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b159-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="9b159-128">Remarks</span></span>

<span data-ttu-id="9b159-129">Para obter mais informações sobre como esse elemento é usado em diferentes exibições, consulte [componentes de exibição de tabela](./creating-a-table-view.md), componentes de exibição de [lista](./creating-a-list-view.md), [componentes de exibição ampla](./creating-a-wide-view.md)e [componentes de controle personalizado](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="9b159-129">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="9b159-130">O `SelectionSetName` elemento é usado quando o arquivo de formatação define um conjunto de objetos que são exibidos por vários modos de exibição.</span><span class="sxs-lookup"><span data-stu-id="9b159-130">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="9b159-131">Para obter mais informações sobre como os conjuntos de seleção são definidos e referenciados, consulte [definindo conjuntos de objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9b159-131">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="9b159-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9b159-132">Example</span></span>

<span data-ttu-id="9b159-133">O exemplo a seguir mostra como especificar o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) para uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="9b159-133">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="9b159-134">O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9b159-134">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="9b159-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b159-135">See Also</span></span>

[<span data-ttu-id="9b159-136">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="9b159-136">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9b159-137">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="9b159-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9b159-138">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="9b159-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9b159-139">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="9b159-139">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="9b159-140">Definir conjuntos de seleção</span><span class="sxs-lookup"><span data-stu-id="9b159-140">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="9b159-141">Elemento SelectionSetName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9b159-141">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="9b159-142">Elemento TypeName (formato)</span><span class="sxs-lookup"><span data-stu-id="9b159-142">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="9b159-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b159-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
