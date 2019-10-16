---
title: Elemento ScriptBlock para WideItem para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362025"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="9e0e5-102">Elemento ScriptBlock para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9e0e5-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="9e0e5-103">Especifica o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="9e0e5-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="9e0e5-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format) @ Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="9e0e5-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9e0e5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9e0e5-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e0e5-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9e0e5-106">Attributes and Elements</span></span>

<span data-ttu-id="9e0e5-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="9e0e5-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e0e5-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9e0e5-108">Attributes</span></span>

<span data-ttu-id="9e0e5-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9e0e5-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9e0e5-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="9e0e5-110">Child Elements</span></span>

<span data-ttu-id="9e0e5-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9e0e5-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9e0e5-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="9e0e5-112">Parent Elements</span></span>

|<span data-ttu-id="9e0e5-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e0e5-113">Element</span></span>|<span data-ttu-id="9e0e5-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e0e5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e0e5-115">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="9e0e5-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="9e0e5-116">Define a propriedade ou bloco de script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="9e0e5-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9e0e5-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9e0e5-117">Text Value</span></span>

<span data-ttu-id="9e0e5-118">Especifique o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="9e0e5-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e0e5-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="9e0e5-119">Remarks</span></span>

<span data-ttu-id="9e0e5-120">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9e0e5-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9e0e5-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9e0e5-121">Example</span></span>

<span data-ttu-id="9e0e5-122">Este exemplo mostra um elemento `WideItem` que define um script cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="9e0e5-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="9e0e5-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9e0e5-123">See Also</span></span>

[<span data-ttu-id="9e0e5-124">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="9e0e5-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="9e0e5-125">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="9e0e5-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9e0e5-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e0e5-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
