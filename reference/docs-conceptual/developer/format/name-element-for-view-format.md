---
title: Elemento de nome para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362635"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="b570f-102">Elemento Name para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b570f-102">Name Element for View (Format)</span></span>

<span data-ttu-id="b570f-103">Especifica o nome que é usado para identificar a exibição.</span><span class="sxs-lookup"><span data-stu-id="b570f-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="b570f-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) nome Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b570f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b570f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b570f-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b570f-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b570f-106">Attributes and Elements</span></span>

<span data-ttu-id="b570f-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `Name`.</span><span class="sxs-lookup"><span data-stu-id="b570f-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="b570f-108">Apenas um elemento `Name` é permitido para cada exibição.</span><span class="sxs-lookup"><span data-stu-id="b570f-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="b570f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b570f-109">Attributes</span></span>

<span data-ttu-id="b570f-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b570f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b570f-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="b570f-111">Child Elements</span></span>

<span data-ttu-id="b570f-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b570f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b570f-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="b570f-113">Parent Elements</span></span>

|<span data-ttu-id="b570f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b570f-114">Element</span></span>|<span data-ttu-id="b570f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b570f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b570f-116">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="b570f-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="b570f-117">Define uma exibição que é usada para exibir os membros de um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="b570f-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b570f-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="b570f-118">Text Value</span></span>

<span data-ttu-id="b570f-119">Especifique um nome amigável exclusivo para a exibição.</span><span class="sxs-lookup"><span data-stu-id="b570f-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="b570f-120">Esse nome pode incluir uma referência ao tipo da exibição (como uma exibição de tabela ou exibição de lista), qual objeto ou conjunto de objetos usa a exibição, qual comando retorna os objetos ou uma combinação deles.</span><span class="sxs-lookup"><span data-stu-id="b570f-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="b570f-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="b570f-121">Remarks</span></span>

<span data-ttu-id="b570f-122">Para obter mais informações sobre os diferentes tipos de exibições, consulte os seguintes tópicos: [exibição de tabela](./creating-a-table-view.md), [exibição de lista](./creating-a-list-view.md), exibição [ampla](./creating-a-wide-view.md)e [exibição personalizada](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b570f-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="b570f-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b570f-123">Example</span></span>

<span data-ttu-id="b570f-124">O exemplo a seguir mostra um elemento `View` que define uma exibição de tabela para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="b570f-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="b570f-125">O nome da exibição é "serviço".</span><span class="sxs-lookup"><span data-stu-id="b570f-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="b570f-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b570f-126">See Also</span></span>

[<span data-ttu-id="b570f-127">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="b570f-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="b570f-128">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="b570f-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b570f-129">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="b570f-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b570f-130">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="b570f-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="b570f-131">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="b570f-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="b570f-132">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b570f-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
