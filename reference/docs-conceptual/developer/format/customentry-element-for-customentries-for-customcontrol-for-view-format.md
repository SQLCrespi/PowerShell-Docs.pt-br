---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntry para CustomEntries para CustomControl para View (formato)
description: Elemento CustomEntry para CustomEntries para CustomControl para View (formato)
ms.openlocfilehash: ff481f13e6f16267bdda4c3053faebc96d9a6d3a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646050"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="6033c-103">Elemento CustomEntry para CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6033c-103">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="6033c-104">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="6033c-104">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="6033c-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) CustomControl Element (Format) CustomEntries elemento para CustomControl para View (Format) CustomEntry Element for CustomEntries para View (Format)</span><span class="sxs-lookup"><span data-stu-id="6033c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6033c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6033c-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6033c-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6033c-107">Attributes and Elements</span></span>

<span data-ttu-id="6033c-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="6033c-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="6033c-109">Você deve especificar os itens exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="6033c-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="6033c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6033c-110">Attributes</span></span>

<span data-ttu-id="6033c-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="6033c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6033c-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6033c-112">Child Elements</span></span>

|<span data-ttu-id="6033c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6033c-113">Element</span></span>|<span data-ttu-id="6033c-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6033c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6033c-115">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6033c-115">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="6033c-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="6033c-116">Optional element.</span></span><br /><br /> <span data-ttu-id="6033c-117">Define os tipos .NET que usam a definição do modo de exibição de controle personalizado ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="6033c-117">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="6033c-118">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6033c-118">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="6033c-119">Define um controle para a definição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="6033c-119">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6033c-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6033c-120">Parent Elements</span></span>

|<span data-ttu-id="6033c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="6033c-121">Element</span></span>|<span data-ttu-id="6033c-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="6033c-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6033c-123">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6033c-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="6033c-124">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="6033c-124">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="6033c-125">A exibição de controle personalizado deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="6033c-125">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6033c-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="6033c-126">Remarks</span></span>

<span data-ttu-id="6033c-127">Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle personalizado, mas é possível ter várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes.</span><span class="sxs-lookup"><span data-stu-id="6033c-127">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="6033c-128">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="6033c-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="6033c-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6033c-129">See Also</span></span>

[<span data-ttu-id="6033c-130">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="6033c-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="6033c-131">Elemento CustomItem para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6033c-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6033c-132">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="6033c-132">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6033c-133">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6033c-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
