---
title: Elemento CustomItem para CustomEntry para controles para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364025"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="e6efa-102">Elemento CustomItem para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="e6efa-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e6efa-103">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="e6efa-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="e6efa-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="e6efa-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e6efa-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração ( Format) elemento CustomEntry para CustomControl para controles para o elemento Configuration (Format) CustomItem para CustomEntry para controles para a configuração</span><span class="sxs-lookup"><span data-stu-id="e6efa-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="e6efa-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6efa-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e6efa-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e6efa-107">Attributes and Elements</span></span>

<span data-ttu-id="e6efa-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomItem`.</span><span class="sxs-lookup"><span data-stu-id="e6efa-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="e6efa-109">Para obter mais informações, consulte Remarks.</span><span class="sxs-lookup"><span data-stu-id="e6efa-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="e6efa-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e6efa-110">Attributes</span></span>

<span data-ttu-id="e6efa-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e6efa-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e6efa-112">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="e6efa-112">Child Elements</span></span>

|<span data-ttu-id="e6efa-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6efa-113">Element</span></span>|<span data-ttu-id="e6efa-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6efa-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e6efa-115">Elemento ExpressionBinding para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e6efa-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e6efa-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6efa-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e6efa-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="e6efa-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="e6efa-118">Elemento frame para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e6efa-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e6efa-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6efa-119">Optional element.</span></span><br /><br /> <span data-ttu-id="e6efa-120">Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita.</span><span class="sxs-lookup"><span data-stu-id="e6efa-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="e6efa-121">Elemento de nova linha para CustomItem para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="e6efa-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e6efa-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6efa-122">Optional element.</span></span><br /><br /> <span data-ttu-id="e6efa-123">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="e6efa-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="e6efa-124">Elemento Text para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e6efa-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="e6efa-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="e6efa-125">Optional element.</span></span><br /><br /> <span data-ttu-id="e6efa-126">Adiciona texto, como parênteses ou colchetes, à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="e6efa-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e6efa-127">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="e6efa-127">Parent Elements</span></span>

|<span data-ttu-id="e6efa-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6efa-128">Element</span></span>|<span data-ttu-id="e6efa-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6efa-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e6efa-130">Elemento CustomEntry para CustomControl para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e6efa-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="e6efa-131">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="e6efa-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e6efa-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6efa-132">Remarks</span></span>

<span data-ttu-id="e6efa-133">Ao especificar os elementos filho do elemento `CustomItem`, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6efa-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="e6efa-134">Os elementos filho devem ser adicionados na seguinte sequência: `ExpressionBinding`, `NewLine`, `Text`e `Frame`.</span><span class="sxs-lookup"><span data-stu-id="e6efa-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="e6efa-135">Não há nenhum limite máximo para o número de sequências que você pode especificar.</span><span class="sxs-lookup"><span data-stu-id="e6efa-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="e6efa-136">Em cada sequência, não há nenhum limite máximo para o número de elementos `ExpressionBinding` que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="e6efa-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6efa-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6efa-137">See Also</span></span>

[<span data-ttu-id="e6efa-138">Elemento ExpressionBinding para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e6efa-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e6efa-139">Elemento frame para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e6efa-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e6efa-140">Elemento de nova linha para CustomItem para controles para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="e6efa-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e6efa-141">Elemento Text para CustomItem para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="e6efa-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="e6efa-142">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6efa-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
