---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ScriptBlock para WideItem para WideControl (formato)
description: Elemento ScriptBlock para WideItem para WideControl (formato)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659878"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="5dd75-103">Elemento ScriptBlock para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="5dd75-103">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="5dd75-104">Especifica o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="5dd75-104">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="5dd75-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format) @ Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="5dd75-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5dd75-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5dd75-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5dd75-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5dd75-107">Attributes and Elements</span></span>

<span data-ttu-id="5dd75-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="5dd75-108">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5dd75-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5dd75-109">Attributes</span></span>

<span data-ttu-id="5dd75-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="5dd75-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5dd75-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5dd75-111">Child Elements</span></span>

<span data-ttu-id="5dd75-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="5dd75-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5dd75-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5dd75-113">Parent Elements</span></span>

|<span data-ttu-id="5dd75-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="5dd75-114">Element</span></span>|<span data-ttu-id="5dd75-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5dd75-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5dd75-116">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="5dd75-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="5dd75-117">Define a propriedade ou bloco de script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="5dd75-117">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="5dd75-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="5dd75-118">Text Value</span></span>

<span data-ttu-id="5dd75-119">Especifique o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="5dd75-119">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5dd75-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="5dd75-120">Remarks</span></span>

<span data-ttu-id="5dd75-121">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="5dd75-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5dd75-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5dd75-122">Example</span></span>

<span data-ttu-id="5dd75-123">Este exemplo mostra um `WideItem` elemento que define um script cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="5dd75-123">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="5dd75-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5dd75-124">See Also</span></span>

[<span data-ttu-id="5dd75-125">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="5dd75-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="5dd75-126">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="5dd75-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5dd75-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dd75-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
