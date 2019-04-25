---
title: Elemento CustomItem para CustomEntry controles para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066372"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="83ccc-102">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="83ccc-103">Define quais dados são exibidos pelo controle e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="83ccc-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="83ccc-104">Esse elemento é usado durante a definição de controles que podem ser usados por um modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="83ccc-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="83ccc-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento controles elemento (formato) controle elemento de configuração para controles para exibição (formato) CustomControl elemento de controle para controles para elemento CustomEntries de exibição (formato) CustomControl para elemento de exibição (formato) CustomEntry CustomEntries para controles para elemento de exibição (formato) CustomItem CustomEntry controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="83ccc-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="83ccc-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="83ccc-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="83ccc-107">Attributes and Elements</span></span>

<span data-ttu-id="83ccc-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="83ccc-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="83ccc-109">Para obter mais informações, consulte comentários.</span><span class="sxs-lookup"><span data-stu-id="83ccc-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="83ccc-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="83ccc-110">Attributes</span></span>

<span data-ttu-id="83ccc-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="83ccc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="83ccc-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="83ccc-112">Child Elements</span></span>

|<span data-ttu-id="83ccc-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="83ccc-113">Element</span></span>|<span data-ttu-id="83ccc-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="83ccc-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83ccc-115">Elemento ExpressionBinding para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="83ccc-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="83ccc-116">Optional element.</span></span><br /><br /> <span data-ttu-id="83ccc-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="83ccc-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="83ccc-118">Elemento de quadro para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="83ccc-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="83ccc-119">Optional element.</span></span><br /><br /> <span data-ttu-id="83ccc-120">Define como os dados são exibidos, como o deslocamento de dados para a esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="83ccc-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="83ccc-121">Elemento de nova linha para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="83ccc-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="83ccc-122">Optional element.</span></span><br /><br /> <span data-ttu-id="83ccc-123">Adiciona uma linha em branco para a exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="83ccc-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="83ccc-124">Elemento de texto para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="83ccc-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="83ccc-125">Optional element.</span></span><br /><br /> <span data-ttu-id="83ccc-126">Adiciona texto, como parênteses ou colchetes, para a exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="83ccc-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="83ccc-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="83ccc-127">Parent Elements</span></span>

|<span data-ttu-id="83ccc-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="83ccc-128">Element</span></span>|<span data-ttu-id="83ccc-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="83ccc-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83ccc-130">Elemento CustomEntry para CustomEntries controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="83ccc-131">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="83ccc-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83ccc-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="83ccc-132">Remarks</span></span>

<span data-ttu-id="83ccc-133">Ao especificar os elementos filho do `CustomItem` elemento, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83ccc-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="83ccc-134">Os elementos filho devem ser adicionados na sequência a seguir: `ExpressionBinding`, `NewLine`, `Text`, e `Frame`.</span><span class="sxs-lookup"><span data-stu-id="83ccc-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="83ccc-135">Não há nenhum limite máximo ao número de sequências que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="83ccc-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="83ccc-136">Em cada sequência, não há nenhum limite máximo ao número de `ExpressionBinding` elementos que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="83ccc-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="83ccc-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83ccc-137">See Also</span></span>

[<span data-ttu-id="83ccc-138">Elemento ExpressionBinding para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="83ccc-139">Elemento de quadro para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="83ccc-140">Elemento de nova linha para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="83ccc-141">Elemento de texto para CustomItem controles para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="83ccc-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="83ccc-142">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="83ccc-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
