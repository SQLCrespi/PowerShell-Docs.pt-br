---
title: Elemento TypeName para ViewSelectedBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9a391565c3e66041dd9a340455dccfce9ce929b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780025"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="b5a4e-102">Elemento TypeName para ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="b5a4e-103">Especifica um objeto .NET que é exibido pela exibição.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="b5a4e-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b5a4e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b5a4e-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b5a4e-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b5a4e-106">Attributes and Elements</span></span>

<span data-ttu-id="b5a4e-107">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b5a4e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5a4e-108">Attributes</span></span>

<span data-ttu-id="b5a4e-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b5a4e-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b5a4e-110">Child Elements</span></span>

<span data-ttu-id="b5a4e-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b5a4e-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b5a4e-112">Parent Elements</span></span>

|<span data-ttu-id="b5a4e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5a4e-113">Element</span></span>|<span data-ttu-id="b5a4e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="b5a4e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b5a4e-115">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="b5a4e-116">Define os objetos .NET que são exibidos pela exibição.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b5a4e-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b5a4e-117">Text Value</span></span>

<span data-ttu-id="b5a4e-118">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="b5a4e-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5a4e-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="b5a4e-119">Remarks</span></span>

<span data-ttu-id="b5a4e-120">Para obter mais informações sobre como esse elemento é usado em diferentes exibições, consulte [criando uma exibição de tabela](./creating-a-table-view.md), [criando uma exibição de lista](./creating-a-list-view.md), [criando uma exibição ampla](./creating-a-wide-view.md)e [componentes de exibição personalizada](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b5a4e-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="b5a4e-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b5a4e-121">Example</span></span>

<span data-ttu-id="b5a4e-122">O exemplo a seguir mostra como especificar o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) para uma exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="b5a4e-123">O mesmo esquema é usado para exibições de tabela, ampla e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b5a4e-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="b5a4e-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5a4e-124">See Also</span></span>

[<span data-ttu-id="b5a4e-125">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="b5a4e-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="b5a4e-126">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="b5a4e-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b5a4e-127">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="b5a4e-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b5a4e-128">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="b5a4e-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="b5a4e-129">Elemento ViewSelectedBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b5a4e-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="b5a4e-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5a4e-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
