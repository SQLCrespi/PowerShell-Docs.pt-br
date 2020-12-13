---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento WideEntry para WideControl (formato)
description: Elemento WideEntry para WideControl (formato)
ms.openlocfilehash: 3faaf767d11914792effd6765beed956a502c642
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664539"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="65e4a-103">Elemento WideEntry para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="65e4a-103">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="65e4a-104">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="65e4a-104">Provides a definition of the wide view.</span></span>

<span data-ttu-id="65e4a-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65e4a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="65e4a-106">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="65e4a-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="65e4a-107">Attributes and Elements</span></span>

<span data-ttu-id="65e4a-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="65e4a-108">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="65e4a-109">Você deve especificar um único `WideItem` elemento filho.</span><span class="sxs-lookup"><span data-stu-id="65e4a-109">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="65e4a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="65e4a-110">Attributes</span></span>

<span data-ttu-id="65e4a-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="65e4a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65e4a-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="65e4a-112">Child Elements</span></span>

|<span data-ttu-id="65e4a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="65e4a-113">Element</span></span>|<span data-ttu-id="65e4a-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="65e4a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65e4a-115">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="65e4a-115">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="65e4a-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="65e4a-116">Optional element.</span></span><br /><br /> <span data-ttu-id="65e4a-117">Define os tipos .NET que usam essa definição de entrada larga ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="65e4a-117">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="65e4a-118">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-118">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="65e4a-119">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="65e4a-119">Required element.</span></span><br /><br /> <span data-ttu-id="65e4a-120">Define a propriedade ou o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="65e4a-120">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="65e4a-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="65e4a-121">Parent Elements</span></span>

|<span data-ttu-id="65e4a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="65e4a-122">Element</span></span>|<span data-ttu-id="65e4a-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="65e4a-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65e4a-124">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-124">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="65e4a-125">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="65e4a-125">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="65e4a-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="65e4a-126">Remarks</span></span>

<span data-ttu-id="65e4a-127">Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="65e4a-127">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="65e4a-128">Ao contrário de outros tipos de exibições, você pode especificar apenas um elemento item para cada definição de exibição.</span><span class="sxs-lookup"><span data-stu-id="65e4a-128">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="65e4a-129">Para obter mais informações sobre os outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="65e4a-129">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="65e4a-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="65e4a-130">Example</span></span>

<span data-ttu-id="65e4a-131">O exemplo a seguir mostra um `WideEntry` elemento que define um único `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="65e4a-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="65e4a-132">O `WideItem` elemento define a propriedade cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="65e4a-132">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="65e4a-133">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="65e4a-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="65e4a-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="65e4a-134">See Also</span></span>

[<span data-ttu-id="65e4a-135">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="65e4a-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="65e4a-136">Elemento SelectionCondition para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-136">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="65e4a-137">Elemento SelectionSetName para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-137">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="65e4a-138">Elemento TypeName para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-138">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="65e4a-139">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-139">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="65e4a-140">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="65e4a-140">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="65e4a-141">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="65e4a-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
