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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364015"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="32f36-102">Elemento CustomEntry para CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="32f36-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="32f36-103">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="32f36-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="32f36-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) CustomControl Element (Format) CustomEntries elemento para CustomControl para View (Format) CustomEntry Element for CustomEntries para View (Format)</span><span class="sxs-lookup"><span data-stu-id="32f36-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="32f36-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32f36-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="32f36-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="32f36-106">Attributes and Elements</span></span>

<span data-ttu-id="32f36-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="32f36-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="32f36-108">Você deve especificar os itens exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="32f36-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="32f36-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="32f36-109">Attributes</span></span>

<span data-ttu-id="32f36-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="32f36-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="32f36-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="32f36-111">Child Elements</span></span>

|<span data-ttu-id="32f36-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="32f36-112">Element</span></span>|<span data-ttu-id="32f36-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="32f36-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32f36-114">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="32f36-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="32f36-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="32f36-115">Optional element.</span></span><br /><br /> <span data-ttu-id="32f36-116">Define os tipos .NET que usam a definição do modo de exibição de controle personalizado ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="32f36-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="32f36-117">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="32f36-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="32f36-118">Define um controle para a definição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="32f36-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="32f36-119">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="32f36-119">Parent Elements</span></span>

|<span data-ttu-id="32f36-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="32f36-120">Element</span></span>|<span data-ttu-id="32f36-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="32f36-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="32f36-122">Elemento CustomEntries para CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="32f36-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="32f36-123">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="32f36-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="32f36-124">A exibição de controle personalizado deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="32f36-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="32f36-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="32f36-125">Remarks</span></span>

<span data-ttu-id="32f36-126">Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle personalizado, mas é possível ter várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes.</span><span class="sxs-lookup"><span data-stu-id="32f36-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="32f36-127">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="32f36-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="32f36-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32f36-128">See Also</span></span>

[<span data-ttu-id="32f36-129">Elemento CustomControl para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="32f36-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="32f36-130">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="32f36-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="32f36-131">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="32f36-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="32f36-132">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f36-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
