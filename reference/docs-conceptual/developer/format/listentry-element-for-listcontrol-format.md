---
title: Elemento ListEntry para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d98f0b5215eea7668f866d2733214ade79d748f1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785686"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="96b46-102">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="96b46-102">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="96b46-103">Fornece uma definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="96b46-103">Provides a definition of the list view.</span></span>

<span data-ttu-id="96b46-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries (Format) ListEntry Element (Format)</span><span class="sxs-lookup"><span data-stu-id="96b46-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="96b46-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="96b46-105">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96b46-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="96b46-106">Attributes and Elements</span></span>

<span data-ttu-id="96b46-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="96b46-107">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="96b46-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="96b46-108">Attributes</span></span>

<span data-ttu-id="96b46-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="96b46-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="96b46-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="96b46-110">Child Elements</span></span>

|<span data-ttu-id="96b46-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="96b46-111">Element</span></span>|<span data-ttu-id="96b46-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="96b46-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96b46-113">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="96b46-113">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="96b46-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="96b46-114">Optional element.</span></span><br /><br /> <span data-ttu-id="96b46-115">Define os objetos .NET que usam essa definição de exibição de lista ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="96b46-115">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="96b46-116">Elemento ListItems (formato)</span><span class="sxs-lookup"><span data-stu-id="96b46-116">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="96b46-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="96b46-117">Required element.</span></span><br /><br /> <span data-ttu-id="96b46-118">Define as propriedades e os scripts cujos valores são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="96b46-118">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="96b46-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="96b46-119">Parent Elements</span></span>

|<span data-ttu-id="96b46-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="96b46-120">Element</span></span>|<span data-ttu-id="96b46-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="96b46-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96b46-122">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="96b46-122">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="96b46-123">Fornece as definições da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="96b46-123">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="96b46-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="96b46-124">Remarks</span></span>

<span data-ttu-id="96b46-125">Uma exibição de lista é um formato de lista que exibe valores de propriedade ou valores de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="96b46-125">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="96b46-126">Para obter mais informações sobre exibições de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="96b46-126">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="96b46-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="96b46-127">Example</span></span>

<span data-ttu-id="96b46-128">Este exemplo mostra os elementos XML que definem a exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="96b46-128">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="96b46-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="96b46-129">See Also</span></span>

[<span data-ttu-id="96b46-130">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="96b46-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="96b46-131">Elemento EntrySelectedBy para ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="96b46-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="96b46-132">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="96b46-132">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="96b46-133">Elemento ListItems (formato)</span><span class="sxs-lookup"><span data-stu-id="96b46-133">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="96b46-134">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96b46-134">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
