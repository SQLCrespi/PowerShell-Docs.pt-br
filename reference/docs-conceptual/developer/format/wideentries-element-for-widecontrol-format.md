---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento WideEntries para WideControl (formato)
description: Elemento WideEntries para WideControl (formato)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651235"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="264c9-103">Elemento WideEntries para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="264c9-103">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="264c9-104">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="264c9-104">Provides the definitions of the wide view.</span></span> <span data-ttu-id="264c9-105">A exibição ampla deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="264c9-105">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="264c9-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl Element (Format) WideEntries elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="264c9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="264c9-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="264c9-107">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="264c9-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="264c9-108">Attributes and Elements</span></span>

<span data-ttu-id="264c9-109">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="264c9-109">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="264c9-110">Pelo menos um elemento filho deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="264c9-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="264c9-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="264c9-111">Attributes</span></span>

<span data-ttu-id="264c9-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="264c9-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="264c9-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="264c9-113">Child Elements</span></span>

|<span data-ttu-id="264c9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="264c9-114">Element</span></span>|<span data-ttu-id="264c9-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="264c9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="264c9-116">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="264c9-116">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="264c9-117">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="264c9-117">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="264c9-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="264c9-118">Parent Elements</span></span>

|<span data-ttu-id="264c9-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="264c9-119">Element</span></span>|<span data-ttu-id="264c9-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="264c9-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="264c9-121">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="264c9-121">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="264c9-122">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="264c9-122">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="264c9-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="264c9-123">Remarks</span></span>

<span data-ttu-id="264c9-124">Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="264c9-124">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="264c9-125">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="264c9-125">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="264c9-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="264c9-126">Example</span></span>

<span data-ttu-id="264c9-127">O exemplo a seguir mostra um `WideEntries` elemento que define um único `WideEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="264c9-127">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="264c9-128">O `WideEntry` elemento contém um único `WideItem` elemento que define qual valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="264c9-128">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="264c9-129">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="264c9-129">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="264c9-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="264c9-130">See Also</span></span>

[<span data-ttu-id="264c9-131">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="264c9-131">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="264c9-132">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="264c9-132">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="264c9-133">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="264c9-133">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="264c9-134">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="264c9-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
