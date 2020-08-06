---
title: Elemento WideEntry para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13dd1f6ad7ac1e9d8d0524f0a0f18fe80ffaf8e2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780008"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="a363c-102">Elemento WideEntry para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a363c-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="a363c-103">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="a363c-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="a363c-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a363c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a363c-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a363c-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a363c-106">Attributes and Elements</span></span>

<span data-ttu-id="a363c-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="a363c-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="a363c-108">Você deve especificar um único `WideItem` elemento filho.</span><span class="sxs-lookup"><span data-stu-id="a363c-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a363c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a363c-109">Attributes</span></span>

<span data-ttu-id="a363c-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a363c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a363c-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="a363c-111">Child Elements</span></span>

|<span data-ttu-id="a363c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a363c-112">Element</span></span>|<span data-ttu-id="a363c-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="a363c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a363c-114">Elemento EntrySelectedBy para WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="a363c-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="a363c-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a363c-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a363c-116">Define os tipos .NET que usam essa definição de entrada larga ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="a363c-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a363c-117">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="a363c-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="a363c-118">Required element.</span></span><br /><br /> <span data-ttu-id="a363c-119">Define a propriedade ou o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="a363c-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a363c-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="a363c-120">Parent Elements</span></span>

|<span data-ttu-id="a363c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a363c-121">Element</span></span>|<span data-ttu-id="a363c-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="a363c-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a363c-123">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="a363c-124">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="a363c-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a363c-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="a363c-125">Remarks</span></span>

<span data-ttu-id="a363c-126">Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="a363c-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="a363c-127">Ao contrário de outros tipos de exibições, você pode especificar apenas um elemento item para cada definição de exibição.</span><span class="sxs-lookup"><span data-stu-id="a363c-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="a363c-128">Para obter mais informações sobre os outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="a363c-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a363c-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a363c-129">Example</span></span>

<span data-ttu-id="a363c-130">O exemplo a seguir mostra um `WideEntry` elemento que define um único `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="a363c-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="a363c-131">O `WideItem` elemento define a propriedade cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="a363c-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="a363c-132">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="a363c-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a363c-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a363c-133">See Also</span></span>

[<span data-ttu-id="a363c-134">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="a363c-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a363c-135">Elemento SelectionCondition para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a363c-136">Elemento SelectionSetName para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a363c-137">Elemento TypeName para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="a363c-138">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="a363c-139">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a363c-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="a363c-140">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a363c-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
