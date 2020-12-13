---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ViewDefinitions (formato)
description: Elemento ViewDefinitions (formato)
ms.openlocfilehash: fceef0e5ec91e8c59a7b2b90fd31ca422ff0c94d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664579"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="ce7cd-103">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="ce7cd-103">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="ce7cd-104">Define as exibições usadas para exibir objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-104">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="ce7cd-105">Essas exibições podem exibir as propriedades e os valores de script de um objeto em um formato de tabela, formato de lista, formato largo e formato de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-105">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="ce7cd-106">Elemento de configuração (Format) ViewDefinitions (Format XML) Element</span><span class="sxs-lookup"><span data-stu-id="ce7cd-106">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="ce7cd-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ce7cd-107">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ce7cd-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ce7cd-108">Attributes and Elements</span></span>

<span data-ttu-id="ce7cd-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ViewDefinitions` elemento.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-109">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="ce7cd-110">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação e elas podem ser adicionadas em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-110">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="ce7cd-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ce7cd-111">Attributes</span></span>

<span data-ttu-id="ce7cd-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ce7cd-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ce7cd-113">Child Elements</span></span>

|<span data-ttu-id="ce7cd-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce7cd-114">Element</span></span>|<span data-ttu-id="ce7cd-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="ce7cd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ce7cd-116">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="ce7cd-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="ce7cd-117">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-117">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ce7cd-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ce7cd-118">Parent Elements</span></span>

|<span data-ttu-id="ce7cd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce7cd-119">Element</span></span>|<span data-ttu-id="ce7cd-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="ce7cd-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ce7cd-121">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="ce7cd-121">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="ce7cd-122">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-122">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ce7cd-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="ce7cd-123">Remarks</span></span>

<span data-ttu-id="ce7cd-124">Para obter mais informações sobre os componentes dos diferentes tipos de exibições, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ce7cd-124">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="ce7cd-125">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="ce7cd-125">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="ce7cd-126">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="ce7cd-126">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="ce7cd-127">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="ce7cd-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="ce7cd-128">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="ce7cd-128">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="ce7cd-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ce7cd-129">Example</span></span>

<span data-ttu-id="ce7cd-130">Este exemplo mostra um `ViewDefinitions` elemento que contém os elementos pai para uma exibição de tabela e um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="ce7cd-130">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="ce7cd-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce7cd-131">See Also</span></span>

[<span data-ttu-id="ce7cd-132">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="ce7cd-132">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="ce7cd-133">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="ce7cd-133">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="ce7cd-134">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="ce7cd-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ce7cd-135">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="ce7cd-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ce7cd-136">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="ce7cd-136">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ce7cd-137">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="ce7cd-137">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="ce7cd-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce7cd-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
