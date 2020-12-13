---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListEntries para ListControl (formato)
description: Elemento ListEntries para ListControl (formato)
ms.openlocfilehash: d4d6625bb92ea27863fc30d5bf5625f9275e4f69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666596"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="87e4d-103">Elemento ListEntries para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="87e4d-103">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="87e4d-104">Fornece as definições da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="87e4d-104">Provides the definitions of the list view.</span></span> <span data-ttu-id="87e4d-105">A exibição de lista deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="87e4d-105">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="87e4d-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="87e4d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="87e4d-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="87e4d-107">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87e4d-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="87e4d-108">Attributes and Elements</span></span>

<span data-ttu-id="87e4d-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="87e4d-109">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="87e4d-110">Pelo menos um elemento filho deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="87e4d-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="87e4d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="87e4d-111">Attributes</span></span>

<span data-ttu-id="87e4d-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="87e4d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="87e4d-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="87e4d-113">Child Elements</span></span>

|<span data-ttu-id="87e4d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="87e4d-114">Element</span></span>|<span data-ttu-id="87e4d-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="87e4d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87e4d-116">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="87e4d-116">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="87e4d-117">Fornece uma definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="87e4d-117">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="87e4d-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="87e4d-118">Parent Elements</span></span>

|<span data-ttu-id="87e4d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="87e4d-119">Element</span></span>|<span data-ttu-id="87e4d-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="87e4d-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87e4d-121">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="87e4d-121">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="87e4d-122">Define um formato de lista para a exibição.</span><span class="sxs-lookup"><span data-stu-id="87e4d-122">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="87e4d-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="87e4d-123">Remarks</span></span>

<span data-ttu-id="87e4d-124">Para obter mais informações sobre exibições de lista, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="87e4d-124">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="87e4d-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="87e4d-125">Example</span></span>

<span data-ttu-id="87e4d-126">Este exemplo mostra os elementos XML que definem a exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="87e4d-126">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="87e4d-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="87e4d-127">See Also</span></span>

[<span data-ttu-id="87e4d-128">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="87e4d-128">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="87e4d-129">Elemento ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="87e4d-129">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="87e4d-130">Exibição de lista</span><span class="sxs-lookup"><span data-stu-id="87e4d-130">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="87e4d-131">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87e4d-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
