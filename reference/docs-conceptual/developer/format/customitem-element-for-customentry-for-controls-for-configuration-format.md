---
title: Elemento CustomItem para CustomEntry para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bb8124242496f192717127f201674bc1428e5de0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785856"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="11e83-102">Elemento CustomItem para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="11e83-103">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="11e83-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="11e83-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="11e83-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="11e83-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para o elemento de configuração (Format) CustomItem para CustomEntry para controles para a configuração</span><span class="sxs-lookup"><span data-stu-id="11e83-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="11e83-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="11e83-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="11e83-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="11e83-107">Attributes and Elements</span></span>

<span data-ttu-id="11e83-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="11e83-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="11e83-109">Para obter mais informações, consulte Comentários.</span><span class="sxs-lookup"><span data-stu-id="11e83-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="11e83-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="11e83-110">Attributes</span></span>

<span data-ttu-id="11e83-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="11e83-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="11e83-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="11e83-112">Child Elements</span></span>

|<span data-ttu-id="11e83-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="11e83-113">Element</span></span>|<span data-ttu-id="11e83-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="11e83-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="11e83-115">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="11e83-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="11e83-116">Optional element.</span></span><br /><br /> <span data-ttu-id="11e83-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="11e83-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="11e83-118">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="11e83-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="11e83-119">Optional element.</span></span><br /><br /> <span data-ttu-id="11e83-120">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="11e83-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="11e83-121">Elemento NewLine para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="11e83-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="11e83-122">Optional element.</span></span><br /><br /> <span data-ttu-id="11e83-123">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="11e83-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="11e83-124">Elemento Text para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="11e83-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="11e83-125">Optional element.</span></span><br /><br /> <span data-ttu-id="11e83-126">Adiciona texto, como parênteses ou colchetes, à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="11e83-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="11e83-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="11e83-127">Parent Elements</span></span>

|<span data-ttu-id="11e83-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="11e83-128">Element</span></span>|<span data-ttu-id="11e83-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="11e83-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="11e83-130">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="11e83-131">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="11e83-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="11e83-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="11e83-132">Remarks</span></span>

<span data-ttu-id="11e83-133">Ao especificar os elementos filho do `CustomItem` elemento, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="11e83-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="11e83-134">Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding` ,, `NewLine` `Text` e `Frame` .</span><span class="sxs-lookup"><span data-stu-id="11e83-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="11e83-135">Não há nenhum limite máximo para o número de sequências que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="11e83-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="11e83-136">Em cada sequência, não há nenhum limite máximo para o número de `ExpressionBinding` elementos que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="11e83-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="11e83-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11e83-137">See Also</span></span>

[<span data-ttu-id="11e83-138">Elemento ExpressionBinding para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="11e83-139">Elemento Frame para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="11e83-140">Elemento NewLine para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="11e83-141">Elemento Text para CustomItem para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="11e83-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="11e83-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="11e83-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
