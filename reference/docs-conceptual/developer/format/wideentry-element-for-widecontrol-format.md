---
title: Elemento WideEntry para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367895"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="3b855-102">Elemento WideEntry para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3b855-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="3b855-103">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="3b855-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="3b855-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3b855-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3b855-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3b855-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="3b855-106">Attributes and Elements</span></span>

<span data-ttu-id="3b855-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `WideEntry`.</span><span class="sxs-lookup"><span data-stu-id="3b855-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="3b855-108">Você deve especificar um único elemento filho `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="3b855-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3b855-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b855-109">Attributes</span></span>

<span data-ttu-id="3b855-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3b855-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3b855-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="3b855-111">Child Elements</span></span>

|<span data-ttu-id="3b855-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b855-112">Element</span></span>|<span data-ttu-id="3b855-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b855-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3b855-114">Elemento EntrySelectedBy para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="3b855-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3b855-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3b855-116">Define os tipos .NET que usam essa definição de entrada larga ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="3b855-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="3b855-117">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="3b855-118">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="3b855-118">Required element.</span></span><br /><br /> <span data-ttu-id="3b855-119">Define a propriedade ou o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="3b855-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3b855-120">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="3b855-120">Parent Elements</span></span>

|<span data-ttu-id="3b855-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b855-121">Element</span></span>|<span data-ttu-id="3b855-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b855-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3b855-123">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="3b855-124">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="3b855-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3b855-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="3b855-125">Remarks</span></span>

<span data-ttu-id="3b855-126">Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="3b855-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="3b855-127">Ao contrário de outros tipos de exibições, você pode especificar apenas um elemento item para cada definição de exibição.</span><span class="sxs-lookup"><span data-stu-id="3b855-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="3b855-128">Para obter mais informações sobre os outros componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="3b855-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3b855-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3b855-129">Example</span></span>

<span data-ttu-id="3b855-130">O exemplo a seguir mostra um elemento `WideEntry` que define um único elemento `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="3b855-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="3b855-131">O elemento `WideItem` define a propriedade cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="3b855-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="3b855-132">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="3b855-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b855-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b855-133">See Also</span></span>

[<span data-ttu-id="3b855-134">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="3b855-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="3b855-135">Elemento SelectionCondition para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3b855-136">Elemento SelectionSetName para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="3b855-137">Elemento TypeName para WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="3b855-138">Elemento WideEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="3b855-139">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="3b855-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="3b855-140">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b855-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
