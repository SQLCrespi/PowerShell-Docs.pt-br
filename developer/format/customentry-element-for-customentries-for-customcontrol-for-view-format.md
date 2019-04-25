---
title: Elemento CustomEntry para CustomEntries para CustomControl para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066440"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="9b787-102">Elemento CustomEntry para CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="9b787-103">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b787-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="9b787-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento CustomControl (formato) CustomEntries elemento de configuração para CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9b787-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b787-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b787-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="9b787-106">Attributes and Elements</span></span>

<span data-ttu-id="9b787-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="9b787-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="9b787-108">Você deve especificar os itens exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="9b787-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b787-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b787-109">Attributes</span></span>

<span data-ttu-id="9b787-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9b787-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9b787-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9b787-111">Child Elements</span></span>

|<span data-ttu-id="9b787-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b787-112">Element</span></span>|<span data-ttu-id="9b787-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b787-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b787-114">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="9b787-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9b787-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9b787-116">Define os tipos de .NET que usam a definição da exibição do controle personalizado ou a condição que deve existir para essa definição a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9b787-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="9b787-117">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="9b787-118">Define um controle para a definição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b787-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9b787-119">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9b787-119">Parent Elements</span></span>

|<span data-ttu-id="9b787-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b787-120">Element</span></span>|<span data-ttu-id="9b787-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b787-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9b787-122">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="9b787-123">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b787-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="9b787-124">O modo de exibição do controle personalizado deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="9b787-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b787-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="9b787-125">Remarks</span></span>

<span data-ttu-id="9b787-126">Na maioria dos casos, somente uma definição, é necessária para cada modo de exibição do controle personalizado, mas é possível ter várias definições, se você quiser usar a mesma exibição para exibir objetos diferentes do .NET.</span><span class="sxs-lookup"><span data-stu-id="9b787-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="9b787-127">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="9b787-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b787-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9b787-128">See Also</span></span>

[<span data-ttu-id="9b787-129">Elemento CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="9b787-130">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9b787-131">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="9b787-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9b787-132">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b787-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
