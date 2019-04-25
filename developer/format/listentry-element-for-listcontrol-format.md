---
title: Elemento ListEntry para ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d16bca8-d025-432d-aa84-8b607b8af3ae
caps.latest.revision: 12
ms.openlocfilehash: 1a3bafd4ca94aee70e869c699f7a4ef8befc5511
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065216"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="2063e-102">Elemento ListEntry para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-102">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="2063e-103">Fornece uma definição da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="2063e-103">Provides a definition of the list view.</span></span>

<span data-ttu-id="2063e-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento ListControl (formato) elemento ListEntries (formato) ListEntry elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2063e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2063e-105">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2063e-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="2063e-106">Attributes and Elements</span></span>

<span data-ttu-id="2063e-107">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `ListEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="2063e-107">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2063e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="2063e-108">Attributes</span></span>

<span data-ttu-id="2063e-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2063e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2063e-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2063e-110">Child Elements</span></span>

|<span data-ttu-id="2063e-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2063e-111">Element</span></span>|<span data-ttu-id="2063e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="2063e-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2063e-113">Elemento EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-113">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="2063e-114">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="2063e-114">Optional element.</span></span><br /><br /> <span data-ttu-id="2063e-115">Define os objetos do .NET que usam essa definição de exibição de lista ou a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="2063e-115">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="2063e-116">Elemento ListItems (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-116">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="2063e-117">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="2063e-117">Required element.</span></span><br /><br /> <span data-ttu-id="2063e-118">Define as propriedades e os scripts cujos valores são exibidos pela exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="2063e-118">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2063e-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2063e-119">Parent Elements</span></span>

|<span data-ttu-id="2063e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2063e-120">Element</span></span>|<span data-ttu-id="2063e-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="2063e-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2063e-122">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-122">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="2063e-123">Fornece as definições de exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="2063e-123">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2063e-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="2063e-124">Remarks</span></span>

<span data-ttu-id="2063e-125">Uma exibição de lista é um formato de lista que exibe valores de propriedade ou script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="2063e-125">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="2063e-126">Para obter mais informações sobre modos de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="2063e-126">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2063e-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2063e-127">Example</span></span>

<span data-ttu-id="2063e-128">Este exemplo mostra os elementos XML que definem o modo de exibição de lista para o [ServiceProcess](/dotnet/api/System.ServiceProcess.ServiceController) objeto.</span><span class="sxs-lookup"><span data-stu-id="2063e-128">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2063e-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2063e-129">See Also</span></span>

[<span data-ttu-id="2063e-130">Criando uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="2063e-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2063e-131">Elemento EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="2063e-132">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-132">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="2063e-133">Elemento ListItems (formato)</span><span class="sxs-lookup"><span data-stu-id="2063e-133">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="2063e-134">Escrevendo um formatação do Windows PowerShell e tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="2063e-134">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
