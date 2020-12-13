---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Name para View (formato)
description: Elemento Name para View (formato)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666443"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="d416c-103">Elemento Name para View (formato)</span><span class="sxs-lookup"><span data-stu-id="d416c-103">Name Element for View (Format)</span></span>

<span data-ttu-id="d416c-104">Especifica o nome que é usado para identificar a exibição.</span><span class="sxs-lookup"><span data-stu-id="d416c-104">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="d416c-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) nome Element (Format)</span><span class="sxs-lookup"><span data-stu-id="d416c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d416c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d416c-106">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d416c-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d416c-107">Attributes and Elements</span></span>

<span data-ttu-id="d416c-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `Name` elemento.</span><span class="sxs-lookup"><span data-stu-id="d416c-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="d416c-109">Somente um `Name` elemento é permitido para cada exibição.</span><span class="sxs-lookup"><span data-stu-id="d416c-109">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="d416c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d416c-110">Attributes</span></span>

<span data-ttu-id="d416c-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d416c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d416c-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d416c-112">Child Elements</span></span>

<span data-ttu-id="d416c-113">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d416c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d416c-114">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d416c-114">Parent Elements</span></span>

|<span data-ttu-id="d416c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d416c-115">Element</span></span>|<span data-ttu-id="d416c-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="d416c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d416c-117">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="d416c-117">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="d416c-118">Define uma exibição que é usada para exibir os membros de um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="d416c-118">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d416c-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="d416c-119">Text Value</span></span>

<span data-ttu-id="d416c-120">Especifique um nome amigável exclusivo para a exibição.</span><span class="sxs-lookup"><span data-stu-id="d416c-120">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="d416c-121">Esse nome pode incluir uma referência ao tipo da exibição (como uma exibição de tabela ou exibição de lista), qual objeto ou conjunto de objetos usa a exibição, qual comando retorna os objetos ou uma combinação deles.</span><span class="sxs-lookup"><span data-stu-id="d416c-121">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="d416c-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="d416c-122">Remarks</span></span>

<span data-ttu-id="d416c-123">Para obter mais informações sobre os diferentes tipos de exibições, consulte os seguintes tópicos: [exibição de tabela](./creating-a-table-view.md), [exibição de lista](./creating-a-list-view.md), exibição [ampla](./creating-a-wide-view.md)e [exibição personalizada](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d416c-123">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="d416c-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d416c-124">Example</span></span>

<span data-ttu-id="d416c-125">O exemplo a seguir mostra um `View` elemento que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="d416c-125">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="d416c-126">O nome da exibição é "serviço".</span><span class="sxs-lookup"><span data-stu-id="d416c-126">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="d416c-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d416c-127">See Also</span></span>

[<span data-ttu-id="d416c-128">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="d416c-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d416c-129">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="d416c-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d416c-130">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="d416c-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="d416c-131">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="d416c-131">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="d416c-132">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="d416c-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="d416c-133">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d416c-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
