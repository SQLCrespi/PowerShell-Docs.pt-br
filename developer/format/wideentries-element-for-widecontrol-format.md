---
title: Elemento WideEntries para WideControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083681"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="e65f2-102">Elemento WideEntries para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e65f2-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="e65f2-103">Fornece as definições do modo de exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="e65f2-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="e65f2-104">O modo de exibição amplo deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="e65f2-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="e65f2-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento WideControl (formato) WideEntries elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="e65f2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e65f2-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e65f2-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e65f2-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="e65f2-107">Attributes and Elements</span></span>

<span data-ttu-id="e65f2-108">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `WideEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="e65f2-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="e65f2-109">Pelo menos um elemento filho deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="e65f2-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="e65f2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e65f2-110">Attributes</span></span>

<span data-ttu-id="e65f2-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e65f2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e65f2-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e65f2-112">Child Elements</span></span>

|<span data-ttu-id="e65f2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e65f2-113">Element</span></span>|<span data-ttu-id="e65f2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e65f2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e65f2-115">Elemento WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e65f2-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="e65f2-116">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="e65f2-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e65f2-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e65f2-117">Parent Elements</span></span>

|<span data-ttu-id="e65f2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e65f2-118">Element</span></span>|<span data-ttu-id="e65f2-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="e65f2-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e65f2-120">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e65f2-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="e65f2-121">Define uma ampla (único valor) formato de lista para o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e65f2-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e65f2-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="e65f2-122">Remarks</span></span>

<span data-ttu-id="e65f2-123">Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="e65f2-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="e65f2-124">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [componentes de exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="e65f2-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e65f2-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e65f2-125">Example</span></span>

<span data-ttu-id="e65f2-126">A exemplo a seguir mostra uma `WideEntries` que define um único elemento `WideEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="e65f2-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="e65f2-127">O `WideEntry` elemento contém um único `WideItem` elemento que define qual valor de propriedade ou o script é exibido no modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="e65f2-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="e65f2-128">Para obter um exemplo completo de uma exibição ampla, consulte [exibição ampla (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="e65f2-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e65f2-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e65f2-129">See Also</span></span>

[<span data-ttu-id="e65f2-130">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="e65f2-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e65f2-131">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="e65f2-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="e65f2-132">Elemento WideEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="e65f2-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="e65f2-133">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e65f2-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
