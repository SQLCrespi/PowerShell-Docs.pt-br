---
title: Elemento ListControl (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0173b9797bffcca74f1a32903686f771366ebb1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785720"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="960d8-102">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="960d8-102">ListControl Element (Format)</span></span>

<span data-ttu-id="960d8-103">Define um formato de lista para a exibição.</span><span class="sxs-lookup"><span data-stu-id="960d8-103">Defines a list format for the view.</span></span>

<span data-ttu-id="960d8-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="960d8-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="960d8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="960d8-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="960d8-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="960d8-106">Attributes and Elements</span></span>

<span data-ttu-id="960d8-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ListControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="960d8-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="960d8-108">Este elemento deve conter apenas um único elemento filho.</span><span class="sxs-lookup"><span data-stu-id="960d8-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="960d8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="960d8-109">Attributes</span></span>

<span data-ttu-id="960d8-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="960d8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="960d8-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="960d8-111">Child Elements</span></span>

|<span data-ttu-id="960d8-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="960d8-112">Element</span></span>|<span data-ttu-id="960d8-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="960d8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="960d8-114">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="960d8-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="960d8-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="960d8-115">Required element.</span></span><br /><br /> <span data-ttu-id="960d8-116">Fornece as definições da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="960d8-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="960d8-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="960d8-117">Parent Elements</span></span>

|<span data-ttu-id="960d8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="960d8-118">Element</span></span>|<span data-ttu-id="960d8-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="960d8-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="960d8-120">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="960d8-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="960d8-121">Define uma exibição que é usada para exibir os membros de um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="960d8-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="960d8-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="960d8-122">Remarks</span></span>

<span data-ttu-id="960d8-123">Para obter mais informações sobre como criar um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="960d8-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="960d8-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="960d8-124">Example</span></span>

<span data-ttu-id="960d8-125">Este exemplo mostra um modo de exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="960d8-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="960d8-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="960d8-126">See Also</span></span>

[<span data-ttu-id="960d8-127">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="960d8-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="960d8-128">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="960d8-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="960d8-129">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="960d8-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="960d8-130">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="960d8-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
