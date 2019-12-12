---
title: Elemento TypeName para ViewSelectedBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ad807a9-d7d8-4e96-b799-9c6a7677cc2d
caps.latest.revision: 12
ms.openlocfilehash: e2028c479103cc414295dc24a0f9bb69190bfc66
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361435"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="100aa-102">Elemento TypeName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="100aa-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="100aa-103">Especifica um objeto .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="100aa-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="100aa-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="100aa-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="100aa-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="100aa-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="100aa-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="100aa-106">Attributes and Elements</span></span>

<span data-ttu-id="100aa-107">As seções a seguir descrevem atributos, elementos filho e os elementos pai do elemento `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="100aa-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="100aa-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="100aa-108">Attributes</span></span>

<span data-ttu-id="100aa-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="100aa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="100aa-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="100aa-110">Child Elements</span></span>

<span data-ttu-id="100aa-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="100aa-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="100aa-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="100aa-112">Parent Elements</span></span>

|<span data-ttu-id="100aa-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="100aa-113">Element</span></span>|<span data-ttu-id="100aa-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="100aa-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="100aa-115">Elemento ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="100aa-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="100aa-116">Define os objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="100aa-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="100aa-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="100aa-117">Text Value</span></span>

<span data-ttu-id="100aa-118">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="100aa-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="100aa-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="100aa-119">Remarks</span></span>

<span data-ttu-id="100aa-120">Para obter mais informações sobre como esse elemento é usado em diferentes exibições, consulte [criando uma exibição de tabela](./creating-a-table-view.md), [criando uma exibição de lista](./creating-a-list-view.md), [criando uma exibição ampla](./creating-a-wide-view.md)e [componentes de exibição personalizada](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="100aa-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="100aa-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="100aa-121">Example</span></span>

<span data-ttu-id="100aa-122">O exemplo a seguir mostra como especificar o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) para uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="100aa-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="100aa-123">O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="100aa-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="100aa-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="100aa-124">See Also</span></span>

[<span data-ttu-id="100aa-125">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="100aa-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="100aa-126">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="100aa-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="100aa-127">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="100aa-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="100aa-128">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="100aa-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="100aa-129">Elemento ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="100aa-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="100aa-130">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="100aa-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
