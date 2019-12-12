---
title: Elemento ViewDefinitions (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361415"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="cec18-102">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="cec18-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="cec18-103">Define as exibições usadas para exibir objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="cec18-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="cec18-104">Essas exibições podem exibir as propriedades e os valores de script de um objeto em um formato de tabela, formato de lista, formato largo e formato de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="cec18-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="cec18-105">Elemento de configuração (Format) ViewDefinitions (Format XML) Element</span><span class="sxs-lookup"><span data-stu-id="cec18-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="cec18-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cec18-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cec18-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="cec18-107">Attributes and Elements</span></span>

<span data-ttu-id="cec18-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `ViewDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="cec18-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="cec18-109">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação e elas podem ser adicionadas em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="cec18-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="cec18-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="cec18-110">Attributes</span></span>

<span data-ttu-id="cec18-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="cec18-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cec18-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="cec18-112">Child Elements</span></span>

|<span data-ttu-id="cec18-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="cec18-113">Element</span></span>|<span data-ttu-id="cec18-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="cec18-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cec18-115">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="cec18-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="cec18-116">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="cec18-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cec18-117">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="cec18-117">Parent Elements</span></span>

|<span data-ttu-id="cec18-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="cec18-118">Element</span></span>|<span data-ttu-id="cec18-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="cec18-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cec18-120">Elemento Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="cec18-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="cec18-121">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="cec18-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cec18-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="cec18-122">Remarks</span></span>

<span data-ttu-id="cec18-123">Para obter mais informações sobre os componentes dos diferentes tipos de exibições, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="cec18-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="cec18-124">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="cec18-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="cec18-125">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="cec18-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="cec18-126">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="cec18-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="cec18-127">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="cec18-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="cec18-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cec18-128">Example</span></span>

<span data-ttu-id="cec18-129">Este exemplo mostra um elemento `ViewDefinitions` que contém os elementos pai para uma exibição de tabela e um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="cec18-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cec18-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cec18-130">See Also</span></span>

[<span data-ttu-id="cec18-131">Elemento Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="cec18-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="cec18-132">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="cec18-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="cec18-133">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="cec18-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="cec18-134">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="cec18-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="cec18-135">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="cec18-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cec18-136">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="cec18-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="cec18-137">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cec18-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
