---
title: Elemento WideItem para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361395"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="a8148-102">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="a8148-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="a8148-103">Define a propriedade ou o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="a8148-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="a8148-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) elemento WideControl (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a8148-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a8148-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a8148-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="a8148-106">Attributes and Elements</span></span>

<span data-ttu-id="a8148-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="a8148-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="a8148-108">O elemento `FormatString` é opcional.</span><span class="sxs-lookup"><span data-stu-id="a8148-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="a8148-109">No entanto, você deve especificar um elemento `PropertyName` ou `ScriptBlock`, mas não pode especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="a8148-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="a8148-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8148-110">Attributes</span></span>

<span data-ttu-id="a8148-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a8148-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a8148-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="a8148-112">Child Elements</span></span>

|<span data-ttu-id="a8148-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8148-113">Element</span></span>|<span data-ttu-id="a8148-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="a8148-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8148-115">Elemento FormatString para WideItem para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="a8148-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="a8148-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a8148-117">Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="a8148-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="a8148-118">Elemento PropertyName para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="a8148-119">Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="a8148-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="a8148-120">Elemento ScriptBlock para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="a8148-121">Especifica o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="a8148-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a8148-122">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="a8148-122">Parent Elements</span></span>

|<span data-ttu-id="a8148-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8148-123">Element</span></span>|<span data-ttu-id="a8148-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="a8148-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8148-125">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="a8148-126">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="a8148-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a8148-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="a8148-127">Remarks</span></span>

<span data-ttu-id="a8148-128">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="a8148-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a8148-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a8148-129">Example</span></span>

<span data-ttu-id="a8148-130">O exemplo a seguir mostra um elemento `WideEntry` que define um único elemento `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="a8148-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="a8148-131">O elemento `WideItem` define a propriedade ou o script cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="a8148-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="a8148-132">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="a8148-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8148-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a8148-133">See Also</span></span>

[<span data-ttu-id="a8148-134">Elemento FormatString para WideItem para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="a8148-135">Elemento PropertyName para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="a8148-136">Elemento ScriptBlock para WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="a8148-137">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a8148-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="a8148-138">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8148-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
