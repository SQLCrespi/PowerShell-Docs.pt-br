---
title: Elemento ViewDefinitions (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772477"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="1feb9-102">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="1feb9-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="1feb9-103">Define as exibições usadas para exibir objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="1feb9-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="1feb9-104">Essas exibições podem exibir as propriedades e os valores de script de um objeto em um formato de tabela, formato de lista, formato largo e formato de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="1feb9-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="1feb9-105">Elemento de configuração (Format) ViewDefinitions (Format XML) Element</span><span class="sxs-lookup"><span data-stu-id="1feb9-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="1feb9-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1feb9-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1feb9-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1feb9-107">Attributes and Elements</span></span>

<span data-ttu-id="1feb9-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ViewDefinitions` elemento.</span><span class="sxs-lookup"><span data-stu-id="1feb9-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="1feb9-109">Não há nenhum limite para o número de exibições que podem ser definidas em um arquivo de formatação e elas podem ser adicionadas em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="1feb9-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="1feb9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1feb9-110">Attributes</span></span>

<span data-ttu-id="1feb9-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1feb9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1feb9-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1feb9-112">Child Elements</span></span>

|<span data-ttu-id="1feb9-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1feb9-113">Element</span></span>|<span data-ttu-id="1feb9-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="1feb9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1feb9-115">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="1feb9-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="1feb9-116">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="1feb9-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1feb9-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1feb9-117">Parent Elements</span></span>

|<span data-ttu-id="1feb9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1feb9-118">Element</span></span>|<span data-ttu-id="1feb9-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="1feb9-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1feb9-120">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="1feb9-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="1feb9-121">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="1feb9-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1feb9-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="1feb9-122">Remarks</span></span>

<span data-ttu-id="1feb9-123">Para obter mais informações sobre os componentes dos diferentes tipos de exibições, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1feb9-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="1feb9-124">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="1feb9-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="1feb9-125">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="1feb9-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="1feb9-126">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="1feb9-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="1feb9-127">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="1feb9-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="1feb9-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1feb9-128">Example</span></span>

<span data-ttu-id="1feb9-129">Este exemplo mostra um `ViewDefinitions` elemento que contém os elementos pai para uma exibição de tabela e um modo de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="1feb9-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1feb9-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1feb9-130">See Also</span></span>

[<span data-ttu-id="1feb9-131">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="1feb9-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="1feb9-132">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="1feb9-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="1feb9-133">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="1feb9-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="1feb9-134">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="1feb9-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1feb9-135">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="1feb9-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="1feb9-136">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="1feb9-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="1feb9-137">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1feb9-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
