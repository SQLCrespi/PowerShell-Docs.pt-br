---
title: Elemento CustomEntry para CustomControl para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2987cb45-f646-45d4-b81b-7871e77af36f
caps.latest.revision: 5
ms.openlocfilehash: dcf4f8b2bbd422067ffdf9b3b4972e279e91edf9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066459"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="b932f-102">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="b932f-103">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="b932f-103">Provides a definition of the control.</span></span> <span data-ttu-id="b932f-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="b932f-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b932f-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomEntry GroupBy (formato) CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b932f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b932f-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b932f-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="b932f-107">Attributes and Elements</span></span>

<span data-ttu-id="b932f-108">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="b932f-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b932f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b932f-109">Attributes</span></span>

<span data-ttu-id="b932f-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b932f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b932f-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b932f-111">Child Elements</span></span>

|<span data-ttu-id="b932f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="b932f-112">Element</span></span>|<span data-ttu-id="b932f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="b932f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b932f-114">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="b932f-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b932f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b932f-116">Define os tipos de .NET que usam essa definição de controle ou a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="b932f-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="b932f-117">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="b932f-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="b932f-118">Required element.</span></span><br /><br /> <span data-ttu-id="b932f-119">Define como o controle exibe os dados.</span><span class="sxs-lookup"><span data-stu-id="b932f-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b932f-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b932f-120">Parent Elements</span></span>

|<span data-ttu-id="b932f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b932f-121">Element</span></span>|<span data-ttu-id="b932f-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="b932f-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b932f-123">Elemento CustomEntries para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="b932f-124">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="b932f-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b932f-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="b932f-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b932f-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b932f-126">See Also</span></span>

[<span data-ttu-id="b932f-127">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="b932f-128">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="b932f-129">Elemento CustomEntries para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b932f-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="b932f-130">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b932f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
