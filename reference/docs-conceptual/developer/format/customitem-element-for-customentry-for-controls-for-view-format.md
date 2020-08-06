---
title: Elemento CustomItem para CustomEntry para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 747ea14e7118be62ebee00e7d80af2dccb5c8353
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785839"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="b71c7-102">Elemento CustomItem para CustomEntry para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="b71c7-103">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="b71c7-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="b71c7-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="b71c7-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="b71c7-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para os controles do elemento View (Format) CustomItem para CustomEntry para os controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="b71c7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b71c7-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b71c7-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b71c7-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b71c7-107">Attributes and Elements</span></span>

<span data-ttu-id="b71c7-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="b71c7-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="b71c7-109">Para obter mais informações, consulte Comentários.</span><span class="sxs-lookup"><span data-stu-id="b71c7-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="b71c7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b71c7-110">Attributes</span></span>

<span data-ttu-id="b71c7-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b71c7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b71c7-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b71c7-112">Child Elements</span></span>

|<span data-ttu-id="b71c7-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="b71c7-113">Element</span></span>|<span data-ttu-id="b71c7-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="b71c7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b71c7-115">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="b71c7-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b71c7-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b71c7-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="b71c7-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="b71c7-118">Elemento Frame para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="b71c7-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b71c7-119">Optional element.</span></span><br /><br /> <span data-ttu-id="b71c7-120">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="b71c7-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="b71c7-121">Elemento NewLine para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="b71c7-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b71c7-122">Optional element.</span></span><br /><br /> <span data-ttu-id="b71c7-123">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="b71c7-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="b71c7-124">Elemento Text para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="b71c7-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="b71c7-125">Optional element.</span></span><br /><br /> <span data-ttu-id="b71c7-126">Adiciona texto, como parênteses ou colchetes, à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="b71c7-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b71c7-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b71c7-127">Parent Elements</span></span>

|<span data-ttu-id="b71c7-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="b71c7-128">Element</span></span>|<span data-ttu-id="b71c7-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="b71c7-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b71c7-130">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="b71c7-131">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="b71c7-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b71c7-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="b71c7-132">Remarks</span></span>

<span data-ttu-id="b71c7-133">Ao especificar os elementos filho do `CustomItem` elemento, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b71c7-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="b71c7-134">Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding` ,, `NewLine` `Text` e `Frame` .</span><span class="sxs-lookup"><span data-stu-id="b71c7-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="b71c7-135">Não há nenhum limite máximo para o número de sequências que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="b71c7-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="b71c7-136">Em cada sequência, não há nenhum limite máximo para o número de `ExpressionBinding` elementos que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="b71c7-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="b71c7-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b71c7-137">See Also</span></span>

[<span data-ttu-id="b71c7-138">Elemento ExpressionBinding para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="b71c7-139">Elemento Frame para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="b71c7-140">Elemento NewLine para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="b71c7-141">Elemento Text para CustomItem para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="b71c7-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="b71c7-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b71c7-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
