---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento ColumnNumber para WideControl (formato)
description: Elemento ColumnNumber para WideControl (formato)
ms.openlocfilehash: 1ddbbfbd5b53065afcc6c1326d6abf1fadedc67b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648394"
---
# <a name="columnnumber-element-for-widecontrol-format"></a><span data-ttu-id="353e4-103">Elemento ColumnNumber para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="353e4-103">ColumnNumber Element for WideControl (Format)</span></span>

<span data-ttu-id="353e4-104">Especifica o número de colunas exibidas na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="353e4-104">Specifies the number of columns displayed in the wide view.</span></span>

<span data-ttu-id="353e4-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento WideControl Element (Format) ColumnNumber elemento para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="353e4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) ColumnNumber Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="353e4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="353e4-106">Syntax</span></span>

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="353e4-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="353e4-107">Attributes and Elements</span></span>

<span data-ttu-id="353e4-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ColumnNumber` elemento.</span><span class="sxs-lookup"><span data-stu-id="353e4-108">The following sections describe attributes, child elements, and the parent element of the `ColumnNumber` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="353e4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="353e4-109">Attributes</span></span>

<span data-ttu-id="353e4-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="353e4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="353e4-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="353e4-111">Child Elements</span></span>

<span data-ttu-id="353e4-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="353e4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="353e4-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="353e4-113">Parent Elements</span></span>

|<span data-ttu-id="353e4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="353e4-114">Element</span></span>|<span data-ttu-id="353e4-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="353e4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="353e4-116">Elemento WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="353e4-116">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="353e4-117">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="353e4-117">Defines a wide (single value) list format for the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="353e4-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="353e4-118">Text Value</span></span>

<span data-ttu-id="353e4-119">Especifique um valor inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="353e4-119">Specify a positive integer value.</span></span>

## <a name="remarks"></a><span data-ttu-id="353e4-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="353e4-120">Remarks</span></span>

<span data-ttu-id="353e4-121">Ao definir uma exibição ampla, você pode adicionar o `AutoSize` elemento ou o `ColumnNumber` elemento, mas não pode adicionar ambos.</span><span class="sxs-lookup"><span data-stu-id="353e4-121">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` element, but you cannot add both.</span></span>

<span data-ttu-id="353e4-122">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="353e4-122">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="353e4-123">Para obter um exemplo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="353e4-123">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="353e4-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="353e4-124">See Also</span></span>

[<span data-ttu-id="353e4-125">Elemento AutoSize para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="353e4-125">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="353e4-126">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="353e4-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="353e4-127">Exibição ampla (Básica)</span><span class="sxs-lookup"><span data-stu-id="353e4-127">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="353e4-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="353e4-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
