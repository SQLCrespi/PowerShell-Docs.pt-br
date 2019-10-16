---
title: Elemento ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37beeb0b-7a81-4747-becb-e309e17278fb
caps.latest.revision: 12
ms.openlocfilehash: 7a117c25b0d117dc846ba8e060e31e838b5edd52
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362775"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="29be2-102">Elemento ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="29be2-102">ListControl Element (Format)</span></span>

<span data-ttu-id="29be2-103">Define um formato de lista para a exibição.</span><span class="sxs-lookup"><span data-stu-id="29be2-103">Defines a list format for the view.</span></span>

<span data-ttu-id="29be2-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="29be2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="29be2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="29be2-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="29be2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="29be2-106">Attributes and Elements</span></span>

<span data-ttu-id="29be2-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `ListControl`.</span><span class="sxs-lookup"><span data-stu-id="29be2-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="29be2-108">Este elemento deve conter apenas um único elemento filho.</span><span class="sxs-lookup"><span data-stu-id="29be2-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="29be2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="29be2-109">Attributes</span></span>

<span data-ttu-id="29be2-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="29be2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="29be2-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="29be2-111">Child Elements</span></span>

|<span data-ttu-id="29be2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="29be2-112">Element</span></span>|<span data-ttu-id="29be2-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="29be2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="29be2-114">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="29be2-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="29be2-115">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="29be2-115">Required element.</span></span><br /><br /> <span data-ttu-id="29be2-116">Fornece as definições da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="29be2-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="29be2-117">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="29be2-117">Parent Elements</span></span>

|<span data-ttu-id="29be2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="29be2-118">Element</span></span>|<span data-ttu-id="29be2-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="29be2-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="29be2-120">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="29be2-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="29be2-121">Define uma exibição que é usada para exibir os membros de um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="29be2-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="29be2-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="29be2-122">Remarks</span></span>

<span data-ttu-id="29be2-123">Para obter mais informações sobre como criar um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="29be2-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="29be2-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="29be2-124">Example</span></span>

<span data-ttu-id="29be2-125">Este exemplo mostra um modo de exibição de lista para o objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="29be2-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="29be2-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="29be2-126">See Also</span></span>

[<span data-ttu-id="29be2-127">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="29be2-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="29be2-128">Elemento ListEntries (formato)</span><span class="sxs-lookup"><span data-stu-id="29be2-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="29be2-129">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="29be2-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="29be2-130">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29be2-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
