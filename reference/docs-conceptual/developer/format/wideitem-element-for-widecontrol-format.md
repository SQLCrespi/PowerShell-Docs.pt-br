---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento WideItem para WideControl (formato)
description: Elemento WideItem para WideControl (formato)
ms.openlocfilehash: b9c416bbe3befcd689b8a2c0b72a8ff1301b9659
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647808"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="bdfdf-103">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-103">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="bdfdf-104">Define a propriedade ou o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-104">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="bdfdf-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bdfdf-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bdfdf-106">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bdfdf-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="bdfdf-107">Attributes and Elements</span></span>

<span data-ttu-id="bdfdf-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-108">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="bdfdf-109">O elemento `FormatString` é opcional.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-109">The `FormatString` element is optional.</span></span> <span data-ttu-id="bdfdf-110">No entanto, você deve especificar um `PropertyName` `ScriptBlock` elemento ou, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-110">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="bdfdf-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdfdf-111">Attributes</span></span>

<span data-ttu-id="bdfdf-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bdfdf-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="bdfdf-113">Child Elements</span></span>

|<span data-ttu-id="bdfdf-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdfdf-114">Element</span></span>|<span data-ttu-id="bdfdf-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="bdfdf-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bdfdf-116">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-116">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="bdfdf-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-117">Optional element.</span></span><br /><br /> <span data-ttu-id="bdfdf-118">Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-118">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="bdfdf-119">Elemento PropertyName para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-119">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="bdfdf-120">Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-120">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="bdfdf-121">Elemento ScriptBlock para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-121">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="bdfdf-122">Especifica o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-122">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bdfdf-123">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="bdfdf-123">Parent Elements</span></span>

|<span data-ttu-id="bdfdf-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdfdf-124">Element</span></span>|<span data-ttu-id="bdfdf-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="bdfdf-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bdfdf-126">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="bdfdf-127">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bdfdf-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="bdfdf-128">Remarks</span></span>

<span data-ttu-id="bdfdf-129">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="bdfdf-129">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="bdfdf-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bdfdf-130">Example</span></span>

<span data-ttu-id="bdfdf-131">O exemplo a seguir mostra um `WideEntry` elemento que define um único `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="bdfdf-132">O `WideItem` elemento define a propriedade ou o script cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="bdfdf-132">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="bdfdf-133">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="bdfdf-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bdfdf-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bdfdf-134">See Also</span></span>

[<span data-ttu-id="bdfdf-135">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-135">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="bdfdf-136">Elemento PropertyName para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-136">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="bdfdf-137">Elemento ScriptBlock para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-137">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="bdfdf-138">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="bdfdf-138">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="bdfdf-139">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdfdf-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
