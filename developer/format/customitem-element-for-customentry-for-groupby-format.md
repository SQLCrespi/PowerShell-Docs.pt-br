---
title: Elemento CustomItem para CustomEntry para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066378"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="91d36-102">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="91d36-103">Define quais dados são exibidos com o modo de exibição do controle personalizado e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="91d36-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="91d36-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="91d36-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="91d36-105">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento GroupBy elemento de configuração para o modo de exibição (formato) CustomControl elemento do elemento GroupBy (formato) CustomEntries para CustomControl para elemento de CustomItem GroupBy (formato) CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91d36-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91d36-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91d36-107">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="91d36-107">Attributes and Elements</span></span>

<span data-ttu-id="91d36-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomItem` elemento.</span><span class="sxs-lookup"><span data-stu-id="91d36-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91d36-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="91d36-109">Attributes</span></span>

<span data-ttu-id="91d36-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="91d36-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91d36-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="91d36-111">Child Elements</span></span>

|<span data-ttu-id="91d36-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="91d36-112">Element</span></span>|<span data-ttu-id="91d36-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="91d36-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91d36-114">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="91d36-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="91d36-115">Optional element.</span></span><br /><br /> <span data-ttu-id="91d36-116">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="91d36-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="91d36-117">Elemento de quadro para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="91d36-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="91d36-118">Optional element.</span></span><br /><br /> <span data-ttu-id="91d36-119">Define quais dados são exibidos com o modo de exibição do controle personalizado e como ele é exibido.</span><span class="sxs-lookup"><span data-stu-id="91d36-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="91d36-120">Elemento de nova linha para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="91d36-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="91d36-121">Optional element.</span></span><br /><br /> <span data-ttu-id="91d36-122">Adiciona uma linha em branco para a exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="91d36-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="91d36-123">Elemento de texto para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="91d36-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="91d36-124">Optional element.</span></span><br /><br /> <span data-ttu-id="91d36-125">Especifica o texto adicional para os dados exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="91d36-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="91d36-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="91d36-126">Parent Elements</span></span>

|<span data-ttu-id="91d36-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="91d36-127">Element</span></span>|<span data-ttu-id="91d36-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="91d36-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91d36-129">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="91d36-130">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="91d36-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="91d36-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="91d36-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="91d36-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91d36-132">See Also</span></span>

[<span data-ttu-id="91d36-133">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="91d36-134">Elemento ExpressionBinding para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="91d36-135">Elemento de quadro para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="91d36-136">Elemento de nova linha para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="91d36-137">Elemento de texto para CustomItem para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="91d36-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="91d36-138">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="91d36-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
