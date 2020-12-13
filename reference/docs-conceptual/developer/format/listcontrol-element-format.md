---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListControl (formato)
description: Elemento ListControl (formato)
ms.openlocfilehash: cd5687ac8e94e2245d1ae2de8b2206185e5b8ca4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666579"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="197f2-103">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="197f2-103">ListControl Element (Format)</span></span>

<span data-ttu-id="197f2-104">Define um formato de lista para a exibição.</span><span class="sxs-lookup"><span data-stu-id="197f2-104">Defines a list format for the view.</span></span>

<span data-ttu-id="197f2-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="197f2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="197f2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="197f2-106">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="197f2-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="197f2-107">Attributes and Elements</span></span>

<span data-ttu-id="197f2-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="197f2-108">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="197f2-109">Este elemento deve conter apenas um único elemento filho.</span><span class="sxs-lookup"><span data-stu-id="197f2-109">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="197f2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="197f2-110">Attributes</span></span>

<span data-ttu-id="197f2-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="197f2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="197f2-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="197f2-112">Child Elements</span></span>

|<span data-ttu-id="197f2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="197f2-113">Element</span></span>|<span data-ttu-id="197f2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="197f2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="197f2-115">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="197f2-115">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="197f2-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="197f2-116">Required element.</span></span><br /><br /> <span data-ttu-id="197f2-117">Fornece as definições da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="197f2-117">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="197f2-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="197f2-118">Parent Elements</span></span>

|<span data-ttu-id="197f2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="197f2-119">Element</span></span>|<span data-ttu-id="197f2-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="197f2-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="197f2-121">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="197f2-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="197f2-122">Define uma exibição que é usada para exibir os membros de um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="197f2-122">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="197f2-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="197f2-123">Remarks</span></span>

<span data-ttu-id="197f2-124">Para obter mais informações sobre como criar um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="197f2-124">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="197f2-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="197f2-125">Example</span></span>

<span data-ttu-id="197f2-126">Este exemplo mostra um modo de exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="197f2-126">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="197f2-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="197f2-127">See Also</span></span>

[<span data-ttu-id="197f2-128">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="197f2-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="197f2-129">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="197f2-129">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="197f2-130">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="197f2-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="197f2-131">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="197f2-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
