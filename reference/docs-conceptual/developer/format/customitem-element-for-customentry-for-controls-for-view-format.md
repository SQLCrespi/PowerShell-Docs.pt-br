---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomItem para CustomEntry para Controls para View (formato)
description: Elemento CustomItem para CustomEntry para Controls para View (formato)
ms.openlocfilehash: 67bff97c27cfedf046b17eea438efcd66ae2ee4a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666749"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="14e0b-103">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-103">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="14e0b-104">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="14e0b-104">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="14e0b-105">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="14e0b-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="14e0b-106">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para os controles do elemento View (Format) CustomItem para CustomEntry para os controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="14e0b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="14e0b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="14e0b-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="14e0b-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="14e0b-108">Attributes and Elements</span></span>

<span data-ttu-id="14e0b-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="14e0b-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="14e0b-110">Para obter mais informações, consulte Comentários.</span><span class="sxs-lookup"><span data-stu-id="14e0b-110">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="14e0b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="14e0b-111">Attributes</span></span>

<span data-ttu-id="14e0b-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="14e0b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="14e0b-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="14e0b-113">Child Elements</span></span>

|<span data-ttu-id="14e0b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="14e0b-114">Element</span></span>|<span data-ttu-id="14e0b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="14e0b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="14e0b-116">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="14e0b-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="14e0b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="14e0b-118">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="14e0b-118">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="14e0b-119">Elemento Frame para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-119">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="14e0b-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="14e0b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="14e0b-121">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="14e0b-121">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="14e0b-122">Elemento NewLine para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-122">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="14e0b-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="14e0b-123">Optional element.</span></span><br /><br /> <span data-ttu-id="14e0b-124">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="14e0b-124">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="14e0b-125">Elemento Text para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-125">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="14e0b-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="14e0b-126">Optional element.</span></span><br /><br /> <span data-ttu-id="14e0b-127">Adiciona texto, como parênteses ou colchetes, à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="14e0b-127">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="14e0b-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="14e0b-128">Parent Elements</span></span>

|<span data-ttu-id="14e0b-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="14e0b-129">Element</span></span>|<span data-ttu-id="14e0b-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="14e0b-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="14e0b-131">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-131">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="14e0b-132">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="14e0b-132">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="14e0b-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="14e0b-133">Remarks</span></span>

<span data-ttu-id="14e0b-134">Ao especificar os elementos filho do `CustomItem` elemento, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="14e0b-134">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="14e0b-135">Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding` ,, `NewLine` `Text` e `Frame` .</span><span class="sxs-lookup"><span data-stu-id="14e0b-135">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="14e0b-136">Não há nenhum limite máximo para o número de sequências que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="14e0b-136">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="14e0b-137">Em cada sequência, não há nenhum limite máximo para o número de `ExpressionBinding` elementos que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="14e0b-137">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="14e0b-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="14e0b-138">See Also</span></span>

[<span data-ttu-id="14e0b-139">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-139">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="14e0b-140">Elemento Frame para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-140">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="14e0b-141">Elemento NewLine para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-141">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="14e0b-142">Elemento Text para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="14e0b-142">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="14e0b-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="14e0b-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
