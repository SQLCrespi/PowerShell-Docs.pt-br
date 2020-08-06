---
title: Elemento WideEntries para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785040"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="849c8-102">Elemento WideEntries para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="849c8-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="849c8-103">Fornece as definições da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="849c8-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="849c8-104">A exibição ampla deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="849c8-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="849c8-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl Element (Format) WideEntries elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="849c8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="849c8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="849c8-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="849c8-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="849c8-107">Attributes and Elements</span></span>

<span data-ttu-id="849c8-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `WideEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="849c8-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="849c8-109">Pelo menos um elemento filho deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="849c8-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="849c8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="849c8-110">Attributes</span></span>

<span data-ttu-id="849c8-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="849c8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="849c8-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="849c8-112">Child Elements</span></span>

|<span data-ttu-id="849c8-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="849c8-113">Element</span></span>|<span data-ttu-id="849c8-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="849c8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="849c8-115">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="849c8-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="849c8-116">Fornece uma definição da exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="849c8-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="849c8-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="849c8-117">Parent Elements</span></span>

|<span data-ttu-id="849c8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="849c8-118">Element</span></span>|<span data-ttu-id="849c8-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="849c8-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="849c8-120">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="849c8-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="849c8-121">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="849c8-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="849c8-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="849c8-122">Remarks</span></span>

<span data-ttu-id="849c8-123">Uma exibição ampla é um formato de lista que exibe um valor de propriedade única ou de script para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="849c8-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="849c8-124">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [Wide View Components](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="849c8-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="849c8-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="849c8-125">Example</span></span>

<span data-ttu-id="849c8-126">O exemplo a seguir mostra um `WideEntries` elemento que define um único `WideEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="849c8-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="849c8-127">O `WideEntry` elemento contém um único `WideItem` elemento que define qual valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="849c8-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="849c8-128">Para obter um exemplo completo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="849c8-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="849c8-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="849c8-129">See Also</span></span>

[<span data-ttu-id="849c8-130">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="849c8-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="849c8-131">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="849c8-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="849c8-132">Elemento WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="849c8-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="849c8-133">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="849c8-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
