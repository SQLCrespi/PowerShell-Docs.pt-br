---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ListEntry para ListControl (formato)
description: Elemento ListEntry para ListControl (formato)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666562"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="d6dfb-103">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-103">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="d6dfb-104">Fornece uma definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-104">Provides a definition of the list view.</span></span>

<span data-ttu-id="d6dfb-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format) ListEntry Element (Format)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d6dfb-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d6dfb-106">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d6dfb-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d6dfb-107">Attributes and Elements</span></span>

<span data-ttu-id="d6dfb-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d6dfb-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d6dfb-109">Attributes</span></span>

<span data-ttu-id="d6dfb-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d6dfb-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="d6dfb-111">Child Elements</span></span>

|<span data-ttu-id="d6dfb-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6dfb-112">Element</span></span>|<span data-ttu-id="d6dfb-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="d6dfb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6dfb-114">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-114">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="d6dfb-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d6dfb-116">Define os objetos .NET que usam essa definição de exibição de lista ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-116">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="d6dfb-117">Elemento ListItems (formato)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-117">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="d6dfb-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-118">Required element.</span></span><br /><br /> <span data-ttu-id="d6dfb-119">Define as propriedades e os scripts cujos valores são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-119">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d6dfb-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="d6dfb-120">Parent Elements</span></span>

|<span data-ttu-id="d6dfb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6dfb-121">Element</span></span>|<span data-ttu-id="d6dfb-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="d6dfb-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6dfb-123">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-123">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="d6dfb-124">Fornece as definições da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-124">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d6dfb-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="d6dfb-125">Remarks</span></span>

<span data-ttu-id="d6dfb-126">Uma exibição de lista é um formato de lista que exibe valores de propriedade ou valores de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="d6dfb-126">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="d6dfb-127">Para obter mais informações sobre exibições de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="d6dfb-127">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d6dfb-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d6dfb-128">Example</span></span>

<span data-ttu-id="d6dfb-129">Este exemplo mostra os elementos XML que definem a exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="d6dfb-129">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d6dfb-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d6dfb-130">See Also</span></span>

[<span data-ttu-id="d6dfb-131">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="d6dfb-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d6dfb-132">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-132">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="d6dfb-133">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-133">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="d6dfb-134">Elemento ListItems (formato)</span><span class="sxs-lookup"><span data-stu-id="d6dfb-134">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="d6dfb-135">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6dfb-135">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
