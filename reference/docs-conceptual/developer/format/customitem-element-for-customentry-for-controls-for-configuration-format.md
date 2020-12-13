---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomItem para CustomEntry para Controls para Configuration (formato)
description: Elemento CustomItem para CustomEntry para Controls para Configuration (formato)
ms.openlocfilehash: 06c399e982b6ac0fba9c11e20c468fe8bef6f694
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666766"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="33726-103">Elemento CustomItem para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-103">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="33726-104">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="33726-104">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="33726-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="33726-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="33726-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para a configuração</span><span class="sxs-lookup"><span data-stu-id="33726-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="33726-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="33726-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="33726-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="33726-108">Attributes and Elements</span></span>

<span data-ttu-id="33726-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="33726-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="33726-110">Para obter mais informações, consulte Comentários.</span><span class="sxs-lookup"><span data-stu-id="33726-110">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="33726-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="33726-111">Attributes</span></span>

<span data-ttu-id="33726-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="33726-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="33726-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="33726-113">Child Elements</span></span>

|<span data-ttu-id="33726-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="33726-114">Element</span></span>|<span data-ttu-id="33726-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="33726-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33726-116">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="33726-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="33726-117">Optional element.</span></span><br /><br /> <span data-ttu-id="33726-118">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="33726-118">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="33726-119">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-119">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="33726-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="33726-120">Optional element.</span></span><br /><br /> <span data-ttu-id="33726-121">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="33726-121">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="33726-122">Elemento NewLine para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-122">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="33726-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="33726-123">Optional element.</span></span><br /><br /> <span data-ttu-id="33726-124">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="33726-124">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="33726-125">Elemento Text para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-125">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="33726-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="33726-126">Optional element.</span></span><br /><br /> <span data-ttu-id="33726-127">Adiciona texto, como parênteses ou colchetes, à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="33726-127">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="33726-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="33726-128">Parent Elements</span></span>

|<span data-ttu-id="33726-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="33726-129">Element</span></span>|<span data-ttu-id="33726-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="33726-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33726-131">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-131">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="33726-132">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="33726-132">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33726-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="33726-133">Remarks</span></span>

<span data-ttu-id="33726-134">Ao especificar os elementos filho do `CustomItem` elemento, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="33726-134">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="33726-135">Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding` ,, `NewLine` `Text` e `Frame` .</span><span class="sxs-lookup"><span data-stu-id="33726-135">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="33726-136">Não há nenhum limite máximo para o número de sequências que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="33726-136">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="33726-137">Em cada sequência, não há nenhum limite máximo para o número de `ExpressionBinding` elementos que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="33726-137">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="33726-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33726-138">See Also</span></span>

[<span data-ttu-id="33726-139">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-139">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="33726-140">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-140">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="33726-141">Elemento NewLine para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-141">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="33726-142">Elemento Text para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="33726-142">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="33726-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="33726-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
