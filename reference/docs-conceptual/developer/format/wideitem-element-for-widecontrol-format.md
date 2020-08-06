---
title: Elemento WideItem para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779889"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="c4456-102">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c4456-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="c4456-103">Define a propriedade ou o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="c4456-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="c4456-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c4456-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c4456-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c4456-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c4456-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="c4456-106">Attributes and Elements</span></span>

<span data-ttu-id="c4456-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="c4456-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="c4456-108">O elemento `FormatString` é opcional.</span><span class="sxs-lookup"><span data-stu-id="c4456-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="c4456-109">No entanto, você deve especificar um `PropertyName` `ScriptBlock` elemento ou, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="c4456-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="c4456-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4456-110">Attributes</span></span>

<span data-ttu-id="c4456-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c4456-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c4456-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="c4456-112">Child Elements</span></span>

|<span data-ttu-id="c4456-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4456-113">Element</span></span>|<span data-ttu-id="c4456-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="c4456-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4456-115">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c4456-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="c4456-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="c4456-116">Optional element.</span></span><br /><br /> <span data-ttu-id="c4456-117">Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="c4456-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="c4456-118">Elemento PropertyName para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c4456-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="c4456-119">Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="c4456-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="c4456-120">Elemento ScriptBlock para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c4456-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="c4456-121">Especifica o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="c4456-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c4456-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="c4456-122">Parent Elements</span></span>

|<span data-ttu-id="c4456-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4456-123">Element</span></span>|<span data-ttu-id="c4456-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="c4456-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4456-125">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="c4456-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="c4456-126">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="c4456-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c4456-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="c4456-127">Remarks</span></span>

<span data-ttu-id="c4456-128">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="c4456-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c4456-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c4456-129">Example</span></span>

<span data-ttu-id="c4456-130">O exemplo a seguir mostra um `WideEntry` elemento que define um único `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="c4456-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="c4456-131">O `WideItem` elemento define a propriedade ou o script cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="c4456-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="c4456-132">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="c4456-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4456-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c4456-133">See Also</span></span>

[<span data-ttu-id="c4456-134">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="c4456-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="c4456-135">Elemento PropertyName para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c4456-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="c4456-136">Elemento ScriptBlock para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c4456-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="c4456-137">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="c4456-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="c4456-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4456-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
