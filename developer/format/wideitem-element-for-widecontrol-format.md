---
title: Elemento WideItem para WideControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17352fc4-ba83-4f04-86bc-f591765d85a8
caps.latest.revision: 18
ms.openlocfilehash: fa9eda3ea1028c27dbfb3eb04747af3b817c1a81
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083630"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="3d8cf-102">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="3d8cf-103">Define a propriedade ou o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="3d8cf-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento WideControl (formato) elemento WideEntries (formato) elemento WideEntry (formato) WideItem elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3d8cf-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3d8cf-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3d8cf-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="3d8cf-106">Attributes and Elements</span></span>

<span data-ttu-id="3d8cf-107">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="3d8cf-108">O `FormatString` elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="3d8cf-109">No entanto, você deve especificar uma `PropertyName` ou `ScriptBlock` elemento, mas você não é possível especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="3d8cf-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d8cf-110">Attributes</span></span>

<span data-ttu-id="3d8cf-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3d8cf-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="3d8cf-112">Child Elements</span></span>

|<span data-ttu-id="3d8cf-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d8cf-113">Element</span></span>|<span data-ttu-id="3d8cf-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d8cf-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3d8cf-115">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="3d8cf-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-116">Optional element.</span></span><br /><br /> <span data-ttu-id="3d8cf-117">Especifica um padrão de formato que define como o valor da propriedade ou o script é exibido no modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="3d8cf-118">Elemento PropertyName para WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="3d8cf-119">Especifica a propriedade do objeto cujo valor é exibido no modo de exibição amplo.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="3d8cf-120">Elemento ScriptBlock para WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="3d8cf-121">Especifica o script cujo valor é exibido no modo de exibição amplo.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3d8cf-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="3d8cf-122">Parent Elements</span></span>

|<span data-ttu-id="3d8cf-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d8cf-123">Element</span></span>|<span data-ttu-id="3d8cf-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d8cf-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3d8cf-125">Elemento WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="3d8cf-126">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3d8cf-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="3d8cf-127">Remarks</span></span>

<span data-ttu-id="3d8cf-128">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="3d8cf-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3d8cf-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3d8cf-129">Example</span></span>

<span data-ttu-id="3d8cf-130">A exemplo a seguir mostra uma `WideEntry` que define um único elemento `WideItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="3d8cf-131">O `WideItem` elemento define a propriedade ou cujo valor é exibido no modo de exibição de script.</span><span class="sxs-lookup"><span data-stu-id="3d8cf-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="3d8cf-132">Para obter um exemplo completo de uma exibição ampla, consulte [exibição ampla (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="3d8cf-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3d8cf-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d8cf-133">See Also</span></span>

[<span data-ttu-id="3d8cf-134">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="3d8cf-135">Elemento PropertyName para WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="3d8cf-136">Elemento ScriptBlock para WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="3d8cf-137">Elemento WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="3d8cf-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="3d8cf-138">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d8cf-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
