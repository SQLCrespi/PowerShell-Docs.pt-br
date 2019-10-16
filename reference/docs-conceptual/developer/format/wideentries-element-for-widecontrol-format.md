---
title: Elemento WideEntries para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361425"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="78e76-102">Elemento WideEntries para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="78e76-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="78e76-103">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="78e76-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="78e76-104">A exibição ampla deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="78e76-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="78e76-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl Element (Format) WideEntries elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="78e76-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="78e76-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="78e76-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="78e76-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="78e76-107">Attributes and Elements</span></span>

<span data-ttu-id="78e76-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `WideEntries`.</span><span class="sxs-lookup"><span data-stu-id="78e76-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="78e76-109">Pelo menos um elemento filho deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="78e76-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="78e76-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="78e76-110">Attributes</span></span>

<span data-ttu-id="78e76-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="78e76-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78e76-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="78e76-112">Child Elements</span></span>

|<span data-ttu-id="78e76-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="78e76-113">Element</span></span>|<span data-ttu-id="78e76-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="78e76-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78e76-115">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="78e76-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="78e76-116">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="78e76-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="78e76-117">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="78e76-117">Parent Elements</span></span>

|<span data-ttu-id="78e76-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="78e76-118">Element</span></span>|<span data-ttu-id="78e76-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="78e76-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78e76-120">Elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78e76-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="78e76-121">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="78e76-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78e76-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="78e76-122">Remarks</span></span>

<span data-ttu-id="78e76-123">Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="78e76-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="78e76-124">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="78e76-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="78e76-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="78e76-125">Example</span></span>

<span data-ttu-id="78e76-126">O exemplo a seguir mostra um elemento `WideEntries` que define um único elemento `WideEntry`.</span><span class="sxs-lookup"><span data-stu-id="78e76-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="78e76-127">O elemento `WideEntry` contém um único elemento `WideItem` que define qual valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="78e76-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="78e76-128">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="78e76-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78e76-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="78e76-129">See Also</span></span>

[<span data-ttu-id="78e76-130">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="78e76-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="78e76-131">Elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="78e76-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="78e76-132">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="78e76-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="78e76-133">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="78e76-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
