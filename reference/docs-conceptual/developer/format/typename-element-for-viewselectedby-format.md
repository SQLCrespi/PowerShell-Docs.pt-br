---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TypeName para ViewSelectedBy (formato)
description: Elemento TypeName para ViewSelectedBy (formato)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667718"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="7c496-103">Elemento TypeName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="7c496-103">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="7c496-104">Especifica um objeto .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="7c496-104">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="7c496-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7c496-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7c496-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7c496-106">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c496-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7c496-107">Attributes and Elements</span></span>

<span data-ttu-id="7c496-108">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="7c496-108">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c496-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="7c496-109">Attributes</span></span>

<span data-ttu-id="7c496-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7c496-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7c496-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="7c496-111">Child Elements</span></span>

<span data-ttu-id="7c496-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="7c496-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c496-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="7c496-113">Parent Elements</span></span>

|<span data-ttu-id="7c496-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="7c496-114">Element</span></span>|<span data-ttu-id="7c496-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c496-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c496-116">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="7c496-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="7c496-117">Define os objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="7c496-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7c496-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="7c496-118">Text Value</span></span>

<span data-ttu-id="7c496-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="7c496-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c496-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="7c496-120">Remarks</span></span>

<span data-ttu-id="7c496-121">Para obter mais informações sobre como esse elemento é usado em diferentes exibições, consulte [criando uma exibição de tabela](./creating-a-table-view.md), [criando uma exibição de lista](./creating-a-list-view.md), [criando uma exibição ampla](./creating-a-wide-view.md)e [componentes de exibição personalizada](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7c496-121">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="7c496-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7c496-122">Example</span></span>

<span data-ttu-id="7c496-123">O exemplo a seguir mostra como especificar o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) para uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="7c496-123">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="7c496-124">O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7c496-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="7c496-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c496-125">See Also</span></span>

[<span data-ttu-id="7c496-126">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="7c496-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7c496-127">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="7c496-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7c496-128">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="7c496-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7c496-129">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="7c496-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7c496-130">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="7c496-130">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="7c496-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c496-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
