---
title: Elemento CustomItem para CustomEntry para GroupBy (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7c517aa-24f5-41ae-b82d-cb0fac81a245
caps.latest.revision: 7
ms.openlocfilehash: 2d821f5e3bc8d0f81ef8a8a040c6f9bcb1658bee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363875"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a><span data-ttu-id="4311e-102">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="4311e-102">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="4311e-103">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="4311e-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="4311e-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="4311e-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="4311e-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento de exibição (Format) CustomControl para o elemento CustomEntries GroupBy (Format) para CustomControl para o elemento GroupBy (Format) CustomItem para CustomEntry para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4311e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4311e-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4311e-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="4311e-107">Attributes and Elements</span></span>

<span data-ttu-id="4311e-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomItem`.</span><span class="sxs-lookup"><span data-stu-id="4311e-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4311e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4311e-109">Attributes</span></span>

<span data-ttu-id="4311e-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4311e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4311e-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="4311e-111">Child Elements</span></span>

|<span data-ttu-id="4311e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4311e-112">Element</span></span>|<span data-ttu-id="4311e-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="4311e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4311e-114">Elemento ExpressionBinding para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-114">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="4311e-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4311e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4311e-116">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="4311e-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="4311e-117">Elemento frame para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-117">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="4311e-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4311e-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4311e-119">Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="4311e-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="4311e-120">Elemento de nova linha para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-120">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="4311e-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4311e-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4311e-122">Adiciona uma linha em branco à exibição do controle.</span><span class="sxs-lookup"><span data-stu-id="4311e-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="4311e-123">Elemento Text para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-123">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="4311e-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="4311e-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4311e-125">Especifica texto adicional para os dados exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="4311e-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4311e-126">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="4311e-126">Parent Elements</span></span>

|<span data-ttu-id="4311e-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="4311e-127">Element</span></span>|<span data-ttu-id="4311e-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="4311e-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4311e-129">Elemento CustomEntry para CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="4311e-130">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="4311e-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4311e-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="4311e-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="4311e-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4311e-132">See Also</span></span>

[<span data-ttu-id="4311e-133">Elemento CustomEntry para CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-133">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="4311e-134">Elemento ExpressionBinding para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-134">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="4311e-135">Elemento frame para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-135">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="4311e-136">Elemento de nova linha para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-136">NewLine Element for CustomItem for GroupBy (Format)</span></span>](./newline-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="4311e-137">Elemento Text para CustomItem para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4311e-137">Text Element for CustomItem for GroupBy (Format)</span></span>](./text-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="4311e-138">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4311e-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
